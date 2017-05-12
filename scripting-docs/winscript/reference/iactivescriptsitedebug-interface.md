---
title: "IActiveScriptSiteDebug 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptSiteDebug 인터페이스"
ms.assetid: 2557ee09-688b-4c03-a821-180c24dfa0e6
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptSiteDebug 인터페이스
스마트 호스트를 구현 하는 `IActiveScriptSiteDebug` 인터페이스 문서 관리를 수행 하 고 디버깅에 참여 합니다.  `IActiveScriptSite` 개체는 일반적으로 구현 하는 제공 된 `IActiveScriptSiteDebug` 인터페이스.  이 경우 호출의 `IActiveScriptSite::QueryInterface` 얻으려면 메서드는 `IActiveScriptSiteDebug` 인터페이스.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IActiveScriptSiteDebug` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IActiveScriptSiteDebug::GetDocumentContextFromPosition](../../winscript/reference/iactivescriptsitedebug-getdocumentcontextfromposition.md)|언어 엔진에서 위임 사용 `IDebugCodeContext::GetSourceContext`.|  
|[IActiveScriptSiteDebug::GetApplication](../../winscript/reference/iactivescriptsitedebug-getapplication.md)|이 스크립트 사이트와 연관 된 디버그 응용 프로그램 개체를 반환 합니다.|  
|[IActiveScriptSiteDebug::GetRootApplicationNode](../../winscript/reference/iactivescriptsitedebug-getrootapplicationnode.md)|문서에서 어떤 스크립트를 추가 해야 응용 프로그램 노드를 가져옵니다.|  
|[IActiveScriptSiteDebug::OnScriptErrorDebug](../../winscript/reference/iactivescriptsitedebug-onscripterrordebug.md)|스마트 호스트를 런타임 오류를 처리 하는 방법을 결정할 수 있습니다.|