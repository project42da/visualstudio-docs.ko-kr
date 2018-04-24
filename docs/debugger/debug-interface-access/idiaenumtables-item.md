---
title: 'Idiaenumtables:: Item | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::Item method
ms.assetid: d65ab262-10c6-48ce-95a3-b5e4cb2c85af
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 68a9dbba4226e0fa4f591bfc48b03add62ad75b3
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumtablesitem"></a>IDiaEnumTables::Item
인덱스 또는 이름을 사용 하 여 테이블을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT Item (   
   VARIANT     index,  
   IDiaTable** table  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `index`  
 [in] 인덱스 또는 이름은 [IDiaTable](../../debugger/debug-interface-access/idiatable.md) 를 검색할 수 있습니다. 0에서 범위에 있어야 정수 변형을 사용 하는 경우 `count`-1로, 여기서 `count` 에서 반환 되는 [idiaenumtables:: Get_count](../../debugger/debug-interface-access/idiaenumtables-get-count.md) 메서드.  
  
 `table`  
 [out] 반환 된 [IDiaTable](../../debugger/debug-interface-access/idiatable.md) 원하는 테이블을 나타내는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 문자열 variant를 지정 하는 경우 문자열 이름을 특정 테이블입니다. 이름에 정의 된 테이블 이름 중 하나 여야 합니다 [상수 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md)합니다.  
  
## <a name="example"></a>예제  
  
```C++  
VARIANT var;  
var.vt = VT_BSTR;  
var.bstrVal = SysAllocString(DiaTable_Symbols );  
IDiaTable* pTable;  
pEnumTables->Item( var, &pTable );  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)   
 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)   
 [Idiaenumtables:: Get_count](../../debugger/debug-interface-access/idiaenumtables-get-count.md)   
 [상수(디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md)