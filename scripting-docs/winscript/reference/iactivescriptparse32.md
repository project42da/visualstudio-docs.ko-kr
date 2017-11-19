---
title: IActiveScriptParse32 | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c39c14aa-beb7-4eca-8b8c-2181da1c2e3e
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: 688a89515179912c1ed3ac815f0febf50ab4db0f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptparse32"></a>IActiveScriptParse32
Windows 스크립트 엔진 원시 텍스트 코드 스크립틀릿을 스크립트에 추가 하거나 런타임에 평가할 식 텍스트 있습니다를 구현 하는 경우는 `IActiveScriptParse32` 인터페이스입니다. 해석 된 스크립트 언어는 VBScript 같은 독립 제작 환경 없음이 제공 하는 대체 메커니즘 (이외의 `IPersist*`) 스크립팅 엔진에 스크립트 코드 하 고 스크립트 조각 다양 한 개체에 연결 이벤트입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptParse32::AddScriptlet](../../winscript/reference/iactivescriptparse32-addscriptlet.md)|스크립트에 코드 스크립틀릿을 추가 합니다.|  
|[IActiveScriptParse32::InitNew](../../winscript/reference/iactivescriptparse32-initnew.md)|스크립팅 엔진을 초기화합니다.|  
|[IActiveScriptParse32::ParseScriptText](../../winscript/reference/iactivescriptparse32-parsescripttext.md)|네임 스페이스에 선언을 추가 하 고 코드를 적절 하 게 평가 지정 된 코드 스크립틀릿을 구문 분석 합니다.|