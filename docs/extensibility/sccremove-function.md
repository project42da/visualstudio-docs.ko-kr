---
title: "SccRemove 함수 | Microsoft Docs"
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
  - "SccRemove"
helpviewer_keywords: 
  - "SccRemove 함수"
ms.assetid: 20830fdc-c0e9-4a5f-bf60-33f28874442f
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# SccRemove 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 소스 제어 시스템에서 파일을 삭제합니다.  
  
## 구문  
  
```cpp#  
SCCRTN SccRemove(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LPCSTR    lpComment,  
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
 \[in\] 제거할 파일의 정규화 된 로컬 경로 이름의 배열입니다.  
  
 lpComment  
 \[in\] 제거 하 고 각 파일에 적용할 주석입니다.  
  
 옵션이  
 \[in\] \(사용 되지 않는\) 명령 플래그입니다.  
  
 pvOptions  
 \[in\] 소스 제어 플러그 인에 대 한 옵션입니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|제거 성공 했습니다.|  
|SCC\_E\_FILENOTCONTROLLED|선택한 파일이 소스 제어 하지 않습니다.|  
|SCC\_E\_OPNOTSUPPORTED|소스 제어 시스템에서이 작업을 지원 하지 않습니다.|  
|SCC\_E\_ISCHECKEDOUT|사용자가 체크 아웃 한 파일을 제거할 수 없습니다.|  
|SCC\_E\_ACCESSFAILURE|소스 제어 시스템에 경합 또는 네트워크 문제 때문에 액세스할 수 없습니다.|  
|SCC\_E\_NOTAUTHORIZED|사용자가이 작업을 수행할 수 없습니다.|  
|SCC\_E\_NONSPECIFICERROR|알 수 없는 오류입니다. 파일 제거 되지 않았습니다.|  
|SCC\_I\_OPERATIONCANCELED|작업이 완료 되기 전에 취소 되었습니다.|  
  
## 설명  
 이 함수는 소스 제어 시스템에서 파일을 제거 하지만 사용자의 로컬 하드 드라이브에서 삭제 하지 않습니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)