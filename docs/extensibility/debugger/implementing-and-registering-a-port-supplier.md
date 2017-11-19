---
title: "구현 하 고 포트 공급자를 등록 하는 중 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], registering port suppliers
- port suppliers, registering
ms.assetid: fb057052-ee16-4272-8e16-a4da5dda0ad4
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fa7378493c8df41b70be6fda17b2763f90fd7f04
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="implementing-and-registering-a-port-supplier"></a>구현 하 고 포트 공급자를 등록 하는 중
추적 하 고 차례로 프로세스를 관리 하는 포트를 제공 합니다. 포트 공급자의 역할이입니다. 포트를 만들어야 하는 시간에 (세션 디버그 관리자 [SDM] 포트 공급자는 사용자가 선택한 또는 프로젝트 시스템에서 지정 된 포트 공급자를 사용 합니다.) 포트 공급 업체의 GUID를 가진 CoCreate를 사용 하 여 포트 공급자는 인스턴스화됩니다. 그런 다음은 SDM이 호출 [CanAddPort](../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md) 모든 포트를 추가할 수 있는지 확인 하려면. 새 포트를 호출 하 여 요청 된 포트를 추가할 수 있으면 [포트 추가](../../extensibility/debugger/reference/idebugportsupplier2-addport.md) 전달 하는 [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) 포트를 설명 하는 합니다. `AddPort`나타내는 새 포트는 반환 된 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) 인터페이스입니다.  
  
## <a name="discussion"></a>토론  
 포트를 컴퓨터 또는 디버그 서버와 다시 연결 되는 포트 공급자를 통해 생성 됩니다. 서버를 통해 그 포트 공급자를 열거할 수는[EnumPortSuppliers](../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md) 메서드와 포트 공급자를 통해 해당 포트를 열거할 수는 [EnumPorts](../../extensibility/debugger/reference/idebugportsupplier2-enumports.md) 메서드.  
  
 일반적인 COM 등록 뿐만 아니라 포트 공급자 등록 해야 자체 Visual Studio와 함께 특정 레지스트리 위치에서 이름과 CLSID를 배치 하 여 합니다. Debugging SDK 도우미 함수가 호출 `SetMetric` 이 작업을 처리: 따라서 등록할 수 있도록 각 항목에 대해 한 번씩 호출 됩니다.  
  
```cpp  
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
  
 포트 공급자를 호출 하 여 자체를 등록 취소 `RemoveMetric` (또 다른 Debugging SDK 도우미 함수가) 되므로 등록 된 각 항목에 대해 한 번씩:  
  
```cpp  
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
>  [디버깅할 수 있도록 SDK 도우미](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) `SetMetric` 및 `RemoveMetric` 는 정적 함수 dbgmetric.h에서 정의 되었고 ad2de.lib로 컴파일됩니다. `metrictypePortSupplier`, `metricCLSID`, 및 `metricName` 도우미 dbgmetric.h에서 정의 됩니다.  
  
 포트 공급자 메서드를 통해 해당 이름 및 GUID를 제공할 수 [GetPortSupplierName](../../extensibility/debugger/reference/idebugportsupplier2-getportsuppliername.md) 및 [GetPortSupplierId](../../extensibility/debugger/reference/idebugportsupplier2-getportsupplierid.md)각각.  
  
## <a name="see-also"></a>참고 항목  
 [포트 공급자 구현](../../extensibility/debugger/implementing-a-port-supplier.md)   
 [디버깅을 위한 도우미 SDK](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [포트 공급자](../../extensibility/debugger/port-suppliers.md)