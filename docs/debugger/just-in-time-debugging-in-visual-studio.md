---
title: "Visual Studio에서 Just-In-Time 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "CSharp"
  - "VB"
helpviewer_keywords: 
  - "디버깅[Visual Studio], Just-In-Time"
  - "Just-In-Time 디버깅"
ms.assetid: 14972d5f-69bc-479b-9529-03b8787b118f
caps.latest.revision: 48
caps.handback.revision: 40
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# Visual Studio에서 Just-In-Time 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 외부에서 실행 중인 프로그램에 예외 또는 충돌이 발생하면 JIT\(Just\-In\-Time\) 디버깅을 통해 Visual Studio가 자동으로 시작됩니다.  따라서 Visual Studio가 실행 중이 아닐 때 응용 프로그램을 테스트하고, 문제가 발생할 경우 Visual Studio를 사용하여 디버깅을 시작할 수 있습니다.  
  
 Just\-In\-Time 디버깅은 Windows 스토어 응용 프로그램에서 작동하지 않습니다.  Just\-In\-Time 디버깅은 시각화 도우미 같은 네이티브 응용 프로그램에 호스팅된 관리 코드에 대해 작동하지 않습니다.  
  
## Just\-In\-Time 디버깅 사용  
 Visual Studio를 설치하면 Just\-In\-Time 디버깅이 기본적으로 활성화됩니다.  Just\-In\-Time 디버깅을 비활성화하거나 다시 활성화해야 하는 경우에는 [단계별 코드 실행을 내 코드만으로 제한](../debugger/navigating-through-code-with-the-debugger.md#BKMK_Restrict_stepping_to_Just_My_Code)을 참조하세요.  
  
 Just\-In\-Time 디버깅이 활성화되어 있으면 Visual Studio 외부에서 응용 프로그램을 테스트할 수 있습니다.  충돌이나 예외가 발생하면 다음과 같은 메시지가 포함된 대화 상자가 나타납니다.  
  
 처리되지 않은 예외\('System.TypeInitializationException'\)가 terrarium.exe\[3384\]에서 발생했습니다.  
  
 이 대화 상자가 나타나면 다음 절차에 따라 디버깅을 시작할 수 있습니다.  
  
#### 오류 발생 시 Just\-In\-Time 디버깅을 시작하려면  
  
1.  Just\-In\-Time 디버깅 대화 상자의 **사용 가능한 디버거** 목록에서 **다음 제품의 새 인스턴스: Visual Studio 2015**를 클릭하거나 이미 실행 중인 Visual Studio의 인스턴스를 클릭합니다.  
  
2.  이후의 모든 충돌에 대해 Visual Studio를 자동으로 사용하려면 **현재 선택한 디버거를 기본값으로 설정**을 클릭합니다.  
  
3.  디버깅할 수 있는 코드 형식을 선택하려면 **디버깅 엔진을 수동으로 선택**을 클릭합니다.  이 옵션을 선택하지 않으면 프로그램의 코드 형식에 적합한 디버깅 엔진이 자동으로 선택됩니다.  
  
4.  **확인**을 클릭합니다.  
  
5.  응용 프로그램에 신뢰할 수 없는 코드가 있는 어셈블리가 포함되어 있으면 보안 경고 대화 상자가 나타납니다.  이 대화 상자에서 디버깅을 계속할지 여부를 결정할 수 있습니다.  디버깅을 계속하기 전에 코드를 신뢰할 수 있는지 확인해야 합니다.  직접 작성한 코드인지,  코드 작성자를 신뢰할 수 있는지,  응용 프로그램이 원격 컴퓨터에서 실행 중인 경우 프로세스 이름을 알 수 있는지 등을 확인합니다.  응용 프로그램이 로컬로 실행 중이라고 해서 반드시 신뢰할 수 있는 것은 아닙니다.  예를 들어 Internet Explorer에서 악의적인 ActiveX 컨트롤이 실행될 수도 있습니다.  이러한 악의적인 코드가 컴퓨터에서 실행될 수 있다는 가능성을 고려해야 합니다.  디버깅하려는 코드가 신뢰할 수 있는 것으로 확인되면 **디버그**를 클릭합니다.  그렇지 않으면 **디버그 안 함**을 클릭합니다.  
  
##  <a name="BKMK_Enabling"></a> Just\-In\-Time 디버깅 활성화 또는 비활성화  
 **옵션** 대화 상자에서 Just\-In\-Time 디버깅을 활성화하거나 비활성화할 수 있습니다.  
  
#### Just\-In\-Time 디버깅을 활성화하거나 비활성화하려면  
  
1.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
2.  **옵션** 대화 상자에서 **디버깅** 폴더를 선택합니다.  
  
3.  **디버깅** 폴더에서 **Just\-In\-Time** 페이지를 선택합니다.  
  
4.  **다음 코드 형식에 Just\-In\-Time 디버깅 사용** 상자에서 해당 프로그램 형식\(**관리**, **네이티브** 또는 **스크립트**\)을 선택하거나 해제합니다.  
  
     활성화되어 있는 Just\-In\-Time 디버깅을 비활성화하려면 프로그램을 관리자 권한으로 실행해야 합니다.  Just\-In\-Time 디버깅을 활성화하면 레지스트리 키가 설정되고 이 키를 변경하려면 관리자 권한이 있어야 합니다.  
  
5.  **확인**을 클릭합니다.  
  
 기본적으로 Windows Forms 응용 프로그램에는 복구할 수 있는 경우 프로그램을 계속 실행할 수 있도록 하는 최상위 예외 처리기가 있습니다.  따라서 Windows Forms 응용 프로그램의 Just\-In\-Time 디버깅을 활성화하려면 다음과 같은 단계를 추가로 수행해야 합니다.  
  
#### Windows Form에 Just\-In\-Time 디버깅을 사용하려면  
  
1.  machine.config 또는 *application*.exe.config 파일의 `system.windows.form` 섹션에서 `jitDebugging` 값을 `true`로 설정합니다.  
  
    ```  
    <configuration>  
        <system.windows.forms jitDebugging="true" />  
    </configuration>  
    ```  
  
2.  C\+\+ Windows Forms 응용 프로그램의 경우 .config 파일이나 코드에서 `DebuggableAttribute`도 설정해야 합니다.  [\/Zi](/visual-cpp/build/reference/z7-zi-zi-debug-information-format)만 사용하고 [\/Og](/visual-cpp/build/reference/og-global-optimizations)는 사용하지 않은 상태에서 컴파일하면 컴파일러에서 이 특성을 자동으로 설정합니다.  그러나 최적화되지 않은 릴리스 빌드를 디버깅하려면 이 특성을 직접 설정해야 합니다.  응용 프로그램의 AssemblyInfo.cpp 파일에 다음 줄을 추가하여 이 특성을 설정할 수 있습니다.  
  
    ```  
    [assembly:System::Diagnostics::DebuggableAttribute(true, true)];   
    ```  
  
     자세한 내용은 <xref:System.Diagnostics.DebuggableAttribute>을 참조하세요.  
  
 컴퓨터에 Visual Studio가 더 이상 설치되어 있지 않아도 Just\-In\-Time 디버깅은 계속 활성화되어 있습니다.  그러나 Visual Studio가 설치되어 있지 않으면 Visual Studio **옵션** 대화 상자에서 Just\-In\-Time 디버깅을 비활성화할 수 없습니다.  이 경우 Windows 레지스트리를 편집하여 Just\-In\-Time 디버깅을 비활성화할 수 있습니다.  
  
#### 레지스트리를 편집하여 Just\-In\-Time 디버깅을 비활성화하려면  
  
1.  **시작** 메뉴에서 `regedit.exe`를 검색하고 실행합니다.  
  
2.  **레지스트리 편집기** 창에서 다음 레지스트리 키를 찾아 삭제합니다.  
  
    -   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AeDebug\\Debugger  
  
    -   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework\\DbgManagedDebugger  
  
3.  컴퓨터가 64비트 운영 체제에서 실행되는 경우에는 다음 레지스트리 키도 삭제합니다.  
  
    -   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Windows NT\\CurrentVersion\\AeDebug\\Debugger  
  
    -   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework\\DbgManagedDebugger  
  
4.  실수로 다른 레지스트리 키를 삭제하거나 변경하지 않도록 주의합니다.  
  
5.  **레지스트리 편집기** 창을 닫습니다.  
  
## Just\-In\-Time 디버깅 오류  
 Just\-In\-Time 디버깅과 관련된 다음 오류 메시지가 나타날 수도 있습니다.  
  
-   **충돌 프로세스에 연결할 수 없습니다.  지정한 프로그램은 Windows 또는 MS\-DOS 프로그램이 아닙니다.**  
  
     이 오류는 Windows 2000에서 다른 사용자로 실행 중인 프로세스에 연결하려고 할 때 발생합니다.  
  
     이 문제를 해결하려면 Visual Studio를 시작하고 **디버그** 메뉴에서 **프로세스에 연결** 대화 상자를 연 다음 **사용 가능한 프로세스** 목록에서 디버깅할 프로세스를 찾습니다.  프로세스 이름을 모르는 경우에는 **Visual Studio Just\-In\-Time Debugger** 대화 상자에서 프로세스 ID를 확인한 다음  **사용 가능한 프로세스** 목록에서 프로세스를 선택하고 **연결**을 클릭합니다.  **Visual Studio Just\-In\-Time Debugger** 대화 상자에서 **아니요**를 클릭하여 대화 상자를 닫습니다.  
  
-   **로그온한 사용자가 없으므로 디버거를 시작할 수 없습니다.**  
  
     이 오류는 콘솔에 로그온한 사용자가 없는 컴퓨터에서 Just\-In\-Time 디버깅 시 Visual Studio를 시작하려고 할 때 발생합니다.  로그온한 사용자가 없으므로 Just\-In\-Time 디버깅 대화 상자를 표시할 사용자 세션이 없습니다.  
  
     이 문제를 해결하려면 컴퓨터에 로그온합니다.  
  
-   **클래스가 등록되지 않았습니다.**  
  
     이 오류는 설치 문제 등으로 인해 등록되지 않은 COM 클래스를 디버거에서 만들려고 했음을 의미합니다.  
  
     이 문제를 해결하려면 설치 디스크를 사용하여 Visual Studio를 다시 설치하거나 Visual Studio 설치를 복구합니다.  
  
## 참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [디버거 기본 사항](../debugger/debugger-basics.md)   
 [옵션 대화 상자, 디버깅, Just\-In\-Time](../debugger/just-in-time-debugging-options-dialog-box.md)   
 [보안 경고: 신뢰할 수 없는 사용자가 소유한 프로세스에 연결하면 위험할 수 있습니다. 아래의 정보가 의심스럽거나 잘 모르겠으면 이 프로세스에 연결하지 마십시오.](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process.md)