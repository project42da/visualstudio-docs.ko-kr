---
title: "SccHistory 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccHistory"
helpviewer_keywords: 
  - "SccHistory 함수"
ms.assetid: a636d9d3-47c1-4b48-ac6b-bcfde19d6cf9
caps.latest.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 16
---
# SccHistory 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 지정된 된 파일의 기록을 표시합니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccHistory(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### 매개 변수  
 `pvContext`  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 `hWnd`  
 \[in\] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 `nFiles`  
 \[in\] 에 지정 된 파일의 수는 `lpFileName` 배열입니다.  
  
 `lpFileName`  
 \[in\] 파일의 정규화 된 이름의 배열입니다.  
  
 `fOptions`  
 \[in\] \(현재 사용 되지 않음\) 하는 명령 플래그입니다.  
  
 `pvOptions`  
 \[in\] 소스 제어 플러그 인에 대 한 옵션입니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|버전 기록이 가져왔습니다.|  
|SCC\_I\_RELOADFILE|소스 제어 시스템 \(예를 들어, 그 이전 버전의 내용이\), 여 역사를 인출 하는 동안 디스크에 있는 파일을 실제로 수정 하므로 IDE이이 파일을 다시 로드 해야 합니다.|  
|SCC\_E\_FILENOTCONTROLLED|소스 제어는 파일이 아닙니다.|  
|SCC\_E\_OPNOTSUPPORTED|소스 제어 시스템에서이 작업을 지원 하지 않습니다.|  
|SCC\_E\_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC\_E\_ACCESSFAILURE|소스 제어 시스템에 경합 또는 네트워크 문제 때문에 액세스할 수 없습니다. 다시 시도 사용 하는 것이 좋습니다.|  
|SCC\_E\_PROJNOTOPEN|프로젝트 되어 열립니다.|  
|SCC\_E\_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다. 파일 히스토리를 가져올 수 없습니다.|  
  
## 설명  
 소스 제어 플러그 인 각 파일의 기록을 표시 하는 자체 대화 상자를 표시할 수를 사용 하 여 `hWnd` 부모 창으로 합니다. 또는 선택적 텍스트 출력 콜백 함수에 제공 되는 [SccOpenProject](../extensibility/sccopenproject-function.md) 지원 되는 경우 사용할 수 있습니다.  
  
 참고 특정 상황에서는이 호출의 실행 하는 동안 검사할 파일이 변경 될 수 있습니다. 예를 들어는 [!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] 기록 명령 파일의 이전 버전을 얻을 수는 사용자에 게 있습니다. 이 경우 소스 제어 플러그 인 반환 `SCC_I_RELOAD` 파일 다시 로드 해야 함을 IDE에 게 경고 합니다.  
  
> [!NOTE]
>  소스 제어 플러그 인 파일의 배열에 대해이 함수를 지원 하지 않으면, 첫 번째 파일에 대 한 파일 기록만 표시할 수 있습니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)