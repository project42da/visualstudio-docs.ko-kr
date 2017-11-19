---
title: ISimpleConnectionPoint::Advise | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: ISimpleConnectionPoint.Advise
apilocation: pdm.dll
helpviewer_keywords: ISimpleConnectionPoint::Advise
ms.assetid: 59ded60d-b938-4110-aca3-e69ba234ca9a
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7ec43d135401386a3f54f2c047040897f038ba19
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="isimpleconnectionpointadvise"></a>ISimpleConnectionPoint::Advise
간단한 연결 지점 개체와 클라이언트의 싱크 간에 연결을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Advise(  
   IDispatch*  pdisp,  
   DWORD*      pdwCookie  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdisp`  
 [in] 에 대 한 포인터는 `IDispatch` 클라이언트에서 인터페이스의 싱크를 하시기 바랍니다. 클라이언트의 싱크 간단한 연결 지점에서 보내는 호출을 받습니다.  
  
 `pdwCookie`  
 [out] 이 연결을 고유 하 게 식별 하는 반환 된 토큰에 대 한 포인터입니다. 호출자에 게이 토큰 사용 하 여이 나중에 전달 하 여 연결을 삭제 하 고 `ISimpleConnectionPoint::Unadvise` 메서드. 연결이 연결이 성공적으로 설정 되지 않으면이 값은 0입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 간단한 연결 지점 개체와 클라이언트의 싱크 간에 연결을 설정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ISimpleConnectionPoint 인터페이스](../../winscript/reference/isimpleconnectionpoint-interface.md)   
 [ISimpleConnectionPoint::Unadvise](../../winscript/reference/isimpleconnectionpoint-unadvise.md)