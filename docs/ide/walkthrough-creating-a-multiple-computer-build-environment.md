---
title: "연습: 여러 컴퓨터 빌드 환경 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "빌드 환경, MSBuild"
  - "MSBuild, 여러 컴퓨터에서 빌드"
ms.assetid: ae5391b1-3eec-42f5-beb3-f28630615a9e
caps.latest.revision: 7
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 7
---
# 연습: 여러 컴퓨터 빌드 환경 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

호스트 컴퓨터에서 Visual Studio 설치하여 조직 내에서 빌드 환경을 만들 수 있고, 다양한 파일들의 복사 및 다른 컴퓨터에 대한 설정을 통해 빌드에 참여할 수 있도록 만듭니다.  다른 컴퓨터에 Visual Studio를 설치할 필요가 없습니다.  
  
 이 문서는 외부에 소프트웨어를 재배포하거나 타사로 빌드 환경을 제공하기 위한 권한을 제공하지 않습니다.  
  
||  
|-|  
|고지 사항<br /><br /> 이 문서는 "as\-is"을 기초로 제공되어집니다.  설명하는 단계에서 테스트 되었지만, 모든 구성을 철저히 테스트 할 수는 없습니다.  추가적인 학습정보와 함께 문서를 최신상태로 유지하려고 합니다.  이 설명서는 URL 및 기타 인터넷 웹 사이트 참조들을 포함하며, 설명서의 내용은 예고 없이 변경될 수 있습니다.  Microsoft는 여기에 제공된 정보에 대해 어떤 명시적, 묵시적 보증도 하지 않습니다.  여러분은 이것을 사용하는 것에 대한 위험을 부담합니다.<br /><br /> 이 문서는 여러분께 Microsoft 제품의 지적 재산권에 대한 어떤 법적 권한도 제공하지 않습니다.  여러분의 내부적, 참조목적을 위해 이 문서를 사용하고 복사할 수 있을 것입니다.<br /><br /> Microsoft에 제안, 의견 또는 이 문서와 관련된 피드백을 보내야할 의무는 없습니다.  그러나, 자발적으로 제공하는 피드백은 Microsoft 제품 및 관련된 사양과 기타 문서\("Microsoft 제품"을 총괄하여\)를 이용하여 제품을 개발 하는 이들이 더 신뢰할 수 있도록 만드는데 사용할 수 있습니다.  따라서, 만일 Microsoft제품들 또는 이 문서의 어떤 버전에 대한 사용자 의견을 준다면, 동의하십시오: \(a\) Microsoft는 자유롭게 사용, 재현, 라이센스, 배포할 수 있고, 그렇지 않으면 모든 Microsoft제품에 여러분의 의견을 상용화할 수 있습니다; \(b\) 또한, 여러분의 의견이 포함하는 Microsoft제품의 특정 부분을 사용하거나 인터페이스에 다른 제품을 사용하는데 필요한 특허권을 무료로 타사에 인정하고; \(c\) Microsoft에 제공하는 모든 의견\(i\)은 특허, 저작권 또는 타사의 기타 지적 재산권 소송등의 목적으로 제공하지 않아야 합니다; 또는 \(ii\)사용자의견에서 파생되거나 결합하는 모든 MS Offering을 요구를 얻는 사용권의 적용을 받거나 Microsoft의 기타 지적 재산권을 허가하거나 제 3 자에게 공유 할 수 있습니다.|  
  
 이 단계에서는 명령줄에서 MSBuild를 실행하고 Team Foundation Build를 사용하여, 다음 운영 체제에 대한 유효성이 확인 되었습니다.  
  
-   Windows 8\(x86과 x64\)  
  
-   Windows 7 Ultimate  
  
-   Windows Server 2008 R2 Standard  
  
 이 연습 단계를 완료 한 후, 이러한 종류의 응용 프로그램을 빌드할 경우 다중 컴퓨터 환경에서 사용할 수 있습니다.  
  
-   Windows 8 SDK를 사용하는 C\+\+ 데스크톱 응용 프로그램  
  
-   .NET Framework 4.5를 대상으로 하는 Visual Basic 또는 C\# 데스크톱 응용 프로그램  
  
 다중 컴퓨터 환경에서 이러한 종류의 응용 프로그램 빌드를 사용할 수 없습니다.  
  
