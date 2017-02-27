---
title: "방법: 편집기 모드 관리 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "코드 편집기, 모드"
  - "코드 편집기, 옵션 보기 및 표시"
  - "글꼴 및 크기"
  - "전체 화면 모드"
  - "줄 번호"
  - "줄 번호, 표시"
  - "뷰, 모드 변경"
  - "뷰, 새 창 만들기"
  - "뷰, 줄 번호"
  - "뷰, 개요"
  - "뷰, 분할"
  - "뷰, 가상 공간"
  - "뷰, 워드 래핑"
  - "가상 공간 모드"
  - "자동 줄 바꿈"
ms.assetid: 1fb48027-d870-439f-8b72-4a0321390748
caps.latest.revision: 20
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 20
---
# 방법: 편집기 모드 관리
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다양한 표시 모드에서 Visual Studio 코드 편집기를 표시할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 전체 화면 모드 사용  
 **전체 화면** 모드를 사용하여 모든 도구 창을 숨기고 문서 창만 보이도록 선택할 수 있습니다.  
  
#### 전체 화면 모드를 사용하려면  
  
-   Alt\+Shift\+Enter를 눌러 **전체 화면** 모드에 들어가거나 해당 모드를 종료합니다.  
  
     \-\- 또는 \-\-  
  
-   **명령** 창에서 `View.Fullscreen` 명령을 실행합니다.  
  
## 가상 공간 모드 사용  
 **가상 공간** 모드에서 각 코드 줄의 끝에는 공백이 삽입됩니다.  코드 옆의 일정한 지점에 주석을 배치하려면 이 옵션을 선택합니다.  
  
#### 가상 공간 모드를 사용하려면  
  
1.  **도구** 메뉴에서 **옵션**을 선택합니다.  
  
2.  **텍스트 편집기** 폴더를 확장하고 **모든 언어**를 선택하여 이 옵션을 전역으로 설정하거나 특정 언어 폴더를 선택합니다.  예를 들어, Visual Basic에서 줄 번호만 표시하도록 설정하려면 텍스트 편집기 옵션에서 기본을 선택합니다.  
  
3.  **일반** 옵션을 선택하고 **설정**에서 **가상 공간 활성화**를 선택합니다.  
  
    > [!NOTE]
    >  **가상 공간**이 **열 선택** 모드에서 활성화됩니다.  **가상 공간** 모드가 활성화되지 않으면 삽입 지점이 한 줄 끝에서 다음 줄의 첫 번째 문자로 바로 이동합니다.  
  
## 참고 항목  
 [편집기 사용자 지정](../ide/customizing-the-editor.md)   
 [방법: 창 정렬 및 도킹](../misc/how-to-arrange-and-dock-windows.md)   
 [옵션 대화 상자, 환경, 글꼴 및 색](../ide/reference/fonts-and-colors-environment-options-dialog-box.md)