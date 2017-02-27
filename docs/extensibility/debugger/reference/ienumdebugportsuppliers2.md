---
title: "IEnumDebugPortSuppliers2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugPortSuppliers2"
helpviewer_keywords: 
  - "IEnumDebugPortSuppliers2"
ms.assetid: cd0a73dc-dd25-46fd-8c4f-5b011501afeb
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IEnumDebugPortSuppliers2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 포트 공급자 열거합니다.  
  
## 구문  
  
```  
IEnumDebugPortSuppliers2 : IUnknown  
```  
  
## 구현자 참고 사항  
 Visual Studio 포트 공급 업체 목록을 표시 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md) 포트 공급자 목록을 얻을 수 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IEnumDebugPortSuppliers2`.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-next.md)|포트 공급자 열거 시퀀스에서 지정 된 시간을 검색합니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-skip.md)|포트 공급자 열거 시퀀스에서 지정 된 수를 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-getcount.md)|포트 공급자의 수를의 열거자를 가져옵니다.|  
  
## 설명  
 일반적으로 디버그 엔진은이 인터페이스를 얻이 필요가 없습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md)