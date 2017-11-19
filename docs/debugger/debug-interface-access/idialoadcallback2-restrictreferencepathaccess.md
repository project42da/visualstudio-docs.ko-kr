---
title: 'Idialoadcallback2:: Restrictreferencepathaccess | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaLoadCallback2::RestrictReferencePathAccess method
ms.assetid: e20cb45c-0360-4ff0-a92c-b1b6f76d6e85
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4800ab08f1fba65f3b40564a789630f370d21ac1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idialoadcallback2restrictreferencepathaccess"></a>IDiaLoadCallback2::RestrictReferencePathAccess
.Exe 파일이 있는 경로에 허용 된.pdb 파일을 찾는 경우를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT RestrictReferencePathAccess();  
```  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이외의 다른 모든 반환 코드 `S_OK` .exe 파일이 있는 경로에.pdb 파일을 찾는 방지 하기 위해 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)