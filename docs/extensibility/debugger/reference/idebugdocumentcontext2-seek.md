---
title: "IDebugDocumentContext2::Seek | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugDocumentContext2::Seek"
helpviewer_keywords: 
  - "IDebugDocumentContext2::Seek"
ms.assetid: 71501356-8a82-4d36-b354-6625bdd2baa0
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugDocumentContext2::Seek
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

문서의 컨텍스트에서 지정 된 문 또는 줄 수 만큼 이동합니다.  
  
## 구문  
  
```cpp#  
HRESULT Seek(   
   int                      nCount,  
   IDebugDocumentContext2** ppDocContext  
);  
```  
  
```cpp#  
int Seek(   
   int                        nCount,  
   out IDebugDocumentContext2 ppDocContext  
);  
```  
  
#### 매개 변수  
 `nCount`  
 \[in\] 문 또는 문서의 상황에 따라 앞으로 이동할 줄 수입니다.  
  
 `ppDocContext`  
 \[out\] 새 반환 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 개체의 새 위치에 있습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)