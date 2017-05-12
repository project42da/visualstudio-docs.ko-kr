---
title: "IDebugHelper 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugHelper 인터페이스"
ms.assetid: ef5691e0-1d82-42c2-997c-888e31c478dd
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugHelper 인터페이스
개체 브라우저 및 간단한 연결 지점에 대 한 팩터리 역할을 합니다.  프로세스 디버그 관리자 \(PDM\) 스크립트 엔진에서 사용 되는이 인터페이스를 구현 합니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugHelper` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugHelper::CreatePropertyBrowser](../../winscript/reference/idebughelper-createpropertybrowser.md)|VARIANT를 래핑하는 속성 브라우저에 반환 합니다.|  
|[IDebugHelper::CreatePropertyBrowserEx](../../winscript/reference/idebughelper-createpropertybrowserex.md)|VARIANT를 배치 하 고 사용자 지정 VARIANT 값 또는 VARTYPE 형식의 문자열로 변환 하는 속성 브라우저에 반환 합니다.|  
|[IDebugHelper::CreateSimpleConnectionPoint](../../winscript/reference/idebughelper-createsimpleconnectionpoint.md)|반환 이벤트 인터페이스를 래핑하는 주어진 `IDispatch` 개체입니다.|