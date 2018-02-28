---
title: "IScriptEntry 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IScriptEntry interface
ms.assetid: 86da3bc1-58b7-4d73-87ab-bc3ce34e3f41
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a785be8777cf3400f7723c24f1022bad6e22e330
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iscriptentry-interface"></a>IScriptEntry 인터페이스
구현 하는 개체는 `IScriptEntry` 인터페이스는 스크립트 블록 또는 함수 개체를 나타냅니다.  
  
 상속 된 메서드 외에도 `IScriptNode`, `IScriptEntry` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IScriptEntry::GetBody](../../winscript/reference/iscriptentry-getbody.md)|본문에 해당 하는 텍스트를 반환 합니다.는 `IScriptEntry` 스크립트 블록, 함수 블록 또는 스크립틀릿 합니다.|  
|[IScriptEntry::GetItemName](../../winscript/reference/iscriptentry-getitemname.md)|식별 하는 항목 이름을 반환 하는 `IScriptEntry` 개체입니다.|  
|[IScriptEntry::GetName](../../winscript/reference/iscriptentry-getname.md)|단일 개체 (예: 함수)를 나타내는 항목에 대 한 개체의 이름을 반환 합니다.|  
|[IScriptEntry::GetRange](../../winscript/reference/iscriptentry-getrange.md)|시작 위치와 항목의 길이 반환합니다.|  
|[IScriptEntry::GetSignature](../../winscript/reference/iscriptentry-getsignature.md)|반환 형식에 대 한 정보는 `IScriptEntry` 함수 개체입니다.|  
|[IScriptEntry::GetText](../../winscript/reference/iscriptentry-gettext.md)|에 해당 하는 텍스트를 반환 된 `IScriptEntry` 스크립트 블록 또는에 포함 된 소스 코드는 `IScriptScriptlet` 이벤트 처리기입니다.|  
|[IScriptEntry::SetBody](../../winscript/reference/iscriptentry-setbody.md)|본문에 있는 텍스트를 설정 하는 `IScriptEntry` 스크립트 블록 또는 `IScriptScriptlet` 스크립틀릿 합니다.|  
|[IScriptEntry::SetItemName](../../winscript/reference/iscriptentry-setitemname.md)|식별 하는 항목 이름을 설정 하는 `IScriptEntry` 개체입니다.|  
|[IScriptEntry::SetName](../../winscript/reference/iscriptentry-setname.md)|단일 개체 (예: 함수)를 나타내는 항목에 대 한 개체의 이름을 설정 합니다.|  
|[IScriptEntry::SetSignature](../../winscript/reference/iscriptentry-setsignature.md)|집합 형식에 대 한 정보는 `IScriptEntry` 함수 개체입니다.|  
|[IScriptEntry::SetText](../../winscript/reference/iscriptentry-settext.md)|에 해당 하는 텍스트를 설정 하는 `IScriptEntry` 스크립트 블록 또는에 포함 된 소스 코드는 `IScriptScriptlet` 이벤트 처리기입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 작성 인터페이스](../../winscript/reference/active-script-authoring-interfaces.md)