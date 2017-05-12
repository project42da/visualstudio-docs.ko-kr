---
title: "IApplicationDebuggerUI::BringDocumentContextToTop | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IApplicationDebuggerUI.BringDocumentContextToTop
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IApplicationDebuggerUI::BringDocumentContextToTop"
ms.assetid: 7844217d-658b-42af-8d10-2714f4eded20
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IApplicationDebuggerUI::BringDocumentContextToTop
디버거 사용자 인터페이스의 위쪽에 지정 된 문서 컨텍스트를 포함 하는 창을 불러오고 상황으로 창을 스크롤합니다.  
  
## 구문  
  
```  
HRESULT BringDocumentContextToTop(  
   IDebugDocumentContext*  pddc  
);  
```  
  
#### 매개 변수  
 `pddc`  
 \[in\] 문서 컨텍스트를 위쪽으로 디버거 사용자 인터페이스에 표시 합니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_INVALIDARG`|지정 된 컨텍스트 `pddc` 알 수 없습니다.|  
  
## 설명  
 이 이렇게 디버거 사용자 인터페이스의 위쪽에 지정 된 문서 컨텍스트를 포함 하는 창을 불러오고 상황으로 창을 스크롤합니다.  
  
## 참고 항목  
 [IApplicationDebuggerUI 인터페이스](../../winscript/reference/iapplicationdebuggerui-interface.md)