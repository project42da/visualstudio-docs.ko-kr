---
title: "C# 디버그 구성에 대한 프로젝트 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "디버그 빌드, 프로젝트 설정"
  - "디버그 구성, C#"
  - "디버그 구성, J#"
  - "디버깅[C#], 디버거 설정"
  - "디버깅[J#], 디버거 설정"
  - "프로젝트 구성, 디버그"
  - "프로젝트 설정[Visual Studio], 디버그 구성"
  - "프로젝트[Visual Studio], 디버그 구성"
ms.assetid: e30ca810-66e9-4d6e-9cf6-9f285cd0b100
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# C# 디버그 구성에 대한 프로젝트 설정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

C\# 디버그 구성에 대한 프로젝트 설정은 **디버그 및 릴리스 구성**에 설명된 것처럼 [속성 페이지](../debugger/how-to-set-debug-and-release-configurations.md) 창에서 변경할 수 있습니다.  다음 표에서는 **속성 페이지** 창에서 디버거 관련 설정을 확인할 수 있는 위치에 대해 설명합니다.  
  
> [!WARNING]
>  이 항목은 Windows 스토어 응용 프로그램에 적용되지 않습니다.  [디버그 세션 시작\(VB, C\#, C\+\+ 및 XAML\)](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)을 참조하세요.  
  
##  <a name="BKMK_Debug_tab"></a> 디버그 탭  
  
|**설정**|**설명**|  
|------------|------------|  
|**구성**|응용 프로그램의 컴파일 모드를 설정합니다.  **활성\(Debug\)**, **Debug**, **Release**, **모든 구성** 중에서 선택합니다.|  
|**시작 작업**|이 컨트롤 그룹은 디버그 메뉴에서 시작을 선택할 때 수행되는 작업을 지정합니다.<br /><br /> -   기본값인 **시작 프로젝트**를 선택하면 디버깅을 위한 시작 프로젝트가 실행됩니다.  자세한 내용은 [시작 프로젝트 선택](http://msdn.microsoft.com/ko-kr/222e3f32-a6fe-4941-bf37-6b2a921129fd)을 참조하십시오.<br />-   **시작 외부 프로그램**을 선택하면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트에 포함되지 않은 프로그램을 시작하고 연결할 수 있습니다.  자세한 내용은 [실행 중인 프로그램에 연결](http://msdn.microsoft.com/ko-kr/636d0a52-4bfd-48d2-89ad-d7b9ca4dc4f4)을 참조하십시오.<br />-   **다음 URL로 브라우저 시작**을 선택하면 웹 응용 프로그램을 디버깅할 수 있습니다.|  
|**명령줄 인수**|디버깅할 프로그램에 대한 명령줄 인수를 지정합니다.  명령 이름은 시작 외부 프로그램에 지정된 프로그램 이름입니다.  시작 작업이 시작 URL로 설정되면 명령줄 인수를 지정할 수 없습니다.|  
|**작업 디렉터리**|디버깅 중인 프로그램의 작업 디렉터리를 지정합니다.  [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]에서는 응용 프로그램이 시작된 디렉터리가 작업 디렉터리입니다. 이 디렉터리는 기본적으로 \\bin\\debug입니다.|  
|**원격 컴퓨터 사용**|디버깅하기 위해 응용 프로그램을 실행할 원격 컴퓨터의 이름이나 [Msvsmon 서버 이름](../Topic/Start%20%20the%20Remote%20Debugging%20Monitor.md)입니다.  원격 컴퓨터에 있는 EXE의 위치는 구성 속성 폴더의 빌드 범주에 있는 출력 경로 속성으로 지정됩니다.  이 위치는 원격 컴퓨터의 공유할 수 있는 디렉터리여야 합니다.|  
|**비관리 코드 디버깅 사용**|관리되는 응용 프로그램에서의 비관리 네이티브 Win32 코드에 대한 호출을 디버깅할 수 있습니다.|  
|**SQL Server 디버깅 사용**|SQL Server 데이터베이스 개체를 디버깅할 수 있습니다.|  
  
##  <a name="BKMK_Build_tab"></a> 빌드 탭  
  
|설정|설명|  
|--------|--------|  
|**조건부 컴파일 기호:**|DEBUG 및 TRACE 상수가 여기에 정의됩니다.<br /><br /> 이 상수를 사용하면 조건에 따라 [Debug 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.aspx)와 [Trace 클래스](https://msdn.microsoft.com/en-us/library/system.diagnostics.trace.aspx)를 컴파일할 수 있습니다.  이 상수를 정의하면 Debug 및 Trace 클래스 메서드의 결과가 [출력 창](../ide/reference/output-window.md)에 표시됩니다.  이 상수를 정의하지 않으면 Debug 및 Trace 클래스 메서드가 컴파일되지 않으므로 결과가 생성되지 않습니다.<br /><br /> -   Debug 상수는 일반적으로 프로그램의 디버그 버전에 정의되고 릴리스 버전에는 정의되지 않습니다.<br />-   Trace는 일반적으로 디버그 및 릴리스 버전에 모두 정의됩니다.|  
|**코드 최적화**|최적화된 코드에만 나타나는 버그가 발견되지 않을 경우, 디버그 버전에서 이 설정을 해제해야 합니다.  코드를 최적화하면 명령이 소스 창에 있는 문에 직접 대응되지 않기 때문에 디버깅하기 어렵습니다.|  
|**출력 경로:**|디버깅 작업에서는 일반적으로 bin\\Debug로 설정합니다.|  
  
## 참고 항목  
 [디버그 설정 및 준비](../debugger/debugger-settings-and-preparation.md)