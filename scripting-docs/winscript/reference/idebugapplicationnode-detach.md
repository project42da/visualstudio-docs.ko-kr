---
title: "IDebugApplicationNode::Detach | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplicationNode.Detach
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplicationNode::Detach"
ms.assetid: 36bb3e54-a4df-48d5-a6de-3b8d4c0e98a8
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplicationNode::Detach
이 응용 프로그램 노드를 프로젝트 트리에서 제거 합니다.  
  
## 구문  
  
```  
HRESULT Detach();  
```  
  
#### 매개 변수  
 이 메서드는 매개 변수를 사용하지 않습니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 프로젝트 트리에서이 응용 프로그램 노드를 제거합니다.  
  
## 참고 항목  
 [IDebugApplicationNode::Attach](../../winscript/reference/idebugapplicationnode-attach.md)   
 [IDebugApplicationNode 인터페이스](../../winscript/reference/idebugapplicationnode-interface.md)