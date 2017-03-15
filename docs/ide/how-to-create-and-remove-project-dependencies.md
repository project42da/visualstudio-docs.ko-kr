---
title: "방법: 프로젝트 종속성 만들기 및 제거 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.ProjectDependenciesDlg"
helpviewer_keywords: 
  - "빌드[Visual Studio], 설정"
  - "종속성, 프로젝트"
  - "프로젝트 빌드 구성, 종속성"
  - "프로젝트 종속성"
  - "프로젝트[Visual Studio], 종속성"
  - "vs.build.projectdependencies"
ms.assetid: e2a0a8ff-dae7-40a8-b774-b88aa5235183
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 12
---
# 방법: 프로젝트 종속성 만들기 및 제거
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

여러 프로젝트가 포함된 솔루션을 빌드하는 경우, 다른 프로젝트에서 사용되는 실행 코드를 생성하기 위해 특정 프로젝트를 먼저 빌드해야 할 수 있습니다.  다른 프로젝트에서 생성된 실행 코드를 프로젝트에서 사용하는 경우, 이 코드가 생성된 프로젝트는 이 코드를 사용하는 프로젝트에 종속되어 있다고 합니다.  이러한 종속 관계를 정의할 수 있습니다의  **프로젝트 종속성** 대화 상자.  
  
### 프로젝트에 종속성을 할당하려면  
  
1.  솔루션 탐색기에서 프로젝트를 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **프로젝트 종속성**을 선택합니다.  
  
     **프로젝트 종속성** 대화 상자가 열립니다.  
  
    > [!NOTE]
    >  **프로젝트 종속성** 옵션은 프로젝트가 두 개 이상 있는 솔루션에서만 사용할 수 있습니다.  
  
3.  **종속성** 탭의 **프로젝트** 드롭다운 메뉴에서 프로젝트를 선택합니다.  
  
4.  **다음에 종속** 필드에서 이 프로젝트를 빌드하기 전에 빌드해야 하는 프로젝트의 확인란을 선택합니다.  
  
 프로젝트 종속성을 만들려면 솔루션이 둘 이상의 프로젝트로 구성되어 있어야 합니다.  
  
### 프로젝트에서 종속성을 제거하려면  
  
1.  솔루션 탐색기에서 프로젝트를 선택합니다.  
  
2.  **프로젝트** 메뉴에서 **프로젝트 종속성**을 선택합니다.  
  
     **프로젝트 종속성** 대화 상자가 열립니다.  
  
    > [!NOTE]
    >  **프로젝트 종속성** 옵션은 프로젝트가 두 개 이상 있는 솔루션에서만 사용할 수 있습니다.  
  
3.  **종속성** 탭의 **프로젝트** 드롭다운 메뉴에서 프로젝트를 선택합니다.  
  
4.  **다음에 종속** 필드에서 이 프로젝트에 더 이상 종속되지 않는 프로젝트의 확인란을 선택 취소합니다.  
  
## 참고 항목  
 [Visual Studio에서 프로젝트 및 솔루션 빌드 및 정리](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Visual Studio에서 응용 프로그램　빌드](../ide/compiling-and-building-in-visual-studio.md)   
 [빌드 구성 이해](../ide/understanding-build-configurations.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)