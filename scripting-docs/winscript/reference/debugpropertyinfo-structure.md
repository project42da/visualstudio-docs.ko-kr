---
title: "DebugPropertyInfo 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: DebugPropertyInfo
apilocation: scrobj.dll
helpviewer_keywords: DebugPropertyInfo structure
ms.assetid: 3246efbc-c212-4024-8f07-6414c2f85e75
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9baade1a742a06c952906c05c574e752806bc9c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="debugpropertyinfo-structure"></a>DebugPropertyInfo 구조체
개체 이름, 형식 및 값을 가진 계층적 특성에 설명 합니다. 지역 변수, 매개 변수, 조사식 변수 및 식의 디버그 속성을 설명 하는 데 사용 하 고 등록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct DebugPropertyInfo{  
   DBGPROP_INFO_FLAGS  dwValidFields;  
   BSTR  bstrName;  
   BSTR  bstrType;  
   BSTR  bstrValue;  
   BSTR  bstrFullName;  
   DBGPROP_ATTRIB_FLAGS  dwAttrib;  
   IDebugProperty*  pDebugProp;  
};  
```  
  
## <a name="members"></a>멤버  
 dwValidFields  
 초기화 되는 필드를 지정 하는 데 사용 하는 열거형된 데이터 형식입니다.  
  
 bstrName  
 컨텍스트 내에서 속성 이름입니다.  
  
 bstrType  
 속성 형식, 서식이 지정 된 문자열입니다.  
  
 bstrValue  
 속성 값으로 형식이 지정 된 문자열입니다.  
  
 bstrFullName  
 속성의 전체 이름입니다.  
  
 dwAttrib  
 디버그 속성 특성에 대 한 플래그를 지정 하는 열거형입니다.  
  
 pDebugProp  
 `IDebugProperty` 이 정보에 의해 설명 된 `DebugPropertyInfo` 구조입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)   
 [DBGPROP_ATTRIB_FLAGS](../../winscript/reference/dbgprop-attrib-flags.md)   
 [DBGPROP_INFO_FLAGS](../../winscript/reference/dbgprop-info-flags.md)