---
title: "IScriptEntry 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IScriptEntry 인터페이스"
ms.assetid: 86da3bc1-58b7-4d73-87ab-bc3ce34e3f41
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# IScriptEntry 인터페이스
구현 하는 개체는 `IScriptEntry` 인터페이스 함수 개체 또는 스크립트 블록을 나타냅니다.  
  
 `IScriptNode`에서 상속되는 메서드 외에 `IScriptEntry` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IScriptEntry::GetBody](../../winscript/reference/iscriptentry-getbody.md)|본문에 해당 하는 텍스트를 반환 된 `IScriptEntry` 스크립트 블록, 함수 블록 또는 스크립트릿.|  
|[IScriptEntry::GetItemName](../../winscript/reference/iscriptentry-getitemname.md)|식별 항목 이름을 반환 하는 `IScriptEntry` 개체입니다.|  
|[IScriptEntry::GetName](../../winscript/reference/iscriptentry-getname.md)|에 대 한 항목 \(예: 함수\)는 단일 개체를 나타내는 개체의 이름을 반환 합니다.|  
|[IScriptEntry::GetRange](../../winscript/reference/iscriptentry-getrange.md)|시작 위치 및 항목의 길이 반환합니다.|  
|[IScriptEntry::GetSignature](../../winscript/reference/iscriptentry-getsignature.md)|반환에 대 한 정보를 입력은 `IScriptEntry` 함수 개체입니다.|  
|[IScriptEntry::GetText](../../winscript/reference/iscriptentry-gettext.md)|해당 텍스트를 반환 합니다.는 `IScriptEntry` 에 포함 된 소스 코드 또는 스크립트 블록은 `IScriptScriptlet` 이벤트 처리기.|  
|[IScriptEntry::SetBody](../../winscript/reference/iscriptentry-setbody.md)|본문에 있는 텍스트를 설정 하는 `IScriptEntry` 스크립트 블록 또는 `IScriptScriptlet` 스크립트릿.|  
|[IScriptEntry::SetItemName](../../winscript/reference/iscriptentry-setitemname.md)|식별 항목 이름을 설정 하는 `IScriptEntry` 개체입니다.|  
|[IScriptEntry::SetName](../../winscript/reference/iscriptentry-setname.md)|에 대 한 항목 \(예: 함수\)는 단일 개체를 나타내는 개체의 이름을 설정 합니다.|  
|[IScriptEntry::SetSignature](../../winscript/reference/iscriptentry-setsignature.md)|집합에 대 한 정보를 입력은 `IScriptEntry` 함수 개체입니다.|  
|[IScriptEntry::SetText](../../winscript/reference/iscriptentry-settext.md)|설정에 해당 하는 텍스트는 `IScriptEntry` 에 포함 된 소스 코드 또는 스크립트 블록은 `IScriptScriptlet` 이벤트 처리기.|  
  
## 참고 항목  
 [액티브 스크립트 작성 인터페이스](../../winscript/reference/active-script-authoring-interfaces.md)