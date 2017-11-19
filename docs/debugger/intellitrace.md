---
title: IntelliTrace | Microsoft Docs
ms.custom: 
ms.date: 07/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.historicaldebug.overview
helpviewer_keywords:
- debugger, recording execution history
- debugging, recording execution history
- IntelliTrace [Visual Studio ALM]
- IntelliTrace, debugging applications
- debugger, (See also IntelliTrace [Visual Studio ALM])
- debugging, (See also IntelliTrace [Visual Studio ALM])
- IntelliTrace, collecting data from Test Manager
- IntelliTrace
- Test Manager, debugging with IntelliTrace
- IntelliTrace, debugging after a crash
ms.assetid: 486bfec2-39bd-4d78-892a-42352128ee52
caps.latest.revision: "135"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1f009abffb1c956a0f7c57315181234fbea2fc1c
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="intellitrace"></a>IntelliTrace
IntelliTrace를 사용하여 코드의 실행 내역을 기록하고 추적하면 응용 프로그램 디버깅에 사용되는 시간을 줄일 수 있습니다. IntelliTrace를 사용하면 다음이 가능하므로 손쉽게 버그를 찾을 수 있습니다.  
  
-   특정 이벤트 기록  
  
     에 표시 되는 데이터 관련된 코드 검사는 **지역** 디버거 이벤트 및 함수 호출 정보 중 창  
  
-   재현하기 어렵거나 배포에서 발생하는 오류 디버그  
  
 Visual Studio Enterprise Edition(Professional 또는 Community Edition 아님)에서 IntelliTrace를 사용할 수 있습니다.  
  
## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
|||  
|-|-|  
|**IntelliTrace로 응용 프로그램을 디버그 합니다.**<br /><br /> -이전 이벤트 표시 합니다.<br />호출 정보 이전 이벤트를 표시 합니다.<br />-내 IntelliTrace 세션을 저장 합니다.<br />-IntelliTrace가 수집 하는 데이터를 제어 합니다.|-   [연습: IntelliTrace 사용](../debugger/walkthrough-using-intellitrace.md)<br />- [IntelliTrace 기능](../debugger/intellitrace-features.md)<br />-   [기록 디버깅](../debugger/historical-debugging.md)<br />-   [IntelliTrace 단계 백을 사용 하 여 스냅숏을 볼](../debugger/how-to-use-intellitrace-step-back.md)|  
|**테스트 관리자에서 테스트 세션 동안 IntelliTrace 데이터 수집**|-   [수동 테스트에서 추가 진단 데이터 수집](/devops-test-docs/test/collect-more-diagnostic-data-in-manual-tests)|  
|**배포 된 응용 프로그램에서 IntelliTrace 데이터 수집**|-   [IntelliTrace 독립 실행형 수집기 사용](../debugger/using-the-intellitrace-stand-alone-collector.md)|  
|**IntelliTrace 로그 파일 (.iTrace 파일)에서 디버깅을 시작 합니다.**|-   [저장 된 IntelliTrace 데이터를 사용 하 여](../debugger/using-saved-intellitrace-data.md)|  
  
##  <a name="IntelliTraceSupport"></a>IntelliTrace로 앱 디버깅할 수 있습니까?  
  
