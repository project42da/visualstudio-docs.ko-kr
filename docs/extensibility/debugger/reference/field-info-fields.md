---
title: FIELD_INFO_FIELDS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FIELD_INFO_FIELDS
helpviewer_keywords:
- FIELD_INFO_FIELDS enumeration
ms.assetid: a69487d2-e701-4165-804a-8a011df9a3bd
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 95812aa634e799b5594c0cae9f4d2c3d397ca945
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="fieldinfofields"></a>FIELD_INFO_FIELDS
검색할에 대 한 정보를 지정 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_FIELD_INFO_FIELDS {   
   FIF_FULLNAME  = 0x0001,  
   FIF_NAME      = 0x0002,  
   FIF_TYPE      = 0x0004,  
   FIF_MODIFIERS = 0x0008,  
   FIF_ALL       = 0xffffffff,  
   FIF_NONE      = 0x0000  
};  
typedef DWORD FIELD_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_FIELD_INFO_FIELDS {  
   FIF_FULLNAME  = 0x0001,  
   FIF_NAME      = 0x0002,  
   FIF_TYPE      = 0x0004,  
   FIF_MODIFIERS = 0x0008,  
   FIF_ALL       = 0xffffffff,  
   FIF_NONE      = 0x0000  
};  
```  
  
## <a name="members"></a>멤버  
 FIF_FULLNAME  
 초기화/사용 된 `bstrFullName` 필드에 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) 구조입니다.  
  
 FIF_NAME  
 초기화/사용 된 `bstrName` 필드에 `FIELD_INFO` 구조입니다.  
  
 FIF_TYPE  
 초기화/사용 된 `bstrType` 필드에 `FIELD_INFO` 구조입니다.  
  
 FIF_MODIFIERS  
 초기화/사용 된 `bstrModifiers` 필드에 `FIELD_INFO` 구조입니다.  
  
## <a name="remarks"></a>설명  
 이러한 값에 인수로 전달도 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md) 의 필드를 지정 하는 메서드는 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) 구조를 초기화할 수는 있습니다.  
  
 이러한 값에도 사용 됩니다는 `dwFields` 의 멤버는 `FIELD_INFO` 구조에는 필드는 사용 되지 않으며 유효한 합니다.  
  
 이러한 플래그 비트와 함께 `OR`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)