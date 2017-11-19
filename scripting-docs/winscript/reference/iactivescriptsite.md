---
title: IActiveScriptSite | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IActiveScriptSite interface
ms.assetid: 4d604a11-5365-46cf-ab71-39b3dbbe9f22
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c23dba403a7889fe46817a21ed8e4be65b1c05b4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsite"></a>IActiveScriptSite
Windows 스크립트 엔진에 대 한 사이트를 만드는 호스트에서 구현 합니다. 일반적으로이 사이트 (예를 들어, ActiveX 컨트롤) 스크립트에 표시 되는 모든 개체의 컨테이너와 연결 됩니다. 일반적으로이 컨테이너는 문서 또는 보고 있는 페이지에 대응 됩니다. 예를 들어 Microsoft Internet Explorer는 표시 되 고 각 HTML 페이지에 대 한 이러한 컨테이너를 만들 합니다. 각 ActiveX 컨트롤 (또는 다른 자동화 개체)는 페이지와 자체 스크립팅 엔진에는이 컨테이너에 있는 열거 가능한 것입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|||  
|-|-|  
|메서드|설명|  
|[IActiveScriptSite::GetLCID](../../winscript/reference/iactivescriptsite-getlcid.md)|사용자 인터페이스 요소를 표시 하기 위해 사용 하 여 호스트 하는 로캘 식별자를 검색 합니다.|  
|[IActiveScriptSite::GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md)|호출을 통해 엔진에 추가 된 항목에 대 한 정보를 가져옵니다는 [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) 메서드.|  
|[IActiveScriptSite::GetDocVersionString](../../winscript/reference/iactivescriptsite-getdocversionstring.md)|호스트의 관점에서 현재 문서 버전을 고유 하 게 식별 하는 호스트 정의 문자열을 검색 합니다.|  
|[IActiveScriptSite::OnScriptTerminate](../../winscript/reference/iactivescriptsite-onscriptterminate.md)|스크립트 실행이 완료 될 때 호출 합니다.|  
|[IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md)|스크립팅 엔진 상태는 변경 되었음을 호스트에 알립니다.|  
|[IActiveScriptSite::OnScriptError](../../winscript/reference/iactivescriptsite-onscripterror.md)|엔진을 스크립트를 실행 하는 동안 실행 오류가 발생 했음을 호스트에 알립니다.|  
|[IActiveScriptSite::OnEnterScript](../../winscript/reference/iactivescriptsite-onenterscript.md)|스크립팅 엔진이 스크립트 코드 실행을 시작 했음을 호스트에 알립니다.|  
|[IActiveScriptSite::OnLeaveScript](../../winscript/reference/iactivescriptsite-onleavescript.md)|호스트에 알려 스크립팅 엔진 스크립트 코드를 실행할 수 없도록 반환 했습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 인터페이스](../../winscript/reference/active-script-interfaces.md)