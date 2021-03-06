---
title: DEBUG_ADDRESS_UNION | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DEBUG_ADDRESS_UNION
helpviewer_keywords:
- DEBUG_ADDRESS_UNION union
ms.assetid: e3d11aab-de0d-4109-b5dc-11e07e64382d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0b0fcd662e3a4831b78ca55c139ce1511ea04b24
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="debugaddressunion"></a>DEBUG_ADDRESS_UNION
서로 다른 주소에 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _tagDEBUG_ADDRESS_UNION {  
   ADDRESS_KIND dwKind;  
   union {  
      NATIVE_ADDRESS                  addrNative;  
      UNMANAGED_ADDRESS_THIS_RELATIVE addrThisRel;  
      UNMANAGED_ADDRESS_PHYSICAL      addrUPhysical;  
      METADATA_ADDRESS_METHOD         addrMethod;  
      METADATA_ADDRESS_FIELD          addrField;  
      METADATA_ADDRESS_LOCAL          addrLocal;  
      METADATA_ADDRESS_PARAM          addrParam;  
      METADATA_ADDRESS_ARRAYELEM      addrArrayElem;  
      METADATA_ADDRESS_RETVAL         addrRetVal;  
      DWORD                           unused;  
   } addr;  
} DEBUG_ADDRESS_UNION;  
```  
  
```csharp  
public struct DEBUG_ADDRESS_UNION {  
   public ADDRESS_KIND dwKind;  
   public IntPtr       unionmember;  
}  
```  
  
## <a name="terms"></a>용어  
 dwKind  
 값은 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) 합집합을 해석 하는 방법을 지정 하는 열거형입니다.  
  
 addr.addrNative  
 [C + + 전용] 포함 된 [NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md) 경우 구조체 `dwKind` ADDRESS_KIND_NATIVE = 합니다.  
  
 addr.addrThisRel  
 [C + + 전용] 포함 된[UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md) 경우 구조체 `dwKind` ADDRESS_KIND_UNMANAGED_THIS_RELATIVE = 합니다.  
  
 addr.addUPhysical  
 [C + + 전용] 포함 된[UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md) 경우 구조체 `dwKind` ADDRESS_KIND_UNMANAGED_PHYSICAL = 합니다.  
  
 addr.addrMethod  
 [C + + 전용] 포함 된[METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md) 경우 구조체 `dwKind` ADDRESS_KIND_METHOD = 합니다.  
  
 addr.addrField  
 [C + + 전용] 포함 된[METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md) 경우 구조체 `dwKind` ADDRESS_KIND_FIELD = 합니다.  
  
 addr.addrLocal  
 [C + + 전용] 포함 된[METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md) 경우 구조체 `dwKind` ADDRESS_KIND_LOCAL = 합니다.  
  
 addr.addrParam  
 [C + + 전용] 포함 된[METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md) 경우 구조체 `dwKind` ADDRESS_KIND_PARAM = 합니다.  
  
 addr.addrArrayElem  
 [C + + 전용] 포함 된[METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md) 경우 구조체 `dwKind` ADDRESS_KIND_ARRAYELEM = 합니다.  
  
 addr.addrRetVal  
 [C + + 전용] 포함 된[METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md) 경우 구조체 `dwKind` ADDRESS_KIND_RETVAL = 합니다.  
  
 addr.unused  
 [C + +만] 안쪽 여백입니다.  
  
 Addr  
 [C + + 전용] 공용 구조체의 이름입니다.  
  
 unionmember  
 [C#] 이 값에 따라 적절 한 구조 형식으로 마샬링할 수 해야 `dwKind`합니다. 간의 연결에 대 한 설명 부분 참조 `dwKind` 및 공용 구조체의 해석 합니다.  
  
## <a name="remarks"></a>설명  
 이 구조는의 일부는 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) 구조체이 고 다양 한 여러 가지 주소 중 하나를 나타냅니다 (의 `DEBUG_ADDRESS` 구조에 대 한 호출에 의해 채워진는 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) 메서드).  
  
 [C#] 다음 표를 해석 하는 방법을 보여줍니다는 `unionmember` 각 유형의 주소에 대 한 멤버입니다. 한 종류의 주소에 대 한이 작업을 수행 하는 방법을 보여 줍니다.  
  
|`dwKind`|`unionmember` 로 해석|  
|--------------|----------------------------------|  
|`ADDRESS_KIND_NATIVE`|[NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md)|  
|`ADDRESS_KIND_UNMANAGED_THIS_RELATIVE`|[UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md)|  
|`ADDRESS_KIND_UNMANAGED_PHYSICAL`|[UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md)|  
|`ADDRESS_KIND_METHOD`|[METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md)|  
|`ADDRESS_KIND_FIELD`|[METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md)|  
|`ADDRESS_KIND_LOCAL`|[METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md)|  
|`ADDRESS_KIND_PARAM`|[METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md)|  
|`ADDRESS_KIND_ARRAYELEM`|[METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md)|  
|`ADDRESS_KIND_RETVAL`|[METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md)|  
  
## <a name="example"></a>예제  
 이 예제에서는 한 종류의 주소를 해석 하는 방법을 보여 줍니다 (`METADATA_ADDRESS_ARRAYELEM`)의 `DEBUG_ADDRESS_UNION` C#의 구조입니다. 나머지 요소를 동일한 방식으로 해석할 수 있습니다.  
  
```csharp  
using System;  
using System.Runtime.Interop.Services;  
using Microsoft.VisualStudio.Debugger.Interop;  
  
namespace MyPackage  
{  
    public class MyClass  
    {  
        public void Interpret(DEBUG_ADDRESS_UNION dau)  
        {  
            if (dau.dwKind == (uint)enum_ADDRESS_KIND.ADDRESS_KIND_METADATA_ARRAYELEM)  
            {  
                 METADATA_ADDRESS_ARRAYELEM arrayElem =  
                     (METADATA_ADDRESS_ARRAYELEM)Marshal.PtrToStructure(dau.unionmember,  
                                 typeof(METADATA_ADDRESS_ARRAYELEM));  
            }  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)   
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)