---
title: "SccEnumChangedFiles 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SccEnumChangedFiles"
helpviewer_keywords: 
  - "SccEnumChangedFiles 함수"
ms.assetid: 76cac510-107b-4c1a-ba60-9c39b6db2e71
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# SccEnumChangedFiles 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

로컬 파일의 목록이 들어이 함수는 파일은 소스 코드 제어 데이터베이스에는 해당 버전에서 다른 결정 합니다.  
  
## 구문  
  
```cpp  
SCCRTN SccEnumChangedFiles(  
   LPVOID  pContext,  
   HWND    hWnd,  
   LONG    cFiles,  
   LPCSTR* lpFileNames,  
   LONG*   plIsFileDifferent  
);  
```  
  
#### 매개 변수  
 pContext  
 \[in\] 소스 제어 플러그 인 컨텍스트 포인터입니다.  
  
 hWnd  
 \[in\] 소스 제어 플러그 인을 제공 하는 모든 대화 상자에 대 한 부모로 사용할 수 있는 IDE 창 핸들입니다.  
  
 cFiles  
 \[in\] 파일 이름에 지정 된 수의 `lpFileNames` 배열입니다. 크기를 지정 하는 또한 `plIsFileDifferent` 배열입니다.  
  
 lpFileNames  
 \[in\] 확인 하려면 로컬 파일 이름 배열입니다.  
  
 plIsFileDifferent  
 \[에서, out\] 각 파일의 차이점 상태를 나타내는 값의 배열입니다 \(배열에 적어도 있어야 `cFiles` 항목\). 0이 아니면 파일 달라진 다는 것을 의미 합니다.  
  
## 반환 값  
 이 함수의 소스 제어 플러그 인 구현 다음 값 중 하나를 반환 해야 합니다.  
  
|값|설명|  
|-------|--------|  
|SCC\_OK|작업이 완료 되었습니다.|  
|SCC\_UNSPECIFIEDERROR|일반 오류입니다.|  
  
## 참고 항목  
 [소스 제어 플러그 인 API 함수](../extensibility/source-control-plug-in-api-functions.md)