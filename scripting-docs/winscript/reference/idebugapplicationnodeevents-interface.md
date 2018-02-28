---
title: "IDebugApplicationNodeEvents 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNodeEvents interface
ms.assetid: 02e0bb17-84ce-458b-bae6-608a9899e535
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20d0fac68bb7cdb3d7f5cb6aac6b0ab67e373c84
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationnodeevents-interface"></a>IDebugApplicationNodeEvents 인터페이스
에 대 한 이벤트 인터페이스를 제공는 `IDebugApplicationNode` 인터페이스입니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IDebugApplicationNodeEvents` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugApplicationNodeEvents::onAddChild](../../winscript/reference/idebugapplicationnodeevents-onaddchild.md)|자식 노드가 디버그 응용 프로그램 노드 개체에 추가 될 때 이벤트를 처리 합니다.|  
|[IDebugApplicationNodeEvents::onRemoveChild](../../winscript/reference/idebugapplicationnodeevents-onremovechild.md)|자식 노드 디버그 응용 프로그램 노드 개체에서 제거 될 때 이벤트를 처리 합니다.|  
|[IDebugApplicationNodeEvents::onDetach](../../winscript/reference/idebugapplicationnodeevents-ondetach.md)|디버그 응용 프로그램 노드 개체 부모 노드에서 분리 된 이름임을 하는 이벤트를 처리 합니다.|  
|[IDebugApplicationNodeEvents::onAttach](../../winscript/reference/idebugapplicationnodeevents-onattach.md)|디버그 응용 프로그램 노드 개체 부모 노드에 연결 된 것을 나타내는 이벤트를 처리 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplicationNode 인터페이스](../../winscript/reference/idebugapplicationnode-interface.md)