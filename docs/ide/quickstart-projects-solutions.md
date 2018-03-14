---
title: "Visual Studio의 프로젝트 및 솔루션 소개 | Microsoft Docs"
ms.custom: 
ms.date: 12/11/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 284c99c9e9c1ed2e84b05070bbf6d9991c025f94
ms.sourcegitcommit: 3285243d6c0521266053340fe06505885d12178b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2018
---
# <a name="quickstart-projects-and-solutions"></a>빠른 시작: 프로젝트 및 솔루션

10분 빠른 시작에서는 Visual Studio에서 솔루션 및 프로젝트 만들기를 살펴봅니다. 프로젝트의 속성 및 포함될 수 있는 일부 파일을 살펴봅니다. 또한 두 번째 프로젝트에 대한 참조를 만듭니다.

아직 Visual Studio를 설치하지 않은 경우 [Visual Studio 다운로드](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) 페이지로 이동하여 체험용으로 설치합니다.

> [!TIP]
> 이 빠른 시작에서 프로젝트의 개념을 이해하는 교육 연습으로 솔루션 및 프로젝트를 처음부터 구성하겠습니다. 일반적으로 Visual Studio를 사용하는 경우 대부분 Visual Studio에서 새 프로젝트를 만들 때 제공하는 여러 프로젝트 템플릿을 사용합니다.

> [!NOTE]
> Visual Studio에서 앱을 개발하는 데 솔루션과 프로젝트는 필요하지 않습니다. 또한 코드, 시작 코딩, 빌드 및 디버깅을 포함하는 폴더를 열 수 있습니다. 예를 들어 GitHub 리포지토리를 복제하면 Visual Studio 프로젝트와 솔루션이 포함되지 않을 수 있습니다. 자세한 내용은 [프로젝트 또는 솔루션 없이 Visual Studio에서 코드 개발](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)을 참조하세요.

## <a name="solutions"></a>솔루션

솔루션은 Visual Studio가 하나 이상의 관련 프로젝트를 구성하는 데 사용되는 컨테이너입니다. Visual Studio에서 솔루션을 열 때 포함된 모든 프로젝트를 자동으로 로드합니다.

### <a name="create-a-solution"></a>솔루션 만들기

빈 솔루션을 만들어 탐색을 시작합니다. Visual Studio에 대해 알게 되면 너무 자주 빈 솔루션을 만들지 않게 됩니다. Visual Studio에서 새 프로젝트를 만들 때 솔루션이 아직 열려 있지 않은 경우 자동으로 솔루션을 만들어서 프로젝트를 보관합니다.

1. Visual Studio를 시작합니다.

   Visual Studio가 열리면 창의 화면 대부분을 차지하는 **시작 페이지**가 표시됩니다.

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트...**를 선택합니다.

   **새 프로젝트** 대화 상자가 열립니다.

1. 왼쪽 창에서 **기타 프로젝트 형식**을 확장하고 **Visual Studio 솔루션**을 선택합니다. 가운데 창에서 **빈 솔루션**을 선택합니다. 솔루션 이름을 "QuickSolution"으로 지정한 다음 **확인**을 선택합니다.

   ![빈 솔루션 템플릿](media/quickstart-projects-new-solution.png)

   **시작 페이지**가 닫히고 솔루션이 Visual Studio 창 오른쪽에 있는 **솔루션 탐색기**에 표시됩니다. 자주 **솔루션 탐색기**를 사용하여 프로젝트의 내용을 탐색할 수 있습니다.

### <a name="add-a-project"></a>프로젝트 추가

이제 첫 번째 프로젝트를 솔루션에 추가해 보겠습니다. 빈 프로젝트를 시작하고 프로젝트에 필요한 항목을 추가합니다.

1. **솔루션 탐색기**의 **솔루션 'QuickSolution'**을 마우스 오른쪽 단추로 클릭하거나 상황에 맞는 메뉴에서 **추가** > **새 프로젝트...**를 선택합니다.

   **새 프로젝트 추가** 대화 상자가 열립니다.

