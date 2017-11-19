---
title: "Iactivescriptsitetraceinfo:: Sendscripttraceinfo 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 0419e4c5-eb7c-45a3-b6dc-1a5e157d95f9
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5290cc6a92be7c8bc99e4715c77bfe6f8f6abb53
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsitetraceinfosendscripttraceinfo-method"></a>IActiveScriptSiteTraceInfo::SendScriptTraceInfo 메서드
이벤트 유형, 컨텍스트 및 스크립트 문을 포함 하는 추적 정보를 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SendScriptTraceInfo(     [in] SCRIPTTRACEINFO stiEventType,     [in] GUID guidContextID,     [in] DWORD dwScriptContextCookie,     [in] LONG lScriptStatementStart,     [in] LONG lScriptStatementEnd,     [in] DWORD64 dwReserved );   
```  
  
#### <a name="parameters"></a>매개 변수  
 `stiEventType`  
 이벤트 유형입니다.  
  
 `guidContextId`  
 컨텍스트 GUID입니다.  
  
 `dwScriptContextCookie`  
 컨텍스트는 쿠키입니다.  
  
 `lScriptStatementStart`  
 스크립트 문의 시작 위치입니다.  
  
 `lScriptStatementEnd`  
 스크립트 문의 끝의 위치입니다.  
  
 `dwReserved`  
 예약됨.