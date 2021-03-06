---
title: "JsDebugPropertyInfo 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: JsDebugPropertyInfo
apilocation: jscript9diag.dll
ms.assetid: 3a5463a7-2013-4846-9ab2-8beb675a5a6a
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e9d2ae0d93729d4c333509e0178f4c4829ebf13
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsdebugpropertyinfo-structure"></a>JsDebugPropertyInfo 구조체
속성에 대한 정보를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct tagJsDebugPropertyInfo{   BSTR name;   BSTR type;   BSTR value;   BSTR fullName;   JS_PROPERTY_ATTRIBUTES attr;} JsDebugPropertyInfo;  
```  
  
## <a name="members"></a>멤버  
 `name`  
 속성의 이름입니다.  
  
 `type`  
 속성의 형식입니다.  
  
 `value`  
 속성 값입니다.  
  
 `fullName`  
 속성의 전체 이름입니다.  
  
 `attr`  
 속성 특성을 나타내는 열거형입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jscript9diag.h  
  
## <a name="see-also"></a>참고 항목  
 [Windows 스크립트 인터페이스 참조](../../winscript/reference/windows-script-interfaces-reference.md)