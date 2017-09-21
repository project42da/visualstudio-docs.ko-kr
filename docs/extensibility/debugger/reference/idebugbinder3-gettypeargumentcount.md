---
title: "IDebugBinder3::GetTypeArgumentCount | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugBinder3::GetTypeArgumentCount"
helpviewer_keywords: 
  - "IDebugBinder3::GetTypeArgumentCount 메서드"
ms.assetid: caf68de6-6f7c-4efd-b803-121347a5032e
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# IDebugBinder3::GetTypeArgumentCount
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는이 개체와 연관 된 인수 형식의 수를 반환 합니다.  
  
## 구문  
  
```cpp  
HRESULT GetTypeArgumentCount(  
   UINT* uCount  
);  
```  
  
```c#  
int GetTypeArgumentCount(  
   out uint uCount  
);  
```  
  
#### 매개 변수  
 `uCount`  
 \[out\] 이 개체와 연관 된 인수 형식의 수입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드에 의해 반환 되는 값을 사용 하 여 함께 사용할 배열을 할당할 수 있습니다 해당 [GetTypeArguments](../../../extensibility/debugger/reference/idebugbinder3-gettypearguments.md) 메서드가 있습니다.  
  
## 참고 항목  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)   
 [GetTypeArguments](../../../extensibility/debugger/reference/idebugbinder3-gettypearguments.md)