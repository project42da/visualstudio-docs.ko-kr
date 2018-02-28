---
title: IActiveScriptSiteWindow::EnableModeless | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptSiteWindow.EnableModeless
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteWindow_EnableModeless
ms.assetid: 83fe4f62-8e97-4f03-bc6f-d90aa888657d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7099fe7d13a1cb3231e67049104722af9373d7a8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsitewindowenablemodeless"></a>IActiveScriptSiteWindow::EnableModeless
호스트를 사용 하도록 설정 하거나 주 창 뿐만 아니라 모든 모덜리스 대화 상자를 사용 하지 않도록 설정 하면 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnableModeless(  
    BOOL fEnable  // enable flag  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fEnable`  
 [in] 경우 플래그는 `TRUE`, 주 창 및 모덜리스 대화 상자를 사용 하도록 설정 하거나, 있는 경우 `FALSE`, 해당를 사용 하지 않도록 설정 합니다.  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 하면 또는 `E_FAIL` 오류가 발생 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 `IOleInPlaceFrame::EnableModeless` 메서드.  
  
 이 메서드의 호출을 중첩 될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptSiteWindow](../../winscript/reference/iactivescriptsitewindow.md)