---
title: "GetAutoInsertExtensions 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
ms.assetid: 78388cce-7aae-4163-8db5-ce00d0a0c331
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1d222f7b6751381ceb4ebdb27bb6a6bf223616df
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="getautoinsertextensions-method"></a>GetAutoInsertExtensions 메서드
  디버깅 하는 동안 자동으로 삽입 될 Office 용 앱에 대 한 정보를 가져옵니다.  
  
 @FSHO2@이 메서드는 나중에 사용할 수 있도록 예약되어 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetAutoInsertExtensions(  
    [out, retval] SAFEARRAY(BSTR)* psaExtensionNames  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|*psaExtensionNames*|Office 용 앱 확장 이름입니다.|  
  
## <a name="return-value"></a>반환 값  
 메서드가 성공적으로 완료되었는지 여부를 나타내는 HRESULT 값입니다.  
  
## <a name="remarks"></a>설명  
 각 응용 프로그램을 삽입할 수 있는 Office 용 HKEY_CURRENT_USER\Software\Microsoft\Office\WEF\Developer 아래에 있는 값에 해당 하는 Office 응용 프로그램 확장 이름으로 반환 됩니다. 호스트는 이러한 레지스트리 값을 조회 하 고 확장을 자동으로 삽입 해야 합니다.  
  
  