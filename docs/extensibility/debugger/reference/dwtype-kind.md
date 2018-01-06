---
title: dwTYPE_KIND | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: dwTYPE_KIND
helpviewer_keywords: dwTYPE_KIND enumeration
ms.assetid: 6ff56b0f-c502-4e6c-9829-bfa05361b783
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 97136c781fa0ba6b3eb79250a4ecbe0bd2e4e694
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="dwtypekind"></a>dwTYPE_KIND
형식을 해석 하는 방법을 지정는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_dwTYPE_KIND {  
   TYPE_KIND_METADATA = 0x0001,  
   TYPE_KIND_PDB      = 0x0002,  
   TYPE_KIND_BUILT    = 0x0003,  
};  
  
typedef DWORD dwTYPE_KIND;  
```  
  
```csharp  
public enum enum_dwTYPE_KIND {  
   TYPE_KIND_METADATA = 0x0001,  
   TYPE_KIND_PDB      = 0x0002,  
   TYPE_KIND_BUILT    = 0x0003,  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 TYPE_KIND_METADATA  
 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) union으로 해석할지는 [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md) 구조입니다.  
  
 TYPE_KIND_PDB  
 `TYPE_INFO` union으로 해석할지는 [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md) 구조입니다.  
  
 TYPE_KIND_BUILT  
 `TYPE_INFO` union으로 해석할지는 [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md) 구조입니다.  
  
## <a name="remarks"></a>설명  
 이 열거형의 값에 표시는 `dwKind` 필드는 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) 구조체를 해석 하는 방법을 결정 하는 데 사용 되는 `type` 공용 구조체 멤버입니다. `TYPE_INFO` 에 대 한 호출에서 반환 된 [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)   
 [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)   
 [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md)   
 [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md)   
 [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md)