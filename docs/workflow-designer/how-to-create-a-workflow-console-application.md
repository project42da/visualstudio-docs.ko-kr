---
title: '워크플로 디자이너-방법: 워크플로 콘솔 응용 프로그램 만들기'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 51a2eea7-921c-49f1-b358-68afc27f1ee9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6461a644bdedd3d391059cd8a3a17f887e77c6b3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-workflow-console-application"></a>방법: 워크플로 콘솔 응용 프로그램 만들기

Windows WF (Workflow Foundation)를 사용 하면 시스템 또는 사용자 프로세스를 실행 하기 위한 워크플로 만들 수 있습니다. Windows 워크플로 디자이너는 이러한 워크플로 만들기 위한 디자인 화면을 제공 합니다. 워크플로 디자이너는 Visual Studio 내에서 워크플로 만드는 데 사용할 수 있습니다 또는 디자이너를 다시 호스트 하는 다른 응용 프로그램에 통합할 수 있습니다.

이 항목에서는 워크플로를 만드는 콘솔 응용 프로그램에서 Visual Studio 2010에서 워크플로 디자이너를 사용 하는 방법을 설명 합니다.

## <a name="to-create-a-workflow-console-application"></a>워크플로 콘솔 응용 프로그램을 만들려면

1.  Visual Studio 2010을 시작합니다.

2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음, **프로젝트**를 선택합니다.

     **새 프로젝트** 대화 상자가 열립니다.

3.  에 **설치 된 템플릿** 창 선택 **워크플로** 중 하 나와 **Visual C#** 또는 **Visual Basic** 그룹화에 따라 프로그램 기본 설정 언어입니다.

4.  가운데 창에서 선택 **워크플로 콘솔 응용 프로그램**합니다.

5.  에 **이름** 상자에 프로젝트를 식별 하기 쉽도록 프로젝트를 설명 하는 이름을 입력 합니다.

6.  에 **위치** 상자에서 프로젝트를 저장 하거나 클릭 하려는 디렉터리를 입력 **찾아보기** 찾습니다.

7.  에 **솔루션** 상자에 새 솔루션에 대 한 이름을 입력 합니다. 클릭 **확인** 는 응용 프로그램을 만듭니다.

    > [!NOTE]
    > 기존 솔루션에 워크플로 콘솔 응용 프로그램을 추가 하려는 경우 Visual Studio 2010에서 해당 솔루션을 열고, 솔루션을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기**를 선택 하 고 **추가**, 다음  **새 프로젝트** 열려는 **새 프로젝트** 대화 상자. 그런 다음 이 절차의 윗부분에 설명된 대로 진행합니다.

8.  프로젝트 템플릿이 XAML로 워크플로 정의를 만들고 소스 코드 안에 콘솔 응용 프로그램 정의를 만듭니다. Workflow Designer가 열리고 만들어진 워크플로의 캔버스가 표시 됩니다.

9. 활동이 나 다른 워크플로 항목을 끌어 워크플로 구성 하는 **도구 상자** 워크플로의 디자인 화면에 있습니다.

## <a name="see-also"></a>참고자료

- [워크플로 프로젝트 만들기](../workflow-designer/creating-a-workflow-project.md)