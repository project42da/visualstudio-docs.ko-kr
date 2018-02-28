---
title: "IActiveScriptSiteDebug 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IActiveScriptSiteDebug interface
ms.assetid: 2557ee09-688b-4c03-a821-180c24dfa0e6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b9b36054deeceb0528fb7ea399cc41d8edbbb47e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsitedebug-interface"></a>IActiveScriptSiteDebug 인터페이스
스마트 호스트를 구현 하는 `IActiveScriptSiteDebug` 문서 관리를 수행 하 고 디버깅에 참여 하는 인터페이스입니다. `IActiveScriptSite` 개체는 일반적으로의 구현을 제공는 `IActiveScriptSiteDebug` 인터페이스입니다. 이 도구를 실행 하는 경우 호출 된 `IActiveScriptSite::QueryInterface` 를 얻는 메서드를는 `IActiveScriptSiteDebug` 인터페이스입니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IActiveScriptSiteDebug` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptSiteDebug::GetDocumentContextFromPosition](../../winscript/reference/iactivescriptsitedebug-getdocumentcontextfromposition.md)|위임 하는 언어 엔진에서 사용 하는 `IDebugCodeContext::GetSourceContext`합니다.|  
|[IActiveScriptSiteDebug::GetApplication](../../winscript/reference/iactivescriptsitedebug-getapplication.md)|이 스크립트 사이트와 연결 된 디버그 응용 프로그램 개체를 반환 합니다.|  
|[IActiveScriptSiteDebug::GetRootApplicationNode](../../winscript/reference/iactivescriptsitedebug-getrootapplicationnode.md)|스크립트에서 문서를 추가할 응용 프로그램 노드를 가져옵니다.|  
|[IActiveScriptSiteDebug::OnScriptErrorDebug](../../winscript/reference/iactivescriptsitedebug-onscripterrordebug.md)|런타임 오류를 처리 하는 방법을 결정 하기 위해 스마트 호스트 수 있습니다.|