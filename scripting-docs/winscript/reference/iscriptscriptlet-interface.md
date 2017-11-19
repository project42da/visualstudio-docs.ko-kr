---
title: "IScriptScriptlet 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IScriptScriptlet interface
ms.assetid: b9981908-a337-4228-864c-c741f111ab2d
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f3fa3253997d3a09a7170f3795bf8a7bbf8a182c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iscriptscriptlet-interface"></a>IScriptScriptlet 인터페이스
구현 하는 개체는 `IScriptScriptlet` 인터페이스는 이벤트 처리기 스크립트를 나타냅니다.  
  
 상속 된 메서드 외에도 `IScriptEntry`, `IScriptScriptlet` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IScriptScriptlet::GetEventName](../../winscript/reference/iscriptscriptlet-geteventname.md)|스크립틀릿와 연결 된 이벤트의 이름을 반환 합니다.|  
|[IScriptScriptlet:: GetSimpleEventName](../../winscript/reference/iscriptscriptlet-getsimpleeventname.md)|스크립틀릿 연관 된 단순 이벤트 이름을 반환 합니다. 공백을 포함 하지 않는 단일 단어 이름입니다.|  
|[IScriptScriptlet::GetSubItemName](../../winscript/reference/iscriptscriptlet-getsubitemname.md)|스크립틀릿 개체 호스트의 정규화 된 이름에서 마지막 식별자를 반환합니다.|  
|[IScriptScriptlet::SetEventName](../../winscript/reference/iscriptscriptlet-seteventname.md)|스크립틀릿와 연결 된 이벤트의 이름을 설정 합니다.|  
|[IScriptScriptlet::SetSimpleEventName](../../winscript/reference/iscriptscriptlet-setsimpleeventname.md)|스크립틀릿 연관 된 단순 이벤트 이름을 설정 합니다. 공백을 포함 하지 않는 단일 단어 이름입니다.|  
|[IScriptScriptlet::SetSubItemName](../../winscript/reference/iscriptscriptlet-setsubitemname.md)|스크립틀릿 개체 호스트의 정규화 된 이름에서 마지막 식별자를 설정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 작성 인터페이스](../../winscript/reference/active-script-authoring-interfaces.md)