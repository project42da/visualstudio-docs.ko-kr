---
title: "IDebugHelper 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugHelper interface
ms.assetid: ef5691e0-1d82-42c2-997c-888e31c478dd
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3f0f70ecb8ead264d0d4b074f8fc1d9e3a6091eb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebughelper-interface"></a>IDebugHelper 인터페이스
개체 브라우저 및 간단한 연결 지점에 대 한 팩터리 역할을 합니다. 프로세스 디버그 관리자 (PDM) 스크립트 엔진에서 사용 되는이 인터페이스를 구현 합니다.  
  
 상속 된 메서드 외에도 `IUnknown`, `IDebugHelper` 인터페이스는 다음 메서드를 노출 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDebugHelper::CreatePropertyBrowser](../../winscript/reference/idebughelper-createpropertybrowser.md)|속성 브라우저를 래핑하는 VARIANT를 반환 합니다.|  
|[IDebugHelper::CreatePropertyBrowserEx](../../winscript/reference/idebughelper-createpropertybrowserex.md)|속성 브라우저를 문자열로 VARIANT 값 이나 VARTYPE 형식이의 사용자 지정 변환 알리고 래핑하는 VARIANT를 반환 합니다.|  
|[IDebugHelper::CreateSimpleConnectionPoint](../../winscript/reference/idebughelper-createsimpleconnectionpoint.md)|래핑하는 이벤트 인터페이스를 반환 된 주어진 `IDispatch` 개체입니다.|