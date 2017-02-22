---
title: "옵션 대화 상자, 디버깅, Just-In-Time | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.ToolsOptionsPages.Debugger.JIT"
  - "vs.debug.options.JIT"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "Just-In-Time 디버깅, 옵션 설정"
  - "옵션 대화 상자, 디버깅"
ms.assetid: 7f11b2e3-3fb5-449d-b07c-6ecf1d6a487d
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 옵션 대화 상자, 디버깅, Just-In-Time
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**Just\-In\-Time** 페이지에 액세스하려면 **도구** 메뉴에서 **옵션**을 클릭합니다.  **옵션** 대화 상자에서 **디버깅** 노드를 확장하고 **Just\-In\-Time**을 선택합니다.  이 페이지에서는 관리 코드, 네이티브 코드 및 스크립트에 대해 Just\-In\-Time 디버깅을 사용하도록 설정할 수 있습니다.  자세한 내용은 [Just\-In\-Time 디버깅](../debugger/just-in-time-debugging-in-visual-studio.md)을 참조하십시오.  
  
 다음과 같은 프로그램 유형에 대해 Just\-In\-Time 디버깅을 사용하도록 설정할 수 있습니다.  
  
-   Managed  
  
-   네이티브  
  
-   스크립트  
  
 Just\-In\-Time 디버깅은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 외부에서 시작된 프로그램을 디버깅하는 기술입니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 환경 외부에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 만든 프로그램을 실행할 수 있습니다.  Just\-in\-time 디버깅을 사용하도록 설정한 상태에서 프로그램이 충돌하면 디버깅할지 여부를 묻는 대화 상자가 표시됩니다.  
  
## 관련된 경고  
 **옵션** 대화 상자에서 이 페이지를 열면 다음과 같은 경고 메시지가 표시될 수 있습니다.  
  
 **다른 디버거가 자신을 Just\-In\-Time 디버거로 등록했습니다.  복구하려면 Just\-In\-Time 디버깅을 사용하도록 설정하거나 Visual Studio 복구를 실행하십시오.**  
  
 이 메시지는 다른 디버거\(예: 이전 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 디버거\)가 Just\-In\-Time 디버거로 설정되어 있는 경우에 발생합니다.  
  
 다음과 같은 다른 메시지가 표시될 수도 있습니다.  
  
 **Just\-In\-Time 디버깅 등록 오류가 발견되었습니다.  복구하려면 Just\-In\-Time 디버깅을 사용하도록 설정하거나 Visual Studio 복구를 실행하십시오.**  
  
 이러한 경고 중 하나가 표시되는 경우 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]에서 Just\-In\-Time 디버깅을 수행하려면 문제를 해결할 때까지 관리자 권한이 필요합니다.  이러한 상황에서 관리자 이외의 권한으로 Just\-In\-Time 디버깅을 사용하도록 설정하려고 하면 다음과 같은 오류 메시지가 표시됩니다.  
  
 **액세스가 거부되었습니다.  관리자에게 문의하여 Just\-In\-Time 디버깅을 사용하도록 설정하거나 Visual Studio 설치를 복구하십시오.**  
  
## 참고 항목  
 [옵션 대화 상자, 디버깅](../debugger/debugging-options-dialog-box.md)   
 [방법: 디버거 설정 지정](../debugger/how-to-specify-debugger-settings.md)