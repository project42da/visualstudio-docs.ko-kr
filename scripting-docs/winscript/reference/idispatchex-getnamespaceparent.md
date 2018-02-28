---
title: IDispatchEx::GetNameSpaceParent | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDispatchEx.GetNameSpaceParent
apilocation:
- scrobj.dll
helpviewer_keywords:
- GetNameSpaceParent method
ms.assetid: 0b077d39-2fd6-4390-8cd5-128d9b8dc90c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 12168ddb5f65c62e81a8f724cacf8b3fd4a1b3a9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idispatchexgetnamespaceparent"></a>IDispatchEx::GetNameSpaceParent
개체의 네임 스페이스 부모에 대 한 인터페이스를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetNameSpaceParent(  
   IUnknown **ppunk  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppunk`  
 주소는 `IUnknown` 네임 스페이스 부모 인터페이스를 수신 하는 인터페이스 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 하는 경우 또는 그렇지 않으면 OLE 정의 된 오류 코드입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDispatchEx 인터페이스](../../winscript/reference/idispatchex-interface.md)