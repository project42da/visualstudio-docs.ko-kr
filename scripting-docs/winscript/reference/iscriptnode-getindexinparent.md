---
title: "IScriptNode::GetIndexInParent | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptNode.GetIndexInParent
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptNode::GetIndexInParent"
ms.assetid: 521c1ca1-2d27-4344-bf3b-d8b53132b648
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IScriptNode::GetIndexInParent
부모의 자식 목록에서 개체의 인덱스를 반환합니다.  
  
## 구문  
  
```  
HRESULT GetIndexInParent(  
   ULONG              pisn,  
);  
```  
  
#### 매개 변수  
 `pisn`  
 \[out\] 부모의 자식 목록에서 개체의 인덱스를 반환합니다.  
  
 이 메서드를 호출 하는 경우는 `IScriptNode` 개체 웹 페이지를 나타내는 0이 매개이 변수를 반환 합니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)