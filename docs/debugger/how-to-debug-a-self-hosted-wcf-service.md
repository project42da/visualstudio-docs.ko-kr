---
title: "방법: 자체 호스팅된 WCF 서비스 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, self-hosted service
- WCF, debugging
ms.assetid: 288922be-ba3f-411e-af50-bba39c9529cc
caps.latest.revision: "25"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e64f764153106c252ba1a9586bfd0a33f4e239f4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-debug-a-self-hosted-wcf-service"></a>방법: 자체 호스팅 WCF 서비스 디버깅
A *자체 호스팅 서비스* 는 IIS, WCF 서비스 호스트 내에서 실행 되지 않는 WCF 서비스 또는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 개발 서버. 구성 하는 것 자체 호스팅된 WCF 디버깅 하는 가장 쉬운 방법은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 선택 하면 클라이언트와 서버를 시작 하려면 **디버깅 시작** 에 **디버그** 메뉴.  
  
 WCF 서비스가 자체 호스팅 서비스 내에 있느냐 프로세스 NT 서비스와 같은 이러한 방식으로 시작할 수 없는 경우이 메서드를 사용할 수 없습니다. 대신, 다음 중 하나를 수행할 수 있습니다.  
  
-   수동으로 호스팅 프로세스에 디버거를 연결 합니다. 자세한 내용은 참조 [실행 중인 프로세스에 연결할](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)합니다.  
  
     — 또는 —  
  
-   클라이언트 디버깅을 시작 하 고 서비스에 대 한 호출에 다음 단계를 진행 합니다. 이렇게 하려면 app.config 파일에서 디버깅을 활성화 하면 합니다. 자세한 내용은 [WCF 디버깅의 제한 사항](../debugger/limitations-on-wcf-debugging.md)합니다.  
  
### <a name="to-start-both-client-and-host-from-visual-studio"></a>클라이언트와 호스트 Visual Studio에서 시작 하려면  
  
1.  만들기는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 클라이언트와 서버 프로젝트를 포함 하는 솔루션입니다.  
  
2.  선택 하면 클라이언트와 서버 프로세스를 시작 하도록 솔루션 구성 **시작** 에 **디버그** 메뉴.  
  
    1.  **솔루션 탐색기**, 솔루션 이름을 마우스 오른쪽 단추로 클릭 합니다.  
  
    2.  클릭 **시작 프로젝트 설정**합니다.  
  
    3.  에 **솔루션 \<이름 > 속성** 대화 상자에서 **여러 개의 시작 프로젝트**합니다.  
  
    4.  에 **여러 개의 시작 프로젝트** 서버 프로젝트에 해당 하는 줄 눈금 클릭 **동작** 선택 **시작**합니다.  
  
    5.  클라이언트 프로젝트에 해당 하는 줄에서 클릭 **동작** 선택 **시작**합니다.  
  
    6.  **확인**을 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF 서비스 디버깅](../debugger/debugging-wcf-services.md)   
 [WCF 디버깅의 제한 사항](../debugger/limitations-on-wcf-debugging.md)   
 [방법: WCF 서비스 한 단계씩 실행](../debugger/how-to-step-into-wcf-services.md)