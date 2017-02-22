---
title: "방법: 자체 호스팅 WCF 서비스 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "디버깅, WCF"
  - "WCF, 디버깅"
  - "WCF, 자체 호스팅 서비스"
ms.assetid: 288922be-ba3f-411e-af50-bba39c9529cc
caps.latest.revision: 25
caps.handback.revision: 25
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 자체 호스팅 WCF 서비스 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

*자체 호스팅 서비스*는 IIS, WCF 서비스 호스트 또는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] Development Server 내에서 실행되지 않는 WCF 서비스입니다.  자체 호스팅 WCF를 가장 쉽게 디버깅하는 방법은 **디버그** 메뉴에서 **디버깅 시작**을 선택할 때 클라이언트와 서버가 모두 시작되도록 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 구성하는 것입니다.  
  
 그러나 WCF 서비스가 내부 자체 호스팅 서비스이거나 NT 서비스 같이 이러한 방식으로 시작할 수 없는 프로세스인 경우에는 이 방법을 사용할 수 없습니다.  이러한 경우에는 대신 다음 중 하나를 수행할 수 있습니다.  
  
-   디버거를 호스팅 프로세스에 수동으로 연결합니다.  자세한 내용은 [실행 중인 프로세스에 연결](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)을 참조하십시오.  
  
     \-또는\-  
  
-   클라이언트 디버깅을 시작한 다음 서비스 호출을 한 단계씩 실행합니다.  이렇게 하려면 app.config 파일에서 디버깅을 사용하도록 설정해야 합니다.  자세한 내용은 [WCF 디버깅의 제한 사항](../debugger/limitations-on-wcf-debugging.md)을 참조하십시오.  
  
### Visual Studio에서 클라이언트와 호스트를 모두 시작하려면  
  
1.  클라이언트와 서버 프로젝트가 모두 포함된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 솔루션을 만듭니다.  
  
2.  **디버그** 메뉴에서 **시작**을 선택하면 클라이언트 및 서버 프로세스가 모두 시작되도록 해당 솔루션을 구성합니다.  
  
    1.  **솔루션 탐색기**에서 솔루션 이름을 마우스 오른쪽 단추로 클릭합니다.  
  
    2.  **시작 프로젝트 설정**을 클릭합니다.  
  
    3.  다음 **솔루션 \<이름\> 속성** 대화상자에서, **여러 개의 시작 프로젝트**를 선택합니다.  
  
    4.  **여러 개의 시작 프로젝트** 표의 서버 프로젝트에 해당하는 줄에서 **작업**을 클릭한 다음 **시작**을 선택합니다.  
  
    5.  클라이언트 프로젝트에 해당하는 줄에서 **작업**을 클릭한 다음 **시작**을 선택합니다.  
  
    6.  **확인**을 클릭합니다.  
  
## 참고 항목  
 [WCF 서비스 디버깅](../debugger/debugging-wcf-services.md)   
 [WCF 디버깅의 제한 사항](../debugger/limitations-on-wcf-debugging.md)   
 [방법: WCF 서비스 한 단계씩 실행](../debugger/how-to-step-into-wcf-services.md)