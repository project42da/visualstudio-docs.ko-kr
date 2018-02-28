---
title: IDebugApplicationNode100::SetFilterForEventSink | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNode100::SetFilterForEventSink
ms.assetid: cfb34efe-c6e1-4692-8ffd-3ede3a24cd4b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6db8ea26787427844a92417bf525dba271063cba
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationnode100setfilterforeventsink"></a>IDebugApplicationNode100::SetFilterForEventSink
필터에서 특정 설정 [IDebugApplicationNodeEvents 인터페이스](../../winscript/reference/idebugapplicationnodeevents-interface.md) 구현 합니다. 스크립트 디버거를 PDM 이러한 생성 되거나 제거 될 때 이벤트를 더 이상 송신할 수 있도록 컴파일러에서 생성 된 자식 응용 프로그램 노드를 필터링 할 수 없습니다. 기본적으로 모든 노드에 전송 됩니다.  
  
> [!IMPORTANT]
>  [IDebugApplicationNode100 인터페이스](../../winscript/reference/idebugapplicationnode100-interface.md) PDM v 10.0으로 구현 하 고 큰 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetFilterForEventSink(        [in] DWORD dwCookie,        [in] APPLICATION_NODE_EVENT_FILTER filter        );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwCookie`  
 필터의 쿠키입니다.  
  
 `filter`  
 필터입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplicationNode100 인터페이스](../../winscript/reference/idebugapplicationnode100-interface.md)