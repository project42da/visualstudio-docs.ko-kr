---
title: 'Idiaenumsegments:: Clone | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments::Clone method
ms.assetid: 93deaac6-72ab-4408-ba14-66174a618757
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3198e21440d2fc20898fde83925aaf8ae0e3a3be
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumsegmentsclone"></a>IDiaEnumSegments::Clone
현재 열거자와 동일한 열거 상태가 포함 하는 열거자를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT Clone (   
   IDiaEnumSegments** ppenum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 ppenum  
 [out] 반환 된 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md) 열거자의 중복을 포함 하는 개체입니다. 세그먼트는 복제 되지 않습니다는 열거자입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)