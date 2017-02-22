---
title: "포트 공급자 | Microsoft Docs"
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
  - "포트 공급자"
  - "디버깅 [디버깅 SDK] 포트 공급자"
ms.assetid: a8f3db96-1a13-4e93-9ef6-0861880369e0
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# 포트 공급자
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버거 아키텍처 측면에서  **포트 공급자**:  
  
-   서버에서 포함 되어 있으며 포트 요청을 해당 서버에 제공 합니다.  
  
-   추가 하 고 포트를 포함 하는 서버에서 제거할 수 있습니다.  
  
-   서버에 제공 되는 모든 포트를 열거할 수 있습니다.  
  
-   표시 되는 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) Visual Studio 가진 레지스트리를 통해 등록 된 인터페이스를.  이 인터페이스를 호출 하 여 얻을 수 있습니다 [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md).  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]기본 포트 공급자 및 기본 포트를 제공합니다.  사용자 지정 포트를 구현 하는 경우 사용자 지정 포트 공급자도 해당 사용자 지정 포트를 제공 합니다 구현 해야 합니다.  
  
## 참고 항목  
 [서버](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [포트](../../extensibility/debugger/ports.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)