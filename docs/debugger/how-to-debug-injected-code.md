---
title: "방법: 삽입 된 코드를 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.injected
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- assembly language, viewing
- debugging [C++], viewing assembly code
- debugging [C++], injected code
- debugging [C++], enabling source annotation
- injected code
- Show Source Code command [debugger]
- debugging [C++], using attributes
- disassembly code, debugging
ms.assetid: a1b4104d-d49e-451f-a91e-e39ceaf35875
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 2c06209d2c2774eb12c0e04d8f448b8ceb2de771
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-debug-injected-code"></a>방법: 삽입한 코드 디버깅
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 도구 메뉴에서 설정 가져오기 및 내보내기를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
 특성을 사용하면 C++ 프로그래밍을 매우 단순화할 수 있습니다. 자세한 내용은 참조 [개념](/cpp/windows/attributed-programming-concepts)합니다. 일부 특성은 컴파일러가 직접 해석합니다. 프로그램 소스에 코드를 삽입하여 컴파일러가 컴파일할 수 있게 하는 특성도 있습니다. 이렇게 코드를 삽입하면 프로그래머가 써야 하는 코드의 양이 줄어들어 보다 쉽게 프로그래밍할 수 있습니다. 그러나 때때로 버그가 발생하여 삽입된 코드를 실행하는 동안 응용 프로그램에 문제가 생기기도 합니다. 이런 경우에는 삽입된 코드를 볼 수 있습니다. Visual Studio에서는 두 가지 방법으로 삽입된 코드를 볼 수 있습니다.  
  
-   에 삽입 된 코드를 볼 수는 **디스어셈블리** 창.  
  
-   사용 하 여 [/Fx](/cpp/build/reference/fx-merge-injected-code), 원래와 삽입 된 코드를 포함 하는 병합 된 소스 파일을 만들 수 있습니다.  
  
 **디스어셈블리** 창에는 소스 코드와 특성에 의해 삽입 된 코드에 해당 하는 어셈블리 언어 명령을 표시 합니다. 또한는 **디스어셈블리** 창에는 소스 코드 주석이 표시 될 수 있습니다.  
  
### <a name="to-turn-on-source-annotation"></a>소스 주석을 설정하려면  
  
-   마우스 오른쪽 단추로 클릭는 **디스어셈블리** 창 선택 **소스 코드 표시** 바로 가기 메뉴에서.  
  
     소스 창에 있는 특성의 위치를 알고 있는 경우에 삽입 된 코드를 찾는 바로 가기 메뉴를 사용할 수 있습니다는 **디스어셈블리** 창.  
  
### <a name="to-view-injected-code"></a>삽입된 코드를 보려면  
  
1.  디버거는 중단 모드에 있어야 합니다.  
  
2.  소스 코드 창에서 보려는 삽입된 코드의 특성 앞에 커서를 놓습니다.  
  
3.  마우스 오른쪽 단추로 클릭 하 고 선택 **디스어셈블리로 이동** 바로 가기 메뉴에서.  
  
     선택할 수 있습니다 특성 위치에 가까운 경우 현재 실행 위치는 **디스어셈블리** 에서 창 고 **디버그** 메뉴 합니다.  
  
### <a name="to-view-the-disassembly-code-at-the-current-execution-point"></a>현재 실행 위치에서 디스어셈블리 코드를 보려면  
  
1.  디버거는 중단 모드에 있어야 합니다.  
  
2.  **디버그** 메뉴 선택 **Windows**를 클릭 하 고 **디스어셈블리**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)