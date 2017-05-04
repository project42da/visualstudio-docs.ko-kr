---
title: "IDebugApplication::RemoveGlobalExpressionContextProvider | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplication.RemoveGlobalExpressionContextProvider
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplication::RemoveGlobalExpressionContextProvider"
ms.assetid: ace638a3-ed34-4d20-8404-45c684aaaf1a
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplication::RemoveGlobalExpressionContextProvider
이 응용 프로그램에서 전역 식 컨텍스트 공급자를 제거합니다.  
  
## 구문  
  
```  
HRESULT RemoveGlobalExpressionContextProvider(  
   DWORD_PTR  dwCookie  
);  
```  
  
#### 매개 변수  
 `dwCookie`  
 \[in\] 반환 되는 쿠키는 `AddGlobalExpressionContextProvider` 전역 컨텍스트 공급자가 추가 될 때 메서드.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 `RemoveGlobalExpressionContextProvider` 메서드는이 응용 프로그램에서 전역 식 컨텍스트 공급자를 제거 합니다.  
  
## 참고 항목  
 [IDebugApplication::AddGlobalExpressionContextProvider](../../winscript/reference/idebugapplication-addglobalexpressioncontextprovider.md)   
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)