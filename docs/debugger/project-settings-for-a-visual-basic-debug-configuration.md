---
title: "프로젝트는 Visual Basic 디버그 구성에 대 한 설정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vbProjectPropertiesDebug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- debugging [Visual Basic], debugger settings
- projects [Visual Studio], debug configurations
- project configurations, debug
- debug configurations, Visual Basic
ms.assetid: 72a8483a-af0b-4403-8b0d-ee9ad71ee435
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 47047758d237bb652d5b8e447f8fc7b6e608148e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="project-settings-for-a-visual-basic-debug-configuration"></a>Project Settings for a Visual Basic Debug Configuration
에 대 한 프로젝트 설정을 변경할 수 있습니다는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 디버그 구성에는 **속성 페이지** 창에 설명 된 대로 [디버그 및 릴리스 구성](../debugger/how-to-set-debug-and-release-configurations.md)합니다. 다음 표에에서 디버거 관련 설정을 확인할 수 있는 위치는 **속성 페이지** 창.  
  
> [!WARNING]
>  이 항목은 UWP 앱에 적용되지 않습니다. 참조 [(VB, C#, c + + 및 XAML) 디버그 세션 시작](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)  
  
### <a name="debug-tab"></a>디버그 탭  
  
|설정|설명|  
|-------------|-----------------|  
|**구성**|응용 프로그램의 컴파일 모드를 설정합니다. 중에서 선택 **활성 (Debug)**, **디버그**, **릴리스**, **모든 구성**합니다.|  
|**시작 작업**|이 컨트롤 그룹은 디버그 메뉴에서 시작을 선택할 때 수행되는 작업을 지정합니다.<br /><br /> -   **시작 프로젝트** 기본값을 디버깅 하는 것에 대 한 시작 프로젝트를 실행 합니다. 자세한 내용은 참조 [NIB 방법: 시작 프로젝트 설정](http://msdn.microsoft.com/en-us/31465836-0911-48db-a5d9-e456b635e970)합니다.<br />-   **시작 외부 프로그램** 시작 되지 않은 프로그램에 연결 하 여 수의 일부로 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트. 자세한 내용은 참조 [실행 중인 프로세스에 연결할](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)합니다.<br />-   **URL로 브라우저 시작** 웹 응용 프로그램을 디버깅할 수 있도록 합니다.|  
|**명령줄 인수**|디버깅할 프로그램에 대한 명령줄 인수를 지정합니다. 명령 이름은 시작 외부 프로그램에 지정된 프로그램 이름입니다. 시작 작업이 시작 URL로 설정되면 명령줄 인수가 무시됩니다.|  
|**작업 디렉터리**|디버깅 중인 프로그램의 작업 디렉터리를 지정합니다. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서는 응용 프로그램이 시작된 디렉터리가 작업 디렉터리입니다. 기본 작업 디렉터리에는 \bin\Debug 또는 \bin\Release 현재 구성에 따라입니다.|  
|**원격 컴퓨터 사용**|이 확인란을 선택하면 원격 디버깅이 활성화됩니다. 텍스트 상자에 디버깅을 위해 응용 프로그램을 실행할 원격를 컴퓨터의 이름을 입력할 수 있습니다 또는 [Msvsmon 서버 이름](../debugger/remote-debugging.md)합니다. 원격 컴퓨터에 있는 EXE의 위치는 빌드 탭에 있는 출력 경로 속성으로 지정됩니다. 이 위치는 원격 컴퓨터의 공유할 수 있는 디렉터리여야 합니다.|  
|**비관리 코드 디버깅**|관리되는 응용 프로그램에서의 비관리 네이티브 Win32 코드에 대한 호출을 디버깅할 수 있습니다. 이 옵션을 설정하는 것은 [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] 프로젝트에서 디버거 형식을 혼합으로 선택한 것과 같습니다.|  
|**SQL Server 디버깅**|SQL Server 데이터베이스 개체를 디버깅할 수 있습니다.|  
  
### <a name="compile-tab-press-advanced-compile-options-button"></a>컴파일 탭: 고급 컴파일 옵션 단추 클릭  
  
|설정|설명|  
|-------------|-----------------|  
|**최적화 사용**|이 옵션은 선택하지 말아야 합니다. 최적화를 사용하면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 표시되는 소스 코드와 실제로 실행되는 코드가 달라지므로 코드의 디버깅이 어려워집니다. 코드를 최적화하면 내 코드만 옵션을 적용하여 디버깅할 때 기본적으로 기호가 로드되지 않습니다.|  
|**디버그 정보 생성**|/debug 컴파일러 옵션에 해당하는 이 설정은 디버그 버전과 릴리스 버전에 모두 기본적으로 설정되어 있으며 빌드 시 디버그 정보를 생성합니다. 디버거에서는 이 정보를 사용하여 디버깅할 때 편리한 서식으로 변수 이름과 기타 정보를 표시합니다. 이 정보를 사용하지 않고 프로그램을 컴파일하면 디버거의 기능이 제한됩니다. 자세한 내용은 참조 [/debug](/dotnet/visual-basic/reference/command-line-compiler/debug)합니다.|  
|**DEBUG 상수 정의**|이 기호를 사용 하면 출력 함수를 조건에 따라는 [Debug 클래스](/dotnet/api/system.diagnostics.debug)합니다. 이 기호를 정의 하면 Debug 클래스 메서드의 결과가 출력을는 [출력 창](../ide/reference/output-window.md)합니다. 이 기호를 정의하지 않으면 Debug 클래스 메서드가 컴파일되지 않으므로 결과가 생성되지 않습니다. 이 기호는 디버그 버전에 정의되고 릴리스 버전에는 정의되지 않습니다. 릴리스 버전에 이 기호를 정의하면 불필요한 코드가 생성되어 프로그램 속도가 느려집니다.|  
|**TRACE 상수 정의**|이 기호를 사용 하면 출력 함수를 조건에 따라는 [Trace 클래스](/dotnet/api/system.diagnostics.trace.aspx)합니다. 이 기호를 정의 하면 Trace 클래스 메서드의 결과가 [출력 창](../ide/reference/output-window.md)합니다. 이 기호를 정의하지 않으면 Trace 클래스 메서드가 컴파일되지 않으므로 추적 결과가 생성되지 않습니다. 이 기호는 디버그 버전과 릴리스 버전에 모두 기본적으로 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [디버거 설정 및 준비](../debugger/debugger-settings-and-preparation.md)