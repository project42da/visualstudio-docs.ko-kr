---
title: "IScriptNode 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IScriptNode 인터페이스"
ms.assetid: cfa76c4a-6543-48e8-a946-d212cd0bf934
caps.latest.revision: 21
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 21
---
# IScriptNode 인터페이스
구현 하는 개체는 `IScriptNode` 인터페이스 웹 페이지를 나타냅니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IScriptNode` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IScriptNode::Alive](../../winscript/reference/iscriptnode-alive.md)|개체가 여전히 활성화 되어 있는지 여부를 나타냅니다.|  
|[IScriptNode:: CreateChildEntry](../../winscript/reference/iscriptnode-createchildentry.md)|자식 인스턴스를 추가 `IScriptEntry`.|  
|[IScriptNode::CreateChildHandler](../../winscript/reference/iscriptnode-createchildhandler.md)|스크립트릿으로 자식 인스턴스를 추가 된 `IScriptNode`.|  
|[IScriptNode::Delete](../../winscript/reference/iscriptnode-delete.md)|개체 트리를 삭제합니다.|  
|[IScriptNode::GetChild](../../winscript/reference/iscriptnode-getchild.md)|노드를 지정 된 인덱스에 있는 자식을 반환 합니다.|  
|[IScriptNode::GetCookie](../../winscript/reference/iscriptnode-getcookie.md)|스크립트릿은 호스트 개체에 연결 하는 데 사용 되는 응용 프로그램 정의 값을 반환 합니다.|  
|[IScriptNode::GetIndexInParent](../../winscript/reference/iscriptnode-getindexinparent.md)|부모의 자식 목록에서 개체의 인덱스를 반환합니다.|  
|[IScriptNode::GetLanguage](../../winscript/reference/iscriptnode-getlanguage.md)|스크립트 노드에서 현재 사용 되는 스크립트 언어를 반환 합니다.|  
|[IScriptNode::GetNumberOfChildren](../../winscript/reference/iscriptnode-getnumberofchildren.md)|자식 노드 수를 반환 된 `IScriptNode` 개체입니다.|  
|[IScriptNode::GetParent](../../winscript/reference/iscriptnode-getparent.md)|반환 된 `IScriptNode` 개체의 부모 개체입니다.|  
  
## 참고 항목  
 [액티브 스크립트 작성 인터페이스](../../winscript/reference/active-script-authoring-interfaces.md)