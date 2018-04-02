---
title: Visual Studio에서 진단 데이터 어댑터에 대한 시간 제한 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Diagnostic Data Adapter, increasing time-outs
ms.assetid: 39fff4fc-9233-4f67-96ac-e81bbaf7ca82
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 50bdf23e83ca9ef70c40b010050a3e6aba90e0a5
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-prevent-time-outs-for-diagnostic-data-adapters"></a>방법: 진단 데이터 어댑터에 대한 시간 제한 방지

테스트 설정에 진단 데이터 어댑터를 사용하는 경우 다음 이유 중 하나로 인해 테스트 실행을 시작할 때 시간 초과가 발생할 수 있습니다.

-   테스트 컨트롤러 컴퓨터에서 테스트 컨트롤러 서비스가 실행되고 있지 않습니다. 서비스를 다시 시작해야 할 수 있습니다. 테스트 컨트롤러를 결정하고 테스트 컨트롤러를 관리하는 방법에 대한 자세한 내용은 [Visual Studio를 사용하여 테스트 컨트롤러 및 테스트 에이전트 관리](../test/manage-test-controllers-and-test-agents.md)를 참조하세요.

-   원격 컴퓨터에서 데이터를 수집하는 경우 방화벽이 Microsoft Test Manager를 차단할 수 있습니다. Microsoft Test Manager를 실행하는 컴퓨터에서는 테스트 컨트롤러로부터 들어오는 연결을 허용해야 합니다. 컨트롤러에서 보낸 메시지가 방화벽에 의해 차단되어 Microsoft Test Manager가 메시지를 받지 못할 경우 시간 초과가 발생합니다. Microsoft Test Manager를 실행하는 컴퓨터에서 방화벽 설정을 확인해야 합니다. 방화벽 설정에 대한 자세한 내용은 다음 [Microsoft 웹 사이트](http://go.microsoft.com/fwlink/?LinkId=184980)를 참조하세요.

-   테스트 컨트롤러에서는 Microsoft Test Manager를 실행하는 컴퓨터의 이름을 확인할 수 없습니다. DNS에서 이 컴퓨터에 대한 잘못된 주소를 제공할 경우 이 문제가 발생할 수 있습니다. 이 문제를 해결하려면 네트워크 관리자에게 문의해야 합니다.

 많은 양의 데이터를 수집해야 하는 장기 테스트를 실행하는 경우 데이터 수집 과정에서 시간 초과가 발생할 수 있습니다. 뒤에 나오는 절차에 따라 이 문제를 해결할 수 있습니다.

 이런 경우 Microsoft Test Manager의 구성 파일 또는 제한 시간을 초과하는 테스트 에이전트의 구성 파일을 업데이트하여 제한 시간을 늘릴 수 있습니다.

 Microsoft Test Manager의 경우 구성 파일은 **mtm.exe.config**입니다. 이 파일은 *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE* 디렉터리에 있습니다.

 테스트 에이전트를 업데이트하려면 테스트 에이전트 컴퓨터에서 다음 구성 파일을 업데이트해야 합니다. 이러한 파일은 모두 테스트 에이전트 컴퓨터의 *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE* 디렉터리에 있습니다.

-   QTAgent.exe.config

-   QTAgent32.exe.config

-   QTDCAgent.exe.config

-   QTDCAgent32.exe.config

 환경에서 수동 테스트를 실행하고 데이터를 수집하는 경우 버그가 만들어지거나 테스트 사례가 완료되면 진단 데이터 어댑터에서 수집된 모든 데이터가 수동 테스트를 실행하는 컴퓨터로 전송됩니다. 수집된 데이터의 양이 많거나 네트워크 연결 속도가 느린 경우에는 기본값인 60초보다 더 오랜 시간이 걸릴 수 있습니다. 예를 들어 많은 프로세스에 대한 IntelliTrace 이벤트와 호출 정보를 수집하도록 IntelliTrace 어댑터를 구성한 경우 데이터 전송 시간이 기본 제한 시간을 초과할 수 있습니다. 이 값을 늘리려면 다음 절차에 따라 **mtm.exe.config**를 업데이트합니다.

 Test Runner 작업 또는 테스트 에이전트에서 제한 시간을 초과하면 오류 메시지가 표시됩니다. 테스트 에이전트의 오류 메시지에는 시간을 초과한 테스트 에이전트 컴퓨터에 대한 정보가 포함됩니다. 표시된 오류 메시지에 따라 다음 지침을 사용하여 구성 파일을 업데이트합니다.

## <a name="to-increase-the-time-outs-for-your-diagnostic-data-adapters"></a>진단 데이터 어댑터에 대한 제한 시간을 늘리려면

1.  Windows 탐색기 또는 파일 탐색기 창을 엽니다.

     이렇게 하려면 **시작**을 마우스 오른쪽 단추로 클릭하고 **탐색**을 가리킵니다.

    > [!NOTE]
    > 구성 파일을 업데이트하려면 관리자 권한이 필요할 수도 있습니다.

2.  컴퓨터에서 업데이트할 파일이 포함된 *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE* 디렉터리를 찾습니다.

3.  파일을 마우스 오른쪽 단추로 클릭하고 **연결 프로그램**을 가리킵니다. 편집기를 선택합니다.

     편집기에 파일이 표시됩니다. 이 파일에는 많은 설정이 저장되어 있습니다. 이러한 설정의 대부분은 Microsoft Test Manager를 사용하여 변경할 수 있습니다. 그러나 제한 시간 설정은 다음 단계의 설명에 따라 수동으로 변경해야 합니다.

4.  제한 시간 값을 늘리려면 테스트 실행 설정 섹션을 수정해야 합니다. 이 섹션의 형식은 다음과 같습니다.

    ```
    <!-- Begin: Test execution settings -->

        <!-- How long test runner will wait for an event raised to all local data collectors to complete.  Default is 300. -->
        <add key="DataCollectorEventTimeoutInSeconds" value="300"/>

        <!-- How long test runner will wait for test run operations, such as starting or stopping a test run, to complete.  Default is 60. -->
        <add key="RunOperationTimeoutInSeconds" value="60"/>

        <!-- End: Test execution settings -->
    ```

5.  이벤트가 완료될 때까지 진단 데이터 어댑터가 대기하는 시간을 늘리려면 **DataCollectorEventTimeoutInSeconds** 키의 값을 늘립니다.

6.  Test Runner 작업에 대한 제한 시간 오류 메시지가 표시된 경우에는 **RunOperationTimeoutInSeconds** 키의 값을 늘려야 합니다.

7.  버그에 대해 수집된 데이터의 전송 제한 시간 또는 테스트가 테스트를 실행하는 컴퓨터에서 종료되는 제한 시간을 늘리려면 파일의 appSettings 섹션에서 **mtm.exe.config**에 다음 제한 시간을 추가해야 합니다.

    ```
    <!-- How long test runner waits for data collected by diagnostic data adapters to be transferred to the computer. Default is 60 seconds. -->
    <add key="GetCollectorDataTimeout" value="300"/>
    ```

    > [!NOTE]
    > 제한 시간 값은 초 단위입니다.

8.  파일의 변경 내용을 저장하고 이전에 시간 초과된 테스트를 다시 실행합니다.

## <a name="see-also"></a>참고 항목

- [테스트 설정을 사용하여 진단 정보 수집](../test/collect-diagnostic-information-using-test-settings.md)