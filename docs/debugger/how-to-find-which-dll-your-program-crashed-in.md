---
title: "방법: 프로그램에서 충돌이 발생 하는 DLL 찾기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.dll
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, DLL crashes
- Module List dialog box
- errors [debugger], DLL crashes
- Modules window
- debugging [Visual Studio], DLL crashes
- DLLs, load order of
ms.assetid: ecf62568-8b65-4a41-b8a4-e962ff2dfb71
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 95ad4f9c028b9b40bf5104539a608453c9d6f9dd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-find-which-dll-your-program-crashed-in"></a>방법: 프로그램에서 충돌이 발생하는 DLL 찾기
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 도구 메뉴에서 설정 가져오기 및 내보내기를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
 시스템 DLL 또는 다른 사람의 코드를 호출하는 동안 응용 프로그램에 충돌이 발생하면 충돌 발생 시 활성 상태였던 DLL을 찾아야 합니다. 사용자 프로그램 외부 DLL에 충돌이 발생 하면 사용 하 여 위치를 식별할 수 있습니다는 **모듈** 창.  
  
### <a name="to-find-where-a-crash-occurred-using-the-modules-window"></a>모듈 창을 사용하여 충돌이 발생한 위치를 찾으려면  
  
1.  충돌이 발생한 주소를 기록합니다.  
  
2.  에 **디버그** 메뉴 선택 **Windows**를 클릭 하 고 **모듈**합니다.  
  
3.  에 **모듈** 창 찾기는 **주소** 열입니다. 이 열을 표시하려면 스크롤 막대를 사용해야 할 수도 있습니다.  
  
4.  클릭는 **주소** 주소별로 Dll을 정렬 하려면 열 맨 위에 있는 단추입니다.  
  
5.  정렬된 목록을 조사하여 충돌 위치가 속하는 주소 범위를 가진 DLL을 찾습니다.  
  
6.  확인 된 **이름** 및 **경로** 열에서 DLL 이름과 경로를 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [DLL 프로젝트 디버깅](../debugger/debugging-dll-projects.md)   
 [방법: 모듈 창 사용](../debugger/how-to-use-the-modules-window.md)