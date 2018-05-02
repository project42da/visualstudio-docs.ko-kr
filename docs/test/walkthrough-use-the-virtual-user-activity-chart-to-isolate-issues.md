---
title: Visual Studio에서 부하 테스트에 대한 가상 사용자 동작 차트 사용
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, virtual user activity chart
- virtual user activity chart, isolating performance issues
ms.assetid: d1c10fb9-cfeb-4e7f-9991-2d1e1103699e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: fedc9aebb4d57e258370179bbf820abdc8978940
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-using-the-virtual-user-activity-chart-to-isolate-issues"></a>연습: 가상 사용자 동작 차트를 사용하여 문제 격리

이 연습을 통해 가상 사용자 동작 차트를 사용하여 부하 테스트를 실행한 개별 가상 사용자에게 발생한 오류를 격리하는 방법을 배웁니다.

 가상 사용자 동작 차트를 사용하여 부하 테스트와 관련한 가상 사용자 동작을 시각화할 수 있습니다. 차트의 각 행은 개별 가상 사용자를 나타냅니다. 가상 사용자 동작 차트에는 각 가상 사용자가 테스트 중에 실행한 작업이 정확하게 표시됩니다. 이 차트에서는 사용자 동작 패턴을 확인하거나, 패턴을 로드하거나, 실패했거나 느린 테스트를 연결하거나, 다른 가상 사용자 동작 요청을 확인하여 성능 문제를 격리할 수 있습니다. 가상 사용자 동작 차트는 부하 테스트를 완료한 이후에만 사용할 수 있습니다.

 이 연습에서는 다음 작업을 수행합니다.

-   가상 사용자 동작 차트와 관련된 다음 도구를 사용하는 방법에 대해 알아 봅니다.

    -   **특정 기간 확대** 도구를 사용하여, 분석할 차트에 특정 기간을 지정할 수 있습니다.

    -   **정보 범례** 창과 **필터 결과** 창을 통해 차트에 필터링을 적용하여 문제를 격리할 수 있습니다.

-   가상 사용자 동작 차트를 사용하여 특정 가상 사용자에게 발생한 오류를 분석하고 문제가 되는 오류 형식 정보를 확인합니다.

 자세한 내용은 [세부 정보 뷰에서 가상 사용자 동작 분석](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)을 참조하세요.

## <a name="prerequisites"></a>전제 조건

-   Visual Studio Enterprise

