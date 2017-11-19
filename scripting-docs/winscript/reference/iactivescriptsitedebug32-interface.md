---
title: "IActiveScriptSiteDebug32 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03f42217-303d-46e7-9792-61a5ab95252c
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: a752851aa6afd903747dc58fed79d2bc5b27e3e8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsitedebug32-interface"></a>IActiveScriptSiteDebug32 인터페이스
스마트 호스트를 구현 하는 `IActiveScriptSiteDebug32` 문서 관리를 수행 하 고 디버깅에 참여 하는 인터페이스입니다. `IActiveScriptSite` 개체는 일반적으로의 구현을 제공는 `IActiveScriptSiteDebug32` 인터페이스입니다. 이 도구를 실행 하는 경우 호출 된 `IActiveScriptSite::QueryInterface` 를 얻는 메서드를는 `IActiveScriptSiteDebug32` 인터페이스입니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IActiveScriptSiteDebug32` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptSiteDebug32::GetApplication](../../winscript/reference/iactivescriptsitedebug32-getapplication.md)|이 스크립트 사이트와 연결 된 디버그 응용 프로그램 개체를 반환 합니다.|  
|[IActiveScriptSiteDebug32::GetDocumentContextFromPosition](../../winscript/reference/iactivescriptsitedebug32-getdocumentcontextfromposition.md)|위임 하는 언어 엔진에서 사용 하는 `IDebugCodeContext::GetSourceContext`합니다.|