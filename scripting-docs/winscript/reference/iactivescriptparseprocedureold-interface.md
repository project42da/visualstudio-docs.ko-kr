---
title: "IActiveScriptParseProcedureOld 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptParseProcedureOld
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptParseProcedureOld interface
ms.assetid: d94b391e-4c24-46da-a01f-2c134ca4f041
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 99cff9cd4d04c5d25489b6cc4c9b9af93792dc2a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptparseprocedureold-interface"></a>IActiveScriptParseProcedureOld 인터페이스
스크립트에 추가 하는 절차에 대 한 소스 코드 텍스트를 수 있습니다. VBScript 같은 독립 제작 환경을 갖지 않는 해석 된 스크립팅 언어에 대 한 대체 메커니즘이 제공 (이외의 `IActiveScriptParse` 또는 `IPersist*`) 네임 스페이스에 프로시저 스크립트를 추가 하려면.  
  
> [!NOTE]
>  이 인터페이스는 기준 사용 되지 않습니다는 `IActiveScriptParseProcedure` 인터페이스입니다.  
  
## <a name="methods"></a>메서드  
 상속 된 메서드 외에도 `IUnknown`, `IActiveScriptParseProcedureOld` 인터페이스는 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptParseProcedureOld::ParseProcedureText](../../winscript/reference/iactivescriptparseprocedureold-parseproceduretext.md)|지정 된 코드 프로시저를 구문 분석 하 고 네임 스페이스에는 프로시저를 추가 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptParseProcedure](../../winscript/reference/iactivescriptparseprocedure.md)