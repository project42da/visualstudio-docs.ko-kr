---
title: "IDebugAlias::Dispose | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugAlias::Dispose"
helpviewer_keywords: 
  - "IDebugAlias::Dispose 메서드"
ms.assetid: e84909a4-d378-4f48-bf25-2c014c77c8e3
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# IDebugAlias::Dispose
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 제거에 대 한이 별칭을 표시합니다.  
  
## 구문  
  
```cpp  
HRESULT Dispose();  
```  
  
```c#  
int Dispose();  
```  
  
#### 매개 변수  
 없음  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드를 호출 하면 별칭은 더 이상 사용할 수 없습니다.  
  
## 참고 항목  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)