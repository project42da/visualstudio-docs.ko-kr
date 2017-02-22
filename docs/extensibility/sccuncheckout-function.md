---
title: "SccUncheckout 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccUncheckout"
helpviewer_keywords: 
  - "SccUncheckout 함수"
ms.assetid: 6d498b70-29c7-44b7-ae1c-7e99e488bb09
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# SccUncheckout 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 선택한 파일 또는 파일의 내용을 체크 아웃 이전 상태로 복원 이전 체크 아웃 작업을 실행 취소 합니다. 체크 아웃 이후에 파일을 수정 하는 모든 변경 내용이 손실 됩니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccUncheckout (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### 매개 변수  
 pvContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 구조입니다.  
  
 hWnd  
 \[in\] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 nFiles  
 \[in\] 에 지정 된 파일의 수는 `lpFileNames` 배열입니다.  
  
 lpFileNames  
 \[in\] 체크 아웃을 취소 하려는 파일의 정규화 된 로컬 경로 이름의 배열입니다.  
  
 옵션이  
 \[in\] \(사용 되지 않음\) 하는 명령 플래그입니다.  
  
 pvOptions  
 \[in\] 소스 제어 플러그 인에 대 한 옵션입니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|체크 아웃을 취소 했습니다.|  
|SCC\_E\_FILENOTCONTROLLED|선택한 파일이 소스 코드 제어 하지 않습니다.|  
|SCC\_E\_ACCESSFAILURE|소스 제어 시스템에 경합 또는 네트워크 문제 때문에 액세스할 수 없습니다. 다시 시도 사용 하는 것이 좋습니다.|  
|SCC\_E\_NONSPECIFICERROR|알 수 없는 오류가 발생 했습니다. 실행 취소 체크 아웃 하지 못했습니다.|  
|SCC\_E\_NOTCHECKEDOUT|사용자는 파일을 체크 아웃는 없습니다.|  
|SCC\_E\_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC\_E\_PROJNOTOPEN|프로젝트 소스 제어에서 열리지 않았습니다.|  
|SCC\_I\_OPERATIONCANCELED|작업이 완료 되기 전에 취소 되었습니다.|  
  
## 설명  
 이 작업 후의 `SCC_STATUS_CHECKEDOUT` 및 `SCC_STATUS_MODIFIED` 플래그는 모두 지워집니다 체크 아웃을 취소 수행 된 파일에 대 한 합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)