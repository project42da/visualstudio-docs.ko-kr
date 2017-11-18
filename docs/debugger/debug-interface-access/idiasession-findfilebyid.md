---
title: 'Idiasession:: Findfilebyid | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSession::findFileById method
ms.assetid: 710efe04-78b5-4f3e-a1d8-f9b069063503
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1996bed14323adeac794f12ed4307e96e3ba8b54
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasessionfindfilebyid"></a>IDiaSession::findFileById
소스 파일 식별자도 소스 파일을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findFileById (   
   DWORD            uniqueId,  
   IDiaSourceFile** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `uniqueId`  
 [in] 소스 파일 식별자를 지정합니다.  
  
 `ppResult`  
 [out] 반환 된 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) 소스 파일을 나타내는 개체를 검색 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 소스 파일 식별자는 모든 소스 파일을 고유 하 게 DIA SDK를 내부적으로 사용 하는 고유한 값입니다. 이 메서드는 일반적으로 DIA SDK를 내부적으로 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasession:: Findfile](../../debugger/debug-interface-access/idiasession-findfile.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)