---
title: "IntelliTrace 기능 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliTrace, debugging with events
- IntelliTrace, recording execution history
- debugging [Visual Studio ALM], recording execution history
- IntelliTrace, turn off
- IntelliTrace, navigating event and call history
- IntelliTrace, saving your session
- IntelliTrace, enabling
- IntelliTrace, start debugging
- IntelliTrace, debugging with events and call information
- IntelliTrace, disabling
- IntelliTrace, turn on
- debugging [Visual Studio ALM], IntelliTrace
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 273f7f94127929a3939d21414bd8da5c12abc83e
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2018
---
# <a name="intellitrace-features"></a>IntelliTrace 기능

IntelliTrace를 사용하여 응용 프로그램의 이벤트 및 메서드 호출을 기록하고 실행 중 다양한 지점에서 상태(호출 스택 및 지역 변수 값)를 검사할 수 있습니다. -평소와 같이 디버깅을 시작 하 고, 기본적으로 IntelliTrace가 켜져 하 고, 새에서 IntelliTrace가 기록 정보를 볼 수 **진단 도구** 창의 **이벤트** 탭 합니다. 이벤트를 선택 하 고 클릭 **기록 디버깅 활성화** 호출 스택 및이 이벤트에 대해 기록 된 지역 변수를 볼 수 있습니다.

참조에 대 한 단계별 설명은 [연습: IntelliTrace를 사용 하 여](../debugger/walkthrough-using-intellitrace.md)합니다.

IntelliTrace는 Visual Studio Enterprise Edition에서 사용할 수 있으며 Visual Studio Professional 또는 Community Edition에서는 사용할 수 없습니다.

IntelliTrace가 켜져 있는지를 확인 하려면 열에서 **도구 > 옵션 > IntelliTrace** 옵션 페이지입니다. **IntelliTrace를 활성화** 기본적으로 선택 해야 합니다.

> [!NOTE]
> 모든 설정의 범위는 **IntelliTrace** 옵션 페이지 사용 하는 Visual Studio 전체, 개별이 아닌 프로젝트 또는 솔루션입니다. 이 설정에서 변경된 내용은 Visual Studio의 모든 인스턴스, 모든 디버깅 세션 및 모든 프로젝트나 솔루션에 적용됩니다.

## <a name="ChooseEvents"></a> IntelliTrace에서 기록 하는 이벤트를 선택 합니다.

특정 IntelliTrace 이벤트에 대한 기록을 설정하거나 해제할 수 있습니다.

디버그 중이면 디버깅을 중지합니다. 로 이동 **도구 > 옵션 > IntelliTrace > IntelliTrace 이벤트**합니다. IntelliTrace에서 기록하도록 지정할 이벤트를 선택합니다.

## <a name="Snapshots"></a> 이벤트 및 스냅숏 수집

기본적으로 사용 되지 않으며이 있지만 IntelliTrace 수 모든 중단점 및 디버거 단계 이벤트에서 응용 프로그램의 스냅숏을 캡처하고 기록 디버깅 세션에서 이러한 스냅숏을 볼 수 있습니다. 스냅숏 전체 응용 프로그램 상태 보기를 제공 합니다. 스냅숏의 캡처를 사용 하도록 설정 하려면로 이동 **도구 > 옵션 > IntelliTrace > 일반**를 선택 하 고 **IntelliTrace 이벤트 및 스냅숏**합니다. 자세한 내용은 참조 [IntelliTrace 단계 백을 사용 하 여 스냅숏 보기](../debugger/how-to-use-intellitrace-step-back.md)

Visual Studio Enterprise 2017 15.5 이상 버전에서에서 사용할 수 있는 스냅숏이 및 Windows 10 Anniversary 업데이트 필요 이상.  스냅숏은.NET Core 및 ASP.NET Core 응용 프로그램의 현재 사용할 수 없습니다.

## <a name="GoingFurther"></a> IntelliTrace 이벤트 및 호출 정보 수집

기본적으로 사용 되지 않으며이 있지만 IntelliTrace 이벤트와 함께 메서드 호출을 기록할 수 있습니다. 호출으로 이동 하는 메서드의 컬렉션을 사용 하도록 설정 하려면 **도구 > 옵션 > IntelliTrace > 일반**를 선택 하 고 **IntelliTrace 이벤트 및 호출 정보**합니다.

호출 정보를.NET Core 및 ASP.NET Core 응용 프로그램의 현재 사용할 수 없는 경우 

이렇게 하면 호출 스택 이력을 참조하고 코드에서 호출을 통해 앞뒤로 이동할 수 있습니다. IntelliTrace는 메서드 이름, 메서드 시작/종료 지점, 특정 매개 변수 값, 반환 값 등의 데이터를 기록합니다.

