---
title: "IActiveScriptSite | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptSite 인터페이스"
ms.assetid: 4d604a11-5365-46cf-ab71-39b3dbbe9f22
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptSite
Windows 스크립트 엔진을 위한 사이트를 만들려면 호스트 구현 합니다.  일반적으로이 사이트 \(예를 들어, ActiveX 컨트롤\) 스크립트를 볼 수 있는 모든 개체의 컨테이너와 연관 됩니다.  일반적으로이 컨테이너 문서 또는 페이지를 보는 사용자에 해당 됩니다.  예를 들어, Microsoft Internet Explorer, 컨테이너 표시 되 고 각 HTML 페이지를 만듭니다.  각 ActiveX 컨트롤 \(또는 다른 자동화 개체\) 페이지, 스크립트 엔진 자체에 수이 내의 컨테이너를 열거할 수 있습니다.  
  
## Vtable 순서의 메서드  
  
|||  
|-|-|  
|메서드|설명|  
|[IActiveScriptSite::GetLCID](../../winscript/reference/iactivescriptsite-getlcid.md)|호스트의 사용자 인터페이스 요소를 표시 하는 데 사용 하는 로케일 식별자를 검색 합니다.|  
|[IActiveScriptSite::GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md)|엔진 호출을 통해 추가 된 항목에 대 한 정보를 가져오는 데는 [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) 메서드.|  
|[IActiveScriptSite::GetDocVersionString](../../winscript/reference/iactivescriptsite-getdocversionstring.md)|호스트의 관점에서 현재 문서 버전을 고유 하 게 식별 하는 호스트 정의 문자열을 검색 합니다.|  
|[IActiveScriptSite::OnScriptTerminate](../../winscript/reference/iactivescriptsite-onscriptterminate.md)|스크립트 실행이 완료 되었을 때 호출 됩니다.|  
|[IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md)|스크립팅 엔진 상태가 변경 되었음을 호스트에 게 알립니다.|  
|[IActiveScriptSite::OnScriptError](../../winscript/reference/iactivescriptsite-onscripterror.md)|엔진은 스크립트를 실행 하는 동안 실행 오류가 발생 했음을 호스트에 게 알립니다.|  
|[IActiveScriptSite::OnEnterScript](../../winscript/reference/iactivescriptsite-onenterscript.md)|스크립팅 엔진이 스크립트 코드를 실행을 시작 했음을 호스트에 게 알립니다.|  
|[IActiveScriptSite::OnLeaveScript](../../winscript/reference/iactivescriptsite-onleavescript.md)|스크립팅 엔진이 스크립트 코드 실행에서 반환 되었음을 호스트에 게 알립니다.|  
  
## 참고 항목  
 [액티브 스크립트 인터페이스](../../winscript/reference/active-script-interfaces.md)