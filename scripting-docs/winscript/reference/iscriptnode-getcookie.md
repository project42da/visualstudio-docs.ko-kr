---
title: "IScriptNode::GetCookie | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptNode.GetCookie
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptNode::GetCookie"
ms.assetid: 007339c6-a73a-4147-b3c0-cc041e467ecd
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# IScriptNode::GetCookie
스크립트릿은 호스트 개체에 연결 하는 데 사용 되는 응용 프로그램 정의 값을 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetCookie(  
   DWORD              *pdwCookie  
);  
```  
  
#### 매개 변수  
 `pdwCookie`  
 \[out\] 에 `IScriptEntry` 개체, 응용 프로그램 정의 쿠키 값을 반환 합니다.  
  
 에 `IScriptNode` 개체는 웹 페이지를 나타내는 0을 반환 합니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)