---
title: IActiveScriptSiteWindow | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IActiveScriptSiteWindow interface
ms.assetid: 96d5c493-2c0b-47e2-848b-4a8dacdcd65c
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3043a3c36b2f1ebdf439f22b1de19dd559e50cfa
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsitewindow"></a>IActiveScriptSiteWindow
로 동일한 개체에 대 한 사용자 인터페이스를 지 원하는 호스트에서이 인터페이스는 구현 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 합니다. 서버와 같은 사용자 인터페이스를 지원 하지 않는 호스트를 구현 하지 않습니다는 `IActiveScriptSiteWindow` 인터페이스입니다. 이 인터페이스를 호출 하 여 액세스 하는 스크립팅 엔진 `QueryInterface` 에서 `IActiveScriptSite`합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IActiveScriptSiteWindow::GetWindow](../../winscript/reference/iactivescriptsitewindow-getwindow.md)|스크립팅 엔진을 표시 해야 하는 팝업 창의 소유자로 작동할 수 있는 창 핸들을 검색 합니다.|  
|[IActiveScriptSiteWindow::EnableModeless](../../winscript/reference/iactivescriptsitewindow-enablemodeless.md)|호스트를 사용 하도록 설정 하거나 주 창 뿐만 아니라 모든 모덜리스 대화 상자를 사용 하지 않도록 설정 하면 됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 인터페이스](../../winscript/reference/active-script-interfaces.md)