---
title: "방법: DLL 프로젝트에서 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 05/24/2017
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
- DLL projects, debugging
- debugging DLLs
- DLLs, debugging projects
- debugging [Visual Studio], DLLs
ms.assetid: 40a94339-d3f7-4ab9-b8a1-b8cf82942f44
caps.latest.revision: "30"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 371c48282b2f775833287046ed9810f0cbc8f69e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-debug-from-a-dll-project-in-visual-studio"></a>방법: Visual Studio에서 DLL 프로젝트에서 디버깅
DLL 프로젝트를 디버깅 하는 한 가지 방법은 DLL 프로젝트의 프로젝트 속성에서 호출 응용 프로그램을 지정 하는 것을 자체 DLL 프로젝트에서 디버깅을 시작할 수 있습니다. 이 방법을 사용 하려면 응용 프로그램이 DLL을 호출 해야 하며 DLL 응용 프로그램에서 찾을 수 있는 위치에 있어야 합니다. (그렇지 않은 경우 응용 프로그램이 서로 다른 버전의 DLL 찾아서 로드 하는 대신, 및 중단점을 적중지 않습니다). 다른 Dll 디버깅 방법에 대 한 참조 [DLL 프로젝트 디버깅](../debugger/debugging-dll-projects.md)합니다.
  
네이티브 코드를 사용하여 관리되는 DLL을 호출하고 네이티브 코드와 관리되는 DLL을 모두 디버그하려는 경우 프로젝트 속성에서 이를 지정할 수 있습니다. 자세한 내용은 [How to: Debug in Mixed Mode](../debugger/how-to-debug-in-mixed-mode.md)을 참조하십시오.   

C++ 속성 페이지의 레이아웃과 콘텐츠는 C# 및 Visual Basic 속성 페이지와 다릅니다. 
  
### <a name="to-specify-the-calling-application-in-a-c-project"></a>C++ 프로젝트에서 호출 응용 프로그램을 지정하려면  
  
1.  프로젝트 노드를 마우스 오른쪽 단추로 클릭는 **솔루션 탐색기** 선택 **속성**합니다.  
  
2.  다음 사항을 확인는 **구성** 창의 맨 아래에 필드로 설정 되어 **디버그**합니다. 

    A **디버그** 구성은이 메서드에 대 한 필요 합니다. 
  
3.  로 이동 **구성 속성 > 디버깅**합니다.  
  
4.  에 **실행할 디버거** 목록에서 선택 **로컬 Windows 디버거** 또는 **원격 Windows 디버거**합니다.  
  
5.  에 **명령** 또는 **원격 명령** 상자 호출 응용 프로그램 (예:.exe 파일)의 정규화 된 경로 이름을 추가 합니다.

    ![속성 창 디버깅](../debugger/media/dbg-debugging-properties-dll.png "DebuggingPropertiesWindow")  
  
6.  모든 필요한 프로그램 인수를 추가할는 **명령 인수** 상자입니다.  
  
### <a name="to-specify-the-calling-application-in-a-c-or-visual-basic-project"></a>C# 또는 Visual Basic 프로젝트에서 호출 응용 프로그램을 지정하려면  
  
1.  프로젝트 노드를 마우스 오른쪽 단추로 클릭는 **솔루션 탐색기** 선택 **속성**를 선택한 후는 **디버그** 탭 합니다.

2.  다음 사항을 확인는 **구성** 창의 맨 아래에 필드로 설정 되어 **디버그**합니다.

3.  (.NET framework) 선택 **시작 외부 프로그램**, 고 호출 응용 프로그램의 정규화 된 경로 이름을 추가 합니다.

4.  (.NET 코어) 선택 **실행 파일** 에서 **시작** 목록을 연 다음에 호출 응용 프로그램의 정규화 된 경로 이름을 추가 **실행 파일** 필드입니다. 
  
     외부 프로그램의 명령줄 인수를 추가 해야 할 경우에 추가 된 **명령줄 인수** (또는 **응용 프로그램 인수**) 필드입니다.

    ![속성 창 디버깅](../debugger/media/dbg-debugging-properties-dll-csharp.png "DebuggingPropertiesWindow") 

5.  해야 할 경우 URL로 응용 프로그램을 호출할 수도 있습니다. 로컬 ASP.NET 응용 프로그램에 사용되는 관리되는 DLL을 디버그하는 경우에도 이 작업을 수행할 수 있습니다.  
  
     **시작 작업**, 선택는 **URL로 브라우저 시작:** 라디오 단추 및 URL를 입력 합니다.
  
### <a name="to-start-debugging-from-the-dll-project"></a>DLL 프로젝트에서 디버깅을 시작하려면  
  
1.  DLL 프로젝트에 중단점을 설정 합니다. 

2.  DLL 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **시작 프로젝트로 설정**합니다. 

    (또한 있는지 확인 하는 **솔루션 구성** 필드는로 설정 되어 **디버그**.)   
  
3.  디버깅 시작 (F5 키를 눌러, 녹색 화살표를 클릭 하거나 클릭 **디버그 > 디버깅 시작**).

    DLL에서 중단점에 도달 합니다. 중단점을 적중할 수 없는 경우를 DLL 출력 있는지 확인 (기본적으로는 **project\Debug** 폴더) 위치에는 호출 응용 프로그램에서 찾을 수 있습니다.
  
## <a name="see-also"></a>참고 항목  
 [DLL 프로젝트 디버깅](../debugger/debugging-dll-projects.md)   
 [C#에 대 한 프로젝트 설정 디버그 구성](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [디버그 구성에 대 한 Visual Basic 프로젝트 설정](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [C++ 디버그 구성에 대한 프로젝트 설정](../debugger/project-settings-for-a-cpp-debug-configuration.md)