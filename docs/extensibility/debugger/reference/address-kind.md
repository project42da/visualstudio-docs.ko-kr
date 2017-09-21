---
title: "ADDRESS_KIND | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ADDRESS_KIND"
helpviewer_keywords: 
  - "ADDRESS_KIND 열거형"
ms.assetid: 3a12fbec-7088-4cf9-8f6f-ad8ddec6009a
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# ADDRESS_KIND
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

종류의 주소를 지정합니다.  
  
## 구문  
  
```cpp  
enum enum_ADDRESS_KIND {  
   ADDRESS_KIND_NATIVE                  = 0x0001,  
   ADDRESS_KIND_UNMANAGED_THIS_RELATIVE = 0x0002,  
   ADDRESS_KIND_UNMANAGED_PHYSICAL      = 0x0005,  
   ADDRESS_KIND_METADATA_METHOD         = 0x0010,  
   ADDRESS_KIND_METADATA_FIELD          = 0x0011,  
   ADDRESS_KIND_METADATA_LOCAL          = 0x0012,  
   ADDRESS_KIND_METADATA_PARAM          = 0x0013,  
   ADDRESS_KIND_METADATA_ARRAYELEM      = 0x0014,  
   ADDRESS_KIND_METADATA_RETVAL         = 0x0015,  
};  
typedef DWORD ADDRESS_KIND;  
```  
  
```c#  
public enum enum_ADDRESS_KIND {  
   ADDRESS_KIND_NATIVE                  = 0x0001,  
   ADDRESS_KIND_UNMANAGED_THIS_RELATIVE = 0x0002,  
   ADDRESS_KIND_UNMANAGED_PHYSICAL      = 0x0005,  
   ADDRESS_KIND_METADATA_METHOD         = 0x0010,  
   ADDRESS_KIND_METADATA_FIELD          = 0x0011,  
   ADDRESS_KIND_METADATA_LOCAL          = 0x0012,  
   ADDRESS_KIND_METADATA_PARAM          = 0x0013,  
   ADDRESS_KIND_METADATA_ARRAYELEM      = 0x0014,  
   ADDRESS_KIND_METADATA_RETVAL         = 0x0015,  
};  
```  
  
## 용어  
 ADDRESS\_KIND\_NATIVE  
 표시 되는 기본 주소를 [NATIVE\_ADDRESS](../../../extensibility/debugger/reference/native-address.md) 구조입니다.  
  
 ADDRESS\_KIND\_UNMANAGED\_THIS\_RELATIVE  
 관리 되지 않는 주소를 기준으로 `this` \(`Me` Visual Basic\) 포인터 및 표시 되는 [UNMANAGED\_ADDRESS\_THIS\_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md) 구조.  
  
 ADDRESS\_KIND\_UNMANAGED\_PHYSICAL  
 표시 되는 관리 되지 않는 실제 주소는 [UNMANAGED\_ADDRESS\_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md) 구조체입니다.  
  
 ADDRESS\_KIND\_METHOD  
 표시 되는 클래스의 메서드는 [METADATA\_ADDRESS\_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md) 구조입니다.  
  
 ADDRESS\_KIND\_FIELD  
 표시 되는 클래스의 필드는 [METADATA\_ADDRESS\_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md) 구조입니다.  
  
 ADDRESS\_KIND\_LOCAL  
 주소에 대 한 로컬 변수 이며 표시 됩니다 있는 [METADATA\_ADDRESS\_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md) 구조체입니다.  
  
 ADDRESS\_KIND\_PARAM  
 표시 메서드 또는 함수 매개 변수는 [METADATA\_ADDRESS\_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md) 구조입니다.  
  
 ADDRESS\_KIND\_ARRAYELEM  
 배열 요소에 표시 되는 [METADATA\_ADDRESS\_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md) 구조입니다.  
  
 ADDRESS\_KIND\_RETVAL  
 반환 값으로 표현 되는 [METADATA\_ADDRESS\_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md) 구조입니다.  
  
## 설명  
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md) 메서드가 반환의 [DEBUG\_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) 공용 구조체 가능한 구조를 포함 하는 구조는 [DEBUG\_ADDRESS\_UNION](../../../extensibility/debugger/reference/debug-address-union.md) 구조입니다.  `dwKind` 필드는 `DEBUG_ADDRESS_UNION` 저장 구조는 `ADDRESS_KIND` 값 하 고 병합 필드를 해석 하는 방법에 설명 합니다.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)   
 [DEBUG\_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)   
 [DEBUG\_ADDRESS\_UNION](../../../extensibility/debugger/reference/debug-address-union.md)