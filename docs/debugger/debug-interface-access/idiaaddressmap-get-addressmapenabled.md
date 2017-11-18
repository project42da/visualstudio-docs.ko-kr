---
title: 'Idiaaddressmap:: Get_addressmapenabled | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaAddressMap::get_addressMapEnabled method
ms.assetid: 6183dc5e-befa-4e5a-ae5a-f4aa24f3ed9e
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 54ec3dbb0137d5d46862f59f1bc85f7c6b3761f9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaaddressmapgetaddressmapenabled"></a>IDiaAddressMap::get_addressMapEnabled
특정 세션에 대 한 주소 맵이 설정 되었는지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_addressMapEnabled (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 pRetVal  
 [out] 반환 `TRUE` 주소 매핑을 사용 하는 경우.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 경우에 따라 실행 이후 프로세서 실행 파일을 업데이트합니다. DIA 기호 새 레이아웃의 번역을 지원 하기 위한 메커니즘을 포함 합니다.  
  
 클라이언트 응용 프로그램을 가져와서 특정 세션에 대해 매핑된 주소에 설정할 수는 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md) 에서 인터페이스는 [IDiaSession](../../debugger/debug-interface-access/idiasession.md) 인터페이스와 호출 된 [IDiaAddressMap::set_ addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) 메서드를 호출 하 여 뒤에 [idiaaddressmap:: Put_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md) 메서드. `get_addressMapEnabled` 호출의 결과 반환 하는 메서드는 `put_addressMapEnabled` 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [IDiaAddressMap::put_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)