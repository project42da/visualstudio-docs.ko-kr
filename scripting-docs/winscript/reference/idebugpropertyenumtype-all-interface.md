---
title: "IDebugPropertyEnumType_All 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugPropertyEnumType_All
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDebugPropertyEnumType_All 인터페이스"
ms.assetid: 4d0f4fd5-e5f7-47cb-b746-860d6363e2cd
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugPropertyEnumType_All 인터페이스
`IDebugPropertyEnumType` 인터페이스는 Iid의 각 필터에 전달할 수 있도록 정의 `IDebugProperty::EnumMembers` 해당 열거자가 요청 하는 동안.  
  
## 구문  
  
```  
IDebugPropertyEnumType_All : IUnknown  
```  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugPropertyEnumType\_All::GetName](../../winscript/reference/idebugpropertyenumtype-all-getname.md)|이름을 설명 하는 텍스트 문자열을 반환 합니다.|  
  
 다음 인터페이스 상속 `IDebugPropertyEnumType_All`, 및 다른 메서드가 있습니다.  
  
```  
IDebugPropertyEnumType_Arguments : IDebugPropertyEnumType_All   
IDebugPropertyEnumType_Locals : IDebugPropertyEnumType_All   
IDebugPropertyEnumType_LocalsPlusArgs : IDebugPropertyEnumType_All   
IDebugPropertyEnumType_Registers : IDebugPropertyEnumType_All  
```  
  
## 참고 항목  
 [IDebugProperty::EnumMembers](../../winscript/reference/idebugproperty-enummembers.md)