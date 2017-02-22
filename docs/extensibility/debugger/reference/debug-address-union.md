---
title: "DEBUG_ADDRESS_UNION | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DEBUG_ADDRESS_UNION"
helpviewer_keywords: 
  - "DEBUG_ADDRESS_UNION 공용 구조체"
ms.assetid: e3d11aab-de0d-4109-b5dc-11e07e64382d
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# DEBUG_ADDRESS_UNION
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

다양 한 종류의 주소에 설명 합니다.  
  
## 구문  
  
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
  
```c#  
public struct DEBUG_ADDRESS_UNION {  
   public ADDRESS_KIND dwKind;  
   public IntPtr       unionmember;  
}  
```  
  
## 용어  
 dwKind  
 값을는 [ADDRESS\_KIND](../../../extensibility/debugger/reference/address-kind.md) 열거형, 공용 구조체를 해석 하는 방법을 지정 합니다.  
  
 addr.addrNative  
 \[C \+ \+에만\] 포함 되어 있는 [NATIVE\_ADDRESS](../../../extensibility/debugger/reference/native-address.md) 경우 구성 `dwKind` ADDRESS\_KIND\_NATIVE \=.  
  
 addr.addrThisRel  
 \[C \+ \+에만\] 포함 되어 있는[UNMANAGED\_ADDRESS\_THIS\_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md) 경우 구성 `dwKind` ADDRESS\_KIND\_UNMANAGED\_THIS\_RELATIVE \=.  
  
 addr.addUPhysical  
 \[C \+ \+에만\] 포함 되어 있는[UNMANAGED\_ADDRESS\_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md) 경우 구성 `dwKind` ADDRESS\_KIND\_UNMANAGED\_PHYSICAL \=.  
  
 addr.addrMethod  
 \[C \+ \+에만\] 포함 되어 있는[METADATA\_ADDRESS\_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md) 경우 구성 `dwKind` ADDRESS\_KIND\_METHOD \=.  
  
 addr.addrField  
 \[C \+ \+에만\] 포함 되어 있는[METADATA\_ADDRESS\_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md) 경우 구성 `dwKind` ADDRESS\_KIND\_FIELD \=.  
  
 addr.addrLocal  
 \[C \+ \+에만\] 포함 되어 있는[METADATA\_ADDRESS\_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md) 경우 구성 `dwKind` ADDRESS\_KIND\_LOCAL \=.  
  
 addr.addrParam  
 \[C \+ \+에만\] 포함 되어 있는[METADATA\_ADDRESS\_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md) 경우 구성 `dwKind` ADDRESS\_KIND\_PARAM \=.  
  
 addr.addrArrayElem  
 \[C \+ \+에만\] 포함 되어 있는[METADATA\_ADDRESS\_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md) 경우 구성 `dwKind` ADDRESS\_KIND\_ARRAYELEM \=.  
  
 addr.addrRetVal  
 \[C \+ \+에만\] 포함 되어 있는[METADATA\_ADDRESS\_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md) 경우 구성 `dwKind` ADDRESS\_KIND\_RETVAL \=.  
  
 addr.unused  
 \[C \+ \+에만\] 안쪽 여백입니다.  
  
 대상 주소  
 \[C \+ \+에만\] 공용 구조체의 이름입니다.  
  
 unionmember  
 \[C\#만\] 이 값을 기준으로 적절 한 구조 유형을 마샬링할 수 해야 `dwKind`.  사이의 연결에 대 한 설명 부분을 참조 하십시오. `dwKind` 및 통합 해석 합니다.  
  
## 설명  
 이 구조에 속하지는 [DEBUG\_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) 구조와 여러 가지 종류의 주소 중 하나를 나타냅니다 \(는 `DEBUG_ADDRESS` 구조는 기입을 호출 하 여 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) 메서드\).  
  
 \[C\#만\] 다음 표를 해석 하는 방법을 보여 줍니다.의 `unionmember` 멤버의 각 종류의 주소입니다.  한 종류의 주소에 대 한 방법은 보여 줍니다.  
  
|`dwKind`|`unionmember`로 해석|  
|--------------|-----------------------|  
|`ADDRESS_KIND_NATIVE`|[NATIVE\_ADDRESS](../../../extensibility/debugger/reference/native-address.md)|  
|`ADDRESS_KIND_UNMANAGED_THIS_RELATIVE`|[UNMANAGED\_ADDRESS\_THIS\_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md)|  
|`ADDRESS_KIND_UNMANAGED_PHYSICAL`|[UNMANAGED\_ADDRESS\_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md)|  
|`ADDRESS_KIND_METHOD`|[METADATA\_ADDRESS\_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md)|  
|`ADDRESS_KIND_FIELD`|[METADATA\_ADDRESS\_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md)|  
|`ADDRESS_KIND_LOCAL`|[METADATA\_ADDRESS\_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md)|  
|`ADDRESS_KIND_PARAM`|[METADATA\_ADDRESS\_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md)|  
|`ADDRESS_KIND_ARRAYELEM`|[METADATA\_ADDRESS\_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md)|  
|`ADDRESS_KIND_RETVAL`|[METADATA\_ADDRESS\_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md)|  
  
## 예제  
 한 종류의 주소를 해석 하는 방법을 보여 주는이 예제 \(`METADATA_ADDRESS_ARRAYELEM`\)의 `DEBUG_ADDRESS_UNION` C\#의 구조.  나머지 요소 정확히 같은 방식으로 해석 될 수 있습니다.  
  
```c#  
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
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG\_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)   
 [ADDRESS\_KIND](../../../extensibility/debugger/reference/address-kind.md)   
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)