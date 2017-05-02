---
title: "IDebugFormatter 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugFormatter 인터페이스"
ms.assetid: 022142d4-c8e1-47ae-b771-3e24953293e5
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugFormatter 인터페이스
언어 또는 IDE VARIANT 값 또는 VARTYPE 형식과 문자열 간의 변환을 사용자 지정할 수 있습니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugFormatter` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugFormatter::GetStringForVariant](../../winscript/reference/idebugformatter-getstringforvariant.md)|지정 된 VARIANT 값을 나타내는 string을 반환 합니다.|  
|[IDebugFormatter::GetVariantForString](../../winscript/reference/idebugformatter-getvariantforstring.md)|지정 된 문자열을 포함 하는 VARIANT를 반환 합니다.|  
|[IDebugFormatter::GetStringForVarType](../../winscript/reference/idebugformatter-getstringforvartype.md)|지정한 VARTYPE 값을 나타내는 string을 반환 합니다.|