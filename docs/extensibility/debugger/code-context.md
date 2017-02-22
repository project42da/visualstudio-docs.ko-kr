---
title: "코드 컨텍스트 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK] 컨텍스트"
ms.assetid: 65e4d37a-086b-426e-9394-a3534967fd59
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# 코드 컨텍스트
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅은  **코드 컨텍스트**:  
  
-   디버그 엔진 \(DE\)으로 알려진 위치에 코드를 추상화를 제공 합니다.  대부분의 런타임 아키텍처에 대 한 오늘날, 코드 컨텍스트 중에서 프로그램의 명령 스트림 주소로 생각할 수 있습니다.  위치 코드 지침으로 나타낼 수 있습니다, 특수 언어에서 코드 컨텍스트에 다른 방법으로 나타낼 수 있습니다.  
  
-   디버깅 중인 프로그램의 실행 스트림 내의 현재 위치를 설명 합니다.  
  
-   만 프로그램이 중단점에서 중지 된 시기에 존재 합니다.  
  
-   연관 된 문서 컨텍스트가 있습니다.  
  
-   에 의해 구현 되는  [IDebugCodeContext2](../../extensibility/debugger/reference/idebugcodecontext2.md) 인터페이스입니다.  
  
## 참고 항목  
 [문서 컨텍스트](../../extensibility/debugger/document-context.md)   
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)