1. 왼쪽 창에서 **Visual C#**을 확장하고 **Windows 클래식 바탕 화면**을 선택합니다. 그런 다음 가운데 창에서 **빈 프로젝트(.NET Framework)**를 선택합니다. 프로젝트 이름을 "QuickDate"로 지정한 다음 **확인** 단추를 선택합니다.

   "QuickDate"라는 프로젝트는 **솔루션 탐색기**의 솔루션 아래에 나타납니다. 현재 **App.config**라는 단일 파일이 포함됩니다.

   > [!NOTE]
   > 대화 상자의 왼쪽 창에서 **Visual C#**이 표시되지 않으면 **.NET 데스크톱 개발** 워크로드를 설치해야 합니다. 이를 수행하는 쉬운 방법은 대화 상자의 왼쪽 아래에 있는 **Visual Studio 설치 관리자 열기** 링크를 선택하는 것입니다. **Visual Studio 설치 관리자**가 실행된 후 **.NET 데스크톱 개발** 워크로드를 선택한 다음, **수정** 단추를 선택합니다.

   ![Visual Studio 설치 관리자 열기 링크](media/quickstart-projects-open-installer.png)

## <a name="add-an-item-to-the-project"></a>프로젝트에 새 항목 추가

빈 프로젝트가 있으므로&mdash;코드 파일을 추가해 보겠습니다.

1. **솔루션 탐색기**의 **QuickDate**를 마우스 오른쪽 단추로 클릭하거나 상황에 맞는 메뉴에서 **추가** > **새 항목...**을 선택합니다.

   **새 항목 추가** 대화 상자가 열립니다.

1. **Visual C# 항목**을 확장하고 **코드**를 선택합니다. 가운데 창에서 **클래스**를 선택합니다. 클래스 이름을 "Calendar"로 지정한 다음 **추가** 단추를 선택합니다.

   "Calendar.cs"라는 파일을 프로젝트에 추가합니다. 끝의 **.cs**는 C# 코드 파일에 지정된 파일 확장명입니다. **솔루션 탐색기**의 Visual 프로젝트 계층 구조에 파일이 표시되고 편집기에서 내용이 열립니다.

1. **Calendar.cs** 파일의 내용을 다음 코드로 바꿉니다.

   ```csharp
   using System;

   namespace QuickDate
   {
       internal class Calendar
       {
           static void Main(string[] args)
           {
               DateTime now = GetCurrentDate();
               Console.WriteLine($"Today's date is {now}");
               Console.ReadLine();
           }

           internal static DateTime GetCurrentDate()
           {
               return DateTime.Now.Date;
           }
       }
   }
   ```

   코드의 기능을 이해할 필요는 없지만 원하는 경우 프로그램을 실행하고 콘솔 창에 오늘 날짜가 표시된 것을 확인할 수 있습니다.

## <a name="add-a-second-project"></a>두 번째 프로젝트 추가

일반적으로 솔루션에 둘 이상의 프로젝트 및 종종 이러한 프로젝트 참조가 서로 포함됩니다. 솔루션의 프로젝트는 클래스 라이브러리, 실행 가능한 응용 프로그램 및 일부 단위 테스트 프로젝트 또는 웹 사이트일 수 있습니다.

솔루션에 단위 테스트 프로젝트를 추가해 보겠습니다. 이번에는 프로젝트에 추가 코드 파일을 추가하지 않아도 되도록 프로젝트 템플릿으로 시작하겠습니다.

1. **솔루션 탐색기**의 **솔루션 'QuickSolution'**을 마우스 오른쪽 단추로 클릭하거나 상황에 맞는 메뉴에서 **추가** > **새 프로젝트...**를 선택합니다.

   **새 프로젝트 추가** 대화 상자가 열립니다.

1. 왼쪽 창에서 **Visual Basic**을 확장하고 **테스트** 범주를 선택합니다. 가운데 창에서 **단위 테스트 프로젝트(.NET Framework)**를 선택합니다. "QuickTest" 프로젝트 이름을 지정한 다음 **확인** 단추를 선택합니다.

   두 번째 프로젝트가 **솔루션 탐색기**에 추가되고 **UnitTest1.vb**라는 파일이 편집기에서 열립니다. **.vb**는 Visual Basic 코드 파일에 지정된 파일 확장명입니다.

   ![두 개의 프로젝트와 솔루션 탐색기](media/quickstart-projects-solution-explorer.png)

## <a name="add-a-project-reference"></a>프로젝트 참조 추가

해당 프로젝트에 대한 참조를 추가하기 위해 새 단위 테스트 프로젝트를 사용하여 **QuickDate** 프로젝트에서 이 메서드를 테스트하려고 합니다. 그러면 두 개의 프로젝트 간에 빌드 종속성을 만듭니다. 즉, 솔루션을 빌드할 때 **QuickTest** 전에 **QuickDate**가 빌드됩니다.

