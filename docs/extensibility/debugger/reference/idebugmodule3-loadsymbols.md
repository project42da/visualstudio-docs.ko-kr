---
title: "IDebugModule3::LoadSymbols | Microsoft Docs"
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
  - "IDebugModule3::LoadSymbols"
helpviewer_keywords: 
  - "IDebugModule3::LoadSymbols"
ms.assetid: 7548c8c1-cbc6-48aa-a845-19058d4a85bb
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugModule3::LoadSymbols
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

현재 모듈에 대 한 기호를 로드합니다.  
  
## 구문  
  
```cpp#  
HRESULT LoadSymbols(  
   void  
);  
```  
  
```c#  
int LoadSymbols();  
```  
  
## 반환 값  
 메서드가 성공 하면, 반환 `S_OK`.  실패할 경우 오류 코드를 반환합니다.  
  
## 설명  
 이 메서드는 현재 검색 경로에서 기호 로드 \(을 변경할 수 있습니다 호출 하 여 해당 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md) 메서드\).  
  
 이 방법을 통해 사용 하는 것은 [ReloadSymbols\_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md) 메서드가 있습니다.  
  
## 참고 항목  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)   
 [SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)