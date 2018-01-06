---
title: "디버깅 준비: 프로젝트를 콘솔 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
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
- debugging [Visual Studio], console applications
- debugging console applications
- console applications, debugging
ms.assetid: 9641f1d9-2d5a-48b1-8731-6525e8f67892
caps.latest.revision: "26"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9e1ade672c3abd81f4f71d1e48a39560e17e1465
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-preparation-console-projects"></a>디버깅 준비: 콘솔 프로젝트
콘솔 프로젝트 디버깅을 준비하는 과정은 Windows 프로젝트 디버깅을 준비하는 과정과 비슷하지만 몇 가지 사항을 추가로 고려해야 합니다. 자세한 내용은 참조 [Windows Forms 응용 프로그램](../debugger/debugging-preparation-windows-forms-applications.md), 및 [디버깅 준비: Windows Forms 응용 프로그램 (.NET)](http://msdn.microsoft.com/en-us/a8bc54de-41a3-464d-9a12-db9bdcbc1ad5)합니다. 콘솔 응용 프로그램은 모두 비슷하므로 이 항목에서는 다음과 같은 프로젝트 형식을 다룹니다.  
  
-   C# 콘솔 응용 프로그램  
  
-   Visual Basic 콘솔 응용 프로그램  
  
-   C++ 콘솔 응용 프로그램(.NET)  
  
-   C++ 콘솔 응용 프로그램(Win32)  
  
 콘솔 응용 프로그램에 대한 명령줄 인수를 지정해야 할 수도 있습니다. 자세한 내용은 참조 [c + + 디버그 구성에 대 한 프로젝트 설정을](../debugger/project-settings-for-a-cpp-debug-configuration.md), [Visual Basic 디버그 구성에 대 한 프로젝트 설정을](../debugger/project-settings-for-a-visual-basic-debug-configuration.md), 또는 [C# 디버그 구성에 대 한 프로젝트 설정 ](../debugger/project-settings-for-csharp-debug-configurations.md).  
  
 모든 프로젝트 속성과 마찬가지로 이러한 인수도 디버그 세션 사이와 Visual Studio 세션 사이에 지속적으로 적용됩니다. 따라서 이전에 디버깅 한 콘솔 응용 프로그램 이면 프로그램인에 입력 된 이전 세션에서 인수가 있을 수는  **\<프로젝트 > 속성 페이지** 대화 상자.  
  
 콘솔 응용 프로그램을 사용 하 여는 **콘솔** 창 입력을 받고 출력 메시지를 표시 합니다. 에 쓸 수는 **콘솔** 창 응용 프로그램 사용 해야 합니다는 **콘솔** Debug 개체 대신 개체입니다. 에 쓸 수는 **Visual Studio 출력** 창 Debug 개체를 정상적으로 사용 합니다. 사용자는 응용 프로그램에서 출력하는 위치를 정확하게 알아야 합니다. 정확한 위치를 모르면 잘못된 위치에서 메시지를 찾을 수 있습니다. 자세한 내용은 참조 [Console 클래스](/dotnet/api/system.console), [Debug 클래스](/dotnet/api/system.diagnostics.debug), 및 [출력 창](../ide/reference/output-window.md)합니다.  
  
## <a name="starting-the-application"></a>응용 프로그램 시작  
 일부 콘솔 응용 프로그램은 시작되면 완료될 때까지 실행된 다음 종료됩니다. 이 동작은 실행을 중단하고 디버깅할 충분한 시간을 제공하지 않을 수 있습니다. 응용 프로그램을 디버깅할 수 있으려면 다음 절차 중 하나를 사용하여 응용 프로그램을 시작합니다.  
  
-   응용 프로그램 실행이 시작 되 고 중단점에 도달할 때까지 실행 됩니다.  
  
-   응용 프로그램이 시작되고 소스 코드의 첫째 줄에서 즉시 중단됩니다.  
  
-   소스 코드 창에는 줄을 마우스 오른쪽 단추로 클릭 하 고 선택 **커서까지 실행**합니다.  
  
     응용 프로그램이 시작되고 선택된 줄까지 실행되거나 해당 줄 전에 중단점이 적중되는 경우 중단점까지 실행됩니다.  
  
 콘솔 응용 프로그램을 디버깅할 때는 Visual Studio 대신 명령 프롬프트에서 응용 프로그램을 시작하는 경우가 있을 수 있습니다. 이 경우에는 명령 프롬프트에서 응용 프로그램을 시작하고 Visual Studio 디버거를 응용 프로그램에 연결할 수 있습니다. 자세한 내용은 참조 [실행 중인 프로세스에 연결할](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)합니다.  
  
 Visual Studio에서 콘솔 응용 프로그램을 시작할 때의 **콘솔** 창이 Visual Studio 창 뒤에 있는 경우에 따라 나타납니다. Visual Studio에서 콘솔 응용 프로그램을 시작했는데 콘솔 창이 보이지 않으면 Visual Studio 창을 이동해 보십시오.  
  
## <a name="see-also"></a>참고 항목  
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)   
 [Debugging Managed Code](../debugger/debugging-managed-code.md) (관리 코드 디버그)  
 [Visual c + + 프로젝트 형식](../debugger/debugging-preparation-visual-cpp-project-types.md)   
 [C#, F# 및 Visual Basic 프로젝트 형식](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [C + + 디버그 구성에 대 한 프로젝트 설정](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [디버거 보안](../debugger/debugger-security.md)