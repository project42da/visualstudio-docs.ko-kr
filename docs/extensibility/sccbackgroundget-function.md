---
title: "SccBackgroundGet 함수 | Microsoft Docs"
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
  - "SccBackgroundGet"
helpviewer_keywords: 
  - "SccBackgroundGet 함수"
ms.assetid: 69817e52-b9ac-4f4d-820b-2cc9c384f0dc
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# SccBackgroundGet 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 함수는 소스 제어에서 각 지정 된 파일의 사용자 상호 작용 없이 가져옵니다.  
  
## 구문  
  
```cpp  
SCCRTN SccBackgroundGet(  
   LPVOID  pContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LONG    dwFlags,  
   LONG    dwBackgroundOperationID  
);  
```  
  
#### 매개 변수  
 pContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 포인터입니다.  
  
 nFiles  
 \[in\] 에 지정 된 파일의 수는 `lpFileNames` 배열입니다.  
  
 lpFileNames  
 \[에서, out\] 검색할 파일 이름 배열입니다.  
  
> [!NOTE]
>  이름은 정규화 된 로컬 파일 이름 이어야 합니다.  
  
 dwFlags  
 \[in\] 명령 플래그 \(`SCC_GET_ALL`, `SCC_GET_RECURSIVE`\).  
  
 dwBackgroundOperationID  
 \[in\] 이 작업과 연결 된 고유한 값입니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|작업이 완료 되었습니다.|  
|SCC\_E\_BACKGROUNDGETINPROGRESS|배경 검색 이미 진행 중인 \(소스 제어 플러그 인 반환 해야이 동시 일괄 처리 작업을 지원 하지 않는 경우에\).|  
|SCC\_I\_OPERATIONCANCELED|작업이 완료 되 고 하기 전에 취소 되었습니다.|  
  
## 설명  
 이 함수는 항상 소스 제어 플러그 인을 로드 하는 것과에서 다른 스레드에서 호출 됩니다. 이 함수는; 완료 될 때까지 반환 되지 그러나 것 수 여러 번 호출할 수의 동시에 모든 파일을 여러 목록을 사용 하 여 합니다.  
  
 사용 하는 `dwFlags` 인수는 같은 [SccGet](../extensibility/sccget-function.md)합니다.  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)   
 [SccGet](../extensibility/sccget-function.md)