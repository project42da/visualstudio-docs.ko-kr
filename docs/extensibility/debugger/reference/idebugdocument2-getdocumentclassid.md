---
title: "IDebugDocument2::GetDocumentClassID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugDocument2::GetDocumentClassID"
helpviewer_keywords: 
  - "IDebugDocument2::GetDocumentClassID"
ms.assetid: 111c2b85-ebfa-487f-b896-2ec4a3eac4d1
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugDocument2::GetDocumentClassID
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

문서 클래스 id를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetDocumentClassID(   
   CLSID* pclsid  
);  
```  
  
```c#  
int GetDocumentClassID(   
   out Guid pclsid  
);  
```  
  
#### 매개 변수  
 `pclsid`  
 \[out\] 문서 클래스 id는 GUID를 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 클래스 GUID는 문서를 나타내는 개별 클래스를 인스턴스화하는 데 사용할 수 있습니다.  
  
## 참고 항목  
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)