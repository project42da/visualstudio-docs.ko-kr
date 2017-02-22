---
title: "IDebugDocumentPosition2::GetFileName | Microsoft Docs"
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
  - "IDebugDocumentPosition2::GetFileName"
helpviewer_keywords: 
  - "IDebugDocumentPosition2::GetFileName"
ms.assetid: d713635e-088f-465b-b26d-00ac971c9e86
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDocumentPosition2::GetFileName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

문서 위치를 포함 하는 소스 파일의 파일 이름을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetFileName(   
   BSTR* pbstrFileName  
);  
```  
  
```c#  
int GetFileName(   
   out string pbstrFileName  
);  
```  
  
#### 매개 변수  
 `pbstrFileName`  
 \[out\] 소스 파일의 파일 이름을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 원본 파일이 항상 \(원본 파일이 디스크에 예를 들어 존재 하지\) 파일 이름이 없을 수 있습니다.  
  
## 참고 항목  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)