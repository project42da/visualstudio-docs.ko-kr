---
title: '워크플로 디자이너-방법: WCF 워크플로 서비스 응용 프로그램 만들기'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 12d675ac-27d8-4d86-ba16-6f7688f8c841
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93fb69862c228a3b6e61467facba188dd20c67c7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-wcf-workflow-service-application"></a>방법: WCF 워크플로 서비스 응용 프로그램 만들기

Windows Communication Foundation (WCF) 워크플로 서비스 응용 프로그램은 프로세스 경계를 넘어 클라이언트와 메시지를 주고 받는 분산된 통신 서비스입니다. 서비스 쪽에서 서비스 계약 구현은.NET Framework 3.5의 레거시 워크플로 서비스와 비슷한 방식으로.NET Framework 4의 워크플로 활동을 통해 선언적으로 수행 됩니다.

## <a name="to-create-a-wcf-workflow-service-application"></a>WCF 워크플로 서비스 응용 프로그램을 만들려면

1.  Visual Studio 2010을 시작합니다.

2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음, **프로젝트**를 선택합니다.

     **새 프로젝트** 대화 상자가 열립니다.

3.  에 **설치 된 템플릿** 창 선택 **WCF** 또는 **워크플로** 중 하 나와 **Visual C#** 또는 **VisualBasic** 선택한 언어에 따라 그룹화 합니다.

4.  가운데 창에서 선택 **WCF 워크플로 서비스 응용 프로그램**합니다.

5.  에 **이름** 상자에 프로젝트를 식별 하기 쉽도록 프로젝트를 설명 하는 이름을 입력 합니다.

6.  에 **위치** 상자에서 프로젝트를 저장 하거나 클릭 하려는 디렉터리를 입력 **찾아보기** 찾습니다.

7.  에 **솔루션** 상자에서 새 솔루션 만들기 또는 클릭 한 다음 선택 **확인**합니다.

    > [!NOTE]
    > 기존 솔루션에 워크플로 콘솔 응용 프로그램을 추가 하려는 경우 Visual Studio 2010에서 해당 솔루션을 열고, 솔루션을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기**를 선택 하 고 **추가**, 다음  **새 프로젝트** 열려는 **새 프로젝트** 대화 상자. 그런 다음 이 절차의 윗부분에 설명된 대로 진행합니다.

8.  프로젝트 템플릿이 서비스 정의를 XAML로 만듭니다. Windows 워크플로 디자이너의 디자인 보기로 열립니다는 <xref:System.Activities.Statements.Sequence> 집합이 포함 된 활동 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 활동입니다.

## <a name="see-also"></a>참고자료

- [방법: 활동 만들기](/dotnet/framework/windows-workflow-foundation/how-to-create-an-activity)
- [워크플로 프로젝트 만들기](../workflow-designer/creating-a-workflow-project.md)