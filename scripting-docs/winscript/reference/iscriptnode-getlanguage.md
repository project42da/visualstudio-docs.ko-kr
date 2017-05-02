---
title: "IScriptNode::GetLanguage | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptNode.GetLanguage
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptNode::GetLanguage"
ms.assetid: 089715fd-6746-474e-94ed-2e57ee4bc0da
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# IScriptNode::GetLanguage
스크립트 노드에서 현재 사용 되는 스크립트 언어를 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetLanguage(  
   BSTR               *pbstr  
);  
```  
  
#### 매개 변수  
 `pbstr`  
 \[out\] 스크립트 노드 Visual Basic Scripting Edition \(VBScript\) 스크립트 노드를 사용 하는 경우 "VBScript" 또는 JScript를 사용 하는 경우 "JScript"를 반환 합니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)