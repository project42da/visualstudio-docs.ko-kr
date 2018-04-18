---
title: 'Idiasymbol:: Get_virtualbasetabletype | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_virtualBaseTableType method
ms.assetid: e0581c4f-0343-49b5-9754-a48477460e9f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 059e187279506de36eaad96bb744735cb280da24
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgetvirtualbasetabletype"></a>IDiaSymbol::get_virtualBaseTableType
가상 기본 테이블 포인터의 유형을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_virtualBaseTableType(  
   IDiaSymbol *pRetVal  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`pRetVal`|[out] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 기본 테이블의 형식을 지정 하는 개체입니다.|  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 의미는 속성은 해당 기호를 사용할 수 없습니다.  
  
## <a name="remarks"></a>설명  
 가상 기본 테이블 포인터 (`vbtptr`)에 대 한 숨겨진 포인터는 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 처리 가상 기본 클래스에서 상속 하 vtable 합니다. A `vbtptr` 상속 된 클래스에 따라 다양 한 크기를 가질 수 있습니다.  
  
 이 메서드는 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 는 vbtptr의 크기를 결정 하는 데 사용할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
  
|요구 사항|설명|  
|-----------------|-----------------|  
|헤더:|dia2.h|  
|버전:|DIA SDK v 8.0|  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)