-   [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 응용 프로그램.  빌드 [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 응용 프로그램을 빌드 컴퓨터에 Visual Studio 설치 해야 합니다.  
  
-   .NET Framework 4 또는 이전 버전을 대상으로 하는 데스크톱 응용 프로그램입니다.  이러한 종류의 응용 프로그램을 빌드하려면, Visual Studio 나 .NET 참조 어셈블리 및 도구 \(Windows 7.1 SDK\)를 빌드 컴퓨터에 설치해야 합니다.  
  
 이 연습에서는 다음과 같은 부분들로 구분 됩니다.  
  
-   [컴퓨터에 소프트웨어 설치](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#InstallingSoftware)  
  
-   [호스트 컴퓨터에서 빌드할 컴퓨터로 파일 복사](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#CopyingFiles)  
  
-   [레지스트리 설정](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#CreatingRegistry)  
  
-   [빌드 컴퓨터의 환경 변수 설정](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#SettingEnvVariables)  
  
-   [빌드 컴퓨터의 GAC(전역 어셈블리 캐시)에 MSBuild 어셈블리 설치](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#InstallingMSBuildToGAC)  
  
-   [프로젝트 빌드](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#BuildingProjects)  
  
-   [소스 제어로 체크 될 수 있도록 빌드 환경 구성](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#CreatingForSourceControl)  
  
## 사전 요구 사항  
  
-   정품 Visual Studio Premium, Visual Studio Ultimate 또는 Visual Studio Professional.  
  
-   4.5.1,.NET Framework은 [Visual Studio](http://www.microsoft.com/visualstudio/eng/downloads#d-additional-software) 웹 사이트에서 다운로드 할 수 있습니다.  
  
##  <a name="InstallingSoftware"></a> 컴퓨터에 소프트웨어 설치  
 먼저, 호스트 컴퓨터를 설정하고 그 다음 빌드할 컴퓨터를 설정합니다.  
  
 호스트 컴퓨터에서 Visual Studio 설치하고, 이후 빌드 컴퓨터로 복사할 파일과 설정을 만듭니다.  x86 및 x64 컴퓨터에서 Visual Studio를 설치할 수 있지만, 빌드 컴퓨터 구조는 호스트 컴퓨터의 구조와 일치해야 합니다.  
  
#### 컴퓨터에 소프트웨어 설치  
  
1.  호스트 컴퓨터에서 Visual Studio 설치합니다.  
  
2.  빌드 컴퓨터에 .NET Framework 4.5를 설치 합니다. 설치 되어 있는지 확인하기위해, 레지스트리 키의 값 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full@Version가 "4.5"로 시작하는지 확인하십시오.  
  
##  <a name="CopyingFiles"></a> 호스트 컴퓨터에서 빌드할 컴퓨터로 파일 복사  
 이 단원에서는 특정 파일, 컴파일러, 빌드 도구, MSBuild 자산 및 레지스트리 설정을 빌드 컴퓨터에 호스트 컴퓨터에서 복사합니다.  다음 단계는 호스트 컴퓨터에 Visual Studio를 기본경로에 설치한 경우이며, 다른경로에 설치한 경우, 그에 맞게 조정합니다.  
  
-   x86 컴퓨터에서, 기본경로는 C:\\Program Files\\Microsoft Visual Studio 11.0\\  
  
-   x64 컴퓨터의 기본경로는 C:\\Program Files \(x86\)\\Microsoft Visual Studio 11.0\\  
  
 설치된 운영 체제에 따라 Program Files 폴더의 이름이 다름에 주의합니다.  x86 컴퓨터의 경우, \\Program Files\\, x64 컴퓨터의 경우 \\Program Files \(x86\)\\입니다.  시스템 구조에 관계 없이, 여기서 %ProgramFiles%는 Program Files 폴더를 나타냅니다.  
  
> [!NOTE]
>  빌드 컴퓨터에서, 모든 관련 파일들은 동일한 드라이브에 있어야합니다; 그러나 해당 드라이브의 드라이브 문자가 호스트 컴퓨터에서 Visual Studio 설치한 드라이브의 드라이브 문자 보다 다를 수 있습니다.  이 문서의 뒷부분에 설명된 것처럼, 레지스트리 항목을 만들 경우 파일의 위치를 설명해야 합니다.  
  
#### 빌드 컴퓨터에 Windows SDK 파일 복사  
  
1.  만일 설치된 Windows 8에 Windows SDK만 있는 경우, 호스트 컴퓨터에서 빌드 컴퓨터로 이 폴더를 재귀적으로 복사합니다.  
  
    -   %ProgramFiles%\\Windows Kits\\8.0\\bin\\  
  
    -   %ProgramFiles%\\Windows Kits\\8.0\\Catalogs\\  
  
    -   %ProgramFiles%\\Windows Kits\\8.0\\DesignTime\\  
  
    -   %ProgramFiles%\\Windows Kits\\8.0\\include\\  
  
    -   %ProgramFiles%\\Windows Kits\\8.0\\Lib\\  
  
    -   %ProgramFiles%\\Windows Kits\\8.0\\Redist\\  
  
    -   %ProgramFiles%\\Windows Kits\\8.0\\References\\  
  
     만일 여러분이 이러한 다른 Windows 8 키트를 갖고 있다면...  
  
    -   Microsoft Windows 평가 및 배포 키트  
  
    -   Microsoft Windows 드라이버 키트  
  
    -   Microsoft Windows 하드웨어 인증 키트  
  
     ...이전 단계에서 나열된 %ProgramFiles%\\Windows Kits\\8.0\\ 폴더로부터 설치된 파일들이 존재할 것이고, 이 사용약관은 해당 파일에 대한 빌드 서버 권한을 허용하지 않을 것입니다.  빌드 컴퓨터에 파일을 복사할 수 있는지 여부를 확인하려면 설치된 모든 Windows 키트에 대한 사용약관을 확인하십시오.  만일 사용 약관이 빌드 서버 권한을 허용하지 않는 다면, 빌드 컴퓨터에서 파일을 제거 합니다.  
  
2.  호스트 컴퓨터에서 빌드 컴퓨터로 다음 폴더들를 재귀적으로 복사:  
  
    -   %ProgramFiles%\\Microsoft SDKs\\Windows\\v8.0A\\bin\\NETFX 4.0 Tools\\  
  
    -   %ProgramFiles%\\Common Files\\Merge Modules\\  
  
    -   %ProgramFiles%\\Microsoft Visual Studio 11.0\\VC\\  
  
    -   %ProgramFiles%\\Microsoft Visual Studio 11.0\\Common7\\Tools\\ProjectComponents\\  
  
    -   %ProgramFiles%\\MSBuild\\Microsoft.Cpp\\v4.0\\V110\\  
  
    -   %ProgramFiles%\\Reference Assemblies\\Microsoft\\Framework\\.NETCore\\v4.5\\  
  
    -   %ProgramFiles%\\Reference Assemblies\\Microsoft\\Framework\\.NETFramework\\v4.5\\  
  
3.  호스트 컴퓨터에서 빌드할 컴퓨터로 다음 파일들을 복사  
  
    -   %ProgramFiles%\\Microsoft Visual Studio 11.0\\Common7\\IDE\\msobj110.dll  
  
    -   %ProgramFiles%\\Microsoft Visual Studio 11.0\\Common7\\IDE\\mspdb110.dll  
  
    -   %ProgramFiles%\\Microsoft Visual Studio 11.0\\Common7\\IDE\\mspdbcore.dll  
  
    -   %ProgramFiles%\\Microsoft Visual Studio 11.0\\Common7\\IDE\\mspdbsrv.exe  
  
    -   %ProgramFiles%\\Microsoft Visual Studio 11.0\\Common7\\IDE\\msvcdis110.dll  
  
    -   %ProgramFiles%\\Microsoft Visual Studio 11.0\\Common7\\Tools\\makehm.exe  
  
    -   %ProgramFiles%\\Microsoft Visual Studio 11.0\\Common7\\Tools\\VCVarsQueryRegistry.bat  
  
    -   %ProgramFiles%\\Microsoft Visual Studio 11.0\\Common7\\Tools\\vsvars32.bat  
  
4.  빌드 컴퓨터에서 빌드 출력을 실행 하는 경우에 다음 Visual C\+\+ 런타임 라이브러리가 필요합니다—예를 들면, 자동화 된 테스트의 일부  파일은 일반적으로 시스템 아키텍처에 따라 %ProgramFiles%\\Microsoft Visual Studio 11.0\\VC\\redist\\x86\\ 또는 %ProgramFiles%\\Microsoft Visual Studio 11.0\\VC\\redist\\x64\\ 폴더의 하위 폴더에 위치합니다.  x86 시스템의 경우, \\Windows\\System32\\ 폴더에 x86 이진 파일을 복사합니다.  X 64 시스템의 경우, Windows\\SysWOW64\\ 폴더의 x86 이진 파일과 Windows\\System32\\ 폴더에 x64 이진 파일을 복사 합니다.  
  
    -   \\Microsoft.VC110.ATL\\atl110.dll  
  
    -   \\Microsoft.VC110.CRT\\msvcp110.dll  
  
    -   \\Microsoft.VC110.CRT\\msvcr110.dll  
  
    -   \\Microsoft.VC110.CXXAMP\\vcamp110.dll  
  
    -   \\Microsoft.VC110.MFC\\mfc110.dll  
  
    -   \\Microsoft.VC110.MFC\\mfc110u.dll  
  
    -   \\Microsoft.VC110.MFC\\mfcm110.dll  
  
    -   \\Microsoft.VC110.MFC\\mfcm110u.dll  
  
    -   \\Microsoft.VC110.MFCLOC\\mfc110chs.dll  
  
    -   \\Microsoft.VC110.MFCLOC\\mfc110cht.dll  
  
    -   \\Microsoft.VC110.MFCLOC\\mfc110deu.dll  
  
    -   \\Microsoft.VC110.MFCLOC\\mfc110enu.dll  
  
    -   \\Microsoft.VC110.MFCLOC\\mfc110esn.dll  
  
    -   \\Microsoft.VC110.MFCLOC\\mfc110fra.dll  
  
    -   \\Microsoft.VC110.MFCLOC\\mfc110ita.dll  
  
    -   \\Microsoft.VC110.MFCLOC\\mfc110jpn.dll  
  
    -   \\Microsoft.VC110.MFCLOC\\mfc110kor.dll  
  
    -   \\Microsoft.VC110.MFCLOC\\mfc110rus.dll  
  
    -   \\Microsoft.VC110.OPENMP\\vcomp110.dll  
  
5.  그 다음, [디버그 실행 파일을 실행하기 위한 테스트 컴퓨터 준비](/visual-cpp/ide/preparing-a-test-machine-to-run-a-debug-executable)에 설명 된 대로 빌드 컴퓨터의 \\Debug\_NonRedist\\x86\\ 또는 \\Debug\_NonRedist\\x64\\ 폴더에서 다음 파일만 복사합니다.  다른 파일들은 복사할 수 없습니다.  
  
    -   \\Microsoft.VC110.DebugCRT\\msvcp110d.dll  
  
    -   \\Microsoft.VC110.DebugCRT\\msvcr110d.dll  
  
    -   \\Microsoft.VC110.DebugCXXAMP\\vcamp110d.dll  
  
    -   \\Microsoft.VC110.DebugMFC\\mfc110d.dll  
  
    -   \\Microsoft.VC110.DebugMFC\\mfc110ud.dll  
  
    -   \\Microsoft.VC110.DebugMFC\\mfcm110d.dll  
  
    -   \\Microsoft.VC110.DebugMFC\\mfcm110ud.dll  
  
    -   \\Microsoft.VC110.DebugOpenMP\\vcomp110d.dll  
  
##  <a name="CreatingRegistry"></a> 레지스트리 설정  
 MSBuild에 대한 설정을 구성하려면 레지스트리 항목을 만들어야 합니다.  
  
#### 레지스트리 설정 만들기  
  
1.  레지스트리 항목의 부모 폴더를 식별합니다.  동일한 부모 키에서 모든 레지스트리 항목이 만들어집니다.  x86 컴퓨터의 경우, 부모 키는 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\입니다.  x64 컴퓨터의 경우, 부모 키는 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\입니다.  시스템 아키텍처에 관계 없이, 이 단계는 %RegistryRoot%로 부모 키를 참조합니다.  
  
    > [!NOTE]
    >  호스트 컴퓨터의 아키텍처와 빌드 컴퓨터가 다를 경우, 각 컴퓨터에서 적합한 부모 키를 사용할 수 있는지 확인합니다.  이것은 특히 내보내기 프로세스를 자동화 하려는 경우에 중요합니다.  
    >   
    >  또한, 호스트 컴퓨터의 드라이브 문자와 빌드 컴퓨터의 드라이브 문자가 다를 경우, 일치하는 레지스트리 항목의 값을 변경할 수 있는지 확인 합니다.  
  
2.  빌드 컴퓨터에서 다음 레지스트리 항목을 만듭니다.  이러한 항목들은 모두 문자열 \(레지스트리에서 Type \=\= “REG\_SZ”\) 입니다.  다음 항목들을 호스트 컴퓨터의 항목들의 값과 동일하게 설정합니다.  
  
    -   %RegistryRoot%\\.NETFramework\\v4.0.30319\\AssemblyFoldersEx\\VCMSBuild Public Assemblies@\(Default\)  
  
    -   %RegistryRoot%\\Microsoft SDKs\\Windows\\v8.0@InstallationFolder  
  
    -   %RegistryRoot%\\Microsoft SDKs\\Windows\\v8.0A@InstallationFolder  
  
    -   %RegistryRoot%\\Microsoft SDKs\\Windows\\v8.0A\\WinSDK\-NetFx40Tools@InstallationFolder  
  
    -   %RegistryRoot%\\Microsoft SDKs\\Windows\\v8.0A\\WinSDK\-NetFx40Tools\-x86@InstallationFolder  
  
    -   %RegistryRoot%\\VisualStudio\\11.0@Source 디렉터리  
  
    -   %RegistryRoot%\\VisualStudio\\11.0\\Setup\\VC@ProductDir  
  
    -   %RegistryRoot%\\VisualStudio\\SxS\\VC7@FrameworkDir32  
  
    -   %RegistryRoot%\\VisualStudio\\SxS\\VC7@FrameworkDir64  
  
    -   %RegistryRoot%\\VisualStudio\\SxS\\VC7@FrameworkVer32  
  
    -   %RegistryRoot%\\VisualStudio\\SxS\\VC7@FrameworkVer64  
  
    -   %RegistryRoot%\\VisualStudio\\SxS\\VC7@11.0  
  
    -   %RegistryRoot%\\VisualStudio\\SxS\\VS7@11.0  
  
    -   %RegistryRoot%\\Windows Kits\\Installed Roots@KitsRoot  
  
    -   %RegistryRoot%\\MSBuild\\ToolsVersions\\4.0\\11.0@VCTargetsPath  
  
    -   %RegistryRoot%\\MSBuild\\ToolsVersions\\4.0\\11.0@VCTargetsPath10  
  
    -   %RegistryRoot%\\MSBuild\\ToolsVersions\\4.0\\11.0@VCTargetsPath11  
  
     x64 빌드 컴퓨터의 경우 역시 다음 레지스트리 항목을 만들고 호스트 컴퓨터에 따라 이것을 설정 하는 방법을 결정합니다.  
  
    -   %RegistryRoot%\\Microsoft SDKs\\Windows\\v8.0A\\WinSDK\-NetFx40Tools\-x64@InstallationFolder  
  
     만일 빌드 컴퓨터가 x64 이고 64 비트 버전의 MSBuild 사용하려는 경우 또는 x64 컴퓨터에서 Team Foundation Server 빌드 서비스를 사용하는 경우, native 64\-bit 레지스트리에 다음 레지스트리 항목을 만들어야 합니다.  이러한 항목을 설정 하는 방법을 결정 하는호스트 컴퓨터를 참조하십시오.  
  
    -   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\11.0\\Setup\\VS@ProductDir  
  
    -   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MSBuild\\ToolsVersions\\4.0\\11.0@VCTargetsPath  
  
    -   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MSBuild\\ToolsVersions\\4.0\\11.0@VCTargetsPath10  
  
    -   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MSBuild\\ToolsVersions\\4.0\\11.0@VCTargetsPath11  
  
##  <a name="SettingEnvVariables"></a> 빌드 컴퓨터의 환경 변수 설정  
 MSBuild 빌드 컴퓨터를 사용하려면, 경로 환경 변수를 설정해야 합니다.  Vcvarsall.bat 사용하여 변수를 설정하거나, 수동으로 그것을 구성할 수 있습니다.  
  
#### 환경 변수를 설정을 위한 Vcvarsall.bat의 사용  
  
-   빌드 컴퓨터에서 명령 프롬프트 창을 열고 %Program Files%\\Microsoft Visual Studio 11.0\\VC\\vcvarsall.bat.를 실행합니다.  사용할 도구 집합을 지정 하는 명령줄 인수를 사용할 수 있습니다—네이티브 x64, x86, x64 크로스 컴파일러.  만일 특정한 명령줄 인수를 지정 하지 않으면, x86 도구 집합을 사용합니다.  
  
     다음 표는 vcvarsall.bat에 지원되는 인수들입니다.  
  
    |Vcvarsall.bat 인수|컴파일러|빌드 컴퓨터 구조|출력 아키텍처 빌드|  
    |----------------------|----------|---------------|----------------|  
    |x86 \(기본값\)|32\-bit Native|x86, x64|x86|  
    |x86\_amd64|x64 Cross|x86, x64|x64|  
    |amd64|x64 Native|x64|x64|  
  
     Vcvarsall.bat이 성공적으로 실행 되는 경우—즉, 오류 메시지가 표시되지 않는 경우—다음 단계를 건너뛰고 계속해서 [빌드 컴퓨터의 GAC(전역 어셈블리 캐시)에 MSBuild 어셈블리 설치](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#InstallingMSBuildToGAC) 할 수 있습니다.  
  
#### 환경 변수를 수동으로 설정하려면  
  
1.  명령줄 환경에서 수동으로 구성 하려면, 이 경로를 PATH 환경변수에 추가 합니다.  
  
    -   %Program Files%\\Microsoft Visual Studio 11.0\\Common7\\IDE  
  
2.  필요한 경우, 솔루션빌드에 MSBuild를 사용하여 쉽게 수행할 수 있도록 PATH 변수에 다음 경로 또한 추가할 수 있습니다.  
  
     native 32\-bit MSBuild를 사용하려는 경우 이 경로를 PATH 변수에 추가 합니다.  
  
    -   %Program Files%\\Microsoft SDKs\\Windows\\v8.0A\\bin\\NETFX 4.0 Tools  
  
    -   %windir%\\Microsoft.NET\\Framework\\v4.0.30319  
  
     native 64\-bit MSBuild를 사용하려는 경우, 이 경로를 PATH 변수에 추가 합니다.  
  
    -   %Program Files%\\Microsoft SDKs\\Windows\\v8.0A\\bin\\NETFX 4.0 Tools\\x64  
  
    -   %windir%\\Microsoft.NET\\Framework64\\v4.0.30319  
  
##  <a name="InstallingMSBuildToGAC"></a> 빌드 컴퓨터의 GAC\(전역 어셈블리 캐시\)에 MSBuild 어셈블리 설치  
 MSBuild는 일부 추가적인 어셈블리를 빌드 컴퓨터의 GAC에 설치하는 것이 필요합니다.  
  
#### 호스트 컴퓨터에서 어셈블리를 복사하여 빌드 컴퓨터에 설치  
  
1.  호스트 컴퓨터에서 빌드 컴퓨터로 다음 어셈블리들을 복사.  GAC에 설치 될 것이기 때문에, 빌드 컴퓨터에 어디에 그것을 설치하더라도 문제가 되지 않습니다.  
  
    -   %ProgramFiles%\\MSBuild\\Microsoft.Cpp\\v4.0\\v110\\Microsoft.Build.CPPTasks.Common.v110.dll  
  
    -   %ProgramFiles%\\Microsoft Visual Studio 11.0\\Common7\\IDE\\CommonExtensions\\Microsoft\\VC\\Project\\Microsoft.VisualStudio.Project.VisualC.VCProjectEngine.dll  
  
    -   %ProgramFiles%\\Microsoft Visual Studio 11.0\\Common7\\IDE\\PublicAssemblies\\Microsoft.VisualStudio.VCProjectEngine.dll  
  
2.  GAC에 어셈블리를 설치하려면, 빌드 컴퓨터에 gacutil.exe를 찾습니다—일반적으로 이것은 %ProgramFiles%\\Microsoft SDKs\\Windows\\v8.0A\\bin\\NETFX 4.0 Tools\\에 있습니다.  이 폴더를 찾을 수 없는 경우, 이 섹션 [호스트 컴퓨터에서 빌드할 컴퓨터로 파일 복사](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#CopyingFiles) 에서 해당 절차를 반복합니다.  
  
     관리 권한이 있는 명령 프롬프트 창을 열고 각 파일에 대해 이 명령을 실행 합니다.  
  
     **gacutil \-i \<file\>**  
  
    > [!NOTE]
    >  완전히 GAC에 어셈블리를 설치하려면 재 부팅 해야합니다.  
  
##  <a name="BuildingProjects"></a> 프로젝트 빌드  
 여러분은 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] 프로젝트와 솔루션을 빌드하기 위해 Team Foundation Build를 사용할 수 있고, 명령줄에서 이것을 빌드 할 수 있습니다.  프로젝트 빌드를 위해 Team Foundation Build를 사용할 때, 이것은 시스템 아키텍처에 해당하는 MSBuild 실행파일을 호출합니다.  명령줄에서, MSBuild 32\-bit MSBuild 또는 64\-bit MSBuild를 사용할 수 있으며, PATH 환경 변수를 설정하거나 아키텍처에 따른 MSBuild 실행파일을 호출함으로써 MSBuild의 아키텍처를 선택할 수 있습니다.  
  
 명령 프롬프트에서 msbuild.exe를 사용하려면, 다음 명령을 실행합니다. *solution.sln* 는 솔루션의 이름에 대한 자리 표시자입니다.  
  
 **msbuild** *solution.sln*  
  
 명령줄에서 MSBuild를 사용하는 방법에 대한 자세한 내용은 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)을 참고하십시오.  
  
> [!NOTE]
>  이 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] 프로젝트를 빌드하려면, "v110" 플랫폼 도구 집합을 사용해야 합니다.  만일 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] 프로젝트 파일을 편집하지 않으려면, 이 명령줄 인수를 사용하여 플랫폼 도구 집합을 설정할 수 있습니다.  
>   
>  **msbuild** *solution.sln* **\/p:PlatformToolset\=v110**  
  
##  <a name="CreatingForSourceControl"></a> 소스 제어로 체크 될 수 있도록 빌드 환경 구성  
 여러 컴퓨터에 배포할 수 있는 빌드 환경을 만들 수 있고 GAC'ing 파일 또는 레지스트리 설정을 수정할 필요가 없습니다.  다음 단계는 이 작업을 수행할 하나의 방법입니다.  빌드 환경의 고유한 특성에 이 단계를 적용합니다.  
  
> [!NOTE]
>  빌드하는 동안 tracker.exe이 오류가 발생하지 않도록 증분 빌드를 해제해야 합니다.  증분 빌드를 사용하지 않으려면, 이 빌드 매개 변수를 설정합니다.  
>   
>  **msbuild** *solution.sln* **\/p:TrackFileAccess\=false**  
  
#### 소스 제어에 체크할 수 있는 빌드 환경을 만들려면  
  
1.  호스트 컴퓨터에 "Depot" 디렉터리를 만듭니다.  
  
     다음 단계로 %Depot%디렉터리를 참조 하십시오.  
  
2.  방금 만든 %Depot% 디렉터리 아래에 붙여넣기를 제외하고, [호스트 컴퓨터에서 빌드할 컴퓨터로 파일 복사](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#CopyingFiles) 에 설명한 대로 디렉터리와 파일을 복사합니다.  예를 들어, %Depot%\\Windows Kits\\8.0\\bin\\에 %ProgramFiles%\\Windows Kits\\8.0\\bin\\에서 복사합니다.  
  
3.  파일들을 %Depot%에 붙여넣을때 , 이러한 변경내용을 확인합니다.  
  
    -   %Depot%\\MSBuild\\Microsoft.Cpp\\v4.0\\v110\\Microsoft.CPP.Targets, \\Microsoft.Cpp.InvalidPlatforms.targets\\, \\Microsoft.cppbuild.targets\\, \\Microsoft.CppCommon.targets\\에서, 모든 인스턴스을 변경합니다.  
  
         AssemblyName\="Microsoft.Build.CppTasks.Common.v110, Version\=4.0.0.0, Culture\=neutral, PublicKeyToken\=b03f5f7f11d50a3a"  
  
         를 다음으로 변경:  
  
         AssemblyFile\="$\(VCTargetsPath11\)Microsoft.Build.CppTasks.Common.v110.dll”.  
  
         이전 이름은 GAC된 어셈블리에 의존합니다.  
  
    -   %Depot% \\MSBuild\\Microsoft.Cpp\\v4.0\\v110\\Microsoft.CPPClean.Targets에서, 모든 인스턴스를 변경합니다.  
  
         AssemblyName\="Microsoft.Build.CppTasks.Common.v110, Version\=4.0.0.0, Culture\=neutral, PublicKeyToken\=b03f5f7f11d50a3a"  
  
         를 다음으로 변경:  
  
         AssemblyFile\="$\(VCTargetsPath11\)Microsoft.Build.CppTasks.Common.v110.dll”.  
  
4.  .Props 파일 만듭니다—예를 들어, Partner.AutoImports.props—그리고 프로젝트를 포함 하는 폴더의 루트에 이 것을 넣습니다.  이 파일 MSBuild에서 다양한 리소스를 찾는데 사용되는 변수를 설정하는 데 사용됩니다.  이 파일에서 변수가 설정되지 않으면, 다른 .props 파일 및 레지스트리 값을 사용하는.targets 파일에 의해 설정됩니다.  레지스트리 값을 설정하지 않으면, 이러한 변수는 비워질 것이고, 빌드는 실패할 것입니다.  대신, Partner.AutoImports.props를 이것에 추가합니다.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <!-- This file must be imported by all project files at the top of the project file. -->  
    <Project ToolsVersion="4.0"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <PropertyGroup>  
    <VCTargetsPath>$(DepotRoot)MSBuild\Microsoft.Cpp\v4.0\v110\</VCTargetsPath>  
    <VCTargetsPath11>$(DepotRoot)MSBuild\Microsoft.Cpp\v4.0\v110\</VCTargetsPath11>  
    <MSBuildExtensionsPath>$(DepotRoot)MSBuild</MSBuildExtensionsPath>  
    <MSBuildExtensionsPath32>$(DepotRoot)MSBuild</MSBuildExtensionsPath32>  
    <VCInstallDir_110>$(DepotRoot)Microsoft Visual Studio 11.0\VC\</VCInstallDir_110>  
    <VCInstallDir>$(VCInstallDir_110)</VCInstallDir>  
    <WindowsKitRoot>$(DepotRoot)Windows Kits\</WindowsKitRoot>  
    <WindowsSDK80Path>$(WindowsKitRoot)</WindowsSDK80Path>  
    <WindowsSdkDir_80>$(WindowsKitRoot)8.0\</WindowsSdkDir_80>  
    <WindowsSdkDir>$(WindowsSDKDir_80)</WindowsSdkDir>  
    <WindowsSdkDir_80A>$(DepotRoot)Microsoft SDKs\Windows\v8.0A\</WindowsSdkDir_80A>  
    </PropertyGroup>  
    </Project>  
    ```  
  
5.  각 프로젝트 파일에서, 맨 위에 `<Project Default Targets…>` 선 이후에 다음 줄을 추가합니다.  
  
    ```  
    <Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), Partner.AutoImports.props))\Partner.AutoImports.props"/>  
    ```  
  
6.  다음과 같이 명령줄 환경을 변경합니다:  
  
    -   Depot 설정 \=*location of the Depot directory that you created in step 1*  
  
    -   경로 설정 \= %path%;*location of MSBuild on the computer*;%Depot%\\Windows\\System32;%Depot%\\Windows\\SysWOW64;%Depot%\\Microsoft Visual Studio 11.0\\Common7\\IDE\\  
  
         native 64\-bit 빌드에 대한 64\-bit MSBuild를 가리킵니다.  
  
## 참고 항목  
 [디버그 실행 파일을 실행하기 위한 테스트 컴퓨터 준비](/visual-cpp/ide/preparing-a-test-machine-to-run-a-debug-executable)   
 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)