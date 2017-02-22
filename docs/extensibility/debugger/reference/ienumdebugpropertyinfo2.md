---
title: "IEnumDebugPropertyInfo2 | Microsoft Docs"
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
  - "IEnumDebugPropertyInfo2"
helpviewer_keywords: 
  - "IEnumDebugPropertyInfo2"
ms.assetid: fdea8262-40b8-473e-88ba-639e4c4648e6
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugPropertyInfo2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 열거 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 구조체입니다.  
  
## 구문  
  
```  
IEnumDebugPropertyInfo2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 특정 속성에 대 한 정보를 표현 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) 하위 특정 속성을이 인터페이스를 가져올 수 있습니다.  호출 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) 속성의 특정 스택 프레임을 나타내는이 인터페이스를 가져올 수 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IEnumDebugPropertyInfo2`.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-next.md)|지정 된 수의 검색 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 에서 열거 시퀀스 구조입니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-skip.md)|지정 된 개수의 생략 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 에서 열거 시퀀스 구조입니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md)|매핑되는 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 열거자에서 구조.|  
  
## 설명  
 일반적으로 속성 이름, 값, 주소 및 형식을 포함할 수 있는 정보 뿐 아니라 속성이 연결 된 개체 또는 스택 프레임에 적절 한 다른 정보는 계층 구조입니다.  자세한 내용은 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)을 참조하십시오.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [EnumProperties](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)