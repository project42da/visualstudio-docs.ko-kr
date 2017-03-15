---
title: "IDebugEngine2::CauseBreak | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEngine2::CauseBreak"
helpviewer_keywords: 
  - "IDebugEngine2::CauseBreak"
ms.assetid: 17fe4698-b04e-4798-8412-80e0da60c387
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugEngine2::CauseBreak
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 디버그 하면 디버깅 중인 모든 프로그램 \(DE\) 엔진은 다음 실행을 중지 하는 요청을 실행 하는 스레드의 시도 중 하나 시간.  
  
## 구문  
  
```cpp#  
HRESULT CauseBreak(   
   void   
);  
```  
  
```c#  
int CauseBreak();  
```  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드는 비동기입니다:는 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) 이벤트 프로그램이 다음이 메서드를 호출한 후에 실행 하 려 할 때 보내집니다.  
  
## 참고 항목  
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)