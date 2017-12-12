---
title: "XAML 디자이너에서 개체에 애니메이션 효과 주기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb88fa26-e835-47f5-9771-2f279441c83c
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1f4fd45337ebd0f00362d352077cf8441e6f5afa
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="animate-objects-in-xaml-designer"></a>XAML 디자이너에서 개체에 애니메이션 효과 주기
개체를 이동하는 간단한 애니메이션을 만들 수 있고 개체를 페이드 인/페이드 아웃할 수 있습니다.  
  
 시작하려면 *스토리보드*를 만듭니다. 스토리보드에는 하나 이상의 *타임 라인*이 포함됩니다. 타임라인에서 *키 프레임* 을 설정하여 속성 변경 내용을 표시합니다. 그런 다음 애니메이션을 실행하면 Blend가 지정된 기간 동안 속성 변경 내용을 보간합니다. 따라서 부드러운 전환이 가능해집니다. 비시각적 속성을 비롯하여 개체에 속하는 모든 속성에 애니메이션 효과를 적용할 수 있습니다.  
  
 다음 그림은 **위로 이동**이라고 하는 스토리보드를 보여 줍니다. 타임라인에는 사각형의 X 및 Y 위치를 표시하는 키 프레임이 포함됩니다. 이 애니메이션을 실행하면 사각형이 특정 위치에서 다른 위치로 부드럽게 이동합니다.  
  
 ![](../designers/media/982f031a-74a3-414a-abc2-a0f41a741075.png "982f031a-74a3-414a-abc2-a0f41a741075")  
  
 다음 비디오를 시청하여 애니메이션을 만드는 방법을 배워봅니다.  
  
|짧은 비디오 보기:|비디오 내용|  
|--------------------------|-------------------|  
|![설치된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [타임라인 만들기](http://www.popscreen.com/v/6A4eF/Microsoft-Expression-Blend-Creating-Timelines)|타임라인을 만들고 타임라인에서 개체 작업을 수행합니다.|  
|![설치된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [키 프레임 추가 및 애니메이션 반복](http://www.popscreen.com/v/6A4fi/Microsoft-Expression-Blend-Adding-Keyframes-and-Repeating-an-Animation)|키 프레임을 추가하고 각 키 프레임에서 속성을 설정합니다. 그런 다음 애니메이션을 실행하고 애니메이션 간 부드럽게 전환되는 개체를 확인합니다.|  
|![설치된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [대화형 작업을 위한 이벤트 트리거 추가](http://www.popscreen.com/v/6A4e4/Microsoft-Expression-Blend-Adding-Event-Triggers-for-Interactivity)|이벤트가 발생할 때 애니메이션을 시작합니다. 예를 들어 창이 로드되면 애니메이션을 시작합니다.|  
|![설치된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [색 애니메이션](http://www.popscreen.com/v/6A4gv/Microsoft-Expression-Blend-Animating-Colors)|애니메이션을 사용하여 개체의 색을 변경합니다.|  
|![설치된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [이동 경로 만들기 및 수정](http://www.popscreen.com/v/6A4fX/Microsoft-Expression-Blend-Creating-and-Modifying-Motion-Paths)|패스를 따라 개체에 애니메이션 효과를 적용합니다.|  
|![설치된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [키 프레임 감속/가속](http://www.popscreen.com/v/6A4dM/Microsoft-Expression-Blend-Easing-Keyframes)|애니메이션 시작 부분(*가속*)이나 끝 부분(*감속*)에서 애니메이션 속도를 높이거나 낮춥니다.|  
|![설치된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [단추 애니메이션](http://www.popscreen.com/v/6A4fK/Microsoft-Expression-Blend-Animating-a-Button)|사용자가 단추를 가리킬 때 단추에 표시되는 흥미로운 효과를 만듭니다.|  
|![설치된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [애니메이션 만들기 및 감속/가속 작업](https://www.youtube.com/watch?v=mAJXYrwxGYo)|사용자가 계산기의 이미지에 있는 단추를 누를 때 나타나는 효과에 애니메이션 효과를 적용합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Blend for Visual Studio를 사용하여 UI 만들기](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)