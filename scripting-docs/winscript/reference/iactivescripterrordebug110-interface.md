---
title: "IActiveScriptErrorDebug110 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IActiveScriptErrorDebug110 Interface
ms.assetid: 5c1a4993-4cad-4ccf-89c2-53abfddfe1f2
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 152f12154acc59b88fc8b1c9a176ac87a5da847d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescripterrordebug110-interface"></a>IActiveScriptErrorDebug110 인터페이스
에 새로운 기능이 추가 된 [IActiveScriptDebug 인터페이스](../../winscript/reference/iactivescriptdebug-interface.md)합니다. 이 인터페이스는 BREAKREASON_ERROR 이벤트가 발생한 이유를 확인하기 위해 JavaScript 엔진에 의해 구현됩니다.  
  
> [!IMPORTANT]
>  이 인터페이스는 PDM v11.0 이상에 의해 구현됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="methods"></a>메서드  
 `IActiveScriptErrorDebug110` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptErrorDebug110::GetExceptionThrownKind](../../winscript/reference/iactivescripterrordebug110-getexceptionthrownkind.md)|Throw된 예외에 대한 예외 종류를 반환합니다.|