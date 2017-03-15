---
title: "서버 (Visual Studio SDK) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "서버 디버깅"
  - "디버깅 [디버깅 SDK] 서버"
ms.assetid: 62236d64-7956-448c-9ac3-5528f3edac1d
caps.latest.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 17
---
# 서버 (Visual Studio SDK)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버거 아키텍처 측면에서  **server**:  
  
-   포트 및 포트 공급자의 컨테이너 이며 포트 및 포트 공급자 세션 디버그 매니저 \(SDM\) 엔진을 디버깅 하는 데 사용 됩니다.  
  
-   자신을 이름으로 식별 하 고 해당 포트 및 포트 공급자를 열거할 수 있습니다.  
  
-   표시 되는 [IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md) 인터페이스에만 Visual Studio \(Visual Studio 실행의 각 인스턴스에 대 한 서버 인스턴스 하나\)에 의해 구현 됩니다.  
  
## 참고 항목  
 [포트](../../extensibility/debugger/ports.md)   
 [포트 공급자](../../extensibility/debugger/port-suppliers.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md)