---
title: IDiaSymbol::get_isAcceleratorGroupSharedLocal | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 17a20542-5b45-478f-bb80-0d56031aadb5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c1d1ccb6643973dc61e169930f57b4f279ad4c1d
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiasymbolgetisacceleratorgroupsharedlocal"></a>IDiaSymbol::get_isAcceleratorGroupSharedLocal
C + + AMP 액셀러레이터에 대 한 컴파일된 코드에서 그룹 공유 지역 변수 기호 일치 하는지 여부를 나타내는 플래그를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_isAcceleratorGroupSharedLocal(   
   BOOL* pFlag);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pFlag`  
 [out] 에 대 한 포인터는 `BOOL` 기호는 c + + AMP 액셀러레이터에 대 한 컴파일된 코드에서 그룹 공유 지역 변수 일치 하는지 여부를 나타내는입니다. 경우 `TRUE`, `get_baseDataSlot` 및 `get_baseDataOffset` 메서드 변수에 대 한 저장소 위치 정보를 가져오는 데 사용할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get_baseDataSlot](../../debugger/debug-interface-access/idiasymbol-get-basedataslot.md)   
 [IDiaSymbol::get_baseDataOffset](../../debugger/debug-interface-access/idiasymbol-get-basedataoffset.md)