|||  
|-|-|  
|**지원됨**|-.NET Framework 2.0 또는 더 높은 버전을 사용 하는 Visual Basic 및 Visual C# 응용 프로그램<br />     ASP.NET, Microsoft Azure, Windows Forms, WCF, WPF, Windows Workflow, SharePoint 2010, SharePoint 2013 및 64비트 앱을 포함한 대부분의 응용 프로그램을 디버깅할 수 있습니다.<br />     IntelliTrace로 SharePoint 응용 프로그램을 디버깅 하려면 참조 [연습: IntelliTrace를 사용 하 여 SharePoint 응용 프로그램 디버깅](../sharepoint/walkthrough-debugging-a-sharepoint-application-by-using-intellitrace.md)합니다.<br />     IntelliTrace 사용 하 여 Microsoft Azure 앱을 디버깅 하려면 참조 [IntelliTrace 및 Visual Studio는 게시 된 클라우드 서비스 디버깅](/azure/vs-azure-tools-intellitrace-debug-published-cloud-services)합니다.|  
|**제한 된 지원**|-.NET core 및 ASP.NET Core 응용 프로그램 이벤트에 대해서만 지원 합니다.<br />-시험 차원의 F # 응용 프로그램<br />이벤트에 대해서만 지원 되는 Windows 스토어 앱|  
|**지원 안 함**|-C + +, 다른 언어 및 스크립트<br />Windows 서비스, Silverlight, Xbox, 또는 [!INCLUDE[winmobile](../debugger/includes/winmobile_md.md)] 앱|  
  
> [!NOTE]
>  이미 실행 중인 프로세스를 디버깅 하려는 경우에 IntelliTrace 이벤트에만 사용 (호출 정보 없음)를 수집할 수 있습니다. 로컬 컴퓨터에서 32 비트 또는 64 비트 프로세스에 연결할 수 있습니다. 프로세스에 연결 하기 전에 발생 하는 이벤트를 수집 되지 않습니다.
  
