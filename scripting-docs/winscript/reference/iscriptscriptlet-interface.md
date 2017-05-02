---
title: "IScriptScriptlet 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IScriptScriptlet 인터페이스"
ms.assetid: b9981908-a337-4228-864c-c741f111ab2d
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# IScriptScriptlet 인터페이스
구현 하는 개체는 `IScriptScriptlet` 인터페이스는 이벤트 처리기의 스크립트를 나타냅니다.  
  
 `IScriptEntry`에서 상속되는 메서드 외에 `IScriptScriptlet` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IScriptScriptlet::GetEventName](../../winscript/reference/iscriptscriptlet-geteventname.md)|스크립트릿와 연결 된 이벤트의 이름을 반환 합니다.|  
|[IScriptScriptlet:: GetSimpleEventName](../../winscript/reference/iscriptscriptlet-getsimpleeventname.md)|스크립트릿으로 연결 된 간단한 이벤트 이름을 반환 합니다.  이 공백은 포함 하지 않는 단일 word 이름입니다.|  
|[IScriptScriptlet::GetSubItemName](../../winscript/reference/iscriptscriptlet-getsubitemname.md)|마지막 식별자는 스크립트릿 개체 호스트의 정규화 된 이름을 반환합니다.|  
|[IScriptScriptlet::SetEventName](../../winscript/reference/iscriptscriptlet-seteventname.md)|스크립트릿와 연결 된 이벤트의 이름을 설정 합니다.|  
|[IScriptScriptlet::SetSimpleEventName](../../winscript/reference/iscriptscriptlet-setsimpleeventname.md)|스크립트릿으로 연결 된 간단한 이벤트 이름을 설정 합니다.  이 공백은 포함 하지 않는 단일 word 이름입니다.|  
|[IScriptScriptlet::SetSubItemName](../../winscript/reference/iscriptscriptlet-setsubitemname.md)|마지막 식별자는 스크립트릿 개체 호스트의 정규화 된 이름을 설정합니다.|  
  
## 참고 항목  
 [액티브 스크립트 작성 인터페이스](../../winscript/reference/active-script-authoring-interfaces.md)