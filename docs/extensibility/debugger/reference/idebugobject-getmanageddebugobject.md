---
title: "IDebugObject::GetManagedDebugObject | Microsoft Docs"
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
  - "IDebugObject::GetManagedDebugObject"
helpviewer_keywords: 
  - "IDebugObject::GetManagedDebugObject 메서드"
ms.assetid: cb89692e-7657-47ff-846d-311943521951
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugObject::GetManagedDebugObject
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진의 주소 공간에서 관리 되는 개체의 복사본을 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT GetManagedDebugObject(   
   IDebugManagedObject** ppObject  
);  
```  
  
```c#  
int GetManagedDebugObject(  
   out IDebugManagedObject ppObject  
);  
```  
  
#### 매개 변수  
 `ppObject`  
 \[out\] 반환 된 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md) 새로 만든된 관리 되는 개체를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  이 경우 E\_FAIL 반환 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 는 관리 되는 값 클래스 인스턴스를 표시 하지 않습니다.  
  
## 설명  
 이 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 개체는 같은 관리 되는 값 클래스 인스턴스를 나타낼 합니다는 `System.Decimal` 인스턴스.  로컬 복사본, 호출의 오버 헤드를 배치 하 여 [평가](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) 제거 됩니다.  
  
## 참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)