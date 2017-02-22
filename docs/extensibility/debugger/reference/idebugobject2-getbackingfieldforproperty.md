---
title: "IDebugObject2::GetBackingFieldForProperty | Microsoft Docs"
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
  - "IDebugObject2::GetBackingFieldForProperty"
helpviewer_keywords: 
  - "IDebugObject2::GetBackingFieldForProperty 메서드"
ms.assetid: e72c6338-5573-4fad-8075-f3ade3435424
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugObject2::GetBackingFieldForProperty
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

필드 또는 변수 \(있는 경우\)를 가져옵니다는 있습니다 수 백업이 개체가 나타내는 속성입니다.  
  
## 구문  
  
```cpp  
HRESULT GetBackingFieldForProperty(  
   IDebugObject2** ppObject  
);  
```  
  
```c#  
int GetBackingFieldForProperty(  
   out IDebugObject2 ppObject  
);  
```  
  
#### 매개 변수  
 `ppObject`  
 \[out\] [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) 지원 필드를 설명 하는 개체입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) 를 나타내는 관리 되는 코드 클래스 속성은 get 사용 하 여 메서드, 개체 및\/또는 접근자를 설정 합니다.  이러한 속성은 일반적으로 속성으로 조작할 값을 포함할 변수가 필요 합니다.  이 변수는 지원 필드 이름으로 알려져 있습니다.  개체에 대 한 지원 필드가 있을 경우, null 값을 반환 하는 것이 있는지를 확인 하십시오: 일부 호출자가 반환 값에 대 한 관심을 지불 하지 않지만 대신에 null 값이 반환 된 경우 확인 합니다 `ppObject`.  
  
## 참고 항목  
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)