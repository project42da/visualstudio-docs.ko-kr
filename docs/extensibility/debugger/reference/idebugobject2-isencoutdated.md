---
title: "IDebugObject2::IsEncOutdated | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugObject2::IsEncOutdated"
helpviewer_keywords: 
  - "IDebugObject2::IsEncOutdated 메서드"
ms.assetid: d3a8c02d-895b-478c-9957-d663130f308e
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugObject2::IsEncOutdated
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드가이 개체 또는 부모 컨테이너의 편집 하며 계속 하기 상태 최신 것인지 결정 합니다.  이 메서드 및 항상 반환 하는 사용자 지정 식 계산기를 구현 하지 않습니다 `E_NOTIMPL`.  
  
## 구문  
  
```cpp  
HRESULT IsEncOutdated(  
   BOOL* pfEncOutdated  
);  
```  
  
```c#  
int IsEncOutdated(  
   out int pfEncOutdated  
);  
```  
  
#### 매개 변수  
 `pfEncOutdated`  
 \[out\] 0이 아닌 \(`TRUE`\)는 편집 하며 계속 하기 상태를 오래 된 경우에 0 \(`FALSE`\) 되지 않은 경우입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
> [!NOTE]
>  사용자 지정 식 계산기를 항상 반환 해야 `E_NOTIMPL`.  
  
## 참고 항목  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)