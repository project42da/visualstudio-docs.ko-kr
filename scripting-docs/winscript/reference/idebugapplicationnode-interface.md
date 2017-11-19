---
title: "IDebugApplicationNode 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IDebugApplicationNode interface
ms.assetid: 30be3a97-8191-45ac-8706-3f7056c163d6
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 110e04d1c990f1b22f9740d8118a47f485dd041e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationnode-interface"></a>IDebugApplicationNode 인터페이스
`IDebugApplicationNode` 의 기능을 확장 하는 인터페이스는 `IDebugDocumentProvider` 프로젝트 트리 내에서 컨텍스트를 제공 하 여 인터페이스입니다.  
  
 상속 된 메서드 외에도 `IDebugDocumentProvider`, `IDebugApplicationNode` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugApplicationNode::EnumChildren](../../winscript/reference/idebugapplicationnode-enumchildren.md)|이 응용 프로그램 노드의 자식 노드를 열거합니다.|  
|[IDebugApplicationNode::GetParent](../../winscript/reference/idebugapplicationnode-getparent.md)|이 응용 프로그램 노드의 부모 노드를 반환합니다.|  
|[IDebugApplicationNode::SetDocumentProvider](../../winscript/reference/idebugapplicationnode-setdocumentprovider.md)|이 응용 프로그램 노드에 대 한 문서 공급자를 설정합니다.|  
|[IDebugApplicationNode::Close](../../winscript/reference/idebugapplicationnode-close.md)|이 응용 프로그램을 모든 참조를 해제 하 고 비활성 상태를 입력 하면 됩니다.|  
|[IDebugApplicationNode::Attach](../../winscript/reference/idebugapplicationnode-attach.md)|지정 된 프로젝트 트리를이 응용 프로그램 노드를 추가합니다.|  
|[IDebugApplicationNode::Detach](../../winscript/reference/idebugapplicationnode-detach.md)|프로젝트 트리에서이 응용 프로그램 노드를 제거합니다.|