---
title: IDebugHelper::CreatePropertyBrowserEx | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugHelper.CreatePropertyBrowserEx
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugHelper::CreatePropertyBrowserEx
ms.assetid: 87ad322f-09da-4ce8-bb68-0b0bbeec645b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f9bc219ea5c2ff9ff2860d36cd475985d825ae59
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebughelpercreatepropertybrowserex"></a>IDebugHelper::CreatePropertyBrowserEx
VARIANT를 배치 하 고 VARIANT 값 이나 VARTYPE 형식 문자열을 사용자 지정 변환 허용 하는 속성 브라우저를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreatePropertyBrowserEx(  
   VARIANT*                  pvar,  
   LPCOLESTR                 bstrName,  
   IDebugApplicationThread*  pdat,  
   IDebugFormatter*          pdf,  
   IDebugProperty**          ppdob  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pvar`  
 [in] 찾아보려면 루트 variant입니다.  
  
 `bstrName`  
 [in] 루트 부여할 이름입니다.  
  
 `pdat`  
 [in] 스레드가 요청 속성입니다. 이 매개 변수가 NULL 이면 없습니다 마샬링 수행 됩니다.  
  
 `pdf`  
 [in] 변형에 대 한 사용자 지정 서식을 제공 하는 개체입니다.  
  
 `ppdob`  
 [out] 속성 브라우저입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 VARIANT를 배치 하 고 VARIANT 값 이나 VARTYPE 형식 문자열을 사용자 지정 변환 허용 하는 속성 브라우저를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugHelper::CreatePropertyBrowser](../../winscript/reference/idebughelper-createpropertybrowser.md)   
 [IDebugHelper 인터페이스](../../winscript/reference/idebughelper-interface.md)   
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)