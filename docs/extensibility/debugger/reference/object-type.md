---
title: "OBJECT_TYPE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OBJECT_TYPE"
helpviewer_keywords: 
  - "OBJECT_TYPE 열거형"
ms.assetid: c4d246f9-8a98-44ec-b2bb-ff5c684f668e
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# OBJECT_TYPE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

식 계산기에서 개체의 형식을 지정합니다.  
  
## 구문  
  
```cpp#  
enum enum_OBJECT_TYPE {   
   OBJECT_TYPE_BOOLEAN = 0x0,  
   OBJECT_TYPE_CHAR    = 0x1,  
   OBJECT_TYPE_I1      = 0x2,  
   OBJECT_TYPE_U1      = 0x3,  
   OBJECT_TYPE_I2      = 0x4,  
   OBJECT_TYPE_U2      = 0x5,  
   OBJECT_TYPE_I4      = 0x6,  
   OBJECT_TYPE_U4      = 0x7,  
   OBJECT_TYPE_I8      = 0x8,  
   OBJECT_TYPE_U8      = 0x9,  
   OBJECT_TYPE_R4      = 0xa,  
   OBJECT_TYPE_R8      = 0xb,  
   OBJECT_TYPE_OBJECT  = 0xc,  
   OBJECT_TYPE_NULL    = 0xd,  
   OBJECT_TYPE_CLASS   = 0xe  
};  
typedef DWORD OBJECT_TYPE;  
```  
  
```c#  
public enum enum_OBJECT_TYPE {   
   OBJECT_TYPE_BOOLEAN = 0x0,  
   OBJECT_TYPE_CHAR    = 0x1,  
   OBJECT_TYPE_I1      = 0x2,  
   OBJECT_TYPE_U1      = 0x3,  
   OBJECT_TYPE_I2      = 0x4,  
   OBJECT_TYPE_U2      = 0x5,  
   OBJECT_TYPE_I4      = 0x6,  
   OBJECT_TYPE_U4      = 0x7,  
   OBJECT_TYPE_I8      = 0x8,  
   OBJECT_TYPE_U8      = 0x9,  
   OBJECT_TYPE_R4      = 0xa,  
   OBJECT_TYPE_R8      = 0xb,  
   OBJECT_TYPE_OBJECT  = 0xc,  
   OBJECT_TYPE_NULL    = 0xd,  
   OBJECT_TYPE_CLASS   = 0xe  
};  
```  
  
## Members  
 OBJECT\_TYPE\_BOOLEAN  
 Boolean 개체입니다.  
  
 OBJECT\_TYPE\_CHAR  
 개체의 문자입니다.  
  
 OBJECT\_TYPE\_I1  
 1 바이트 부호 있는 정수 개체입니다.  
  
 OBJECT\_TYPE\_U1  
 1 바이트 부호 없는 정수 개체입니다.  
  
 OBJECT\_TYPE\_I2  
 2 바이트 부호 있는 정수 개체입니다.  
  
 OBJECT\_TYPE\_U2  
 2 바이트 부호 없는 정수 개체입니다.  
  
 OBJECT\_TYPE\_I4  
 4 바이트 부호 있는 정수 개체입니다.  
  
 OBJECT\_TYPE\_U4  
 4 바이트 부호 없는 정수 개체입니다.  
  
 OBJECT\_TYPE\_I8  
 개체는 8 바이트 부호 있는 정수입니다.  
  
 OBJECT\_TYPE\_U8  
 개체는 8 바이트 부호 없는 정수입니다.  
  
 OBJECT\_TYPE\_R4  
 4 바이트 부동 소수점 숫자 개체입니다.  
  
 OBJECT\_TYPE\_R8  
 개체는 8 바이트 부동 소수점 수입니다.  
  
 OBJECT\_TYPE\_OBJECT  
 개체는 개체입니다.  
  
 OBJECT\_TYPE\_NULL  
 개체가 NULL입니다.  
  
 OBJECT\_TYPE\_CLASS  
 개체 클래스입니다.  
  
## 설명  
 인수로 전달 되는 [CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md) 및 [CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md) 방법입니다.  
  
## 요구 사항  
 헤더: ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md)   
 [CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md)