---
title: "트리거하는 방법 일시 중단, 다시 시작 및 백그라운드 이벤트를 UWP 앱을 디버깅 하는 동안 | Microsoft Docs"
ms.custom: 
ms.date: 01/16/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.background_task_activate_failure
dev_langs:
- CSharp
- VB
- FSharp
- C++
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 036362ec392e6deba9bed1ef185c602d508d4da4
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-trigger-suspend-resume-and-background-events-while-debugging-uwp-apps-in-visual-studio"></a>트리거하는 방법 일시 중단, 다시 시작 및 백그라운드 이벤트를 Visual Studio에서 UWP 앱을 디버깅 하는 동안
디버깅하고 있지 않을 때는 Windows PLM( **프로세스 수명 관리** )에서 응용 프로그램의 실행 상태(장치 상태 및 사용자 작업에 응답하여 응용 프로그램 시작, 일시 중단, 다시 시작 및 종료)를 제어합니다. 디버깅하는 중에는 Windows가 이러한 활성화 이벤트를 사용하지 않도록 설정합니다. 이 항목에서는 디버거에서 이러한 이벤트를 발생시키는 방법에 대해 설명합니다.  
  
 이 항목에서는 **백그라운드 작업**을 디버깅하는 방법에 대해서도 설명합니다. 백그라운드 작업을 사용하면 응용 프로그램을 실행하고 있지 않은 경우에도 백그라운드 프로세스에서 특정 작업을 수행할 수 있습니다. 디버거를 사용하여 응용 프로그램을 디버그 모드에 둔 다음 UI를 시작하지 않고 백그라운드 작업을 시작하고 디버깅할 수 있습니다.  
  
 프로세스 수명 관리 및 백그라운드 작업에 대 한 자세한 내용은 참조 [시작, 재개 및 멀티태스킹을](/windows/uwp/launch-resume/index)합니다.  
  
##  <a name="BKMK_Trigger_Process_Lifecycle_Management_events"></a> 프로세스 수명 관리 이벤트 트리거  
 사용자가 응용 프로그램에서 벗어나거나 Windows가 절전 상태로 들어갈 때 응용 프로그램이 일시 중단될 수 있습니다. `Suspending` 이벤트에 응답하여 관련 응용 프로그램 및 사용자 데이터를 영구 저장소에 저장하고 리소스를 해제할 수 있습니다. 응용 프로그램은 **일시 중단됨** 상태에서 다시 시작되는 경우 **실행 중** 상태가 되고 일시 중단되었을 때의 위치에서 계속됩니다. `Resuming` 이벤트에 응답하여 응용 프로그램 상태를 복원하거나 새로 고치고 리소스를 회수할 수 있습니다.  
  
 Windows에서 일시 중단된 응용 프로그램을 최대한 많이 메모리에 유지하려고 해도 이를 위한 충분한 리소스가 없으면 응용 프로그램이 종료될 수 있습니다. 사용자가 응용 프로그램을 명시적으로 닫을 수도 있습니다. 사용자가 응용 프로그램을 닫았음을 나타내는 특수 이벤트는 없습니다.  
  
 Visual Studio 디버거에서 수동으로 응용 프로그램을 일시 중단, 다시 시작 및 종료하여 프로세스 수명 이벤트를 디버깅할 수 있습니다. 프로세스 수명 이벤트를 디버깅하려면 다음을 수행합니다.  
  
1.  디버깅할 이벤트의 처리기에 중단점을 설정합니다.  
  
2.  **F5** 키를 눌러 디버깅을 시작합니다.  
  
3.  **디버그 위치** 도구 모음에서 발생시킬 이벤트를 선택합니다.  
  
     ![일시 중단, 다시 시작, 종료 및 백그라운드 작업](../debugger/media/dbg_suspendresumebackground.png "DBG_SuspendResumeBackground")  
  
     **일시 중단 후 종료** 을 사용하면 응용 프로그램이 닫히고 디버깅 세션이 끝납니다.  
  
