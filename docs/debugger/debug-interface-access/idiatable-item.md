---
title: 'Idiatable:: Item | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaTable::Item method
ms.assetid: eae11b26-4807-400c-be25-e85bbc0c6b20
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: af10c9924bb7b319c34b017812289ead48929b13
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idiatableitem"></a>IDiaTable::Item
테이블의 지정된 된 항목에 대 한 참조를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT Item (   
   DWORD      index,  
   IUnknown** element  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `index`  
 [in] 범위는 0에서의 테이블 항목의 인덱스 `count`-1로, 여기서 `count` 에서 반환 되는 [idiatable:: Get_count](../../debugger/debug-interface-access/idiatable-get-count.md)메서드.  
  
 `element`  
 [out] 반환 된 `IUnknown` 지정한 테이블 항목을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 테이블 개체의 컬렉션을 나타냅니다. 이러한 개체에 따라 요소 매개 변수를 적절 한 인터페이스를 캐스팅할 수 있습니다. 예를 들어 테이블에 대 한 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md) 개체에 요소 매개 변수를 캐스팅할 수는 `IDiaSegment` 인터페이스입니다.  
  
 호출 하는 보다 일반적인 방법은 이기는 `QueryInterface` 에서 메서드는 [IDiaTable](../../debugger/debug-interface-access/idiatable.md) 적절 한 열거자 인터페이스에 대 한 인터페이스를 테이블 내용에 액세스 하는 열거자의 특정 메서드를 사용 합니다. 참조는 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md) 예에 대 한 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)   
 [Idiatable:: Get_count](../../debugger/debug-interface-access/idiatable-get-count.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)   
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)