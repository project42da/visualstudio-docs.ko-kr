---
title: IEEDataStorage::GetData | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEEDataStorage::GetData
helpviewer_keywords:
- IEEDataStorage::GetData
ms.assetid: 4d384039-73d4-40b4-ace6-a2474c546397
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2ddbc77950396df743b88ce3b6c1a94bbeaf8126
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ieedatastoragegetdata"></a>IEEDataStorage::GetData
개체에서 지정 된 바이트 수를 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetData(  
   ULONG  dataSize,  
   ULONG* sizeGotten,  
   BYTE*  data  
);  
```  
  
```csharp  
int GetData(  
   uint     dataSize,  
   out uint sizeGotten,  
   byte[]   data  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dataSize`  
 [in] 검색할 바이트 수입니다 (의 `data` 배열 적어도이 바이트 수가 보유 해야 합니다).  
  
 `sizeGotten`  
 [out] 실제 검색 바이트 수를 반환 합니다.  
  
 `data`  
 [out에서] 요청된 된 데이터를 사용 하 여 채울 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 권장 되는 사용이 메서드의 검색 프로세스에서 바이트를 건너뛸 수 없기 때문 로컬 배열에 모든 데이터 바이트를 검색 하는 것입니다. 이 경우, 매개 변수 `dataSize` 값에서 반환 해야는 [GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md)