##  <a name="BKMK_Trigger_background_tasks"></a> 백그라운드 작업 트리거  
 모든 응용 프로그램은 응용 프로그램이 실행되고 있지 않은 경우에도 특정 시스템 이벤트에 응답하도록 백그라운드 작업을 등록할 수 있습니다. 백그라운드 작업은 UI를 직접 업데이트하는 코드는 실행할 수 없습니다. 대신 타일 업데이트, 배지 업데이트 및 알림을 통해 사용자에게 정보를 보여 줍니다. 자세한 내용은 [Supporting your app with background tasks](http://msdn.microsoft.com/en-us/4c7bb148-eb1f-4640-865e-41f627a46e8e)을 참조하세요.  
  
 디버거에서 응용 프로그램의 백그라운드 작업을 시작하는 이벤트를 트리거할 수 있습니다.  
  
> [!NOTE]
>  디버거는 장치 상태의 변경을 나타내는 이벤트처럼 데이터를 포함하지 않는 이벤트만 트리거할 수 있습니다. 사용자 입력 또는 다른 데이터가 필요한 백그라운드 작업은 수동으로 트리거해야 합니다.  
  
 가장 실질적으로 백그라운드 작업 이벤트를 트리거하는 방법은 응용 프로그램이 실행되고 있지 않는 경우입니다. 그러나 표준 디버깅 세션의 이벤트 트리거도 지원됩니다.  
  
###  <a name="BKMK_Trigger_a_background_task_event_from_a_standard_debug_session"></a> 표준 디버그 세션에서 백그라운드 작업 이벤트 트리거  
  
1.  디버깅할 백그라운드 작업 코드에 중단점을 설정합니다.  
  
2.  **F5** 키를 눌러 디버깅을 시작합니다.  
  
3.  **디버그 위치** 도구 모음의 이벤트 목록에서 시작할 백그라운드 작업을 선택합니다.  
  
     ![일시 중단, 다시 시작, 종료 및 백그라운드 작업](../debugger/media/dbg_suspendresumebackground.png "DBG_SuspendResumeBackground")  
  
###  <a name="BKMK_Trigger_a_background_task_when_the_app_is_not_running"></a> 응용 프로그램이 실행 중이지 않을 때 백그라운드 작업 트리거  
  
1.  디버깅할 백그라운드 작업 코드에 중단점을 설정합니다.  
  
2.  시작 프로젝트에 대한 디버그 속성 페이지를 엽니다. 솔루션 탐색기에서 프로젝트를 선택합니다. **디버그** 메뉴에서 **속성**을 선택합니다.  
  
     C + + 및 JavaScript 프로젝트에 대 한 확장 **구성 속성** 선택한 후 **디버깅**합니다.  
  
3.  다음 작업 중 하나를 수행합니다.  
  
    -   Visual C# 및 Visual Basic 프로젝트의 경우 **시작하지 않음(시작 시 코드 디버그)**을 선택합니다.  
  
         ![C# 35; &#47; VB 디버그 시작 응용 프로그램 속성](../debugger/media/dbg_csvb_dontlaunchapp.png "DBG_CsVb_DontLaunchApp")  
  
    -   JavaScript 및 Visual C++ 프로젝트의 경우 **응용 프로그램 시작** 목록에서 **아니요** 를 선택합니다.  
  
         ![C# 43; &#43; &#47; 응용 프로그램 디버그 속성 VB 시작](../debugger/media/dbg_cppjs_dontlaunchapp.png "DBG_CppJs_DontLaunchApp")  
  
4.  **F5** 키를 눌러 응용 프로그램을 디버그 모드에 둡니다. **디버그 위치** 도구 모음의 **프로세스** 목록에 디버그 모드에 있음을 나타내는 앱 패키지 이름이 표시됩니다.  
  
     ![백그라운드 작업 프로세스 목록](../debugger/media/dbg_backgroundtask_processlist.png "DBG_BackgroundTask_ProcessList")  
  
5.  **디버그 위치** 도구 모음의 이벤트 목록에서 시작할 백그라운드 작업을 선택합니다.  
  
     ![일시 중단, 다시 시작, 종료 및 백그라운드 작업](../debugger/media/dbg_suspendresumebackground.png "DBG_SuspendResumeBackground")  
  
##  <a name="BKMK_Trigger_Process_Lifetime_Management_events_and_background_tasks_from_an_installed_app"></a> 설치된 응용 프로그램에서 프로세스 수명 관리 이벤트 및 백그라운드 작업 트리거  
 사용 하 여는 **설치 된 응용 프로그램 패키지 디버그** 대화 상자는 디버거를 이미 설치 되어 있는 응용 프로그램 로드할 수 있습니다. 예를 들어 Microsoft 스토어에서 설치 된 앱을 디버깅 하거나 응용 프로그램에 대 한 소스 파일이 하지만 응용 프로그램에 대 한 Visual Studio 프로젝트가 아니라 있으면 응용 프로그램을 디버깅 수 있습니다. **설치 된 응용 프로그램 패키지 디버그** 대화 상자를 사용 하면 Visual Studio 컴퓨터에서 또는 원격 장치 또는 앱이 시작 되지 않지만 디버그 모드에서 실행 되도록 설정 하려면 디버그 모드에서 응용 프로그램을 시작 합니다. 자세한 내용은 참조 [설치 된 응용 프로그램 패키지 디버그](../debugger/debug-installed-app-package.md)합니다.
  
 응용 프로그램이 디버거에 로드되면 위에서 설명한 절차를 사용할 수 있습니다.  
  
##  <a name="BKMK_Diagnosing_background_task_activation_errors"></a> 백그라운드 작업 활성화 오류 진단  
 Windows 이벤트 뷰어의 백그라운드 인프라에 대 한 진단 로그는 진단 하 고 백그라운드 작업 오류를 해결 하는 데 사용할 수 있는 자세한 정보를 포함 합니다. 로그를 보려면 다음을 수행합니다.  
  
1.  이벤트 뷰어 응용 프로그램을 엽니다.  
  
2.  **작업** 창에서 **보기** 를 선택하고 **분석 및 디버그 로그 표시** 가 선택되어 있는지 확인합니다.  
  
3.  에 **이벤트 뷰어 (로컬)** 트리 노드를 확장 **Applications and Services Logs** > **Microsoft** > **Windows**   >  **BackgroundTasksInfrastructure**합니다.  
  
4.  **진단** 로그를 선택합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio로 UWP 앱 테스트](../test/testing-store-apps-with-visual-studio.md)   
 [Debug apps in Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)   
 [응용 프로그램 수명 주기](/windows/uwp/launch-resume/app-lifecycle)   
 [시작, 재개 및 멀티태스킹](/windows/uwp/launch-resume/index)