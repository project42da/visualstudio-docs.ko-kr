---
title: "IActiveScriptErrorDebug 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptErrorDebug 인터페이스"
ms.assetid: e5d50427-c033-4138-ac6e-3b2dfb3b750a
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptErrorDebug 인터페이스
컴파일 타임 오류 및 런타임 예외에 대 한 문서 컨텍스트 정보를 제공합니다.  `IActiveScriptError::QueryInterface` 지원 메서드는 `IActiveScriptErrorDebug` 인터페이스.  
  
 `IActiveScriptError`에서 상속되는 메서드 외에 `IActiveScriptErrorDebug` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IActiveScriptErrorDebug::GetDocumentContext](../../winscript/reference/iactivescripterrordebug-getdocumentcontext.md)|이 오류에 대 한 문서 컨텍스트를 제공합니다.|  
|[IActiveScriptErrorDebug::GetStackFrame](../../winscript/reference/iactivescripterrordebug-getstackframe.md)|런타임 오류에 대해 적용 되는 스택 프레임을 제공 합니다.|