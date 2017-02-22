---
title: "FIELD_MODIFIERS | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FIELD_MODIFIERS"
helpviewer_keywords: 
  - "FIELD_MODIFIERS 열거형"
ms.assetid: 1e44681c-1f03-41a9-9c04-b79f231b0822
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# FIELD_MODIFIERS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

필드 형식에 대 한 한정자를 지정합니다.  
  
## 구문  
  
```cpp#  
enum enum_FIELD_MODIFIERS {   
   FIELD_MOD_NONE             = 0x00000000,  
  
   // Modifier of the field  
   FIELD_MOD_ACCESS_NONE      = 0x00000001,  
   FIELD_MOD_ACCESS_PUBLIC    = 0x00000002,  
   FIELD_MOD_ACCESS_PROTECTED = 0x00000004,  
   FIELD_MOD_ACCESS_PRIVATE   = 0x00000008,  
  
   // Storage modifier of the field  
   FIELD_MOD_NOMODIFIERS      = 0x00000010,  
   FIELD_MOD_STATIC           = 0x00000020,  
   FIELD_MOD_CONSTANT         = 0x00000040,  
   FIELD_MOD_TRANSIENT        = 0x00000080,  
   FIELD_MOD_VOLATILE         = 0x00000100,  
   FIELD_MOD_ABSTRACT         = 0x00000200,  
   FIELD_MOD_NATIVE           = 0x00000400,  
   FIELD_MOD_SYNCHRONIZED     = 0x00000800,  
   FIELD_MOD_VIRTUAL          = 0x00001000,  
   FIELD_MOD_INTERFACE        = 0x00002000,  
   FIELD_MOD_FINAL            = 0x00004000,  
   FIELD_MOD_SENTINEL         = 0x00008000,  
   FIELD_MOD_INNERCLASS       = 0x00010000,  
   FIELD_TYPE_OPTIONAL        = 0x00020000,  
   FIELD_MOD_BYREF            = 0x00040000,  
   FIELD_MOD_HIDDEN           = 0x00080000,  
   FIELD_MOD_MARSHALASOBJECT  = 0x00100000,  
   FIELD_MOD_SPECIAL_NAME     = 0x00200000,  
   FIELD_MOD_HIDEBYSIG        = 0x00400000,  
  
   FIELD_MOD_WRITEONLY        = 0x80000000,  
   FIELD_MOD_ACCESS_MASK      = 0x000000ff,  
   FIELD_MOD_MASK             = 0xffffff00,  
   FIELD_MOD_ALL              = 0x7fffffff  
};  
typedef DWORD FIELD_MODIFIERS;  
```  
  
```c#  
public enum enum_FIELD_MODIFIERS {  
   FIELD_MOD_NONE             = 0x00000000,  
  
   // Modifier of the field  
   FIELD_MOD_ACCESS_NONE      = 0x00000001,  
   FIELD_MOD_ACCESS_PUBLIC    = 0x00000002,  
   FIELD_MOD_ACCESS_PROTECTED = 0x00000004,  
   FIELD_MOD_ACCESS_PRIVATE   = 0x00000008,  
  
   // Storage modifier of the field  
   FIELD_MOD_NOMODIFIERS      = 0x00000010,  
   FIELD_MOD_STATIC           = 0x00000020,  
   FIELD_MOD_CONSTANT         = 0x00000040,  
   FIELD_MOD_TRANSIENT        = 0x00000080,  
   FIELD_MOD_VOLATILE         = 0x00000100,  
   FIELD_MOD_ABSTRACT         = 0x00000200,  
   FIELD_MOD_NATIVE           = 0x00000400,  
   FIELD_MOD_SYNCHRONIZED     = 0x00000800,  
   FIELD_MOD_VIRTUAL          = 0x00001000,  
   FIELD_MOD_INTERFACE        = 0x00002000,  
   FIELD_MOD_FINAL            = 0x00004000,  
   FIELD_MOD_SENTINEL         = 0x00008000,  
   FIELD_MOD_INNERCLASS       = 0x00010000,  
   FIELD_TYPE_OPTIONAL        = 0x00020000,  
   FIELD_MOD_BYREF            = 0x00040000,  
   FIELD_MOD_HIDDEN           = 0x00080000,  
   FIELD_MOD_MARSHALASOBJECT  = 0x00100000,  
   FIELD_MOD_SPECIAL_NAME     = 0x00200000,  
   FIELD_MOD_HIDEBYSIG        = 0x00400000,  
  
   FIELD_MOD_WRITEONLY        = 0x80000000,  
   FIELD_MOD_ACCESS_MASK      = 0x000000ff,  
   FIELD_MOD_MASK             = 0xffffff00,  
   FIELD_MOD_ALL              = 0x7fffffff  
};  
```  
  
