---
title: 'Idiaenumdebugstreamdata:: Next | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreamData::Next method
ms.assetid: 114171dd-38fd-4bd7-a702-8ff887ffc99b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 81e816edd5b93ffdfec46d36d9aabba154ab035d
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumdebugstreamdatanext"></a>IDiaEnumDebugStreamData::Next
열거 순서에 있는 레코드의 지정된 된 수를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT Next (   
   ULONG  celt,  
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[],  
   ULONG* pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 celt  
 [in] 검색할 레코드의 수입니다.  
  
 cbData  
 [in] 데이터 버퍼의 바이트의 크기입니다.  
  
 pcbData  
 [out] 반환 된 바이트 수를 반환 합니다. 경우 `data` 이 NULL 이면 다음 `pcbData` 요청한 모든 레코드에 대해 사용할 수 있는 데이터의 바이트의 총 수를 포함 합니다.  
  
 데이터]  
 [out] 디버그 스트림 레코드 데이터로 채울 수 있는 버퍼입니다.  
  
 pceltFetched  
 [out에서] 에 있는 레코드의 수를 반환 `data`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 레코드가 더 이상 없는 경우. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)   
 [IDiaEnumDebugStreams::Next](../../debugger/debug-interface-access/idiaenumdebugstreams-next.md)