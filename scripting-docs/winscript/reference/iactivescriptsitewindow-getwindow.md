---
title: IActiveScriptSiteWindow::GetWindow | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptSiteWindow.GetWindow
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteWindow_GetWindow
ms.assetid: 6284e38c-9dfb-4d69-903d-f243f78c0331
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b3257ac5632a2f3d713b6329a9a1eeebc4415851
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptsitewindowgetwindow"></a>IActiveScriptSiteWindow::GetWindow
스크립팅 엔진을 표시 해야 하는 팝업 창 소유자 역할을 수행할 수 있는 창에 대 한 핸들을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetWindow(  
    HWND *phwnd  // address of variable for window handle  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `phwnd`  
 [out] 주소 창 핸들을 수신 하는 변수입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 하면 또는 `E_FAIL` 오류가 발생 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 비슷합니다는 `IOleWindow::GetWindow` 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptSiteWindow](../../winscript/reference/iactivescriptsitewindow.md)