---
title: "IDebugApplicationNode::GetParent | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplicationNode.GetParent
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplicationNode::GetParent"
ms.assetid: 88ba3a53-0cd7-4e1f-8558-79c20ac76cc9
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplicationNode::GetParent
이 응용 프로그램 노드의 부모 노드를 반환합니다.  
  
## 구문  
  
```  
HRESULT GetParent(  
   IDebugApplicationNode**  pprddp  
);  
```  
  
#### 매개 변수  
 `pprddp`  
 \[out\] 응용 프로그램 노드의 부모 노드를이 응용 프로그램입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 노드의 부모 노드를이 응용 프로그램을 반환합니다.  
  
## 참고 항목  
 [IDebugApplicationNode 인터페이스](../../winscript/reference/idebugapplicationnode-interface.md)