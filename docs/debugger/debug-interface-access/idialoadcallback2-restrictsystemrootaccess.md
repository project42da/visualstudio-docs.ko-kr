---
title: 'Idialoadcallback2:: Restrictsystemrootaccess | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaLoadCallback2::RestrictSystemRootAccess method
ms.assetid: 39f22db8-632a-4ef0-babc-23f758e6d937
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a2f77f92487f8f44aa2608f6e29eb779c9292ae8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idialoadcallback2restrictsystemrootaccess"></a>IDiaLoadCallback2::RestrictSystemRootAccess
시스템 루트 디렉터리에.pdb 파일을 검색할 허용 된 경우를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT RestrictSystemRootAccess();  
```  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이외의 다른 모든 반환 코드 `S_OK` .pdb 파일에 대 한 시스템 루트를 검색할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)