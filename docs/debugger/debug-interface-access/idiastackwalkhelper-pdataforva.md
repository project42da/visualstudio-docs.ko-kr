---
title: IDiaStackWalkHelper::pdataForVA | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::pdataByVA method
ms.assetid: fafc38fe-74dc-4726-9a51-eebf3a673d7f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 251b54ca712078e5252a4a55c9237545e14a7536
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idiastackwalkhelperpdataforva"></a>IDiaStackWalkHelper::pdataForVA
가상 주소와 연결 된 PDATA 데이터 블록을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT pdataForVA(   
   ULONGLONG  va,  
   DWORD      cbData,  
   DWORD*     pcbData,  
   BYTE*      pbData  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `va`  
 [in] 데이터를 가져올 가상 주소를 지정 합니다.  
  
 `cbData`  
 [in] 데이터의에서 바이트를 가져올의 크기입니다.  
  
 `pcbData`  
 [out] 데이터의 실제 크기 (바이트)를 눌러 반환 합니다.  
  
 `pbData`  
 [out에서] 요청된 된 데이터를 사용 하 여 입력 되는 버퍼입니다. 일 수 없습니다 `NULL`합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 이면 지정된 된 주소에 대 한 PDATA 없습니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 PDATA (".pdata" 라는 섹션)는 컴파일 대상의 예외 처리 함수에 대 한 정보를 포함 합니다.  
  
 호출자에 게 데이터 양을 반환 하 여 호출자에 게 데이터의 크기는 사용할 수 있는 요청 하지 않아도 되므로 하는 것을 알고 있습니다. 따라서 것이 오류를 반환 하는 경우이 메서드의 구현에서 허용 되는 `pbData` 매개 변수는 `NULL`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)