---
title: '워크플로 디자이너-방법: 식 편집기 사용'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Presentation.View.ExpressionTextBox.UI
ms.assetid: b5f961dd-6dda-41a9-9cae-0383d479ef3d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2e14a967b9721973d8d545e10f58cab3c68b8e15
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-the-expression-editor"></a>방법: 식 편집기 사용

식 편집기에 입력 하 고 이러한 식을 계산 하는 방법으로 많은 워크플로 활동에서 사용 되는 Windows 워크플로 디자이너 컨트롤입니다. 식 편집기는 IntelliSense, 색 지정, ParamInfo, 오류 물결선 등 다양한 기능이 포함된 완벽한 IDE 편집 환경을 제공합니다. 그리고 컴파일러는 입력된 식의 유효성을 검사합니다. 식이 잘못된 경우 오류 아이콘이 표시됩니다. 편집기로 열 수도 있습니다는 **식 편집기** 대화 상자.

 식이란 인수나 속성에 바인딩된 Visual Basic 코드 또는 리터럴 값입니다. 식에는 새 값을 생성하기 위해 연산으로 연결되는 변수, 상수, 리터럴, 속성 등의 값 요소가 포함됩니다. 응용 프로그램이 C#을 사용하는 프로그램에 있는 경우에도 식은 VB.NET 구문으로 작성됩니다. 즉, 대/소문자에 상관 없이 사용 하 여 비교를 수행 하는 단일 등호 ("= =") 하는 대신 기호 ("="), 부울 연산자는 단어 "및" 및 "또는" 기호 대신 "& &" 및 "&#124;&#124;", 및 **Nothing**  대신 사용 됩니다 **null**합니다. 식과 Visual Basic의 연산자에 대 한 자세한 내용은 및 일부 샘플에 대 한 참조 [Visual Basic의 연산자 및 식](http://go.microsoft.com/fwlink/?LinkId=186818)합니다.

 **식 편집기** 다음과 같이 동작 합니다.

-   포커스가 식 편집기에 있지 않을 때는 일반 TextBlock 컨트롤과 비슷하게 보입니다.

-   포커스를 식 편집기에 맞추면 식 편집기 컨트롤처럼 보이고 동작하다가, 포커스를 바꾸면 다시 일반 TextBlock처럼 보입니다.

-   다시 호스트된 Workflow Designer의 식 편집기에 포커스를 맞추면 TextBox처럼 동작하고, 다시 호스트된 워크플로 디자이너에서 포커스를 옮기면 식 편집기가 다시 일반 TextBlock처럼 보입니다.

> [!NOTE]
> 식 편집기에 대 한 IntelliSense는 Visual Studio 2010 안에서 사용할 수 있습니다. Visual Studio 2010와 다시 호스트 된 시나리오 모두에서 컴파일러가 입력 후 식이 올바르지 않으면 식 편집기 오류 아이콘을 표시 식 유효성을 검사 합니다.

## <a name="use-the-expression-editor"></a>식 편집기를 사용 하 여

1.  Visual Studio 2010의 새로운 또는 기존 워크플로 프로젝트를 엽니다.

2.  예를 들어 <xref:System.Activities.Statements.Assign> 활동을 워크플로에 추가합니다.

    > [!NOTE]
    > 여러 가지 워크플로 활동에 식 편집기가 있습니다. 식 TextBlock은 변수 디자이너, 인수 디자이너 및 동적 인수 디자이너에도 나타납니다. 예제에서는 <xref:System.Activities.Statements.Assign> 활동을 사용합니다.

3.  <xref:System.Activities.Statements.Assign> 활동의 활동 디자이너에서 왼쪽 식 편집기를 클릭합니다.

     회색 워터 마크 문자열  **\<를 >** 및  **\<VB 식 입력 >** 는 기본 텍스트 문자열의 식 편집기에는 <xref:System.Activities.Statements.Assign> 활동입니다.

4.  식을 입력합니다. 문자열을 입력할 경우 문자열 앞뒤에 물음표를 붙여야 합니다. 식 인수를 변수에 바인딩하려면 물음표를 제거합니다.

     작업을 마친 뒤 식 편집기 바깥 영역을 선택하여 디자이너의 다른 부분으로 포커스를 옮깁니다. 그러면 앞에서 설명한 것처럼 컴파일러가 식의 유효성을 검사합니다.

     속성 표에서 속성 이름 옆에 있는 줄임표를 클릭하여 식을 입력/편집할 수도 있습니다. 열립니다는 **식 편집기** 대화 상자로 합니다.

## <a name="see-also"></a>참고자료

- <xref:System.Activities.Presentation.View.ExpressionTextBox>