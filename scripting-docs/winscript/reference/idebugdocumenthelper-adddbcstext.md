---
title: "IDebugDocumentHelper::AddDBCSText | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentHelper.AddDBCSText
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugDocumentHelper::AddDBCSText"
ms.assetid: 5e5011b2-bbb4-491b-9a11-eb2846be44aa
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentHelper::AddDBCSText
이 문서의 끝에 DBCS 문자열을 추가합니다.  
  
## 구문  
  
```  
HRESULT AddDBCSText(  
   LPCSTR  pszText  
);  
```  
  
#### 매개 변수  
 `pszText`  
 \[in\] 텍스트를 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_FAIL`|메서드는 문자를 추가 하지 못했습니다.|  
  
## 설명  
 이 메서드를 생성 합니다. `IDebugDocumentTextEvents` 알림.  
  
> [!NOTE]
>  이후에이 메서드를 호출 하면 `IDebugDocumentHelper::AddDeferredText` 호출 된 `E_FAIL` 이 반환 됩니다.  
  
## 참고 항목  
 [IDebugDocumentHelper 인터페이스](../../winscript/reference/idebugdocumenthelper-interface.md)   
 [IDebugDocumentHelper::AddDeferredText](../../winscript/reference/idebugdocumenthelper-adddeferredtext.md)   
 [IDebugDocumentTextEvents 인터페이스](../../winscript/reference/idebugdocumenttextevents-interface.md)