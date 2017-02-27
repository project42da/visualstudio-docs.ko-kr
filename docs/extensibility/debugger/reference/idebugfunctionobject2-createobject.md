---
title: "IDebugFunctionObject2::CreateObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugFunctionObject2::CreateObject"
  - "CreateObject"
ms.assetid: 148de615-941e-4b64-ab11-75b692aae465
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugFunctionObject2::CreateObject
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

평가 플래그 설정 및 제한 시간 값을 지정 하는 생성자를 사용 하 여 개체를 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT CreateObject (  
   IDebugFunctionObject* pConstructor,  
   DWORD                 dwArgs,  
   IDebugObject*         pArgs[],  
   DWORD                 dwEvalFlags,  
   DWORD                 dwTimeout,  
   IDebugObject**        ppObject  
);  
```  
  
```c#  
int CreateObject (  
   IDebugFunctionObject pConstructor,  
   uint                 dwArgs,  
   IDebugObject[]       pArgs,  
   uint                 dwEvalFlags,  
   uint                 dwTimeout,  
   out IDebugObject**   ppObject  
);  
```  
  
#### 매개 변수  
 `pConstructor`  
 \[in\] [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 만들 개체의 생성자를 나타내는 개체입니다.  
  
 `dwArgs`  
 \[in\] 수의 매개 변수는 `pArg` 배열입니다.  생성자에 전달 된 매개 변수의 수를 나타냅니다.  
  
 `pArgs`  
 \[in\] 배열 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 매개 변수를 나타내는 개체를 생성자에 전달 합니다.  
  
 `dwEvalFlags`  
 \[in\] 플래그의 조합에서 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) 평가 수행 하는 방법을 지정 하는 열거형입니다.  
  
 `dwTimeout`  
 \[in\] 이 메서드에서 반환 하기 전에 대기할 시간 \(밀리초\), 최대 시간입니다.  사용  **무한** 무제한으로 대기 합니다.  
  
 `ppObject`  
 \[out\] 반환 된  **IDebugObject** , 새로 만들어진된 개체를 나타내는.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 클래스, 또는 매개 변수가 있는 생성자를 요구 하는 다른 복합 형식 인스턴스를 나타내는 개체를 만드는 데이 메서드를 호출 합니다.  
  
## 참고 항목  
 [IDebugFunctionObject2](../../../extensibility/debugger/reference/idebugfunctionobject2.md)