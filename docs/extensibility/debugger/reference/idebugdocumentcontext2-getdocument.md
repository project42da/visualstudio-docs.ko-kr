---
title: "IDebugDocumentContext2::GetDocument | Microsoft Docs"
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
  - "IDebugDocumentContext2::GetDocument"
helpviewer_keywords: 
  - "IDebugDocumentContext2::GetDocument"
ms.assetid: c6d46c5d-ade8-4dc8-9862-8fc7876658c4
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDocumentContext2::GetDocument
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 문서의 컨텍스트에 포함 된 문서를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetDocument(   
   IDebugDocument2** ppDocument  
);  
```  
  
```c#  
int GetDocument(   
   out IDebugDocument2 ppDocument  
);  
```  
  
#### 매개 변수  
 `ppDocument`  
 \[out\] 반환 된 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) 이 문서 컨텍스트를 포함 하는 문서를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드를 IDE에 직접 문서를 제공 합니다. 이러한 디버깅 엔진입니다.  그렇지 않은 경우이 메서드를 반환 합니다 `E_NOTIMPL`.  
  
## 참고 항목  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)