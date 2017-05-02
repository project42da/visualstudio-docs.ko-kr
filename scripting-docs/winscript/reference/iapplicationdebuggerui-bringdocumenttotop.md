---
title: "IApplicationDebuggerUI::BringDocumentToTop | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IApplicationDebuggerUI.BringDocumentToTop
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IApplicationDebuggerUI::BringDocumentToTop"
ms.assetid: ef5fe1e7-4381-4409-a0d7-58f993abe84e
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IApplicationDebuggerUI::BringDocumentToTop
위쪽 디버거에서 디버그를 지정한 문서를 포함 하는 창 사용자 인터페이스를 제공 합니다.  
  
## 구문  
  
```  
HRESULT BringDocumentToTop(  
   IDebugDocumentText*  pddt  
);  
```  
  
#### 매개 변수  
 `pddt`  
 \[in\] 디버거 사용자 인터페이스의 맨 위로 이동 하는 문서를 디버그 합니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_INVALIDARG`|문서를 알 수 없습니다.|  
  
## 설명  
 이 메서드 위쪽 디버거에서 디버그를 지정한 문서를 포함 하는 창 사용자 인터페이스를 제공 합니다.  
  
## 참고 항목  
 [IApplicationDebuggerUI 인터페이스](../../winscript/reference/iapplicationdebuggerui-interface.md)