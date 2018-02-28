---
title: "IDebugPropertyEnumType_All 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDebugPropertyEnumType_All
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugPropertyEnumType_All interface
ms.assetid: 4d0f4fd5-e5f7-47cb-b746-860d6363e2cd
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 75de35bd42ea91e7d27523ba42c392650686041a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugpropertyenumtypeall-interface"></a>IDebugPropertyEnumType_All 인터페이스
`IDebugPropertyEnumType` 인터페이스를 정의 하는 필터로 전달 될 각 해당 Iid 있도록 `IDebugProperty::EnumMembers` 적절 한 열거자를 요청 하는 중입니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugPropertyEnumType_All : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugPropertyEnumType_All::GetName](../../winscript/reference/idebugpropertyenumtype-all-getname.md)|이름을 설명 하는 텍스트 문자열을 반환 합니다.|  
  
 다음 인터페이스에서 상속 하므로 `IDebugPropertyEnumType_All`, 있고 추가 메서드가 없습니다.  
  
```  
IDebugPropertyEnumType_Arguments : IDebugPropertyEnumType_All   
IDebugPropertyEnumType_Locals : IDebugPropertyEnumType_All   
IDebugPropertyEnumType_LocalsPlusArgs : IDebugPropertyEnumType_All   
IDebugPropertyEnumType_Registers : IDebugPropertyEnumType_All  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProperty::EnumMembers](../../winscript/reference/idebugproperty-enummembers.md)