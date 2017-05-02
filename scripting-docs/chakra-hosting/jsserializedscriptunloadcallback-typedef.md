---
title: "JsSerializedScriptUnloadCallback typedef | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8d18c392-cca0-411e-9f2b-0d788b16161a
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# JsSerializedScriptUnloadCallback typedef
스크립트 실행과 관련된 모든 리소스를 완료하면 런타임에서 호출됩니다. 이때 바이트 코드, 컨텍스트 등 소스가 로드되면 호출자는 소스를 해제해야 합니다.  
  
## 구문  
  
```  
 typedef void (CALLBACK * JsSerializedScriptUnloadCallback)(  
  _In_ JsSourceContext sourceContext  
);  
```  
  
#### 매개 변수  
 `sourceContext`  
 `JsParseSerializedScriptWithCallback` 또는 `JsRunSerializedScriptWithCallback`에 전달된 컨텍스트입니다.  
  
## 설명  
  
> [!WARNING]
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)