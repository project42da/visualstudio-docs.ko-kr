---
title: "ISimpleConnectionPoint 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "ISimpleConnectionPoint 인터페이스"
ms.assetid: f632a82f-942d-4291-963e-e9fa2b162493
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# ISimpleConnectionPoint 인터페이스
설명 하 고 특정 연결점에 발생 하는 이벤트를 열거 하는 간단한 방법을 제공 합니다.  이 인터페이스는 연결을 손쉽게는 `IDispatch` 개체에 해당 하는 이벤트입니다.  이 인터페이스는 프로세스 디버그 관리자 \(PDM에서\), 구현 되 고 스크립트 엔진으로 사용 합니다.  
  
 이 인터페이스에서 사용할 수 `IDebugHelper::CreateSimpleConnectionPoint`.  
  
 `IUnknown`에서 상속되는 메서드 외에 `ISimpleConnectionPoint` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[ISimpleConnectionPoint::Advise](../../winscript/reference/isimpleconnectionpoint-advise.md)|간단한 연결 지점 개체와 클라이언트 싱크 간에 연결을 설정합니다.|  
|[ISimpleConnectionPoint::DescribeEvents](../../winscript/reference/isimpleconnectionpoint-describeevents.md)|각 이벤트에 대 한 이름과 dispid가 이벤트에 지정 된 범위를 반환합니다.|  
|[ISimpleConnectionPoint::GetEventCount](../../winscript/reference/isimpleconnectionpoint-geteventcount.md)|이 인터페이스에서 노출 하는 이벤트의 수를 반환 합니다.|  
|[ISimpleConnectionPoint::Unadvise](../../winscript/reference/isimpleconnectionpoint-unadvise.md)|`ISimpleConnectionPoint::Advise`를 통해 이전에 설치된 권장된 연결을 종료합니다.|  
  
## 참고 항목  
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)