1. **QuickTest** 프로젝트에서 **참조** 노드를 선택하고 마우스 오른쪽 단추로 클릭하거나 상황에 맞는 메뉴에서 **참조 추가...**를 선택합니다.

   ![참조 메뉴 추가](media/quickstart-projects-add-reference.png)

   **참조 관리자** 대화 상자가 열립니다.

1. 왼쪽 창에서 **프로젝트**를 확장하고 **솔루션**을 선택합니다. 가운데 창에서 **QuickDate** 옆에 있는 확인란을 선택한 후 **확인** 단추를 선택합니다.

   **QuickDate** 프로젝트에 대한 참조가 추가됩니다.

## <a name="add-test-code"></a>테스트 코드 추가

1. 이제 Visual Basic 코드 파일에 테스트 코드를 추가합니다. **UnitTest1.vb**의 내용을 다음 코드로 바꿉니다.

   ```vb
   <TestClass()> Public Class UnitTest1

       <TestMethod()> Public Sub TestGetCurrentDate()
           Assert.AreEqual(DateTime.Now.Date, QuickDate.Calendar.GetCurrentDate())
       End Sub

   End Class
   ```

   일부 코드에서 빨간색 "물결선"이 표시됩니다. 테스트 프로젝트를 [friend 어셈블리](/dotnet/csharp/programming-guide/concepts/assemblies-gac/friend-assemblies)에서 **QuickDate** 프로젝트로 만들어서 이 오류를 수정합니다.

1. **QuickDate** 프로젝트에서 **Calendar.cs** 파일이 아직 열려 있지 않으면 열어서, 다음 using 문 및 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성을 추가하여 테스트 프로젝트에서 오류를 해결합니다.

   ```csharp
   using System.Runtime.CompilerServices;

   [assembly: InternalsVisibleTo("QuickTest")]
   ```

   코드 파일이 다음과 같이 나타납니다.

   ![CSharp 코드](media/quickstart-projects-cs-code.png)

## <a name="project-properties"></a>프로젝트 속성

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성이 포함된 C# 코드 파일의 줄은 **QuickTest** 프로젝트의 어셈블리 이름을 참조합니다. 어셈블리 이름은 프로젝트 이름과 동일하지 않을 수 있습니다. 프로젝트의 어셈블리 이름을 찾으려면 프로젝트 속성을 엽니다.

1. **솔루션 탐색기**에서 **QuickTest** 프로젝트를 선택합니다. 마우스 오른쪽 단추로 클릭하거나 상황에 맞는 메뉴에서 **속성**을 선택하거나 **Alt**+**Enter** 키를 누릅니다.

   프로젝트의 속성 페이지가 **응용 프로그램** 탭에서 열립니다. **QuickTest** 프로젝트의 어셈블리의 이름은 실제로 "QuickTest"입니다. 변경하려는 경우 여기에서 변경할 수 있습니다. 그런 다음 테스트 프로젝트를 빌드할 때 결과 실행 파일의 이름이 **QuickTest.exe**에서 선택한 이름으로 변경됩니다.

   ![프로젝트 속성](media/quickstart-projects-properties.png)

1. **컴파일** 및 **설정**과 같은 프로젝트 속성 페이지의 일부 다른 탭을 탐색합니다. 이러한 탭은 프로젝트의 형식에 따라 달라집니다.

## <a name="next-steps"></a>다음 단계

단위 테스트가 작동하는지 확인하려면 메뉴 모음에서 **테스트** > **실행** > **모든 테스트**를 선택합니다. **테스트 탐색기**라는 창이 열리면 **TestGetCurrentDate** 테스트에 통과했다고 표시됩니다.

이 빠른 시작을 완료한 것을 축하 드립니다! 다음으로 Visual Studio에 대한 다른 빠른 시작 중 일부를 탐색하거나 [프로젝트 및 솔루션 만들기](../ide/creating-solutions-and-projects.md)에 대해 자세히 알아봅니다.

## <a name="see-also"></a>참고 항목

[빠른 시작: 먼저 Visual Studio IDE 살펴보기](../ide/quickstart-ide-orientation.md)  
[빠른 시작: Visual Studio IDE 및 편집기 개인 설정](../ide/quickstart-personalize-the-ide.md)  
[빠른 시작: 편집기에서 코딩](../ide/quickstart-editor.md)  
[프로젝트 및 솔루션 속성 관리](../ide/managing-project-and-solution-properties.md)  
[프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)  
[프로젝트 또는 솔루션 없이 Visual Studio에서 코드 개발](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)  
[Visual Studio IDE 개요](../ide/visual-studio-ide.md)
