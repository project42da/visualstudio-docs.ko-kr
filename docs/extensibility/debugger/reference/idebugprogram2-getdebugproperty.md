---
title: "IDebugProgram2::GetDebugProperty | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgram2::GetDebugProperty"
helpviewer_keywords: 
  - "IDebugProgram2::GetDebugProperty"
ms.assetid: d194224e-f0e6-46ab-85d4-9e2639e28946
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugProgram2::GetDebugProperty
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로그램의 속성을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetDebugProperty(   
   IDebugProperty2** ppProperty  
);  
```  
  
```c#  
int GetDebugProperty(   
   out IDebugProperty2 ppProperty  
);  
```  
  
#### 매개 변수  
 `ppProperty`  
 \[out\] 반환 된 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 프로그램의 속성을 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드가 반환 하는 속성 프로그램에 따라 다릅니다.  프로그램이 두 개 이상의 속성을 반환 하는 경우 다음을 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 이 메서드에서 반환 된 개체는 컨테이너의 추가 속성 및 전화는 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) 메서드는 모든 속성의 목록을 반환 합니다.  
  
 프로그램이 모든 개수와 종류를 통해 설명할 수 있습니다 추가 속성을 노출 시킬 수 있습니다 해당 `IDebugProperty2` 인터페이스입니다.  IDE의 추가 프로그램 속성 일반 속성 브라우저 사용자 인터페이스를 통해 표시 됩니다.  
  
## 참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)