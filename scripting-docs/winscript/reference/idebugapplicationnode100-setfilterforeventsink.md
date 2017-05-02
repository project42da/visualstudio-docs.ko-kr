---
title: "IDebugApplicationNode100::SetFilterForEventSink | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugApplicationNode100::SetFilterForEventSink"
ms.assetid: cfb34efe-c6e1-4692-8ffd-3ede3a24cd4b
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# IDebugApplicationNode100::SetFilterForEventSink
필터에서 특정 설정 [IDebugApplicationNodeEvents 인터페이스](../../winscript/reference/idebugapplicationnodeevents-interface.md) 구현.  이 스크립트 디버거를 PDM이 작성 또는 삭제할 때 이벤트 더 이상 보낼 수 응용 프로그램 컴파일러에서 생성 된 자식 노드를 필터링 할 수 없습니다.  기본적으로 모든 노드에 전송 됩니다.  
  
> [!IMPORTANT]
>  [IDebugApplicationNode100 인터페이스](../../winscript/reference/idebugapplicationnode100-interface.md)PDM v 10.0이 고 큰 구현 됩니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 구문  
  
```cpp  
HRESULT SetFilterForEventSink(  
        [in] DWORD dwCookie,  
        [in] APPLICATION_NODE_EVENT_FILTER filter  
        );  
  
```  
  
#### 매개 변수  
 `dwCookie`  
 필터의 쿠키입니다.  
  
 `filter`  
 필터입니다.  
  
## 참고 항목  
 [IDebugApplicationNode100 인터페이스](../../winscript/reference/idebugapplicationnode100-interface.md)