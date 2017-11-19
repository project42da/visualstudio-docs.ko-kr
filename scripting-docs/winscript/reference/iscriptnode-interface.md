---
title: "IScriptNode 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IScriptNode interface
ms.assetid: cfa76c4a-6543-48e8-a946-d212cd0bf934
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 788be3fe9cb5ba529e3d1ca653d4f0f5c35b5932
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iscriptnode-interface"></a>IScriptNode 인터페이스
구현 하는 개체는 `IScriptNode` 인터페이스 웹 페이지를 나타냅니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IScriptNode` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IScriptNode::Alive](../../winscript/reference/iscriptnode-alive.md)|개체가 여전히 활성 상태 인지를 나타냅니다.|  
|[IScriptNode:: CreateChildEntry](../../winscript/reference/iscriptnode-createchildentry.md)|자식 인스턴스 추가 `IScriptEntry`합니다.|  
|[IScriptNode::CreateChildHandler](../../winscript/reference/iscriptnode-createchildhandler.md)|자식 인스턴스로 스크립틀릿 추가 `IScriptNode`합니다.|  
|[IScriptNode::Delete](../../winscript/reference/iscriptnode-delete.md)|개체 트리를 삭제합니다.|  
|[IScriptNode::GetChild](../../winscript/reference/iscriptnode-getchild.md)|노드에 지정 된 인덱스에 있는 자식 항목을 반환 합니다.|  
|[IScriptNode::GetCookie](../../winscript/reference/iscriptnode-getcookie.md)|호스트 개체와는 스크립틀릿을 연결 하는 데 사용 되는 응용 프로그램 정의 값을 반환 합니다.|  
|[IScriptNode::GetIndexInParent](../../winscript/reference/iscriptnode-getindexinparent.md)|부모의 자식 목록에 있는 개체의 인덱스를 반환합니다.|  
|[IScriptNode::GetLanguage](../../winscript/reference/iscriptnode-getlanguage.md)|현재 스크립트 노드에서 사용 하는 스크립트 언어를 반환 합니다.|  
|[IScriptNode::GetNumberOfChildren](../../winscript/reference/iscriptnode-getnumberofchildren.md)|자식 노드 수를 반환 된 `IScriptNode` 개체입니다.|  
|[IScriptNode::GetParent](../../winscript/reference/iscriptnode-getparent.md)|반환 된 `IScriptNode` 개체의 부모인 개체입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 작성 인터페이스](../../winscript/reference/active-script-authoring-interfaces.md)