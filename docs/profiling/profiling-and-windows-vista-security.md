---
title: "프로파일링 및 Windows Vista 보안 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로파일링 도구, 보안"
  - "성능 도구, 보안"
ms.assetid: 842112fc-b886-4801-8cd7-a25b314b0393
caps.latest.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 19
---
# 프로파일링 및 Windows Vista 보안
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

컴퓨터 관리자가 [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)] 사용자 액세스 권한 설정을 사용 가능하도록 설정했는지 여부에 따라 해당 컴퓨터에서 프로세스를 프로파일링할 수 있는 보안 권한이 개별 사용자에게 있을 수 있습니다.  다음 예는 사용자 간에 사용 가능한 작업의 차이를 보여 줍니다.  
  
-   일부 사용자는 관리자가 드라이버 및 서비스를 시작하도록 설정한 경우에 고급 프로파일링 기능에 액세스할 수 있습니다.  
  
-   도메인 사용자는 샘플 프로파일링에만 액세스할 수 있습니다.  
  
-   일부 사용자는 다른 모든 사용자에 대해 프로파일링할 수 있는 액세스 권한을 거부할 수 있습니다.  
  
 자세한 내용은 [VSPerfCmd](../profiling/vsperfcmd.md)에서 ADMIN 옵션을 참조하십시오.  
  
## 상호 세션 프로파일링  
 *상호 세션 프로파일링*은 서로 다른 로그온 세션에서 실행되는 프로세스를 프로파일링할 수 있는 기능입니다.  예를 들어, 대부분의 서비스는 세션 0에서 실행되고 사용자는 세션 0에서 직접 실행할 수 없습니다.  성능 탐색기 도구 모음의 **프로세스에 연결** 단추 또는 VSPerfCmd 명령줄 도구의 \/attach 옵션을 사용하면 서로 다른 로그온 세션에서 대부분의 프로세스를 프로파일링할 수 있습니다.  
  
 크로스 프로세스 프로파일링 시각화 옵션을 설정하면 사용할 수 있는 프로세스 목록을 볼 수 있습니다.  이러한 옵션은 **프로세스에 연결**을 클릭할 때 표시되는 **프로세스에 연결** 창에서 사용할 수 있습니다.  
  
-   **모든 사용자의 프로세스 표시**  
  
     이 옵션을 선택하지 않으면 목록에는 현재 사용자가 소유한 프로세스만 표시됩니다.  **모든 사용자의 프로세스 표시**를 선택하면 목록에 모든 사용자의 프로세스가 표시됩니다.  
  
-   **모든 세션의 프로세스 표시**  
  
     이 옵션을 선택하지 않으면 목록에는 현재 세션의 프로세스가 표시되고,  이 옵션을 선택하면 모든 세션의 프로세스가 표시됩니다.  
  
## 참고 항목  
 [개요](../profiling/overviews-performance-tools.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [How to: Attach to a Running Process](http://msdn.microsoft.com/ko-kr/636d0a52-4bfd-48d2-89ad-d7b9ca4dc4f4)