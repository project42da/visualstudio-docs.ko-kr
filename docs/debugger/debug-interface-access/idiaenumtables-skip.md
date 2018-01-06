---
title: 'Idiaenumtables:: Skip | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumTables::Skip method
ms.assetid: 5c9db956-0654-4f1a-8775-530aa980d8ec
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d2741361ddb0e7483344c5fbe123e5d4ec03588c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idiaenumtablesskip"></a>IDiaEnumTables::Skip
열거형 시퀀스에 있는 테이블의 지정 된 수를 건너뜁니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT Skip (   
   ULONG celt  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 [in] 열거형 시퀀스를 건너뛰려면에 테이블의 수입니다.  
  
## <a name="return-value"></a>반환 값  
 에 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 경우 건너뛸 자세한 테이블이 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)