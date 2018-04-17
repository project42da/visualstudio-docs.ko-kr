---
title: IDiaStackWalkHelper::readMemory | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::readMemory method
ms.assetid: e1eb90aa-49b7-476c-9e70-7e8f08994cbe
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: af93d4d49167a6167d971140c3b668c95a34f799
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idiastackwalkhelperreadmemory"></a>IDiaStackWalkHelper::readMemory
메모리에 실행 파일의 이미지에서 데이터 블록을 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT readMemory(   
   enum MemoryTypeEnum type,  
   ULONGLONG           va,  
   DWORD               cbData,  
   DWORD*              pcbData,  
   BYTE*               pbData  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `type`  
 [in] 값은 [MemoryTypeEnum 열거형](../../debugger/debug-interface-access/memorytypeenum.md) 읽는 데 필요한 메모리가의 형식을 지정 하는 열거형입니다.  
  
 va  
 [in] 읽기를 시작 하는 이미지에서 가상 주소입니다.  
  
 `cbData`  
 [in] 데이터 버퍼의 바이트의 크기입니다.  
  
 `pcbData`  
 [out] 실제로 읽는 바이트 수를 반환 합니다. 경우 `pbData` 은 `NULL`를 사용할 수 있는 데이터의 바이트의 총 수입니다.  
  
 `pbData`  
 [out에서] 읽을 메모리를 사용 하 여 입력 되는 버퍼입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [MemoryTypeEnum 열거형](../../debugger/debug-interface-access/memorytypeenum.md)