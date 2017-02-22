---
title: "IEEVisualizerDataProvider::CanSetObjectForVisualizer | Microsoft Docs"
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
  - "IEEVisualizerDataProvider::CanSetObjectForVisualizer"
helpviewer_keywords: 
  - "IEEVisualizerDataProvider::CanSetObjectForVisualizer 메서드"
ms.assetid: 70fd3c6f-2f82-43a3-993b-c1dc8aa080bf
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IEEVisualizerDataProvider::CanSetObjectForVisualizer
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 시각화 도우미 업데이트 나타내는 데이터 개체를 사용할 수 있는지 여부를 확인 합니다.  
  
## 구문  
  
```cpp  
HRESULT CanSetObjectForVisualizer(  
   BOOL* b  
);  
```  
  
```c#  
int CanSetObjectForVisualizer(  
   out int b  
);  
```  
  
#### 매개 변수  
 `b`  
 \[out\] 0이 아닌 \(`TRUE`\)은 시각화 도우미에서 개체를 업데이트할 수 없으면 0 \(`FALSE`\) 불가능 한 경우.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 예를 들어 읽기 전용 메모리에 바인딩된 경우 변경할 수 있는 개체 수 있습니다.  
  
## 참고 항목  
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)