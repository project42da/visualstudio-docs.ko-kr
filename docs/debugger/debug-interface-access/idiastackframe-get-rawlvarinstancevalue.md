---
title: 'Idiastackframe:: Get_rawlvarinstancevalue | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackFrame::get_rawLVarInstanceValue method
ms.assetid: ce526259-85a6-475b-9274-0b3a21d95db2
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5559ad617afbb2ae4a65ecbf399f7f79d93ae1c7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiastackframegetrawlvarinstancevalue"></a>IDiaStackFrame::get_rawLVarInstanceValue
이 메서드는 원시 바이트로 지정 된 지역 변수 값을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT get_rawLVarInstanceValue(  
   IDiaLVarInstance* pInstance,  
   DWORD             cbDataMax,  
   DWORD*            pcbData,  
   BYTE*             pbData  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pInstance`  
 [in] `IDiaLVarInstance` 지역 변수 값을 가져올의 인스턴스를 나타내는 개체입니다.  
  
 `cbDataMax`  
 [in] 최대 버퍼의 바이트 수로 가리키는 `pbData`합니다. 이 최대 8 바이트 수 (`sizeof(ULONGLONG)`).  
  
 `pcbData`  
 [out] 버퍼에 저장 된 바이트의 실제 수를 반환 합니다.  
  
 `pbData`  
 [out] 데이터를 채울 수 버퍼입니다. 이 될 수 없습니다 `NULL`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)