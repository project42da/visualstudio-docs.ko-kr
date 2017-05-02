---
title: "IActiveScriptDebug 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptDebug 인터페이스"
ms.assetid: e3e28cba-ee08-4a52-973a-b74be488c348
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptDebug 인터페이스
스크립트 엔진은 디버깅 지원 구현.  일반적으로 구현 하는 개체는 `IActiveScriptDebug` 도 구현할 인터페이스는 `IActiveScript` 인터페이스.  이 경우 호출의 `IActiveScript::QueryInterface` 얻으려면 메서드는 `IActiveScriptDebug` 인터페이스.  
  
 `IActiveScriptDebug` 인터페이스는 수단을 제공 합니다.  
  
-   스마트 호스트를 관리를 문서화 합니다.  
  
-   여러 스크립트 엔진의 디버깅 동기화 프로세스 디버그 관리자.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IActiveScriptDebug` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IActiveScriptDebug::GetScriptTextAttributes](../../winscript/reference/iactivescriptdebug-getscripttextattributes.md)|임의의 스크립트 텍스트 블록에 대 한 텍스트 특성을 반환합니다.|  
|[IActiveScriptDebug::GetScriptletTextAttributes](../../winscript/reference/iactivescriptdebug-getscriptlettextattributes.md)|임의의 스크립트릿에 대 한 텍스트 특성을 반환합니다.|  
|[IActiveScriptDebug::EnumCodeContextsOfPosition](../../winscript/reference/iactivescriptdebug-enumcodecontextsofposition.md)|위임 `IDebugDocumentContext::EnumCodeContexts`.|