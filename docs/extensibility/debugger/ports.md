---
title: "포트 | Microsoft Docs"
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
  - "포트"
  - "디버깅 [디버깅 SDK], 포트"
ms.assetid: 1d7f3aa7-7eff-4cab-bc53-0a566b1a9363
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 포트
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버거 아키텍처 측면에서  **포트**:  
  
-   일련의 프로세스에 대 한 컨테이너는 서버에서 실행 됩니다.  예를 들어, 포트 직렬 케이블로 Windows CE 기반 장치 또는 네트워크로 연결 된 비 DCOM 시스템에 대 한 연결을 나타낼 수 있습니다.  로컬 포트 라는 특수 포트를 로컬 컴퓨터에서 실행 중인 모든 프로세스를 포함 합니다.  
  
-   자체 이름이 나 식별자로 확인할 수 있습니다.  
  
-   수 있습니다 포트에서 실행 중인 모든 프로세스를 열거 하 고 시작 하 고 이러한 프로세스를 종료 합니다.  
  
-   표시 되며는 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) 인터페이스를 전달 하 여 생성 되는 [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) 인수를 [포트 추가](../../extensibility/debugger/reference/idebugportsupplier2-addport.md).  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]처리 하는 모든 Windows 기반 프로세스에서 네이티브 및 관리 되는 기본 포트를 제공 합니다.  사용자 지정 포트 연결에 대해 Windows 기반이 아닌 외부 장치에 구현 되어야 합니다.  와 같은 사용자 지정 포트를 지정 하려면 구현도 사용자 지정 포트 공급자 해야.  
  
## 참고 항목  
 [서버](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [프로세스](../../extensibility/debugger/processes.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md)   
 [포트 추가](../../extensibility/debugger/reference/idebugportsupplier2-addport.md)