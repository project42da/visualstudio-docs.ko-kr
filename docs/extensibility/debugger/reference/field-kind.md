---
title: "FIELD_KIND | Microsoft Docs"
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
  - "FIELD_KIND"
helpviewer_keywords: 
  - "FIELD_KIND 열거형"
ms.assetid: fd522b9c-52e2-42fa-939d-343347d5c3b1
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# FIELD_KIND
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

종류에 포함 된 필드의 지정 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 개체입니다.  
  
## 구문  
  
```cpp#  
enum enum_FIELD_KIND {   
   FIELD_KIND_NONE       = 0x00000000,  
  
   // Type of field  
   FIELD_KIND_TYPE       = 0x00000001,  
   FIELD_KIND_SYMBOL     = 0x00000002,  
  
   // Storage type of the field  
   FIELD_TYPE_PRIMITIVE  = 0x00000010,  
   FIELD_TYPE_STRUCT     = 0x00000020,  
   FIELD_TYPE_CLASS      = 0x00000040,  
   FIELD_TYPE_INTERFACE  = 0x00000080,  
   FIELD_TYPE_UNION      = 0x00000100,  
   FIELD_TYPE_ARRAY      = 0x00000200,  
   FIELD_TYPE_METHOD     = 0x00000400,  
   FIELD_TYPE_BLOCK      = 0x00000800,  
   FIELD_TYPE_POINTER    = 0x00001000,  
   FIELD_TYPE_ENUM       = 0x00002000,  
   FIELD_TYPE_LABEL      = 0x00004000,  
   FIELD_TYPE_TYPEDEF    = 0x00008000,  
   FIELD_TYPE_BITFIELD   = 0x00010000,  
   FIELD_TYPE_NAMESPACE  = 0x00020000,  
   FIELD_TYPE_MODULE     = 0x00040000,  
   FIELD_TYPE_DYNAMIC    = 0x00080000,  
   FIELD_TYPE_PROP       = 0x00100000,  
   FIELD_TYPE_INNERCLASS = 0x00200000,  
   FIELD_TYPE_REFERENCE  = 0x00400000,  
   FIELD_TYPE_EXTENDED   = 0x00800000,  
  
   // Specific information about symbols  
   FIELD_SYM_MEMBER      = 0x01000000,  
   FIELD_SYM_LOCAL       = 0x02000000,  
   FIELD_SYM_PARAM       = 0x04000000,  
   FIELD_SYM_THIS        = 0x08000000,  
   FIELD_SYM_GLOBAL      = 0x10000000,  
   FIELD_SYM_PROP_GETTER = 0x20000000,  
   FIELD_SYM_PROP_SETTER = 0x40000000,  
   FIELD_SYM_EXTENDED    = 0x80000000,  
  
   FIELD_KIND_MASK       = 0x0000000f,  
   FIELD_TYPE_MASK       = 0x00fffff0,  
   FIELD_SYM_MASK        = 0xff000000,  
  
   FIELD_KIND_ALL        = 0xffffffff  
};  
typedef DWORD FIELD_KIND;  
```  
  
```c#  
public enum enum_FIELD_KIND {  
   FIELD_KIND_NONE       = 0x00000000,  
  
   // Type of field  
   FIELD_KIND_TYPE       = 0x00000001,  
   FIELD_KIND_SYMBOL     = 0x00000002,  
  
   // Storage type of the field  
   FIELD_TYPE_PRIMITIVE  = 0x00000010,  
   FIELD_TYPE_STRUCT     = 0x00000020,  
   FIELD_TYPE_CLASS      = 0x00000040,  
   FIELD_TYPE_INTERFACE  = 0x00000080,  
   FIELD_TYPE_UNION      = 0x00000100,  
   FIELD_TYPE_ARRAY      = 0x00000200,  
   FIELD_TYPE_METHOD     = 0x00000400,  
   FIELD_TYPE_BLOCK      = 0x00000800,  
   FIELD_TYPE_POINTER    = 0x00001000,  
   FIELD_TYPE_ENUM       = 0x00002000,  
   FIELD_TYPE_LABEL      = 0x00004000,  
   FIELD_TYPE_TYPEDEF    = 0x00008000,  
   FIELD_TYPE_BITFIELD   = 0x00010000,  
   FIELD_TYPE_NAMESPACE  = 0x00020000,  
   FIELD_TYPE_MODULE     = 0x00040000,  
   FIELD_TYPE_DYNAMIC    = 0x00080000,  
   FIELD_TYPE_PROP       = 0x00100000,  
   FIELD_TYPE_INNERCLASS = 0x00200000,  
   FIELD_TYPE_REFERENCE  = 0x00400000,  
   FIELD_TYPE_EXTENDED   = 0x00800000,  
  
   // Specific information about symbols  
   FIELD_SYM_MEMBER      = 0x01000000,  
   FIELD_SYM_LOCAL       = 0x02000000,  
   FIELD_SYM_PARAM       = 0x04000000,  
   FIELD_SYM_THIS        = 0x08000000,  
   FIELD_SYM_GLOBAL      = 0x10000000,  
   FIELD_SYM_PROP_GETTER = 0x20000000,  
   FIELD_SYM_PROP_SETTER = 0x40000000,  
   FIELD_SYM_EXTENDED    = 0x80000000,  
  
   FIELD_KIND_MASK       = 0x0000000f,  
   FIELD_TYPE_MASK       = 0x00fffff0,  
   FIELD_SYM_MASK        = 0xff000000,  
  
   FIELD_KIND_ALL        = 0xffffffff  
};  
```  
  
