---
title: "방법: 혼합된 모드에서 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 06/19/2017
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
- debugging DLLs
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging
ms.assetid: 2859067d-7fcc-46b0-a4df-8c2101500977
caps.latest.revision: "29"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 797724287439631b9398af43616116a1635381ff
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-debug-in-mixed-mode"></a>How to: Debug in Mixed Mode
다음 절차에서는 관리 코드와 네이티브 코드를 모두 디버깅하는 방법에 대해 설명합니다. 이러한 디버깅을 혼합 모드 디버깅이라고도 합니다. 네이티브 코드로 작성된 것이 DLL인지 응용 프로그램인지 여부에 따라 혼합 모드 디버깅에는 두 가지 시나리오가 있습니다.  
  
-   DLL을 호출하는 호출 응용 프로그램이 네이티브 코드로 작성된 경우 DLL이 관리 코드로 작성된 것입니다. 이 경우 관리되는 디버거와 네이티브 디버거가 둘 모두를 디버깅할 수 있어야 합니다. 이 확인할 수는  **\<프로젝트 > 속성 페이지** 대화 상자. 이를 수행하는 방법은 DLL 프로젝트에서 디버깅을 시작하는지 아니면 호출 응용 프로그램 프로젝트에서 디버깅을 시작하는지에 따라 달라집니다.  
  
-   DLL을 호출하는 응용 프로그램이 관리 코드로 작성된 경우 DLL이 네이티브 코드로 작성된 것입니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.

호출 응용 프로그램에 대 한 프로젝트에 액세스할 수 없는, DLL 프로젝트의 DLL를 디버깅할 수 있습니다. 자세한 내용은 [How to: Debug from a DLL Project](../debugger/how-to-debug-from-a-dll-project.md)을 참조하세요. 사용 하도록 하기 위해 방금 DLL 프로젝트 디버깅을 혼합 필요 하지 않습니다.
  
### <a name="to-enable-mixed-mode-debugging-c-calling-app"></a>혼합 모드 디버깅 (c + + 호출 응용 프로그램)를 사용 하도록 설정 하려면  
  
1.  **솔루션 탐색기**, 네이티브 프로젝트를 선택 합니다.
  
2.  에 **보기** 메뉴를 클릭 하 여 **속성 페이지**합니다.
  
3.  에  **\<프로젝트 > 속성 페이지** 대화 상자에서 **구성 속성** 노드를 선택한 후 **디버깅**합니다.  
  
4.  설정 **디버거 형식** 를 **혼합** 또는 **자동**합니다.

    ![혼합된 모드 디버깅을 활성화](../debugger/media/dbg-mixed-mode-from-native.png "혼합된 모드 디버깅을 사용 하도록 설정")

### <a name="to-enable-mixed-mode-debugging-c-or-vb-calling-app"></a>혼합 모드 디버깅 (C# 또는 VB 호출 응용 프로그램)를 사용 하도록 설정 하려면  
  
1.  **솔루션 탐색기**, 관리 되는 프로젝트를 선택 합니다.  
  
2.  에 **보기** 메뉴를 클릭 하 여 **속성 페이지**합니다.  
  
3.  에  **\<프로젝트 > 속성 페이지** 대화 상자는 **디버그** 탭을 선택한 다음 선택 **네이티브 코드 디버깅 사용**

    ![네이티브 코드 디버깅 사용](../debugger/media/dbg-mixed-mode-from-csharp.png "네이티브 코드 디버깅 사용")
  
## <a name="see-also"></a>참고 항목  
 [How to: Debug from a DLL Project](../debugger/how-to-debug-from-a-dll-project.md)