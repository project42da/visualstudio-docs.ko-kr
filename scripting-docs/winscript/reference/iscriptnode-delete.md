---
title: "IScriptNode::Delete | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptNode.Delete
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptNode::Delete"
ms.assetid: 6765ff80-a9a8-40a3-a669-7fcc284c87af
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IScriptNode::Delete
이 개체 트리를 삭제합니다.  
  
## 구문  
  
```  
HRESULT Delete();  
```  
  
#### 매개 변수  
 매개 변수 없이 메서드를 사용 합니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 후에 `Delete` 메서드 호출의 [IScriptNode::Alive](../../winscript/reference/iscriptnode-alive.md) 해야 방법을 나타내는 스크립트 노드 활성화 되어 있지 않습니다.  
  
## 참고 항목  
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)