---
title: "JsRef Typedef | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6aafc39f-6b9c-457f-8bf0-48831bffe9b8
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# JsRef Typedef
Chakra 가비지 수집기가 소유한 개체에 대한 참조입니다.  
  
## 구문  
  
```  
typedef void *JsRef;  
```  
  
## 설명  
 Chakra 런타임은 JsRef 참조가 로컬 변수 또는 매개 변수에\(즉, 스택에\) 저장되어 있는 한 JsRef 참조를 자동으로  추적합니다.  JsRef를 스택 이외의 다른 위치에 저장하려면 JsAddRef 및 JsRelease를 호출하여 개체의 수명을 관리해야 하며, 그렇지 않으면 가비지 수집기가 개체가 여전히 사용 중인 동안 해당 개체를 해제할 수 있습니다.  
  
## 요구 사항  
 **헤더:** jsrt.h  
  
## 참고 항목  
 [참조\(JavaScript 런타임\)](../chakra-hosting/reference-javascript-runtime.md)