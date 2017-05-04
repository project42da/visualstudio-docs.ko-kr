---
title: "IDebugApplicationNode 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugApplicationNode 인터페이스"
ms.assetid: 30be3a97-8191-45ac-8706-3f7056c163d6
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugApplicationNode 인터페이스
`IDebugApplicationNode` 인터페이스 기능을 확장 하는 `IDebugDocumentProvider` 프로젝트 트리 내에 컨텍스트를 제공 하는 인터페이스.  
  
 `IDebugDocumentProvider`에서 상속되는 메서드 외에 `IDebugApplicationNode` 인터페이스는 다음 메서드를 노출합니다.  
  
## 메서드에서 Vtable 순서  
  
|메서드|설명|  
|---------|--------|  
|[IDebugApplicationNode::EnumChildren](../../winscript/reference/idebugapplicationnode-enumchildren.md)|이 응용 프로그램 노드의 자식 노드를 열거합니다.|  
|[IDebugApplicationNode::GetParent](../../winscript/reference/idebugapplicationnode-getparent.md)|이 응용 프로그램 노드의 부모 노드를 반환합니다.|  
|[IDebugApplicationNode::SetDocumentProvider](../../winscript/reference/idebugapplicationnode-setdocumentprovider.md)|이 응용 프로그램 노드를 문서 공급자를 설정합니다.|  
|[IDebugApplicationNode::Close](../../winscript/reference/idebugapplicationnode-close.md)|이 응용 프로그램에 대 한 모든 참조를 해제 하 고 비활성 상태가 됩니다.|  
|[IDebugApplicationNode::Attach](../../winscript/reference/idebugapplicationnode-attach.md)|이 응용 프로그램 노드 트리의 지정 된 프로젝트에 추가합니다.|  
|[IDebugApplicationNode::Detach](../../winscript/reference/idebugapplicationnode-detach.md)|이 응용 프로그램 노드를 프로젝트 트리에서 제거 합니다.|