---
title: "방법: 편집기 모드 관리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- word wrap
- views, virtual space
- line numbers, displaying
- virtual space mode
- line numbers
- Code Editor, view and display options
- full screen mode
- Code Editor, modes
- views, splitting
- views, word wrapping
- fonts and size
- views, creating new windows
- views, line numbers
- views, changing mode
- views, outlining
ms.assetid: 1fb48027-d870-439f-8b72-4a0321390748
caps.latest.revision: 20
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 5ea9179ad37514ffad4876177b05150eecc22def
ms.openlocfilehash: 71566f11a069d266ded2aebe02bbf388cf00730e
ms.contentlocale: ko-kr
ms.lasthandoff: 05/24/2017

---
# <a name="how-to-manage-editor-modes"></a>방법: 편집기 모드 관리
Visual Studio Code 편집기를 다양한 표시 모드로 표시할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="enabling-full-screen-mode"></a>전체 화면 모드 사용  
 **전체 화면** 모드를 사용하도록 설정하여 모든 도구 창을 숨기고 문서 창만 보도록 선택할 수 있습니다.  
  
#### <a name="to-enable-full-screen-mode"></a>전체 화면 모드를 사용하도록 설정하려면  
  
-   ALT+SHIFT+ENTER를 눌러 **전체 화면** 모드를 시작하거나 종료합니다.  
  
     -- 또는 --  
  
-   **명령** 창에서 `View.Fullscreen` 명령을 실행합니다.  
  
## <a name="enabling-virtual-space-mode"></a>가상 공간 모드 사용  
 **가상 공간** 모드에서 각 코드 줄 끝에 공간이 삽입됩니다. 코드 옆의 일정한 지점에 주석을 배치하려면 이 옵션을 선택합니다.  
  
#### <a name="to-enable-virtual-space-mode"></a>가상 공간 모드를 사용하도록 설정하려면  
  
1.  **도구** 메뉴에서 **옵션**을 선택합니다.  
  
2.  **텍스트 편집기** 폴더를 확장하고 **모든 언어**를 선택하여 이 옵션을 전역으로 설정하거나 특정 언어 폴더를 선택합니다. 예를 들어 Visual Basic에서 줄 번호만 켜려면 [Basic], [텍스트 편집기] 옵션을 선택합니다.  
  
3.  **일반** 옵션을 선택하고 **설정**에서 **가상 공간 사용**을 선택합니다.  
  
    > [!NOTE]
    >  **가상 공간**은 **열 선택** 모드에서 사용할 수 있습니다. **가상 공간** 모드가 사용하도록 설정되지 않으면 삽입 지점이 한 줄 끝에서 바로 다음 줄의 첫 번째 문자로 이동합니다.  
  
## <a name="see-also"></a>참고 항목  
 [편집기 사용자 지정](../ide/customizing-the-editor.md)   
 [Visual Studio에서 창 레이아웃 사용자 지정](../ide/customizing-window-layouts-in-visual-studio.md)   
 [옵션 대화 상자, 환경, 글꼴 및 색](../ide/reference/fonts-and-colors-environment-options-dialog-box.md)
