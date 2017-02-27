---
title: "격리 된 셸의 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Visual Studio shell 격리 모드"
ms.assetid: f8d68c3d-9134-4a8f-b566-485956cd321e
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# 격리 된 셸의 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

레지스트리 설정, 실행 시간 설정 및 응용 프로그램 진입점의 격리 된 셸 응용 프로그램 및.vsct,.pkgdef, and.pkgundef 파일을 수정할 수 있습니다.  
  
## 레지스트리 설정  
 .pkgdef 응용 프로그램과.pkgundef 파일에는 격리 된 셸 응용 프로그램에 대 한 레지스트리 설정을 수정합니다. 응용 프로그램을 실행 하는 경우 다음과 같은 순서로 레지스트리 설정이 정의 됩니다.  
  
 응용 프로그램을 실행 하는 경우 다음과 같은 순서로 레지스트리 설정이 정의 됩니다.  
  
1.  응용 프로그램에 대 한 레지스트리 키를 만듭니다.  
  
2.  레지스트리에 지정 된 키와 항목을 정의 하 여 응용 프로그램의.pkgdef 파일에서 업데이트 됩니다.  
  
3.  응용 프로그램의 일부인 모든 패키지는.pkgdef 파일에 해당 패키지의 레지스트리가 업데이트 됩니다. 각 패키지는 $RootKey$ \\Packages\\ 하 여 응용 프로그램의.pkgdef 파일에 정의 된 {*vsPackageGuid*} 패키지에 대 한 키입니다.  
  
4.  레지스트리에서 BaseConfig.pkgdef 고 AppEnvConfig.pkgdef에서 업데이트 되는 *Visual Studio SDK 설치 경로*\\Common7\\IDE\\ShellExtensions\\Platform 디렉터리입니다. 이러한 파일은 Visual Studio의 일부 및 또한 Visual Studio Shell \(격리 모드\) 재배포 가능 패키지의 일부입니다.  
  
5.  레지스트리에 지정 된 키와 항목을 제거 하 여 응용 프로그램의.pkgundef 파일에서 업데이트 됩니다.  
  
## 런타임 설정  
 격리 된 셸 응용 프로그램을 시작 하는 경우 Visual Studio shell의 시작 진입점을 호출 합니다. 응용 프로그램 설정에는 응용 프로그램이 시작 되 면 다음과 같이 정의 됩니다.  
  
1.  Visual Studio shell 특정 키에 대 한 응용 프로그램 레지스트리를 확인합니다. 시작 진입점에 대 한 호출에는 키에 대 한 설정을 지정 하는 경우 해당 값의 레지스트리 값을 재정의 합니다.  
  
2.  레지스트리 나 항목 지점 설정의 값을 지정 하는 매개 변수는 경우 설정에 대해 기본값이 사용 됩니다.  
  
 명령줄에서 응용 프로그램을 시작 하면 모든 명령줄 스위치 Devenv 수행 하는 동일한 방식으로 처리 하는 Visual Studio shell에 전달 됩니다. Devenv 스위치에 대 한 자세한 내용은 참조 [Devenv 명령줄 스위치](../ide/reference/devenv-command-line-switches.md) 및 [VSPackage 개발에 대 한 Devenv 명령줄 스위치](../extensibility/devenv-command-line-switches-for-vspackage-development.md)합니다. 명령줄 스위치에 대 한 패키지를 등록 하는 방법에 대 한 자세한 내용은 참조 [명령줄 스위치를 추가합니다.](../extensibility/adding-command-line-switches.md)합니다.  
  
## 시작 진입점  
 Appenvstub.dll 파일에는 격리 된 셸에 액세스 하기 위한 진입점 포함 되어 있습니다. 응용 프로그램이 시작 될 때 시작 항목 Appenvstub.dll 포인트를 호출 합니다.  
  
 시작 진입점에 전달 되는 마지막 매개 변수 값을 변경 하 여 응용 프로그램의 동작을 변경할 수 있습니다. 자세한 내용은 [격리 된 셸 진입점 매개 변수 \(c \+ \+\)](../extensibility/isolated-shell-entry-point-parameters-cpp.md)을 참조하세요.  
  
## . Vsct 파일  
 .Vsct 파일에는 표준 Visual Studio UI 요소는 응용 프로그램에서 사용할 수 있는 지정할 수 있습니다. 자세한 내용은 [. Vsct 파일](../extensibility/modifying-the-isolated-shell-by-using-the-dot-vsct-file.md)을 참조하십시오.  
  
## . Pkgundef 파일  
 Visual Studio가 이미 설치 된 컴퓨터에 응용 프로그램이 설치 될 때 응용 프로그램에 대 한 Visual Studio 레지스트리 항목의 복사본을 이루어집니다. 기본적으로 응용 프로그램이 컴퓨터에 이미 설치 되어 있는 VSPackages를 사용 합니다. .Pkgundef 파일에는 응용 프로그램에서 Visual Studio 셸 또는 확장 프로그램의 특정 요소를 제거 하기 위해 레지스트리 항목을 제외할 수 있습니다. 자세한 내용은 [. Pkgundef 파일](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgundef-file.md)을 참조하십시오.  
  
 .Pkgundef 파일에는 응용 프로그램에서 Visual Studio 셸 또는 확장 프로그램의 특정 요소를 제거 하기 위해 레지스트리 항목을 제외할 수 있습니다. 자세한 내용은 [. Pkgundef 파일](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgundef-file.md)을 참조하십시오.  
  
 패키지 Guid 제외할 수의 집합에 나열 된 [Visual Studio의 기능 패키지 Guid](../extensibility/package-guids-of-visual-studio-features.md)합니다.  
  
## . Pkgdef 파일  
 .Pkgdef 파일에는 응용 프로그램을 설치할 때 설정 된 응용 프로그램에 대 한 레지스트리 항목을 정의할 수 있습니다. Visual Studio 셸을 사용 하는 레지스트리 항목의 목록 및.pkgdef 파일에 대 한 설명을 참조 하십시오. [. Pkgdef 파일](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)합니다.  
  
## 대체 문자열  
 .Pkgdef 및.pkgundef 파일에 사용 되는 대체 문자열에 나열 된 [사용 되는 대체 문자열입니다. Pkgdef 하 고 있습니다. Pkgundef 파일](../extensibility/substitution-strings-used-in-dot-pkgdef-and-dot-pkgundef-files.md)합니다.  
  
## 기타 설정  
 격리 된 셸 응용 프로그램 Microsoft.VisualStudio.GraphModel.dll에 의존 하는 경우 격리 된 셸 응용 프로그램의.config 파일에 다음 바인딩 리디렉션을 추가 해야 합니다.  
  
```  
<dependentAssembly>  
    <assemblyIdentity name="Microsoft.VisualStudio.GraphModel" publicKeyToken="b03f5f7f11d50a3a" culture="neutral" />  
    <bindingRedirect oldVersion="11.0.0.0" newVersion="12.0.0.0"/>  
</dependentAssembly>  
  
```