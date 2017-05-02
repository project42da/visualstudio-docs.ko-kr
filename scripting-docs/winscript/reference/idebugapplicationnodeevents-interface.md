---
title: "IDebugApplicationNodeEvents 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugApplicationNodeEvents 인터페이스"
ms.assetid: 02e0bb17-84ce-458b-bae6-608a9899e535
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplicationNodeEvents 인터페이스
이벤트 인터페이스에 대 한 제공 된 `IDebugApplicationNode` 인터페이스.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugApplicationNodeEvents` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugApplicationNodeEvents::onAddChild](../../winscript/reference/idebugapplicationnodeevents-onaddchild.md)|디버그 응용 프로그램 노드 개체에 자식 노드를 추가할 때 이벤트를 처리 합니다.|  
|[IDebugApplicationNodeEvents::onRemoveChild](../../winscript/reference/idebugapplicationnodeevents-onremovechild.md)|디버그 응용 프로그램 노드 개체에서 자식 노드를 제거 하면 이벤트를 처리 합니다.|  
|[IDebugApplicationNodeEvents::onDetach](../../winscript/reference/idebugapplicationnodeevents-ondetach.md)|디버그 응용 프로그램 노드 개체에서 부모 노드를 분리 된 것을 나타내는 이벤트를 처리 합니다.|  
|[IDebugApplicationNodeEvents::onAttach](../../winscript/reference/idebugapplicationnodeevents-onattach.md)|디버그 응용 프로그램 노드 개체를 부모 노드에 연결 된 것을 나타내는 이벤트를 처리 합니다.|  
  
## 참고 항목  
 [IDebugApplicationNode 인터페이스](../../winscript/reference/idebugapplicationnode-interface.md)