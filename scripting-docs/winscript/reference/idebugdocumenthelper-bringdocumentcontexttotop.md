---
title: "IDebugDocumentHelper::BringDocumentContextToTop | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentHelper.BringDocumentContextToTop
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugDocumentHelper::BringDocumentContextToTop"
ms.assetid: cf9751c5-e9b7-45c6-b084-3f3873dbf01d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentHelper::BringDocumentContextToTop
이 문서의 컨텍스트에 위쪽으로 디버거 사용자 인터페이스에 표시 됩니다.  
  
## 구문  
  
```  
HRESULT BringDocumentContextToTop(  
   IDebugDocumentContext*  pddc  
);  
```  
  
#### 매개 변수  
 `pddc`  
 문서 컨텍스트를 위쪽으로 디버거 사용자 인터페이스에 표시 합니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는이 문서의 컨텍스트를 위쪽으로 디버거 사용자 인터페이스에 나타납니다.  
  
## 참고 항목  
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)