##  <a name="IntelliTraceVSTraditional"></a>IntelliTrace로 디버깅 하는 이유?  
 전통적인 또는 *라이브* 디버깅만 응용 프로그램의 현재 상태, 이전 이벤트에 대 한 제한 된 데이터를 표시 합니다. 응용 프로그램의 현재 상태를 기반으로 이러한 이벤트를 유추하거나 응용 프로그램을 다시 실행하여 이러한 이벤트를 다시 만들어야 합니다.  
  
 IntelliTrace는 이러한 시점에 특정 이벤트와 데이터를 기록하여 전통적인 디버깅 경험을 확장합니다. 이렇게 하면 특히 버그가 발생한 위치를 지나친 경우 응용 프로그램을 다시 시작하지 않고 어떤 일이 발생했는지 확인할 수 있습니다. IntelliTrace는 전통적인 디버깅 중에 기본적으로 켜지며 데이터를 표시하지 않고 자동으로 수집합니다. 이렇게 하면 전통적인 디버깅과 IntelliTrace 디버깅 사이를 쉽게 전환하여 기록된 정보를 볼 수 있습니다. 참조 [IntelliTrace 기능](../debugger/intellitrace-features.md) 및 [IntelliTrace 수집 데이터 합니까?](#WhatData)  
  
 IntelliTrace는 재현하기 어렵거나 배포할 때 발생하는 오류를 디버깅할 수도 있습니다. IntelliTrace 데이터를 수집하고 IntelliTrace 로그 파일(.iTrace 파일)에 저장할 수 있습니다. .iTrace 파일은 예외, 성능 이벤트, 웹 요청, 테스트 데이터, 스레드, 모듈 및 기타 시스템 정보에 대한 세부 정보를 포함하고 있습니다. Visual Studio Enterprise에서 이 파일을 열고 항목을 선택하고 IntelliTrace를 사용하여 디버깅을 시작할 수 있습니다. 이렇게 하면 파일에 있는 이벤트로 이동하여 해당 시점의 응용 프로그램에 대한 특정 정보를 볼 수 있습니다.  
  
 다음 소스의 IntelliTrace 데이터를 저장할 수 있습니다.  
  
-   Visual Studio 2017 Enterprise, Visual Studio 2015 Enterprise 또는 Visual Studio ultimate 이전 버전의 IntelliTrace 세션입니다.  
  
-   Microsoft Test Manager의 테스트 세션  
  
-   Microsoft Monitoring Agent 단독으로 또는 System Center 2012와 함께 사용할 때 IIS에서 호스팅된 ASP.NET 웹 앱 또는 배포에서 실행 중인 SharePoint 2010 및 SharePoint 2013 응용 프로그램. 참조 [IntelliTrace 독립 실행형 수집기를 사용 하 여](../debugger/using-the-intellitrace-stand-alone-collector.md) 및 [Microsoft Monitoring Agent로 모니터링](http://technet.microsoft.com/library/dn465153.aspx)합니다.  
  
 다음은 IntelliTrace를 이용하여 디버깅하는 몇 가지 예입니다.  
  
-   응용 프로그램의 데이터 파일이 손상되었지만 이 이벤트가 어디에서 발생했는지 모릅니다.  
  
     이 경우 IntelliTrace를 사용하지 않는다면 코드 전체를 검사하여 가능한 모든 파일 액세스를 찾고, 해당 액세스 지점에 중단점을 설정한 다음, 응용 프로그램을 다시 실행하여 문제가 발생하는 지점을 찾아야 합니다. IntelliTrace를 사용하면 수집된 모든 파일 액세스 이벤트와 각 이벤트가 발생했을 때 응용 프로그램에 대한 특정 세부 사항을 볼 수 있습니다.  
  
-   예외가 발생합니다.  
  
     IntelliTrace가 없으면 예외에 대 한 메시지를 얻게 되지만 예외를 발생 시킨 이벤트에 대 한 많은 정보를 필요가 없습니다. 예외를 초래한 호출 체인을 확인할 호출 스택을 검사할 수 있지만 이러한 호출 중 발생 하는 이벤트의 순서를 확인할 수 없습니다. IntelliTrace를 사용하면 예외가 발생하기 전에 발생한 이벤트를 검사할 수 있습니다.  
  
-   응용 프로그램이 테스트 컴퓨터에서 충돌하더라도 개발 컴퓨터에서는 성공적으로 실행됩니다.  
  
     Microsoft Test Manager에서 IntelliTrace 데이터를 수집하고 데이터를 .iTrace 파일에 저장하며 이 파일을 향후 조사를 위해 Team Foundation Server 작업 항목에 첨부할 수 있습니다. 참조 [수동 테스트에서 추가 진단 데이터 수집](/devops-test-docs/test/collect-more-diagnostic-data-in-manual-tests) 및 [저장 된 IntelliTrace 데이터 사용](../debugger/using-saved-intellitrace-data.md)합니다.  
  
-   배포된 응용 프로그램에서 버그 또는 충돌이 발생합니다.  
  
     Microsoft Azure 기반 응용 프로그램의 경우 응용 프로그램을 게시하기 전에 IntelliTrace 데이터 수집을 구성할 수 있습니다. 응용 프로그램을 실행하는 동안 IntelliTrace는 데이터를 .iTrace 파일에 저장합니다. 참조 [IntelliTrace 및 Visual Studio 게시 된 클라우드 서비스 디버깅](http://go.microsoft.com/fwlink/?LinkID=262248)합니다.  
  
     IIS 7.0, 7.5 및 8.0에서 호스팅된 ASP.NET 웹 앱과 SharePoint 2010 또는 SharePoint 2013 응용 프로그램에 대해 Microsoft Monitoring Agent 단독으로 또는 System Center 2012와 함께 사용하여 IntelliTrace 데이터를 .iTrace 파일에 저장합니다.  
  
     배포에서 응용 프로그램의 문제를 진단할 때 유용합니다. 참조 [IntelliTrace 독립 실행형 수집기를 사용 하 여](../debugger/using-the-intellitrace-stand-alone-collector.md)합니다.  
  
##  <a name="WhatData"></a>IntelliTrace는 데이터를 수집 합니까?  
 **이벤트 정보를 수집 합니다.**  
  
 기본적으로 IntelliTrace는 디버거 이벤트, 예외, .NET Framework 이벤트와 같은 IntelliTrace 이벤트와 디버깅에 유용한 기타 시스템 이벤트만 기록합니다. 항상 수집되는 디버거 이벤트와 예외를 제외하고 수집하려는 IntelliTrace 이벤트 종류를 선택할 수 있습니다. 참조 [IntelliTrace 기능](../debugger/intellitrace-features.md)합니다.  
  
-   **디버거 이벤트**  
  
     IntelliTrace는 Visual Studio 디버거에서 발생하는 이벤트는 항상 기록합니다. 예를 들어, 응용 프로그램 시작은 디버거 이벤트입니다. 다른 디버거 이벤트로는 응용 프로그램의 실행을 중단시키는 중지 이벤트가 있습니다. 프로그램이 중단점이는 추적점에 도달 하거나 실행 예를 들어 한 **단계** 명령입니다.  

     기본적으로 성능에 도움이 되도록 IntelliTrace 기록 하지 않습니다는 디버거 이벤트에 대 한 가능한 모든 값입니다. 대신, 다음 값을 기록합니다.  
  
    -   값에 **지역** 창. 유지 된 **지역** 창을 열어 이러한 값을 표시 합니다.  
  
    -   값에 **자동** 경우에만 창은 **자동** 창이  
  
    -   해당 값을 보기 위해 소스 창에 있는 변수 위로 마우스 포인터를 이동하면 나타나는 DataTips의 값입니다. IntelliTrace는 고정된 DataTips에서는 값을 수집하지 않습니다.  

    IntelliTrace 이벤트 및 스냅숏 모드를 설정 하는 경우 IntelliTrace는의 스냅숏을 응용 프로그램의 프로세스에서 각 디버거 **중단점** 및 **단계** 이벤트입니다. 이 값에는 기록의 **지역**, **자동**, 및 **조사식** 는 창이 열려 있는 여부에 관계 없이 windows 합니다. 모든 고정된 데이터 팁에서 값 수집도 됩니다. 
  
-   **예외**  
  
     IntelliTrace에서는 이러한 종류의 예외에 대한 예외 형식과 메시지를 기록합니다.  
  
    -   예외가 throw되고 catch된 경우의 처리된 예외  
  
    -   처리되지 않은 예외  
  
-   **.NET framework 이벤트**  
  
     기본적으로 IntelliTrace는 가장 일반적인 .NET Framework 이벤트를 기록합니다. 예:  
  
    -   확인란 확인 이벤트의 경우 IntelliTrace는 확인란 상태와 텍스트를 수집합니다.  
  
-   **SharePoint 2010 및 SharePoint 2013 응용 프로그램 이벤트**  
  
     Visual Studio 외부에서 실행되는 SharePoint 2010 및 2013 응용 프로그램에 대해 사용자 프로필 이벤트 및 ULS(Unified Logging System) 이벤트의 하위 집합을 기록할 수 있습니다. 이러한 이벤트를 .iTrace 파일에 저장할 수 있습니다. Visual Studio Enterprise 2017, Visual Studio Enterprise 2015, Visual Studio ultimate 이전 버전 필요 또는 [Microsoft Monitoring Agent](http://go.microsoft.com/fwlink/?LinkId=320384) 에서 실행 중인 **추적** 모드입니다.  
  
     .iTrace 파일을 열면 SharePoint 상관 관계 ID를 입력하여 일치하는 웹 요청을 찾고 기록된 이벤트를 보고 특정 이벤트에서 디버깅을 시작합니다. 파일에 처리되지 않은 예외가 있는 경우 상관 관계 ID를 선택하여 예외 디버깅을 시작할 수 있습니다.  
  
     참조  
  
    -   [IntelliTrace 독립 실행형 수집기 사용](../debugger/using-the-intellitrace-stand-alone-collector.md)  
  
    -   [사용 하 여 IntelliTrace 데이터를 저장 합니다.](../debugger/using-saved-intellitrace-data.md)  
  
    -   [연습: IntelliTrace를 사용하여 SharePoint 응용 프로그램 디버깅](../sharepoint/walkthrough-debugging-a-sharepoint-application-by-using-intellitrace.md)  
 
 **스냅숏 캡처**
 
 모든 중단점에서 스냅숏을 캡처하고 디버거 단계 이벤트를 IntelliTrace를 구성할 수 있습니다. IntelliTrace는이 통해 복잡 한 변수를 표시 하 고 식을 평가 하는 각 스냅숏에서 전체 응용 프로그램 상태를 기록 합니다.

 참조 [IntelliTrace 단계 백을 사용 하 여 스냅숏 보기](../debugger/how-to-use-intellitrace-step-back.md)합니다.

 **함수 호출 정보 수집**  
  
 함수의 호출 정보를 수집하도록 IntelliTrace를 구성할 수 있습니다. 이 정보를 사용하면 호출 스택의 내역을 확인하고 코드에 있는 호출을 통해 뒤로/앞으로 이동할 수 있습니다. 각 함수 호출에 대해 IntelliTrace는 이 데이터를 기록합니다.  
  
-   함수 이름  
  
-   함수 시작 지점에서 매개 변수로 전달하고 함수 종료 지점에서 반환되는 기본 데이터 형식의 값  
  
-   읽히거나 변경될 때의 자동 속성 값  
  
-   첫 번째 수준 자식 개체에 대한 포인터, null인지 여부만을 나타내며 해당 값에 대한 포인터는 아님  
  
> [!NOTE]
>  IntelliTrace는 배열에서 처음 256 개체와 문자열의 경우 처음 256자만 수집합니다.  
  
 참조 [기록 디버깅을 사용 하 여 앱 검사](../debugger/historical-debugging-inspect-app.md)합니다.
  
 **모듈 정보 수집**  
  
 IntelliTrace가 호출 정보를 어느 정도 수집할지 제어하려면 관심 있는 모듈만 지정합니다. 이와 같이 하면 컬렉션하는 동안 응용 프로그램 성능을 향상시킬 수 있습니다. 섹션을 참조 [IntelliTrace가 수집 하는 정보의 양을 제어할](../debugger/intellitrace-features.md#ControlCallData) IntelliTrace 기능에 있습니다.  
  
##  <a name="AffectPerformance"></a>내 응용 프로그램 속도 저하 IntelliTrace가?  
 기본적으로 IntelliTrace에서는 선택한 IntelliTrace 이벤트에 대해서만 데이터를 수집합니다. 코드의 구조와 구성에 따라 응용 프로그램이 느려지거나 느려지지 않을 수 있습니다. 예를 들어 IntelliTrace가 자주 이벤트를 기록한다면 이로 인해 응용 프로그램 속도가 느려질 수 있습니다. 또한 이에 따라 응용 프로그램 리팩터링을 고려해 볼 수도 있습니다.  
  
 호출 정보를 수집하면 응용 프로그램 성능이 크게 느려질 수 있습니다. 또한 IntelliTrace 로그 파일(.iTrace 파일)을 디스크에 저장하는 경우 로그 파일의 크기도 커질 수 있습니다. 이러한 효과를 최소화하려면 관심 있는 모듈에 대한 호출 정보만 수집합니다.  .ITrace 파일의 최대 크기를 변경 하려면로 이동 **도구**, **옵션**, **IntelliTrace**, **고급**합니다. 
  
## <a name="in-this-section"></a>단원 내용  
 [IntelliTrace 기능](../debugger/intellitrace-features.md)  
  
 [재현 하기 어려운 버그에 진단 추적 데이터를 포함 합니다.](/devops-test-docs/test_notintoc/including-diagnostic-trace-data-with-bugs-that-are-difficult-to-reproduce)  
  
 [배포 후 문제 진단](../debugger/diagnose-problems-after-deployment.md)  
  
 [사용 하 여 IntelliTrace 데이터를 저장 합니다.](../debugger/using-saved-intellitrace-data.md)  
  
### <a name="blogs"></a>블로그  
 [Visual Studio ALM + Team Foundation Server](http://go.microsoft.com/fwlink/?LinkID=201340)  
  
### <a name="forums"></a>포럼  
 [Visual Studio 진단](http://go.microsoft.com/fwlink/?LinkId=262263)