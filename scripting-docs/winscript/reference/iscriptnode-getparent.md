---
title: "IScriptNode::GetParent | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptNode.GetParent
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptNode::GetParent"
ms.assetid: 0fb813f6-ab94-46b2-b0cf-ef5d1cd38ae4
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IScriptNode::GetParent
반환 된 `IScriptNode` 개체의 부모 개체입니다.  
  
## 구문  
  
```  
HRESULT GetParent(  
   IScriptNode       **ppsnParent  
);  
```  
  
#### 매개 변수  
 `ppsnParent`  
 \[out\] 에 대 한 포인터를 받는 변수의 주소는 `IScriptNode` 부모 인스턴스의 인터페이스.  
  
 클래스를 구현 하는 경우 `IScriptEntry` 또는 `IScriptScriptlet`, `IScriptNode` 개체를 반환 합니다.  
  
 클래스를 구현 하는 경우 `IScriptNode` \(웹 페이지를 나타내는\), NULL이 반환 됩니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)