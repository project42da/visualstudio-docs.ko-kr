---
title: "IDebugFunctionObject2::Evaluate | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugFunctionObject2::Evaluate"
ms.assetid: bc54c652-904b-4297-a6db-faa329684881
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugFunctionObject2::Evaluate
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

함수를 호출 하 고 결과 값을 개체로 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT Evaluate (  
   IDebugObject** ppParams,  
   DWORD          dwParams,  
   DWORD          dwEvalFlags,  
   DWORD          dwTimeout,  
   IDebugObject** ppResult  
);  
```  
  
```c#  
int Evaluate (  
   IDebugObject     ppParams,  
   uint             dwParams,  
   uint             dwEvalFlags,  
   uint             dwTimeout,  
   out IDebugObject ppResult  
);  
```  
  
#### 매개 변수  
 `ppParams`  
 \[in\] 배열 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 입력된 매개 변수를 나타내는 개체입니다.  이러한 매개 변수를이 인터페이스의 작성 방법 중 하나를 사용 하 여 만들어졌습니다.  
  
 `dwParams`  
 \[in\] 수의 매개 변수는 `ppParams` 배열입니다.  
  
 `dwEvalFlags`  
 \[in\] 플래그의 조합에서 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) 평가 수행 하는 방법을 지정 하는 열거형입니다.  
  
 `dwTimeout`  
 \[in\] 이 메서드에서 반환 하기 전에 대기할 시간 \(밀리초\), 최대 시간을 지정 합니다.  사용  **무한** 무제한으로 대기 합니다.  
  
 `ppResult`  
 \[out\] 반환 된  **IDebugObject** 는 함수 개체의 값을 나타냅니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugFunctionObject2](../../../extensibility/debugger/reference/idebugfunctionobject2.md)