---
title: "IDebugInterceptExceptionCompleteEvent2::GetInterceptCookie | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugInterceptExceptionCompleteEvent2::GetInterceptCookie"
helpviewer_keywords: 
  - "IDebugInterceptExceptionCompleteEvent2::GetInterceptCookie"
ms.assetid: 07b20866-e598-4783-9ecc-6aa8625c8804
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugInterceptExceptionCompleteEvent2::GetInterceptCookie
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

차단된 예외 처리가 완료 될 때 호출 됩니다.  
  
## 구문  
  
```cpp#  
HRESULT GetInterceptCookie(  
   UINT64* pqwCookie  
);  
```  
  
```c#  
int GetInterceptCookie(  
   out ulong pqwCookie  
);  
```  
  
#### 매개 변수  
 `pqwCookie`  
 \[out\] 차단 된 예외와 관련 된 고유 값입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  
  
## 설명  
 후는 [InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md) 메서드를 처리 하는 차단 완료 했습니다,이 전송의 [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md) 이벤트입니다.  처리기를 사용할 수 있습니다의 `GetInterceptCookie` 예외와 연결 된 고유 값을 검색 하는 방법 \(전달 된 값은 `InterceptCurrentException` 메서드\).  
  
## 참고 항목  
 [InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md)   
 [IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md)