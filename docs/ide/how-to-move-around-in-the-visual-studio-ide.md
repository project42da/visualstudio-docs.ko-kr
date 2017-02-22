---
title: "방법: Visual Studio IDE에서 이동 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "문서[Visual Studio], 탐색"
  - "환경[Visual Studio], 탐색"
  - "파일[Visual Studio], 항목 간 탐색"
  - "IDE 탐색기"
  - "IDE, 탐색"
  - "탐색[Visual Studio]"
  - "창.다음문서창으로이동"
  - "Visual Studio], 탐색"
ms.assetid: 6c36b6eb-c93f-496b-af08-4199f7afd8bd
caps.latest.revision: 25
caps.handback.revision: 25
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 방법: Visual Studio IDE에서 이동
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

IDE\(통합 개발 환경\)는 사용자의 취향이나 프로젝트 요구 사항에 따라 서로 다른 여러 가지 방법으로 창에서 창으로, 파일에서 파일로 이동할 수 있도록 디자인되었습니다.  편집기에서 현재 열려 있는 파일을 순환할 수도 있고 IDE에서 모든 활성 도구 창을 순환할 수도 있습니다.  마지막으로 액세스한 순서에 관계없이 편집기에서 현재 열려 있는 파일로 직접 전환할 수도 있습니다.  이러한 기능을 통해 IDE에서 작업할 때 생산성을 높일 수 있습니다.  
  
> [!NOTE]
>  대화 상자에서 사용할 수 있는 옵션과 메뉴 명령의 이름 및 위치는 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  이 도움말 페이지는 **일반 개발 설정**을 염두에 두고 작성되었습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 편집기에서 파일 탐색  
 여러 메서드를 편집기에 열려 있는 파일 사이 이동할 수 있습니다.  이러한 속성에 액세스 하 고 IDE 탐색기를 사용 하 여 잘가 항상 볼 수 있도록 현재 열려 있는 파일 또는 핀 즐겨찾기 파일 탭을 빠르게 찾을 수 있는 순서에 따라 파일 간에 이동할 수 있습니다.  
  
 뒤로 탐색 및 앞으로 탐색 기능을 사용하면 편집기에 열려 있는 파일을 액세스한 순서에 따라 순환할 수 있습니다. 이는 Microsoft Internet Explorer에서 뒤로 및 앞으로 기능을 사용하여 열어 본 페이지를 순환하는 경우와 매우 비슷합니다.  
  
#### 열려 있는 파일 사이를 사용 순서에 따라 이동하려면  
  
-   현재 열려 있는 문서를 가장 최근에 액세스한 순서대로 활성화하려면 Ctrl 키와 \- 기호를 함께 누릅니다.  
  
-   현재 열려 있는 문서를 반대 순서로 활성화하려면 Ctrl 키와 Shift 키 및 \- 기호를 함께 누릅니다.  
  
    > [!NOTE]
    >  **뒤로 탐색** 및 **앞으로 탐색**은 **보기** 메뉴에도 있습니다.  
  
 또한 **IDE 탐색기**, 편집기의 **현재 파일** 목록 또는 **창** 대화 상자를 사용하면 마지막으로 파일에 액세스한 시점에 관계없이 편집기에 열려 있는 특정 파일로 전환할 수 있습니다.  
  
 **IDE 탐색기**의 작동 방식은 Windows에서 응용 프로그램을 전환하는 방식과 매우 비슷합니다.  이 기능은 메뉴에서 사용할 수 없으며 바로 가기 키를 통해서만 실행할 수 있습니다.  순환하려는 순서에 따라 두 명령 중 하나로 **IDE 탐색기**에 액세스하여 파일을 순환할 수 있습니다.  `Window.PreviousDocumentWindowNav`를 사용하면 가장 최근에 액세스한 파일로 이동할 수 있고, `Window.NextDocumentWindowNav`를 사용하면 반대 순서로 이동할 수 있습니다.  일반 개발 설정에서는 Ctrl\+Shift\+Tab이 `Window.PreviousDocumentWindowNav`에, Ctrl\+Tab이 `Window.NextDocumentWindowNav`에 할당되어 있습니다.  
  
> [!NOTE]
>  현재 사용 중인 설정 조합에서 이 명령에 바로 가기 키 조합이 할당되어 있지 않은 경우 **옵션** 대화 상자의 **키보드** 페이지에서 사용자 지정 명령을 직접 할당할 수 있습니다.  자세한 내용은 [바로 가기 키 식별 및 사용자 지정](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md)을 참조하십시오.  
  
#### 편집기에서 특정 파일로 전환하려면  
  
-   Ctrl\+Tab을 눌러 **IDE 탐색기**를 표시합니다.  전환할 파일이 선택될 때까지 Ctrl 키를 누른 채로 Tab 키를 반복하여 누릅니다.  
  
    > [!TIP]
    >  **현재 파일** 목록을 역순으로 순환하려면 Ctrl\+Shift를 누른 채로 Tab 키를 누릅니다.  
  
     \-또는\-  
  
-   편집기의 오른쪽 위 모서리에서 선택은  **활성 파일** 단추를 클릭 한 다음 전환 하려면 목록에서 파일을 선택 합니다.  
  
     \-또는\-  
  
-   메뉴 표시줄에서 선택  **창**,  **Windows**.  
  
-   목록에서 확인 하 고 다음을 선택 하려는 파일을 선택 합니다.  **등록**.  
  
## IDE에서 도구 창 탐색  
 **IDE 탐색기**를 사용하여 IDE에 열려 있는 도구 창을 순환할 수도 있습니다.  순환하려는 순서에 따라 두 명령 중 하나로 **IDE 탐색기**에 액세스하여 도구 창을 순환할 수 있습니다.  `Window.PreviousToolWindowNav`를 사용하면 가장 최근에 액세스한 파일로 이동할 수 있고, `Window.NextToolWindowNav`를 사용하면 반대 순서로 이동할 수 있습니다.  일반 개발 설정에서는 Shift\+Alt\+F7이 `Window.PreviousDocumentWindowNav`에, Alt\+F7이 `Window.NextDocumentWindowNav`에 할당되어 있습니다.  
  
> [!NOTE]
>  현재 사용 중인 설정 조합에서 이 명령에 바로 가기 키 조합이 할당되어 있지 않은 경우 **옵션** 대화 상자의 **키보드** 페이지에서 사용자 지정 명령을 직접 할당할 수 있습니다.  자세한 내용은 [바로 가기 키 식별 및 사용자 지정](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md)을 참조하십시오.  
  
#### IDE에서 특정 도구 창으로 전환하려면  
  
-   Alt\+F7을 눌러 **IDE 탐색기**를 표시합니다.  전환할 창이 선택될 때까지 Alt 키를 누른 채로 F7 키를 반복하여 누릅니다.  
  
    > [!TIP]
    >  **활성 도구 창** 목록을 역순으로 순환하려면 Shift\+Alt를 누른 채로 F7 키를 누릅니다.  
  
## 참고 항목  
 [창 레이아웃 사용자 지정](../ide/customizing-window-layouts-in-visual-studio.md)   
 [기본 바로 가기 키](../ide/default-keyboard-shortcuts-in-visual-studio.md)