## Members  
 FIELD\_KIND\_TYPE  
 필드는 형식입니다.  
  
 FIELD\_KIND\_SYMBOL  
 필드 형식, 이름 및 기타 정보를 기호입니다.  
  
 FIELD\_TYPE\_PRIMITIVE  
 필드의 기본 데이터 형식입니다.  
  
 FIELD\_TYPE\_STRUCT  
 구조체의 필드입니다.  
  
 FIELD\_TYPE\_CLASS  
 필드는 클래스입니다.  
  
 FIELD\_TYPE\_INTERFACE  
 인터페이스의 필드입니다.  
  
 FIELD\_TYPE\_UNION  
 공용 구조체의 필드입니다.  
  
 FIELD\_TYPE\_ARRAY  
 필드는 배열입니다.  
  
 FIELD\_TYPE\_METHOD  
 메서드 필드입니다.  
  
 FIELD\_TYPE\_BLOCK  
 필드 블록입니다.  
  
 FIELD\_TYPE\_POINTER  
 필드에 대 한 포인터입니다.  
  
 FIELD\_TYPE\_ENUM  
 필드는 열거형된 데이터 형식입니다.  
  
 FIELD\_TYPE\_LABEL  
 레이블 필드에 있음을 나타냅니다.  
  
 FIELD\_TYPE\_TYPEDEF  
 필드 형식 정의 임을 나타냅니다.  
  
 FIELD\_TYPE\_BITFIELD  
 필드를 비트 필드입니다.  
  
 FIELD\_TYPE\_NAMESPACE  
 네임 스페이스 필드에 있음을 나타냅니다.  
  
 FIELD\_TYPE\_MODULE  
 모듈의 필드입니다.  
  
 FIELD\_TYPE\_DYNAMIC  
 필드는 동적입니다.  
  
 FIELD\_TYPE\_PROP  
 필드 속성입니다.  
  
 FIELD\_TYPE\_INNERCLASS  
 필드는 내부 클래스입니다.  
  
 FIELD\_TYPE\_REFERENCE  
 필드에 대 한 참조입니다.  
  
 FIELD\_TYPE\_EXTENDED  
 다음에 사용하도록 예약됩니다.  
  
 FIELD\_SYM\_MEMBER  
 필드 멤버입니다.  
  
 FIELD\_SYM\_LOCAL  
 로컬 필드 임을 나타냅니다.  
  
 FIELD\_SYM\_PARAMETER  
 매개 변수 필드 임을 나타냅니다.  
  
 FIELD\_SYM\_THIS  
 "This"이 포인터의 필드입니다.  
  
 FIELD\_SYM\_GLOBAL  
 전역 필드에 있음을 나타냅니다.  
  
 FIELD\_SYM\_PROP\_GETTER  
 필드 속성을 검색을 나타냅니다.  
  
 FIELD\_SYM\_PROP\_SETTER  
 필드 속성 설정 하는 것을 나타냅니다.  
  
 FIELD\_SYM\_EXTENDED  
 다음에 사용하도록 예약됩니다.  
  
 FIELD\_KIND\_MASK  
 필드 종류에 대 한 마스크를 나타냅니다.  
  
 FIELD\_TYPE\_MASK  
 필드 형식에 대 한 마스크를 나타냅니다.  
  
 FIELD\_SYM\_MASK  
 기호 정보에 대 한 마스크를 나타냅니다.  
  
## 설명  
 에 대 한 호출에서 반환 되는 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 방법입니다.  
  
 필드의 종류에 따라 [QueryInterface](/visual-cpp/atl/queryinterface) 를 호출할 수는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스는 특정 형태의 인터페이스에 대 한.  예를 들어, 경우 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 반환 `FIELD_TYPE_METHOD`, 다음 호출할 수 있습니다 `QueryInterface` 에서 내가`DebugField` 얻을 수 있는 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) 인터페이스.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FIELD\_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)   
 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)