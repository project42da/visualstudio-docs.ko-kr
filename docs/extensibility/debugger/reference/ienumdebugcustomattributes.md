---
title: "IEnumDebugCustomAttributes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumCustomAttributes"
helpviewer_keywords: 
  - "IEnumDebugCustomAttributes 인터페이스"
ms.assetid: 11aa768d-1852-44d6-9de3-17f9bafaded2
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# IEnumDebugCustomAttributes
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용자 지정 특성을 열거합니다.  
  
## 구문  
  
```  
IEnumCustomAttributes : IUnknown  
```  
  
## 구현자 참고 사항  
 기호 공급자 사용자 지정 특성을 지원 하기 위해이 인터페이스를 구현 합니다. \(\-는 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md) 인터페이스\)입니다.  
  
## 호출자에 대 한 참고 사항  
 [EnumCustomAttributes](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md)이 인터페이스를 반환합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IEnumDebugCustomAttributes`.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugcustomattributes-next.md)|사용자 지정 특성은 열거 시퀀스에서 지정 된 시간을 검색합니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugcustomattributes-skip.md)|사용자 지정 특성은 열거 시퀀스에서 지정한 개수의 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugcustomattributes-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugcustomattributes-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugcustomattributes-getcount.md)|사용자 지정 특성의 수를의 열거자를 가져옵니다.|  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [EnumCustomAttributes](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md)   
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)