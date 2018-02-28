---
title: IActiveScriptParseProcedure | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IActiveScriptParseProcedure interface
ms.assetid: 741a35bb-5b92-489e-ba8a-a406b42125fc
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 77aaa60942855a71f7d71037fbefb06462336a13
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptparseprocedure"></a>IActiveScriptParseProcedure
구현 하는 Windows 스크립트 엔진에서는 스크립트에 추가 하는 절차에 대 한 소스 코드 텍스트를 허용 하는 경우는 `IActiveScriptParseProcedure` 인터페이스입니다. 해석 된 스크립트 언어는 VBScript 같은 독립 제작 환경 없음이 제공 하는 대체 메커니즘 (이외의 `IActiveScriptParse` 또는 `IPersist`*) 스크립트 프로시저 네임 스페이스에 추가 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|||  
|-|-|  
|메서드|설명|  
|[IActiveScriptParseProcedure::ParseProcedureText](../../winscript/reference/iactivescriptparseprocedure-parseproceduretext.md)|지정 된 코드 프로시저를 구문 분석 하 고 네임 스페이스에는 프로시저를 추가 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 인터페이스](../../winscript/reference/active-script-interfaces.md)