---
title: IActiveScriptError | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IActiveScriptError interface
ms.assetid: c8e0288d-38ff-4145-a7e3-f8cdfb72eefe
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a403bf412a0c93a5c435e1a3184202ed68d406ea
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescripterror"></a>IActiveScriptError
이 인터페이스를 구현 하는 개체에 전달 되는 [IActiveScriptSite::OnScriptError](../../winscript/reference/iactivescriptsite-onscripterror.md) 메서드 때마다 스크립팅 엔진에서 처리 되지 않은 오류가 발생 합니다. 호스트는 다음에 발생 한 오류에 대 한 정보를 얻으려면이 개체에서 메서드를 호출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptError::GetExceptionInfo](../../winscript/reference/iactivescripterror-getexceptioninfo.md)|오류에 대 한 정보를 검색합니다.|  
|[IActiveScriptError::GetSourcePosition](../../winscript/reference/iactivescripterror-getsourceposition.md)|오류가 발생 한 소스 코드의 위치를 검색 합니다.|  
|[IActiveScriptError::GetSourceLineText](../../winscript/reference/iactivescripterror-getsourcelinetext.md)|오류가 발생 한 소스 파일의 줄을 검색 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 인터페이스](../../winscript/reference/active-script-interfaces.md)