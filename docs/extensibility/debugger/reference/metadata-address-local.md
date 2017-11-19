---
title: METADATA_ADDRESS_LOCAL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: METADATA_ADDRESS_LOCAL
helpviewer_keywords: METADATA_ADDRESS_LOCAL structure
ms.assetid: 635f6bc5-c486-4e0e-83db-36f15e543843
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a9d5e32f6f99cddcd3d04d8c10bda958e58fbbf3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="metadataaddresslocal"></a>METADATA_ADDRESS_LOCAL
이 구조 (일반적으로 함수 또는 메서드)는 범위 내에서 로컬 변수의 주소를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _tagMETADATA_ADDRESS_LOCAL {  
   _mdToken  tokMethod;  
   IUnknown* pLocal;  
   DWORD     dwIndex;  
} METADATA_ADDRESS_LOCAL;  
```  
  
```csharp  
public struct METADATA_ADDRESS_LOCAL {  
   public int    tokMethod;  
   public object pLocal;  
   public uint   dwIndex;  
}  
```  
  
## <a name="terms"></a>용어  
 tokMethod  
 ID 메서드 또는 함수의 지역 변수의 일부인 합니다.  
  
 [C + +] `_mdToken` 는 `typedef` 32 비트 `int`합니다.  
  
 pLocal  
 이 구조를 나타내는 주소가 토큰입니다.  
  
 dwIndex  
 이 변수는 메서드 또는 함수 또는 일부 다른 값 (언어별)의 인덱스를 수 있습니다.  
  
## <a name="remarks"></a>설명  
 이 구조체의 공용 구조체의 일부인는 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) 때 구조는 `dwKind` 필드는 `DEBUG_ADDRESS_UNION` 구조로 설정 되어 `ADDRESS_KIND_LOCAL` (의 값은 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) 열거형)입니다.  
  
 `Warning:`[C + + 전용]  경우 `pLocal` null이 아니면 호출 해야 합니다 `Release` 토큰 포인터 (`addr` 에 있는 필드는 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) 구조):  
  
```  
if (addr.dwKind == ADDRESS_KIND_METADATA_LOCAL &&  addr.addr.addrLocal.pLocal != NULL)  
{  
    addr.addr.addrLocal.pLocal->Release();  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)