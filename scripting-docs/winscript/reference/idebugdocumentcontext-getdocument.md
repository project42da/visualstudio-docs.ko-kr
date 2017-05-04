---
title: "IDebugDocumentContext::GetDocument | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentContext.GetDocument
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugDocumentContext::GetDocument"
ms.assetid: 32db2fea-4938-4644-b39a-8fae05960d1d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentContext::GetDocument
이 컨텍스트를 포함 하는 문서를 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetDocument(  
   IDebugDocument**  ppsd  
);  
```  
  
#### 매개 변수  
 `ppsd`  
 \[out\] 이 컨텍스트를 포함 하는 문서입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 `GetDocument` 이 들어 있는 문서를 반환 합니다.  
  
## 참고 항목  
 [IDebugDocumentContext 인터페이스](../../winscript/reference/idebugdocumentcontext-interface.md)