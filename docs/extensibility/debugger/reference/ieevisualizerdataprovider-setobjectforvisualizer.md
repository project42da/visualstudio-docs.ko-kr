---
title: "IEEVisualizerDataProvider::SetObjectForVisualizer | Microsoft Docs"
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
  - "IEEVisualizerDataProvider::SetObjectForVisualizer"
helpviewer_keywords: 
  - "IEEVisualizerDataProvider::SetObjectForVisualizer 메서드"
ms.assetid: 40dad2be-57ff-4f74-9d82-c48039c125c4
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IEEVisualizerDataProvider::SetObjectForVisualizer
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 시각화 도우미를 나타내는 개체를 변경 합니다.  
  
## 구문  
  
```cpp  
HRESULT SetObjectForVisualizer(  
   IDebugObject*  pNewObject,  
   BSTR*          error,  
   IDebugObject** pException  
);  
```  
  
```c#  
int SetObjectForVisualizer(  
   IDebugObject     pNewObject,  
   out string       error,  
   out IDebugObject pException  
);  
```  
  
#### 매개 변수  
 `pNewObject`  
 \[in\] 설정할 개체입니다.  
  
 `error`  
 \[out\] 개체를 설정할 때 오류가 발생 했습니다 경우이 문자열에 오류 메시지가 들어 있습니다.  
  
 `pException`  
 \[out\] 오류가 있으면이 개체는 예외 정보를 보유 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 구현자에 오류 정보를 반환 하는 방법을 확인 하는 것.입니다.  그러나 오류가 없는 경우이 메서드는 항상 예외 개체 반환 합니다 오류 메시지를 알고 있을 예외 개체가 반환 된 경우 보려면 확인 했습니다만 호출자에 게 일부를 수 있습니다.  호출자를 확인 하고자 하는 경우 오류는 문자열도 제공 해야를 사용 합니다.  
  
## 참고 항목  
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)