---
title: '방법: 중지 된 경우 MFC를 호출한 함수로 돌아갈 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.mfc
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- functions [C++], debugging
- function calls, returning to calling function
- debugging [MFC], returning to calling function
- debugging [MFC], functions
- Break command
- programs, halting
- functions [debugger]
ms.assetid: d254a5a9-afbd-4923-9d7a-7422d824cabf
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 356e9f4950e62f3ac1399b1e79ee2fe400cec47b
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-get-back-to-the-function-that-called-mfc-if-halted"></a>방법: 중지된 경우 MFC를 호출한 함수로 돌아가기
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 도구 메뉴에서 설정 가져오기 및 내보내기를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
 사용 하는 경우는 **중단** 명령을 **디버그** 프로그램을 중지 하려면 메뉴, MFC에서 중지 되었고 코드 문제 인지 다시 이동 하려면 함수 호출 스택 창을 사용할 수 있습니다. 자세한 내용은 참조 [하는 방법: 호출 스택 창을 사용 하 여](../debugger/how-to-use-the-call-stack-window.md)합니다.  
  
 때로는 코드가 메시지 펌프에서 손상될 수도 있습니다. 그럴 경우 호출 스택에는 사용자 코드가 들어 있지 않습니다. 이 문제를 방지 하려면 중단점 (개 포함할 수 있는 조건 및 적중) 대신 사용할 수 있습니다는 **중단** 명령입니다. 자세한 내용은 참조 [중단점 및 추적점](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)).  
  
### <a name="to-navigate-to-the-function-from-which-mfc-was-called"></a>MFC를 호출한 함수를 탐색하려면  
  
-   사용 하 여 **호출 스택** 창.  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 코드 디버깅 Faq](../debugger/debugging-native-code-faqs.md)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)