## Members  
 FIELD\_MOD\_ACCESS\_TYPE  
 필드에 액세스할 수 없음을 나타냅니다.  
  
 FIELD\_MOD\_ACCESS\_PUBLIC  
 필드가 public 액세스 했음을 나타냅니다.  
  
 FIELD\_MOD\_ACCESS\_PROTECTED  
 필드 액세스 보호 된 것을 나타냅니다.  
  
 FIELD\_MOD\_ACCESS\_PRIVATE  
 필드는 private 액세스 했음을 나타냅니다.  
  
 FIELD\_MOD\_NOMODIFIERS  
 필드 한정자가 없습니다 있음을 나타냅니다.  
  
 FIELD\_MOD\_STATIC  
 정적 필드 인지를 나타냅니다.  
  
 FIELD\_MOD\_CONSTANT  
 필드는 상수입니다.  
  
 FIELD\_MOD\_TRANSIENT  
 필드는 일시적입니다.  
  
 FIELD\_MOD\_VOLATILE  
 Volatile 필드 임을 나타냅니다.  
  
 FIELD\_MOD\_ABSTRACT  
 추상 필드 임을 나타냅니다.  
  
 FIELD\_MOD\_NATIVE  
 필드 전용입니다.  
  
 FIELD\_MOD\_SYNCHRONIZED  
 동기화 필드를 나타냅니다.  
  
 FIELD\_MOD\_VIRTUAL  
 가상 필드 임을 나타냅니다.  
  
 FIELD\_MOD\_INTERFACE  
 인터페이스의 필드입니다.  
  
 FIELD\_MOD\_FINAL  
 Final 필드 임을 나타냅니다.  
  
 FIELD\_MOD\_SENTINEL  
 필드 sentinel입니다.  
  
 FIELD\_MOD\_INNERCLASS  
 필드는 내부 클래스입니다.  
  
 FIELD\_TYPE\_OPTIONAL  
 선택적 필드 임을 나타냅니다.  
  
 FIELD\_MOD\_BYREF  
 필드 참조 인수입니다.  메서드 인수에 대 한 구체적입니다.  
  
 FIELD\_MOD\_HIDDEN  
 필드 숨김 하거나 다른 컨텍스트에서 제공 해야 한다는 나타냅니다. 예를 들어, [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] 정적 지역 변수입니다.  
  
 FIELD\_MOD\_MARSHALASOBJECT  
 필드 개체를 나타내는 `IUnknown` 인터페이스입니다.  
  
 FIELD\_MOD\_SPECIAL\_NAME  
 필드에 특별 한 이름을 예를 들어,이 나타내는 `.ctor` 생성자에 \([!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] 만\).  
  
 FIELD\_MOD\_HIDEBYSIG  
 필드 이면의 `Overloads` 키워드 적용 \([!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)] 만\).  
  
 FIELD\_MOD\_WRITEONLY  
 쓰기 전용 필드에 있음을 나타냅니다.  이 값에 포함 되지 않습니다 `FIELD_MOD_ALL`와 같은 쓰기 전용 필드를 사용 하는 유일한 함수 실행을 있는 그대로입니다.  사용자가 명시적으로 요청 해야 합니다 `FIELD_MOD_WRITEONLY` 필드입니다.  
  
 FIELD\_MOD\_ACCESS\_MASK  
 필드 액세스에 대 한 마스크를 나타냅니다.  
  
 FIELD\_MOD\_MASK  
 필드 한정자에 대 한 마스크를 나타냅니다.  
  
## 설명  
 사용 되는 `dwModifiers` 의 멤버는 [FIELD\_INFO](../../../extensibility/debugger/reference/field-info.md) 구조.  
  
 이러한 값도 전달 되는 [EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md) 특정 필드를 필터링 하는 방법입니다.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FIELD\_INFO](../../../extensibility/debugger/reference/field-info.md)   
 [EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)