-   다음의 절차를 완료합니다.

    -   [웹 성능 테스트 기록 및 실행](http://msdn.microsoft.com/en-us/bd0a82fd-cec0-4861-bc09-e1b0b2d258ef)

    -   [부하 테스트 만들기 및 실행](http://msdn.microsoft.com/en-us/7041cbcf-9ab1-4579-98ff-8f296aeaded4)

## <a name="open-the-colorwebapp-solution-created-in-the-previous-walkthroughs"></a>이전 연습에서 만든 ColorWebApp 솔루션 열기

### <a name="open-the-solution"></a>솔루션 열기

1.  Visual Studio를 시작합니다.

2.  LoadTest1.loadtest가 포함된 ColorWebApp 솔루션을 엽니다. 이 부하 테스트는 이 항목의 시작 부분에서 사전 요구 사항 단원에 나열된 세 가지 연습의 단계를 수행하면 나오는 결과입니다.

     이 연습의 나머지 단계에서는 ColorWebApp라는 웹 응용 프로그램, ColorWebAppTest.webtest라는 웹 성능 테스트 및 LoadTest1.loadtest라는 부하 테스트가 있다고 가정합니다.

## <a name="run-the-load-test"></a>부하 테스트 실행
 부하 테스트를 실행하여 가상 사용자 동작 데이터를 수집합니다.

### <a name="run-the-load-test-to-collect-virtual-user-activity-data"></a>부하 테스트를 실행하여 가상 사용자 동작 데이터 수집

-   부하 테스트 편집기의 도구 모음에서 **실행** 단추를 선택합니다. LoadTest1 실행이 시작됩니다.

## <a name="isolate-issues-in-the-virtual-user-activity-chart"></a>가상 사용자 동작 차트에서 문제 격리

부하 테스트를 실행하고 가상 사용자 동작 데이터를 수집한 후 가상 사용자 동작 차트에 있는 테스트 분석기의 자세히 보기를 사용하여 부하 테스트 결과의 데이터를 볼 수 있습니다. 또한 가상 사용자 동작 차트를 사용하여 부하 테스트에서 성능 문제를 격리할 수 있습니다.

### <a name="to-use-the-virtual-user-activity-chart-in-your-load-test-results"></a>부하 테스트 결과에서 가상 사용자 동작 차트를 사용하려면

1.  부하 테스트 실행이 완료되면 부하 테스트 결과에 대한 요약 페이지가 부하 테스트 분석기에 표시됩니다. 도구 모음에서 **그래프** 단추를 선택합니다.

     그래프 뷰가 표시됩니다.

2.  **페이지 응답 시간** 그래프에서 임계값 위반 아이콘 중 하나의 근처를 마우스 오른쪽 단추로 클릭하고 **사용자 정보로 이동**을 선택합니다.

    > [!NOTE]
    > 부하 테스트 편집기의 도구 모음에서 **세부 정보** 단추를 사용하여 사용자 동작 차트를 열 수도 있습니다. 그러나 **사용자 정보로 이동** 옵션을 사용하는 경우 가상 사용자 동작 차트가 그래프에서 마우스 오른쪽 단추를 클릭한 테스트 부분으로 자동 확대됩니다.

     임계값 위반이 발생한 기간에 초점을 맞춘 **가상 사용자 동작 차트**와 함께 자세히 보기가 표시됩니다.

     Y축의 가로 그림은 개별 가상 사용자를 나타냅니다. X축에는 부하 테스트 실행에 대한 시간 표시 막대가 표시됩니다.

3.  **가상 사용자 동작 차트** 아래의 **특정 기간 확대** 도구에서 왼쪽 슬라이더와 오른쪽 슬라이더를 임계값 위반 아이콘에 가까워질 때까지 조정합니다. 그러면 **가상 사용자 동작 차트**에서 시간 범위가 변경됩니다.

4.  **정보 범례**에서 **(오류 강조 표시)** 에 대한 확인란을 선택합니다. 임계값 위반을 유발한 가상 사용자가 강조 표시됩니다.

5.  **필터 결과** 창에서 **성공적인 결과 표시** 및 **HttpError**에 대한 확인란의 선택을 취소하고 **ValidationRuleError** 확인란은 선택된 채로 둡니다.

     **가상 사용자 동작 차트**에는 이전 연습에서 구성한 임계값 위반에 의해 지정된 대로 Red.aspx 페이지에서 3초 이상 소요한 가상 사용자만 표시됩니다.

6.  임계값 위반에 대한 유효성 검사 규칙 오류를 포함하는 가상 사용자를 나타내는 가로줄 위에 마우스 포인터를 둡니다.

7.  다음 정보와 함께 도구 설명이 표시됩니다.

    -   **User Id**

    -   **시나리오**

    -   **테스트**

    -   **결과**

    -   **Network**

    -   **시작 시간**

    -   **기간**

    -   **에이전트**

    -   **테스트 로그**

8.  **테스트 로그**는 링크입니다. **테스트 로그** 링크를 선택합니다.

9. 로그에 연결된 ColorWebTest 웹 성능 테스트가 웹 성능 테스트 결과 뷰어에서 열립니다. 그러면 임계값 위반이 발생한 위치를 격리할 수 있습니다.

     **정보 범례** 및 **필터 결과** 창의 다양한 설정을 사용하여 부하 테스트의 오류와 성능 문제를 쉽게 격리할 수 있습니다. 이러한 설정과 **특정 기간 확대** 도구를 사용하여 가상 사용자 데이터가 **가상 사용자 동작 차트**에 어떻게 나타나는지 확인합니다.

## <a name="see-also"></a>참고 항목

- [세부 정보 뷰에서 가상 사용자 동작 분석](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [테스트 컨트롤러 및 테스트 에이전트](configure-test-agents-and-controllers-for-load-tests.md)
- [방법: 분산 부하 테스트에 대한 테스트 설정 만들기](../test/how-to-create-a-test-setting-for-a-distributed-load-test.md)
- [테스트 에이전트 설치 및 구성](../test/lab-management/install-configure-test-agents.md)
- [테스트 설정을 사용하여 진단 정보 수집](../test/collect-diagnostic-information-using-test-settings.md)