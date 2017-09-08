---
title: "접근성 팁과 요령 | Microsoft Docs"
ms.custom: 
ms.date: 08/22/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- accessibility [Visual Studio]
ms.assetid: 6b491d88-f79e-4686-8841-857624bdcfda
caps.latest.revision: 22
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 17defdd0b96ec1c3273fc6b845af844b031a4a17
ms.openlocfilehash: 906e8c70df502245001f87795cab9f5efe808c83
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="accessibility-tips-and-tricks"></a>접근성 팁과 요령
> [!TIP]
> 접근성에 대한 최신 업데이트에 대한 자세한 내용은 [Accessibility improvements in Visual Studio 2017 version 15.3(Visual Studio 2017 버전 15.3의 접근성 향상)](https://blogs.msdn.microsoft.com/visualstudio/2017/08/14/accessibility-improvements-in-visual-studio-2017-version-15-3/) 블로그 게시물을 참조하세요.

쉽게 키보드에서 작업하고 화면 판독기나 기타 보조 기술 장치를 사용할 수 있도록 Visual Studio에는 기본 제공 접근성 기능이 포함되어 있습니다. 이 항목에는 접근성 및 여러 유용한 바로 가기 키 조합에 맞게 Visual Studio를 최적화하기 위한 몇 가지 제안 사항이 포함되어 있습니다. 바로 가기 키 조합을 사용하여 키보드를 통해 Visual Studio에서 작업을 수행할 수 있습니다.

## <a name="save-your-ide-settings"></a>IDE 설정 저장  
 창 레이아웃, 키보드 매핑 구성표 및 기타 기본 설정을 저장하여 IDE 환경을 사용자 지정할 수 있습니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  

## <a name="accessing-toolbars"></a>도구 모음 액세스
Visual Studio IDE에는 대부분의 도구 창에 있는 것과 같은 도구 모음이 있습니다. 다음 바로 가기 키 조합을 사용하여 도구 모음에 액세스할 수 있습니다.

|기능|설명|키 조합|  
|-------------|-----------------|---------------------|  
|IDE 도구 모음|표준 도구 모음에서 첫 번째 단추를 선택합니다.|**ALT**, **CTRL** + **TAB**|  
|도구 창 도구 모음|포커스를 도구 창의 도구 모음으로 이동합니다. <br> <br> **참고:** 이 기능은 대부분의 도구 창에서 작동하지만 포커스가 도구 창에 있을 때만 작동합니다. 또한 Alt 키 전에 Shift 키를 선택해야 합니다. 팀 탐색기와 같은 일부 도구 창에서는 Alt 키를 선택하기 전에 잠시 Shift 키를 누르고 있어야 합니다.|**Shift** + **Alt**|
|도구 모음|다음 도구 모음의 첫 번째 항목으로 이동합니다(포커스가 도구 모음에 있을 때).|**CTRL** + **TAB**|

## <a name="other-useful-shortcut-key-combinations"></a>기타 유용한 바로 가기 키 조합  
일부 기타 유용한 바로 가기 키 조합은 다음과 같습니다.

|기능|설명|키 조합|  
|-------------|-----------------|---------------------|  
|IDE|고대비를 켜고 끕니다. <br> <br> **참고:** 표준 Windows 바로 가기|**왼쪽 ALT+왼쪽 SHIFT+PRINT SCREEN**|  
|대화 상자|대화 상자에서 확인란 옵션을 선택 또는 선택 취소합니다. <br> <br> **참고:** 표준 Windows 바로 가기|**스페이스바**|  
|상황에 맞는 메뉴|상황에 맞는(마우스 오른쪽 단추 클릭) 메뉴를 엽니다. <br> <br> **참고:** 표준 Windows 바로 가기|**SHIFT** + **F10**|
|메뉴|액셀러레이터 키를 사용하여 메뉴 항목에 빠르게 액세스합니다. **ALT** 키를 선택하고 나서 메뉴에서 밑줄이 표시된 문자를 선택하여 명령을 활성화합니다. 예를 들어 Visual Studio에서 [프로젝트 열기] 대화 상자를 보려면 **ALT** + **F** + **O** + **P**를 선택합니다.  <br><br> **참고:** 표준 Windows 바로 가기|**ALT** + **[문자]**|
|도구 상자 창|도구 상자 탭 간에 이동합니다.|**Ctrl** + **위쪽 화살표**<br /><br /> 를 갖는<br /><br /> **Ctrl** + **아래쪽 화살표**|  
|도구 상자 창|폼 또는 디자이너에 도구 상자의 컨트롤을 추가합니다.|**Enter**|  
|옵션 대화 상자, 환경, 키보드|**바로 가기 키 누르기** 옵션에 입력된 키 조합을 삭제합니다.|**백스페이스**|  

> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  

## <a name="see-also"></a>참고 항목  
 [Visual Studio의 접근성 기능](../../ide/reference/accessibility-features-of-visual-studio.md)

 [방법: Visual Studio에서 메뉴 및 도구 모음 사용자 지정](../../ide/how-to-customize-menus-and-toolbars-in-visual-studio.md)

 [Visual Studio IDE 개인 설정](../../ide/personalizing-the-visual-studio-ide.md)

