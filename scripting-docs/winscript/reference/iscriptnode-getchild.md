---
title: "IScriptNode::GetChild | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptNode.GetChild
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptNode::GetChild"
ms.assetid: 8cb3f8b0-958b-40bb-a91a-49a788661861
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IScriptNode::GetChild
노드를 지정 된 인덱스에 있는 자식을 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetChild(  
   ULONG              isn,  
   IScriptNode        **ppsn  
);  
```  
  
#### 매개 변수  
 `isn`  
 \[in\] 부모에서 자식의 인덱스입니다.  
  
 `ppsn`  
 \[out\] 에 대 한 포인터를 받는 변수의 주소는 `IScriptNode` 인터페이스 인스턴스의 자식.  
  
 에 대 한 `IScriptNode` 웹 페이지를 나타내는 개체를이 매개 변수 스크립트 블록에 포함 된 개체를 반환 합니다.  
  
 에 대 한 `IScriptEntry` 스크립트 블록을 지정 하는 개체를이 매개 변수 함수를 지정 하는 개체를 반환 합니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 에 대 한 `IScriptEntry` 함수 개체를 지정 하는 개체와 `IScriptScriptlet` 개체에 자식 항목이 없습니다 때문에이 메서드는 실패 합니다.  
  
## 참고 항목  
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)