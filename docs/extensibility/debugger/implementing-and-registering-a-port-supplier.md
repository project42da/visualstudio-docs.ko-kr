---
title: "구현 하 고 포트 공급자를 등록 하는 중 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK], 포트 공급자를 등록 합니다."
  - "포트 공급 업체, 등록"
ms.assetid: fb057052-ee16-4272-8e16-a4da5dda0ad4
caps.latest.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 17
---
# 구현 하 고 포트 공급자를 등록 하는 중
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

포트 공급자의 역할을 추적 하 고 차례로 프로세스를 관리 하는 포트입니다.  포트를 만들어야 할 때 CoCreate \(세션 디버그 관리자 \[SDM\] 프로젝트 시스템에서 지정 된 포트 공급자 또는 사용자가 선택한 포트 공급자 사용 합니다\) 포트 공급자의 GUID를 사용 하 여 포트 공급자를 인스턴스화합니다.  SDM을 호출 하 고 [CanAddPort](../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md) 포트를 추가할 수 있는 경우를 볼 수 있습니다.  포트를 추가할 수 있는 경우 새 포트를 호출 하 여 요청 된 [포트 추가](../../extensibility/debugger/reference/idebugportsupplier2-addport.md) 를 전달 하는 [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) 의 포트에 설명 합니다.  `AddPort`표시 되는 새 포트를 반환 합니다는 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) 인터페이스입니다.  
  
## 토론  
 포트를 컴퓨터 또는 디버그 서버에 연결 된 포트 공급자를 만듭니다.  포트 공급자를 통해 서버를 열거할 수는[EnumPortSuppliers](../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md) 메서드 및 포트 공급자의 포트를 통해 열거할 수 있습니다의 [EnumPorts](../../extensibility/debugger/reference/idebugportsupplier2-enumports.md) 메서드.  
  
 일반 COM 등록 이외에 포트 공급자 자체를 Visual Studio 해당 CLSID와 이름을 특정 레지스트리 위치에 배치 하 여 등록 해야 합니다.  SDK 디버깅 도우미 함수를 호출 합니다. `SetMetric` 이 자동 처리:이 등록할 수 있으므로 각 항목에 대해 한 번씩 호출 됩니다.  
  
```cpp#  
SetMetric(metrictypePortSupplier,  
          <GUID of your port supplier>,  
          metricCLSID,  
          <CLSID of your port supplier>,  
          false,  
          NULL)  
SetMetric(metrictypePortSupplier,  
          <GUID of your port supplier>,  
          metricName,  
          <name of your port supplier>,  
          false,  
          NULL);  
```  
  
 포트 공급자 자체를 호출 하 여 등록 취소 `RemoveMetric` \(다른 SDK 디버깅 도우미 함수\)에 등록 되어 있으므로 각 항목에 대해 한 번씩.  
  
```cpp#  
RemoveMetric(metrictypePortSupplier,  
             <GUID of your port supplier>,  
             metricCLSID,  
             NULL);  
RemoveMetric(metrictypePortSupplier,  
             <GUID of your port supplier>,  
             metricName,  
             NULL);  
```  
  
> [!NOTE]
>  [디버깅을 위한 SDK 도우미](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) `SetMetric` 및 `RemoveMetric` dbgmetric.h에서 정의 되 고 ad2de.lib로 컴파일된 정적 함수입니다.  `metrictypePortSupplier`, `metricCLSID`, 및 `metricName` 도우미도 dbgmetric.h에서 정의 됩니다.  
  
 포트 공급자의 이름과 GUID 메서드를 통해 제공할 수 있습니다 [GetPortSupplierName](../../extensibility/debugger/reference/idebugportsupplier2-getportsuppliername.md) 및 [GetPortSupplierId](../../extensibility/debugger/reference/idebugportsupplier2-getportsupplierid.md), 각각.  
  
## 참고 항목  
 [포트 공급자 구현](../../extensibility/debugger/implementing-a-port-supplier.md)   
 [디버깅을 위한 SDK 도우미](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [포트 공급자](../../extensibility/debugger/port-suppliers.md)