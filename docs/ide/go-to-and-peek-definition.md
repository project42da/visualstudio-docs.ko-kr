---
title: "정의로 이동 및 정의 피킹(Peeking) | Microsoft Docs"
ms.custom: 
ms.date: 10/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code editor, go to definition
- code editor, peek definition
- go to definition
- peek definition
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 467d119e67db254b6e15630c08c411bb15283351
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="go-to-definition-and-peek-definition"></a>정의로 이동 및 정의 피킹(Peeking)  
정의로 이동 및 정의 피킹(Peeking) 기능을 사용하여 형식 또는 멤버의 정의를 쉽게 볼 수 있습니다.

## <a name="go-to-definition"></a>정의로 이동  
정의로 이동 기능은 형식 또는 멤버의 소스로 이동하고 새 탭에 결과를 엽니다. 키보드 사용자인 경우 텍스트 커서를 기호 이름의 어딘가에 놓고 **F12** 키를 누릅니다. 마우스 사용자인 경우 컨텍스트 메뉴에서 **정의로 이동**을 선택하거나 아래 설명된 **Ctrl-클릭** 기능을 사용합니다.  

### <a name="ctrl-click-go-to-definition"></a>Ctrl 키를 누른 채로 [정의로 이동] 클릭  
Visual Studio 2017 15.4 버전에는 마우스 사용자가 정의로 이동에 신속하게 액세스할 수 있는 쉬운 방법이 있습니다. 기호는 **Ctrl** 키를 누르고 해당 형식이나 멤버 위로 마우스를 가져 가면 클릭할 수 있게 됩니다. 기호 정의로 빠르게 이동하려면 **Ctrl** 키를 누른 상태에서 기호를 클릭합니다. 너무나 쉽습니다!

![마우스 클릭 정의로 이동 애니메이션](../ide/media/click_gotodef.gif)

**도구**, **옵션**, **텍스트 편집기**, **일반**으로 이동하고 **보조 키 사용** 드롭다운에서 **Alt** 또는 **Ctrl+Alt**를 선택하여 **정의로 이동**에 대한 보조 키를 변경할 수 있습니다. **마우스를 클릭하면 정의로 이동하도록 허용** 확인란을 선택 취소하여 마우스 클릭 **정의로 이동**을 사용하지 않도록 설정할 수도 있습니다.  

![마우스 클릭 정의로 이동 사용](../ide/media/editor_options_mouse_click_gotodef.png)  

## <a name="peek-definition"></a>정의 피킹
정의 피킹 기능을 사용하면 편집기에서 현재 위치를 벗어나지 않고 형식 정의를 미리 볼 수 있습니다. 키보드 사용자인 경우 텍스트 커서를 형식 또는 멤버 이름의 어딘가에 놓고 **Alt + F12** 키를 누릅니다. 마우스 사용자인 경우 바로 가기 메뉴에서 **정의 피킹**을 선택할 수 있습니다. Visual Studio 2017 버전 15.4 이상에는 마우스를 사용하여 정의 보기를 피킹(Peeking)하는 새로운 방법이 있습니다. 먼저 **도구**, **옵션**, **텍스트 편집기**, **일반**으로 이동합니다. **Peek 뷰에서 정의 열기** 옵션을 선택하고 **확인**을 클릭하여 **옵션** 대화 상자를 닫습니다.  

![마우스 클릭 정의 피킹 옵션 설정](../ide/media/editor_options_peek_view.png)  

그런 다음 **Ctrl**(또는 **옵션**에서 선택한 보조 키) 키를 누르고 형식 또는 멤버를 클릭합니다.  

![정의 피킹 애니메이션](../ide/media/peek_definition.gif)

팝업 창에서 다른 정의를 피킹하는 경우 팝업 위에 표시되는 원과 화살표를 사용하여 탐색할 수 있는 이동 경로가 시작됩니다.  

자세한 내용은 [방법: 정의 피킹(Peeking)을 사용하여 코드 보기 및 편집(Alt+F12)](how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md)을 참조하세요.  

## <a name="see-also"></a>참고 항목  
[코드 탐색](../ide/navigating-code.md)  
[방법: 정의 피킹(Peeking)을 사용하여 코드 보기 및 편집(Alt+F12)](how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md)  
