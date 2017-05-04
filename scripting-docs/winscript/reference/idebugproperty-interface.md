---
title: "IDebugProperty 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugProperty 인터페이스"
ms.assetid: 7e8f5341-23ef-4029-814d-f5c2307b9203
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugProperty 인터페이스
계층적 속성 디버깅 되는 엔터티의 이름, 유형 및 값이 설명 하는 데 사용 합니다.  가장 일반적으로 `IDebugProperty` 식 평가, 문 평가 또는 레지스터 평가의 결과 설명 하는 데 사용 됩니다.  
  
## Vtable 순서의 메서드  
 메서드는 다음 표에 나와 있는 `IDebugProperty` 인터페이스.  
  
|메서드|설명|  
|---------|--------|  
|[IDebugProperty::GetPropertyInfo](../../winscript/reference/idebugproperty-getpropertyinfo.md)|가져오기는 `DebugPropertyInfo` 는이 설명`IDebugProperty``.`|  
|[IDebugProperty::GetExtendedInfo](../../winscript/reference/idebugproperty-getextendedinfo.md)|확장된 속성 정보를 가져옵니다.|  
|[IDebugProperty::SetValueAsString](../../winscript/reference/idebugproperty-setvalueasstring.md)|문자열에서 속성의 값을 설정합니다.|  
|[IDebugProperty::EnumMembers](../../winscript/reference/idebugproperty-enummembers.md)|속성의 구성원을 열거합니다.|  
|[IDebugProperty::GetParent](../../winscript/reference/idebugproperty-getparent.md)|부모를 속성을 가져옵니다.|  
  
## 요구 사항  
 헤더: dbgprop.h