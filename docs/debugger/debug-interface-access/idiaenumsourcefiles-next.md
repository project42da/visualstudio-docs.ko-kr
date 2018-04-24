---
title: 'Idiaenumsourcefiles:: Next | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSourceFiles::Next method
ms.assetid: 83bf6317-ff39-4c5c-8987-cba34e7a6983
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ca815309009ee8e43c17fb8a579c055e75c684e0
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumsourcefilesnext"></a>IDiaEnumSourceFiles::Next
열거형 시퀀스에서 소스 파일의 지정된 된 수를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT Next (   
   ULONG            celt,  
   IDiaSourceFile** rgelt,  
   ULONG*           pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 celt  
 [in] 검색할 열거자에 대 한 소스 파일의 수입니다.  
  
 rgelt  
 [out] 사용 하 여 입력할 수 있는 배열은 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) 원하는 소스 파일을 나타내는 개체입니다.  
  
 pceltFetched  
 [out] 인출 된 열거자에 소스 파일의 수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우 더 많은 원본 파일이 없습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [Idiasession:: Findlinesbylinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)