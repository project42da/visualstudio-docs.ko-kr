---
title: "IActiveScriptParse | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptParse 인터페이스"
ms.assetid: 8c967d70-f582-4f64-9e79-49f40c4dcb7c
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptParse
Windows 스크립트 엔진 스크립트에 추가할 텍스트를 원시 코드 스크립틀릿 허용 또는 식 텍스트 런타임에 계산 될 수 있도록 구현 하는 경우는 `IActiveScriptParse` 인터페이스.  이 제공 하는 대체 메커니즘 없음 VBScript 같은 독립적인 제작 환경 해석 스크립팅 언어 \(이외의 `IPersist*`\) 스크립트 조각 다양 한 개체를 이벤트에 연결할 수 및 스크립팅 엔진에 스크립트 코드를.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IActiveScriptParse::InitNew](../../winscript/reference/iactivescriptparse-initnew.md)|스크립팅 엔진을 초기화합니다.|  
|[IActiveScriptParse::AddScriptlet](../../winscript/reference/iactivescriptparse-addscriptlet.md)|코드 스크립트릿 스크립트에 추가합니다.|  
|[IActiveScriptParse::ParseScriptText](../../winscript/reference/iactivescriptparse-parsescripttext.md)|네임 스페이스 선언을 추가 하 고 코드를 적절 하 게 평가 하는 지정 된 코드 스크립트릿 구문 분석 합니다.|  
  
## 참고 항목  
 [액티브 스크립트 인터페이스](../../winscript/reference/active-script-interfaces.md)