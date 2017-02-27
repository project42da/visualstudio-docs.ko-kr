---
title: "SccPopulateList 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccPopulateList"
helpviewer_keywords: 
  - "SccPopulateList 함수"
ms.assetid: 7416e781-c571-4a7f-8af3-a089ce8be662
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# SccPopulateList 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 특정 소스 제어 명령에 대 한 파일의 목록을 업데이트 하 고 모든 지정 된 파일에 대해 소스 제어 상태를 제공 합니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccPopulateList (  
   LPVOID          pvContext,  
   enum SCCCOMMAND nCommand,  
   LONG            nFiles,  
   LPCSTR*         lpFileNames,  
   POPLISTFUNC     pfnPopulate,  
   LPVOID          pvCallerData,  
   LPLONG          lpStatus,  
   LONG            fOptions  
);  
```  
  
#### 매개 변수  
 pvContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 된 명령  
 \[in\] 모든 파일에 적용 될 소스 제어 명령을 `lpFileNames` 배열 \(참조 [명령 코드](../extensibility/command-code-enumerator.md) 가능한 명령 목록을 대 한\).  
  
 nFiles  
 \[in\] 에 있는 파일 수는 `lpFileNames` 배열입니다.  
  
 lpFileNames  
 \[in\] 파일 이름에는 IDE의 배열입니다.  
  
 pfnPopulate  
 \[in\] 파일 추가 및 제거 하기 위해 호출 하는 IDE 콜백 함수 \(참조 [POPLISTFUNC](../extensibility/poplistfunc.md) 대 한 자세한 내용은\).  
  
 pvCallerData  
 \[in\] 값 변경 되지 않은 콜백 함수에 전달 하는 것입니다.  
  
 lpStatus  
 \[에서, out\] 소스 제어의 각 파일에 대 한 상태 플래그를 반환 하는 플러그 인에 대 한 배열입니다.  
  
 옵션이  
 \[in\] 명령 플래그 \(의 "PopulateList 플래그" 섹션을 참조 [특정 명령에서 사용 하는 비트](../extensibility/bitflags-used-by-specific-commands.md) 대 한 자세한 내용은\).  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|명령 실행 성공|  
|SCC\_E\_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다.|  
  
## 설명  
 이 함수에서는 현재 상태에 대 한 파일의 목록을 검토합니다. 사용 하 여는 `pfnPopulate` 파일에 대 한 조건을 일치 하지 않는 경우 호출자에 게 알리기 위해 콜백 함수는 `nCommand`합니다. 예를 들어, 명령이 실행 되 면 `SCC_COMMAND_CHECKIN` 하 고 목록에서 파일 체크 아웃 하지는 다음 호출자에 게 알리는 데 사용 됩니다. 경우에 따라 소스 제어 플러그 인에 추가 하 고 명령 수 있는 다른 파일을 찾을 수 있습니다. 이 사용 하면 예를 들어 Visual Basic 사용자가 자신의 프로젝트에서 사용 되지만 Visual Basic 프로젝트 파일에 나타나지 않으면.bmp 파일을 체크 아웃 합니다. 사용자가 선택 된 **가져오기** IDE에서 명령입니다. IDE 사용자 얻을 수 것으로 확인 하는 모든 파일의 목록이 표시 됩니다 아직 목록 표시 되는 `SccPopulateList` 함수가 호출 되어 표시 되는 목록을 최신 상태 인지 확인 합니다.  
  
## 예제  
 IDE는 사용자를 가져올 수 있어야 할 파일의 목록을 작성 합니다. 호출 전에이 목록에 표시 되는 `SccPopulateList` 함수를 추가 하 고 목록에서 파일을 삭제 합니다. 소스 제어 플러그 인 기회를 제공 합니다. 지정된 된 콜백 함수를 호출 하 여 플러그 인 수정 목록 \(참조 [POPLISTFUNC](../extensibility/poplistfunc.md) 대 한 자세한 내용은\).  
  
 플러그 인을 계속 호출 하는 `pfnPopulate` 추가 완료 되 고 다음에서 반환 될 때까지 파일을 삭제 하는 함수는 `SccPopulateList` 함수입니다. 그런 다음 IDE 목록을 표시할 수 있습니다.`lpStatus` 배열은 IDE에 의해 전달 된 원래 목록의 모든 파일을 나타냅니다. 또한 시키기 위한 파일 모두의 상태에 플러그 인 채우기는 콜백 함수를 사용 합니다.  
  
> [!NOTE]
>  소스 제어 플러그 인에 항상 단순히이 함수에는 목록 내에서 즉시 반환 하는 옵션을 있습니다. 플러그 인이 함수를 구현 하는 경우를 나타낼 수 있습니다이 설정의 `SCC_CAP_POPULATELIST` 기능 비트 플래그에 대 한 첫 번째 호출에는 [SccInitialize](../extensibility/sccinitialize-function.md)합니다. 기본적으로 플러그 인 항상 가정해 야 모든 항목에 전달 되는 파일. 그러나 IDE 설정 하는 경우는 `SCC_PL_DIR` 플래그는 `fOptions` 매개 변수를 전달 되는 모든 항목 디렉터리로 간주 됩니다. 플러그 인는 디렉터리에 속하는 모든 파일을 추가 해야 합니다. IDE 전달 하지는 않지만 파일 및 디렉터리의 혼합 합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)   
 [POPLISTFUNC](../extensibility/poplistfunc.md)   
 [특정 명령에서 사용 하는 비트](../extensibility/bitflags-used-by-specific-commands.md)   
 [명령 코드](../extensibility/command-code-enumerator.md)