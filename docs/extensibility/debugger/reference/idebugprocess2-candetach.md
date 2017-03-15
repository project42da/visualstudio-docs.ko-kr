---
title: "IDebugProcess2::CanDetach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProcess2::CanDetach"
helpviewer_keywords: 
  - "IDebugProcess2::CanDetach"
ms.assetid: 2830f7c3-69fb-474a-97b8-5b869e38d546
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugProcess2::CanDetach
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

세션 디버그 매니저 \(SDM\) 프로세스를 분리할 수 있습니다 경우 결정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT CanDetach(  
   void  
);  
```  
  
```c#  
int CanDetach();  
```  
  
## 반환 값  
 성공 하면 반환 `S_OK.` 반환 `S_FALSE` 는 경우 디버거를 프로세스에서 분리할 수 없습니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [CanDetach](../../../extensibility/debugger/reference/idebugprogram2-candetach.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)