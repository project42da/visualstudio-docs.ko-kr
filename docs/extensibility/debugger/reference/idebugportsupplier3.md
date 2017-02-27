---
title: "IDebugPortSupplier3 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortSupplier3"
helpviewer_keywords: 
  - "IDebugPortSupplier3 인터페이스"
ms.assetid: e458cd02-2370-4435-8953-17d7a60ce152
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugPortSupplier3
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 포트 공급자 디버거가 호출 사이 \(해당 디스크에 기록 하 여\) 포트를 유지 하 고 다음 해당 보존된 포트 목록을 확인 여부를 결정 하는 호출자가 있습니다.  
  
## 구문  
  
```  
IDebugPortSupplier3 : IDebugPortSupplier2  
```  
  
## 구현자 참고 사항  
 사용자 지정 포트 공급자 지속 또는 포트 정보를 디스크에 저장을 지원 하기 위해이 인터페이스를 구현 합니다.  동일한 개체에서이 인터페이스를 구현 해야 합니다는 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 있는 `IDebugPortSupplier2` 이 인터페이스를 가져올 수 있는 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 상속 된 메서드 외에 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md) 다음 인터페이스,이 인터페이스를 지 원하는.  
  
|메서드|설명|  
|---------|--------|  
|[CanPersistPorts](../../../extensibility/debugger/reference/idebugportsupplier3-canpersistports.md)|포트 공급자 포트 \(해당 디스크에 기록 하 여\) 디버거가 호출 사이 지속 될 수 있는지 여부를 반환 합니다.|  
|[EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md)|열거 하는이 포트 공급자에 의해 디스크에 기록 된 모든 포트를 사용할 수 있는 개체를 반환 합니다.|  
  
## 설명  
 포트 공급자 포트 호출 간에 유지 될 수 있는 경우이 인터페이스를 구현 해야 합니다.  포트 공급자를 인스턴스화하고 포트 공급자 소멸 될 때 디스크에 기록 되는 경우 포트를 로드 합니다.  
  
 디버그 엔진은 일반적으로 포트 협력 업체와 상호 작용 하지 않습니다 및이 인터페이스를 사용 해야 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)