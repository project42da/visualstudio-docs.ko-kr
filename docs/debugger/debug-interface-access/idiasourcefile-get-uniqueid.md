---
title: 'Idiasourcefile:: Get_uniqueid | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSourceFile::get_uniqueId method
ms.assetid: e0b8dbc0-6061-4f31-bead-2cd72be44e41
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3d7a01aafad5349cf3da6957f39130639de34b58
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasourcefilegetuniqueid"></a>IDiaSourceFile::get_uniqueId
이 이미지에 대 한 고유한 단순 정수 키 값을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_uniqueId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pRetVal`  
 [out] 이 이미지에 대 한 고유한 단순 정수 키 값을 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 문자열에는 줄 번호 처리 가속화할 수 대신 키를 비교 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)