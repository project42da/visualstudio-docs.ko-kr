---
title: "C# 디버그 구성에 대 한 설정을 프로젝트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debug configurations, C#
- debugging [J#], debugger settings
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- projects [Visual Studio], debug configurations
- project configurations, debug
- debugging [C#], debugger settings
- debug configurations, J#
ms.assetid: e30ca810-66e9-4d6e-9cf6-9f285cd0b100
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4310b9e84986ef50f735f0e7ddf6813d9c6fd60d
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2017
---
# <a name="project-settings-for--c-debug-configurations"></a>C# 디버그 구성에 대한 프로젝트 설정
C# 디버그 구성에 대 한 프로젝트 설정을 변경할 수 있습니다는 **속성 페이지** 창에 설명 된 대로 [디버그 및 릴리스 구성](../debugger/how-to-set-debug-and-release-configurations.md)합니다. 다음 표에에서 디버거 관련 설정을 확인할 수 있는 위치는 **속성 페이지** 창.  
  
> [!WARNING]
>  이 항목은 UWP 및 Windows 8.1 앱에 적용 되지 않습니다. 참조 [(VB, C#, c + + 및 XAML) 디버그 세션 시작](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)  
  
##  <a name="BKMK_Debug_tab"></a>디버그 탭  
  
|**설정**|**설명**|  
|-----------------|---------------------|  
|**구성**|응용 프로그램의 컴파일 모드를 설정합니다. 중에서 선택 **활성 (Debug)**, **디버그**, **릴리스**, **모든 구성**합니다.|  
|**시작 작업**|이 컨트롤 그룹은 디버그 메뉴에서 시작을 선택할 때 수행되는 작업을 지정합니다.<br /><br /> -   **시작 프로젝트** 기본값을 디버깅 하는 것에 대 한 시작 프로젝트를 실행 합니다. 자세한 내용은 참조 [시작 프로젝트 선택](http://msdn.microsoft.com/en-us/222e3f32-a6fe-4941-bf37-6b2a921129fd)합니다.<br />-   **시작 외부 프로그램** 시작 되지 않은 프로그램에 연결 하 여 수의 일부로 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트. 자세한 내용은 참조 [실행 중인 프로그램에 연결](http://msdn.microsoft.com/en-us/636d0a52-4bfd-48d2-89ad-d7b9ca4dc4f4)합니다.<br />-   **URL로 브라우저 시작** 웹 응용 프로그램을 디버깅할 수 있도록 합니다.|  
|**명령줄 인수**|디버깅할 프로그램에 대한 명령줄 인수를 지정합니다. 명령 이름은 시작 외부 프로그램에 지정된 프로그램 이름입니다. 시작 작업이 시작 URL로 설정되면 명령줄 인수를 지정할 수 없습니다.|  
|**작업 디렉터리**|디버깅 중인 프로그램의 작업 디렉터리를 지정합니다. [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]에서는 응용 프로그램이 시작된 디렉터리가 작업 디렉터리입니다. 이 디렉터리는 기본적으로 \bin\debug입니다.|  
|**원격 컴퓨터 사용**|디버깅을 위해 응용 프로그램을 실행할 원격를 컴퓨터의 이름 또는 [Msvsmon 서버 이름](../debugger/remote-debugging.md)합니다. 원격 컴퓨터에 있는 EXE의 위치는 구성 속성 폴더의 빌드 범주에 있는 출력 경로 속성으로 지정됩니다. 이 위치는 원격 컴퓨터의 공유할 수 있는 디렉터리여야 합니다.|
|**비관리 코드 디버깅 사용**|관리되는 응용 프로그램에서의 비관리 네이티브 Win32 코드에 대한 호출을 디버깅할 수 있습니다.|  
|**SQL Server 디버깅 사용**|SQL Server 데이터베이스 개체를 디버깅할 수 있습니다.|  
  
##  <a name="BKMK_Build_tab"></a>빌드 탭  
  
|설정|설명|  
|-------------|-----------------|  
|**조건부 컴파일 기호:**|DEBUG 및 TRACE 상수가 여기에 정의됩니다.<br /><br /> 이러한 상수를의 조건부 컴파일을 사용 하면는 [Debug 클래스](/dotnet/api/system.diagnostics.debug) 및 [Trace 클래스](/dotnet/api/system.diagnostics.trace)합니다. 이 상수를 정의 디버그 및 Trace 클래스 메서드의 결과가 [출력 창](../ide/reference/output-window.md)합니다. 이 상수를 정의하지 않으면 Debug 및 Trace 클래스 메서드가 컴파일되지 않으므로 결과가 생성되지 않습니다.<br /><br /> -디버그 정상적으로 프로그램의 디버그 버전에서 정의 되 고 릴리스 버전에 정의 되지 않았습니다.<br />추적은 일반적으로 모두 디버그 및 릴리스 버전에 정의 됩니다.|  
|**코드 최적화**|최적화된 코드에만 나타나는 버그가 발견되지 않을 경우, 디버그 버전에서 이 설정을 해제해야 합니다. 코드를 최적화하면 명령이 소스 창에 있는 문에 직접 대응되지 않기 때문에 디버깅하기 어렵습니다.|  
|**출력 경로:**|디버깅 작업에서는 일반적으로 bin\Debug로 설정합니다.|

> [!NOTE]
> 디버그 옵션에 대 한 자세한 내용은 **고급** 단추, 참조 [고급 빌드 설정 대화 상자 (C#)](../ide/reference/advanced-build-settings-dialog-box-csharp.md)합니다. 기호 (.pdb) 파일에 대 한 가능한 형식에는.NET Core에 대 한 가장 최근의 플랫폼 간 형식이입니다. 
  
## <a name="see-also"></a>참고 항목  
 [디버거 설정 및 준비](../debugger/debugger-settings-and-preparation.md)