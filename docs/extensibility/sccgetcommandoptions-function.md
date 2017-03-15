---
title: "SccGetCommandOptions 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccGetCommandOptions"
helpviewer_keywords: 
  - "SccGetCommandOptions 함수"
ms.assetid: bbe4aa4e-b4b0-403e-b7a0-5dd6eb24e5a9
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# SccGetCommandOptions 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 지정된 된 명령에 대 한 고급 옵션에 대 한 사용자를 묻습니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccGetCommandOptions(  
   LPVOID pvContext,  
   HWND hWnd,  
   enum SCCCOMMAND iCommand,  
   LPCMDOPTS* ppvOptions  
);  
```  
  
#### 매개 변수  
 pvContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 \[in\] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 iCommand  
 \[in\] 고급 옵션은 요청 된 명령 \(참조 [명령 코드](../extensibility/command-code-enumerator.md) 가능한 값에 대 한\).  
  
 ppvOptions  
 \[in\] 옵션 구조 \(또한 수 `NULL`\).  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|명령 실행 성공|  
|SCC\_I\_ADV\_SUPPORT|소스 제어 플러그 인은 명령에 대 한 고급 옵션을 지원합니다.|  
|SCC\_I\_OPERATIONCANCELED|사용자는 소스 제어 플러그 인에서 취소 **옵션** 대화 상자입니다.|  
|SCC\_E\_OPTNOTSUPPORTED|소스 제어 플러그 인이 작업을 지원 하지 않습니다.|  
|SCC\_E\_ISCHECKEDOUT|현재 체크 아웃 하는 파일에 대 한이 작업을 수행할 수 없습니다.|  
|SCC\_E\_ACCESSFAILURE|소스 제어 시스템에 경합 또는 네트워크 문제 때문에 액세스할 수 없습니다. 다시 시도 사용 하는 것이 좋습니다.|  
|SCC\_E\_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다.|  
  
## 설명  
 IDE를 처음으로이 함수를 호출 `ppvOptions`\=`NULL` 를 소스 제어 플러그 인 지정된 된 명령에 대 한 고급 옵션 기능을 지원 하는지 확인 합니다. 플러그 인에서 기능을 지원 해당 명령에 대 한, IDE이 함수 호출 하며이 다시 사용자는 고급 옵션을 요청 하면 \(일반적으로 구현 된 **고급** 대화 상자에서 단추\)에 대 한 NULL이 아닌 포인터를 제공 합니다. `ppvOptions` 를 가리키는 `NULL` 포인터. 플러그 인 개인 구조에서 사용자가 지정한 모든 고급 옵션을 저장 하 고 해당 구조에 대 한 포인터를 반환 `ppvOptions`합니다. 이 구조에 대해 알아야 할 후속 호출을 포함 한 다른 모든 소스 제어 플러그 인 API 함수에 전달 됩니다는 `SccGetCommandOptions` 함수입니다.  
  
 예제는이 상황을 명확 하 게 하는 데 도움이 됩니다.  
  
 사용자가 선택는 **가져오기** 명령과 IDE를 표시 한 **가져오기** 대화 상자입니다. 호출 하 여 IDE는 `SccGetCommandOptions` 작동 `iCommand` 로 설정 `SCC_COMMAND_GET` 및 `ppvOptions` 로 설정 `NULL`합니다. 이것은 소스 제어의 질문으로 플러그 인, "있습니까이 명령에 대 한 고급 옵션?" 플러그 인을 반환 하는 경우 `SCC_I_ADV_SUPPORT`, IDE를 표시 한 **고급** 단추 해당 **가져오기** 대화 상자.  
  
 사용자가 처음으로 **고급** 단추, IDE를 다시 호출는 `SccGetCommandOptions` 함수,이 이번에는 비\-`NULL` `ppvOptions` 를 가리키는 `NULL` 포인터입니다.  플러그 인 표시 자체 **가져오기 옵션** 대화 상자 자체 구조에 해당 정보를 업데이트 하 고 해당 구조에 대 한 포인터를 반환 합니다. 사용자에 게 정보를 묻는 `ppvOptions`합니다.  
  
 클릭 하면 **고급** 다시 동일한 대화 상자에서 IDE 호출는 `SccGetCommandOptions` 함수를 변경 하지 않고 다시 `ppvOptions`, 구조는 플러그 인으로 다시 전달 되도록 합니다. 이렇게 하면 플러그 인이 사용자가 이전에 설정 된 값에 해당 대화 상자를 다시 초기화 하십시오. 플러그 인을 반환 하기 전에 위치에 구조를 수정합니다.  
  
 마지막으로, 사용자가 **확인** 는 IDE에서 **가져오기** 대화 상자, IDE 호출의 [SccGet](../extensibility/sccget-function.md), 에서 반환 되는 구조체를 전달 `ppvOptions` 고급 옵션을 포함 하는 합니다.  
  
> [!NOTE]
>  명령 `SCC_COMMAND_OPTIONS` IDE를 표시 하는 경우 사용 되는 **옵션** 사용자 수 있는 대화 상자는 통합의 작동 방법을 제어 하는 환경을 설정 합니다. 표시할 수는 소스 제어 플러그를 자체 기본 설정 대화 상자를 제공 하려는 경우는 **고급** IDE의 기본 설정 대화 상자에서 단추입니다. 플러그 인은 전적으로 부담을 가져오고이 정보를 유지 합니다. IDE를 사용 하지 않거나 수정 합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [명령 코드](../extensibility/command-code-enumerator.md)