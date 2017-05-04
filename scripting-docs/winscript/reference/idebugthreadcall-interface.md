---
title: "IDebugThreadCall 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugThreadCall 인터페이스"
ms.assetid: 9a9a9892-f310-4ef3-8db2-4f868be52d7e
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugThreadCall 인터페이스
`IDebugThreadCall` 인터페이스는 일반적으로 크로스 스레드 호출 하는 구성 요소에서 구현 된 `IDebugThread` 마샬링 구현 프로세스 디버그 관리자 \(PDM\)에 의해 제공.  
  
 PDM 호출에 `IDebugThreadCall` 인터페이스에는 원하는 스레드 및 `IDebugThreadCall` 인터페이스 원하는 구현에 호출을 디스패치합니다.  `IDebugThreadCall` 인터페이스 위쪽에 적절 한 매개 변수 전달 매개 변수 정보를 표시 합니다.  
  
 `IDebugThreadCall` 인터페이스에 자유 스레드 개체입니다.  
  
## 메서드  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugThreadCall` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|---------|--------|  
|[IDebugThreadCall::ThreadCallHandler](../../winscript/reference/idebugthreadcall-threadcallhandler.md)|다른 스레드에서 코드를 실행 하는 호출을 처리 합니다.|