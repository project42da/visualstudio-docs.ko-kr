---
title: "IDebugDocumentHelper::SetDocumentAttr | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentHelper.SetDocumentAttr
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugDocumentHelper::SetDocumentAttr"
ms.assetid: bd7ffdbd-de51-477d-bd3f-760db020fe70
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentHelper::SetDocumentAttr
이 문서에 대 한 특성을 설정합니다.  
  
## 구문  
  
```  
HRESULT SetDocumentAttr(  
   TEXT_DOC_ATTR  pszAttributes  
);  
```  
  
#### 매개 변수  
 `pszAttributes`  
 \[in\] 문서에 적용 되는 특성입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는이 문서에 대 한 특성을 설정합니다.  
  
## 참고 항목  
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [TEXT\_DOC\_ATTR 상수](../../winscript/reference/text-doc-attr-constants.md)