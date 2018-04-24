---
title: 'Idiastackwalkframe:: Readmemory | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame::readMemory method
ms.assetid: 7ab0b525-a5a7-4692-acad-e8c00fa9ab9a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6d23b46f0f487bddc678814e41b5cb96331ff46c
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiastackwalkframereadmemory"></a>IDiaStackWalkFrame::readMemory
이미지에서 메모리를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT readMemory (   
   MemoryTypeEnum type,  
   ULONGLONG va,  
   DWORD     cbData,  
   DWORD*    pcbData,  
   BYTE      data[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `type`  
 [in] 중 하나는 [MemoryTypeEnum 열거형](../../debugger/debug-interface-access/memorytypeenum.md) 액세스 하는 메모리의 종류를 지정 하는 열거형 값입니다.  
  
 `va`  
 [in] 가상 주소 이미지 읽기를 시작할 위치입니다.  
  
 `cbData`  
 [in] 데이터 버퍼의 바이트의 크기입니다.  
  
 `pcbData`  
 [out] 반환 된 바이트 수를 반환 합니다. 경우 `data` 은 `NULL`, 다음 `pcbData` 사용할 수 있는 데이터의 바이트의 총 수를 포함 합니다.  
  
 `data`  
 [out] 지정된 된 위치에서 데이터를 채울 수 있는 버퍼입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)