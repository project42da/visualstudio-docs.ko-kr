---
title: "IDebugDocumentHelper::SetTextAttributes | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentHelper.SetTextAttributes
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugDocumentHelper::SetTextAttributes"
ms.assetid: 31657738-9e4c-436a-be61-23f4185d452e
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentHelper::SetTextAttributes
텍스트를 다른 텍스트에 특성을 재정의 범위에 특성을 설정 합니다.  
  
## 구문  
  
```  
HRESULT SetTextAttributes(  
   ULONG              ulCharOffset,  
   ULONG              cChars,  
   SOURCE_TEXT_ATTR*  pstaTextAttr  
);  
```  
  
#### 매개 변수  
 `ulCharOffset`  
 \[in\] 텍스트 범위의 시작 위치입니다.  
  
 `cChars`  
 \[in\] 범위에 있는 문자의 수입니다.  
  
 `pstaTextAttr`  
 \[in\] 원본 텍스트 범위의 텍스트에 대 한 특성입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 오류가 호출 하는 것이 `SetTextAttributes` 에서 해당 텍스트를 문서에 추가 하기 전에 텍스트 범위.  호출 하는 `AddDBCSText`, `AddUnicodeText`, 또는 `AddDeferredText` 문서에 텍스트를 추가 하는 방법.  
  
## 참고 항목  
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [IDebugDocumentHelper::AddUnicodeText](../../winscript/reference/idebugdocumenthelper-addunicodetext.md)   
 [IDebugDocumentHelper::AddDBCSText](../../winscript/reference/idebugdocumenthelper-adddbcstext.md)   
 [IDebugDocumentHelper::AddDeferredText](../../winscript/reference/idebugdocumenthelper-adddeferredtext.md)   
 [SOURCE\_TEXT\_ATTR 열거형](../../winscript/reference/source-text-attr-enumeration.md)