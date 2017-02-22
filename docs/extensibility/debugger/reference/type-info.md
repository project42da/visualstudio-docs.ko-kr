---
title: "TYPE_INFO | Microsoft Docs"
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
  - "TYPE_INFO"
helpviewer_keywords: 
  - "TYPE_INFO 구조"
ms.assetid: d725cb68-a565-49d1-a16f-ff0445c587a0
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# TYPE_INFO
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 구조가 다양 한 종류의 필드 형식에 대 한 정보를 지정합니다.  
  
## 구문  
  
```cpp#  
struct _tagTYPE_INFO_UNION {  
   dwTYPE_KIND dwKind;  
   union {  
      METADATA_TYPE typeMeta;  
      PDB_TYPE      typePdb;  
      BUILT_TYPE    typeBuilt;  
      DWORD         unused;  
   } type;  
} TYPE_INFO;  
```  
  
```c#  
public struct TYPE_INFO {  
   public uint   dwKind;  
   public IntPtr unionmember;  
};  
```  
  
#### 매개 변수  
 dwKind  
 값은 [dwTYPE\_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) 통합 해석 하는 방법을 결정 하는 열거형입니다.  
  
 type.typeMeta  
 \[C \+ \+에만\] Contains a [METADATA\_TYPE](../../../extensibility/debugger/reference/metadata-type.md) structure if `dwKind` is `TYPE_KIND_METADATA`.  
  
 type.typePdb  
 \[C \+ \+에만\] Contains a [PDB\_TYPE](../../../extensibility/debugger/reference/pdb-type.md) structure if `dwKind` is `TYPE_KIND_PDB`.  
  
 type.typeBuilt  
 \[C \+ \+에만\] Contains a [BUILT\_TYPE](../../../extensibility/debugger/reference/built-type.md) structure if `dwKind` is `TYPE_KIND_BUILT`.  
  
 type.unused  
 사용 하지 않는 안쪽 여백입니다.  
  
 type  
 공용 구조체의 이름입니다.  
  
 unionmember  
 \[C\#만\] 마샬이 유형에 적합 한 구조를 기반으로 한 `dwKind`.  
  
## 설명  
 이 구조체에 전달 되는 [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md) 메서드는 입력 위치에 있습니다.  구조체의 내용을 해석 하는 방법에 따라 해당 `dwKind` 필드입니다.  
  
> [!NOTE]
>  \[C \+ \+에만\] 경우 `dwKind` 인 `TYPE_KIND_BUILT`, 내부를 해제 하 고 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 파괴 하는 경우 개체는 `TYPE_INFO` 구조입니다.  이 호출 하 여 수행 됩니다 `typeInfo.type.typeBuilt.pUnderlyingField->Release()`.  
  
 \[C\#만\] 다음 표를 해석 하는 방법을 보여 줍니다 있는 `unionmember` 각 종류의 형식에 대 한 멤버.  한 종류의 형식에 대 한 방법은 보여 줍니다.  
  
|`dwKind`|`unionmember`로 해석|  
|--------------|-----------------------|  
|`TYPE_KIND_METADATA`|[METADATA\_TYPE](../../../extensibility/debugger/reference/metadata-type.md)|  
|`TYPE_KIND_PDB`|[PDB\_TYPE](../../../extensibility/debugger/reference/pdb-type.md)|  
|`TYPE_KIND_BUILT`|[BUILT\_TYPE](../../../extensibility/debugger/reference/built-type.md)|  
  
## 예제  
 해석 하는 방법을 보여 주는이 예제는 `unionmember` 의 멤버는 `TYPE_INFO` 구조에 C\#.  보여 주는이 예제를 해석 하는 한 가지 종류 \(`TYPE_KIND_METADATA`\) 다른 정확 하 게 같은 방식으로 해석 됩니다.  
  
```c#  
using System;  
using System.Runtime.Interop.Services;  
using Microsoft.VisualStudio.Debugger.Interop;  
  
namespace MyPackage  
{  
    public class MyClass  
    {  
        public void Interpret(TYPE_INFO ti)  
        {  
            if (ti.dwKind == (uint)enum_dwTypeKind.TYPE_KIND_METADATA)  
            {  
                 METADATA_TYPE dataType = (METADATA_TYPE)Marshal.PtrToStructure(ti.unionmember,  
                                               typeof(METADATA_TYPE));  
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
 [dwTYPE\_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)   
 [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)   
 [METADATA\_TYPE](../../../extensibility/debugger/reference/metadata-type.md)   
 [PDB\_TYPE](../../../extensibility/debugger/reference/pdb-type.md)   
 [BUILT\_TYPE](../../../extensibility/debugger/reference/built-type.md)