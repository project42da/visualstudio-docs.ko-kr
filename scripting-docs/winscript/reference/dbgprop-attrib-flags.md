---
title: DBGPROP_ATTRIB_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- DBGPROP_ATTRIB_FLAGS
apilocation:
- scrobj.dll
f1_keywords:
- DBGPROP_ATTRIB_FLAGS
helpviewer_keywords:
- DBGPROP_ATTRIB_FLAGS
ms.assetid: 90314496-527b-4357-9df8-125a360bf216
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 43db6cd118e2097d857d5c41334341c595088302
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="dbgpropattribflags"></a>DBGPROP_ATTRIB_FLAGS
`IDebugProperty`의 여러 특성에 대해 설명합니다. `DebugPropertyInfo` 구조체의 멤버입니다.  
  
## <a name="syntax"></a>구문  
  
```  
enum {  
DBGPROP_ATTRIB_NO_ATTRIB  =0x00000000,  
   DBGPROP_ATTRIB_VALUE_IS_INVALID  =0x00000008,  
   DBGPROP_ATTRIB_VALUE_IS_EXPANDABLE  =0x00000010,  
   DBGPROP_ATTRIB_VALUE_READONLY  =0x00000800,  
   DBGPROP_ATTRIB_ACCESS_PUBLIC  =0x00001000,  
   DBGPROP_ATTRIB_ACCESS_PRIVATE  =0x00002000,  
   DBGPROP_ATTRIB_ACCESS_PROTECTED  =0x00004000,  
   DBGPROP_ATTRIB_ACCESS_FINAL  =0x00008000,  
   DBGPROP_ATTRIB_STORAGE_GLOBAL  =0x00010000,  
   DBGPROP_ATTRIB_STORAGE_STATIC  =0x00020000,  
   DBGPROP_ATTRIB_STORAGE_FIELD  =0x00040000,  
   DBGPROP_ATTRIB_STORAGE_VIRTUAL  =0x00080000,  
   DBGPROP_ATTRIB_TYPE_IS_CONSTANT  =0x00100000,  
   DBGPROP_ATTRIB_TYPE_IS_SYNCHRONIZED  =0x00200000,  
   DBGPROP_ATTRIB_TYPE_IS_VOLATILE  =0x00400000,  
   DBGPROP_ATTRIB_HAS_EXTENDED_ATTRIBS  =0x00800000  
   DBGPROP_ATTRIB_VALUE_IS_RETURN_VALUE  =0x08000000,  
};  
  
```  
  
## <a name="members"></a>멤버  
 DBGPROP_ATTRIB_NO_ATTRIB  
 특성이 없음을 나타냅니다.  
  
 DBGPROP_ATTRIB_VALUE_IS_INVALID  
 `DebugPropertyInfo::bstrValue`의 값이 유효하지 않음을 나타냅니다.  
  
 DBGPROP_ATTRIB_VALUE_IS_EXPANDABLE  
 참조 또는 속성에 자식이 있음을 나타냅니다.  
  
 DBGPROP_ATTRIB_VALUE_READONLY  
 값이 읽기 전용임을 나타냅니다.  
  
 DBGPROP_ATTRIB_ACCESS_PUBLIC  
 공용 액세스 권한이 있는 개체를 나타냅니다.  
  
 DBGPROP_ATTRIB_ACCESS_PRIVATE  
 개인 액세스 권한이 있는 개체를 나타냅니다.  
  
 DBGPROP_ATTRIB_ACCESS_PROTECTED  
 보호 액세스 권한이 있는 개체를 나타냅니다.  
  
 DBGPROP_ATTRIB_ACCESS_FINAL  
 최종 액세스 권한이 있는 개체를 나타냅니다.  
  
 DBGPROP_ATTRIB_STORAGE_GLOBAL  
 전역 저장소를 나타냅니다.  
  
 DBGPROP_ATTRIB_STORAGE_STATIC  
 정적 저장소를 나타냅니다.  
  
 DBGPROP_ATTRIB_STORAGE_FIELD  
 속성인 개체를 나타냅니다.  
  
 DBGPROP_ATTRIB_STORAGE_VIRTUAL  
 가상 저장소를 나타냅니다.  
  
 DBGPROP_ATTRIB_TYPE_IS_CONSTANT  
 개체 형식이 상수임을 나타냅니다.  
  
 DBGPROP_ATTRIB_TYPE_IS_SYNCHRONIZED  
 이 슬롯이 스레드와 동기화되어 있음을 나타냅니다.  
  
 DBGPROP_ATTRIB_TYPE_IS_VOLATILE  
 이 슬롯이 영구 저장소에 대해 일시적임을 나타냅니다.  
  
 DBGPROP_ATTRIB_HAS_EXTENDED_ATTRIBS  
 이 슬롯에 이러한 미리 정의된 비트 이상의 추가 특성이 있음을 나타냅니다.  
  
 DBGPROP_ATTRIB_VALUE_IS_RETURN_VALUE  
 값이 함수의 반환 값임을 나타냅니다.  
  
## <a name="remarks"></a>설명  
 개체의 자식을 필터링할 때도 이러한 플래그를 사용합니다. 비트 OR을 사용하여 값을 결합할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)   
 [DebugPropertyInfo 구조체](../../winscript/reference/debugpropertyinfo-structure.md)