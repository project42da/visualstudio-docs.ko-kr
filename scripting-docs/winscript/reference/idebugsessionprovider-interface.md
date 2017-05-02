---
title: "IDebugSessionProvider 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugSessionProvider 인터페이스"
ms.assetid: 1b898423-7af9-44f5-8dda-987005309c99
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugSessionProvider 인터페이스
디버거 호스트와 언어를 사용 하는 IDE에서 제공 하는 기본 인터페이스 디버깅을 시작 합니다.  실행 중인 응용 프로그램에 대 한 디버그 세션을 설정합니다.  컴퓨터 디버그 관리자가이 인터페이스를 구현 합니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IDebugSessionProvider` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugSessionProvider::StartDebugSession](../../winscript/reference/idebugsessionprovider-startdebugsession.md)|지정 된 응용 프로그램을 디버그 세션을 시작합니다.|