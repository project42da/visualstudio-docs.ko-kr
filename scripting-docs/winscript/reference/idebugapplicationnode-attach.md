---
title: "IDebugApplicationNode::Attach | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplicationNode.Attach
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplicationNode::Attach"
ms.assetid: f4aad4ae-5bb0-4b5e-8f70-912a677f8f7a
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplicationNode::Attach
이 응용 프로그램 노드 트리의 지정 된 프로젝트에 추가합니다.  
  
## 구문  
  
```  
HRESULT Attach(  
   IDebugApplicationNode*  pdanParent  
);  
```  
  
#### 매개 변수  
 `pdanParent`  
 \[in\] 이 응용 프로그램 노드를 추가할 수 있는 프로젝트 트리.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 프로젝트에이 응용 프로그램 노드를 추가 트리를 사용 하 여 `pdanParent` 는 부모.  경우 `pdanParent` 는 `NULL`,이 응용 프로그램 노드는 최상위 노드가 됩니다.  
  
## 참고 항목  
 [IDebugApplicationNode::Detach](../../winscript/reference/idebugapplicationnode-detach.md)   
 [IDebugApplicationNode 인터페이스](../../winscript/reference/idebugapplicationnode-interface.md)