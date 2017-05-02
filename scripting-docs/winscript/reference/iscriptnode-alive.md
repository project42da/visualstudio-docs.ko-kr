---
title: "IScriptNode::Alive | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptNode.Alive
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptNode::Alive"
ms.assetid: d2755c83-e9b9-4c0a-acb7-25b554fc9fe8
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# IScriptNode::Alive
개체가 여전히 활성화 되어 있는지 여부를 나타냅니다.  
  
## 구문  
  
```  
HRESULT Alive();  
```  
  
#### 매개 변수  
 매개 변수 없이 메서드를 사용 합니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|스크립트 노드를 여전히 활성 상태입니다.|  
  
## 설명  
 개체가 활성화 되어 있지 않으면 구성 요소 개체 모델 \(COM\) 마샬링 프록시가 메서드 호출에 대해 오류가 반환 합니다.  
  
## 참고 항목  
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)