---
title: 'Idiaenumtables:: Clone | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumTables::Clone method
ms.assetid: beb21109-b12c-44d8-8c1f-a332216b3713
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6d5c7ee825404586c039fa9e42a9d4f13721443f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumtablesclone"></a>IDiaEnumTables::Clone
현재 열거자와 동일한 열거 상태가 포함 하는 열거자를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT Clone (   
   IDiaEnumTables** ppenum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppenum`  
 [out] 반환 된 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md) 열거자의 중복을 포함 하는 개체입니다. 테이블 중복 되지 않습니다는 열거자입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)