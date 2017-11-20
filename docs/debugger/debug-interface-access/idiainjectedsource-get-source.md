---
title: 'Idiainjectedsource:: Get_source | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaInjectedSource::get_source method
ms.assetid: 3c0b5386-321f-4f8f-85cc-e2ee7b4cc3d2
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 910b96d4114617957907ff1cd4eee4609ebaa250
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiainjectedsourcegetsource"></a>IDiaInjectedSource::get_source
소스 코드 바이트를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_source (   
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cbData`  
 [in] 데이터 버퍼의 크기를 나타내는 바이트 수입니다.  
  
 `pcbData`  
 [out] 반환 된 바이트를 나타내는 바이트 수가 반환 됩니다. 경우 `data` 은 `NULL`, 다음 `pcbData` 는 데이터의 바이트의 총 수를 사용할 수 있는 합니다.  
  
 `data[]`  
 [out] 소스 바이트를 채울 수 있는 버퍼입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우이 속성이 지원 되지 않습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)