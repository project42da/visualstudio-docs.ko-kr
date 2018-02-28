---
title: "IDebugSessionProvider 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugSessionProvider interface
ms.assetid: 1b898423-7af9-44f5-8dda-987005309c99
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4e61b1e5e794c68e34250f958cdda0f50b68334c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugsessionprovider-interface"></a>IDebugSessionProvider 인터페이스
디버거 호스트 및 언어를 사용 하도록 설정 하려면 IDE에서 제공 하는 기본 인터페이스 디버깅을 시작 합니다. 실행 중인 응용 프로그램에 대 한 디버그 세션을 설정 합니다. 이 인터페이스는 컴퓨터 디버그 관리자에 의해 구현 됩니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IDebugSessionProvider` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugSessionProvider::StartDebugSession](../../winscript/reference/idebugsessionprovider-startdebugsession.md)|지정한 응용 프로그램에서 디버그 세션을 시작합니다.|