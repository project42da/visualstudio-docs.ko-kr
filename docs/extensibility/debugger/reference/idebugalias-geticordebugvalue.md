---
title: "IDebugAlias::GetICorDebugValue | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugAlias::GetICorDebugValue"
helpviewer_keywords: 
  - "IDebugAlias::GetICorDebugValue 메서드"
ms.assetid: b9eb39ee-84af-4ace-9cfe-236b3d48aff5
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugAlias::GetICorDebugValue
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 별칭을 연관 된 값을 나타내는 관리 되는 코드 인터페이스를 검색 합니다.  
  
## 구문  
  
```cpp  
HRESULT GetICorDebugValue(  
   IUnknown** ppUnk  
);  
```  
  
```c#  
int GetICorDebugValue(  
   out object ppUnk  
);  
```  
  
#### 매개 변수  
 `ppUnk`  
 \[out\] `IUnknown` 이 별칭을 연관 된 값을 나타내는 인터페이스입니다. 이 인터페이스를 쿼리할 수는 `ICorDebugValue` 인터페이스입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않은 경우 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드는 관리 되는 값에만 적용 됩니다 \(의 `ICorDebugValue` 은 인터페이스에서 사용할 수 있는 [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] 에 정의 되어는 [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] SDK cordebug.idl 파일에서\).  
  
## 참고 항목  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)