> [!TIP]
> 이 옵션은 상당한 오버헤드를 추가하기 때문에 기본적으로 사용하도록 설정되어 있지 않습니다. IntelliTrace는 응용 프로그램에서 발생하는 모든 메서드 호출을 가로채야 할 뿐만 아니라 이를 화면에 표시하거나 디스크에 보관하기 위해서는 훨씬 더 큰 데이터 집합을 처리해야 합니다.
>
> IntelliTrace가 기록하는 이벤트의 목록을 제한하고 수집하는 모듈 수를 최소한으로 유지하면 성능 오버헤드를 줄일 수 있습니다. 자세한 내용은 참조 [제어는 호출 정보의 양 IntelliTrace에서 기록](../debugger/intellitrace-features.md#ControlCallData)합니다.

### <a name="use-the-navigation-gutter"></a>탐색 여백 사용

코드 창의 왼쪽에 표시되는 탐색 여백을 사용할 수 있습니다. 로 이동 하는 탐색 여백 보이지 않으면 **도구 > 옵션 > IntelliTrace > 고급**를 선택 하 고 **디버그 모드에서 탐색 여백 표시**합니다.

탐색 여백을 사용하면 기록 디버깅 모드에서 앞이나 뒤로 이동하며 메서드 호출 및 이벤트를 탐색할 수 있습니다. 기록 디버깅에 대 한 자세한 내용은 참조 [기록 디버깅](../debugger/historical-debugging.md)합니다. 다음과 같은 명령이 있습니다.

|||
|-|-|
|**여기에 디버거 컨텍스트 설정**|디버깅 컨텍스트를 표시되는 호출 기간으로 설정합니다.<br /><br /> 이 아이콘은 현재 호출 스택에만 나타납니다.|
|**호출 사이트로 돌아가기**|포인터와 디버깅 컨텍스트를 현재 함수가 호출된 지점으로 다시 이동합니다.<br /><br /> 라이브 디버깅 모드에 있는 경우 이 명령은 기록 디버깅을 설정합니다. 원래 실행이 중단되었던 지점으로 다시 이동하면 기록 디버깅이 해제되고 라이브 디버깅이 설정됩니다.|
|**이전 호출 또는 IntelliTrace 이벤트로 이동**|포인터와 디버깅 컨텍스트를 이전 호출 또는 이벤트 지점으로 다시 이동합니다.<br /><br /> 라이브 디버깅 모드에 있는 경우 이 명령은 기록 디버깅을 설정합니다.|
|**단계**|현재 선택한 함수를 한 단계씩 실행합니다.<br /><br /> 이 명령은 기록 디버깅 모드에 있는 경우에만 사용할 수 있습니다.|
|**다음 호출 또는 IntelliTrace 이벤트로 이동**|포인터와 디버깅 컨텍스트를 IntelliTrace 데이터가 있는 다음 호출 또는 이벤트로 이동합니다.<br /><br /> 이 명령은 기록 디버깅 모드에 있는 경우에만 사용할 수 있습니다.|
|**라이브 모드로 이동**|라이브 디버깅 모드로 돌아갑니다.|

### <a name="search-for-a-line-or-method-in-intellitrace"></a>IntelliTrace에서 줄 또는 메서드 검색

메서드 호출 정보가 사용하도록 설정된 경우에만 메서드를 검색할 수 있습니다. 특정 줄 또는 메서드에 대해 IntelliTrace 기록을 검색할 수 있습니다. 상황에 맞는 메뉴를 표시 하는 함수 본문 내부를 마우스 오른쪽 단추로 클릭 하 고 클릭 디버거 실행이 중단 하는 동안 **IntelliTrace에서이 줄 검색** 또는 **IntelliTrace에서이 메서드 검색**합니다.

### <a name="ControlCallData"></a> 제어는 호출 정보의 양 IntelliTrace에서 기록

기본적으로 IntelliTrace는 솔루션에 사용되는 모든 모듈에 대한 정보를 기록합니다. IntelliTrace에서 관심 있는 모듈에 대한 호출 정보만 기록하게 설정할 수 있습니다. **도구 > 옵션 > IntelliTrace > 모듈**를 포함 하도록 모듈이 나 IntelliTrace에서 제외할 모듈을 지정할 수 있습니다. IntelliTrace는 지정한 모듈에서 발생하는 이벤트만 수집하며 관심 있는 모듈 내에서 발생한 메서드 호출만 수집합니다.

여러 모듈을 추가하려면 문자열의 시작이나 끝 부분에 와일드카드 문자 *를 사용합니다. 모듈 이름에는 어셈블리 이름이 아닌 파일 이름을 사용합니다. 파일 경로는 사용할 수 없습니다.

모듈의 수를 최소로 유지합니다. 그러면 수집할 데이터의 양이 적기 때문에 성능이 높아집니다. 또한 검토할 데이터가 적기 때문에 UI의 노이즈가 줄어듭니다.

## <a name="SaveSession"></a> IntelliTrace 데이터를 파일 저장

IntelliTrace에서 수집 된 데이터를 저장할 수 있습니다를 **디버그 > IntelliTrace > IntelliTrace 세션 저장** 디버깅 하는 동안 응용 프로그램은 중단 상태에 있습니다. 응용 프로그램이 계속 실행 중이거나 디버깅을 중지한 경우에는 해당 메뉴 항목이 비활성화되어 IntelliTrace에서 수집된 데이터를 저장할 수 없게 됩니다.

자동으로 이동 하 여 파일에 저장 하도록 IntelliTrace를 구성할 수 있습니다 **도구 > 옵션 > IntelliTrace > 고급** 선택 하 고 **이 디렉터리에 IntelliTrace 기록 저장**합니다. 생성된 파일에 대해 집합 크기를 구성할 수도 있습니다. 그러면 공간이 부족할 때 IntelliTrace가 오래된 데이터를 덮어씁니다. Visual Studio는 자동으로 저장되고 Visual Studio 호스팅 프로세스(vshost.exe)가 켜져 있는 경우 각 IntelliTrace 세션에 대해 두 개의 파일을 만듭니다.

> [!TIP]
> 디스크 공간을 절약 하려면 더 이상 필요 없는 경우에 파일을 자동으로 저장 해제 합니다. 기존 파일은 삭제되지 않습니다. 필요에 따라 언제든지 상황에 맞는 메뉴를 사용하여 파일에 저장할 수 있습니다.

IntelliTrace 데이터를 파일에 저장하면 IntelliTrace가 수집한 프로세스별로 .itrace 파일이 하나씩 생깁니다. 로 이동 하 여 Visual Studio에서.itrace 파일을 열고 다음 **파일 > 열기 > 파일** 파일 열기 대화 상자에서.itrace 파일을 선택 하 고 있습니다. 자세한 내용은 참조 [저장 된 IntelliTrace 데이터를 사용 하 여](../debugger/using-saved-intellitrace-data.md)합니다.

## <a name="blogs"></a>블로그

[Visual Studio Enterprise 2015의 IntelliTrace](http://blogs.msdn.com/b/visualstudioalm/archive/2015/01/16/intellitrace-in-visual-studio-ultimate-2015.aspx)

[라이브 디버깅 연습 (텍스트 편집기) Visual Studio 2015의 IntelliTrace를 사용 하 여](http://blogs.msdn.com/b/visualstudioalm/archive/2015/01/16/walkthrough-of-live-debugging-using-intellitrace-in-visual-studio-2015-text-editor.aspx)

[라이브 디버깅 연습 (소셜 클럽) Visual Studio 2015의 IntelliTrace를 사용 하 여](http://blogs.msdn.com/b/visualstudioalm/archive/2000/1/1/walkthrough-of-live-debugging-using-intellitrace-in-visual-studio-2015-social-club.aspx)

[연결 지원 Visual Studio Enterprise 2015의 IntelliTrace!](http://blogs.msdn.com/b/visualstudioalm/archive/2015/05/14/intellitrace-in-visual-studio-enterprise-2015-now-supports-attach.aspx)

[IntelliTrace 독립 실행형 수집기를 사용 하 여 windows 서비스에서 데이터를 수집 합니다.](http://blogs.msdn.com/b/visualstudioalm/archive/2015/05/14/collect-data-from-a-windows-service-using-the-intellitrace-standalone-collector.aspx)

[IntelliTrace 컬렉션 계획 편집](http://blogs.msdn.com/b/visualstudioalm/archive/2015/03/09/editing-the-intellitrace-collection-plan.aspx)

[사용자 지정 TraceSource 및 IntelliTrace를 사용 하 여 디버깅](http://blogs.msdn.com/b/visualstudioalm/archive/2014/12/17/custom-tracesource-and-debugging-using-intellitrace.aspx)

[Active Directory 계정으로 IntelliTrace 독립 실행형 수집기 및 응용 프로그램 풀이 실행](http://blogs.msdn.com/b/visualstudioalm/archive/2014/12/22/intellitrace-standalone-collector-and-application-pools-running-under-active-directory-accounts.aspx)

## <a name="forums"></a>포럼

[Visual Studio 디버거](http://go.microsoft.com/fwlink/?LinkId=262263)

## <a name="videos"></a>비디오

[IntelliTrace 경험](https://channel9.msdn.com/Series/Visual-Studio-2015-Enterprise-Videos/IntelliTrace-Experience)

[Microsoft Visual Studio에서 intellitrace 기록 디버깅 Ultimate 2015](https://channel9.msdn.com/events/Ignite/2015/BRK3716)
