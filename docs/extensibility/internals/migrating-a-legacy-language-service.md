---
title: "레거시 언어 서비스 마이그레이션 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "언어 서비스 마이그레이션"
ms.assetid: e0f666a0-92a7-4f9c-ba79-d05b13fb7f11
caps.latest.revision: 16
caps.handback.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
---
# 레거시 언어 서비스 마이그레이션
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트를 업데이트 하 고 source.extension.vsixmanifest 파일을 프로젝트에 추가 하 여 Visual Studio의 이후 버전으로 레거시 언어 서비스를 마이그레이션할 수 있습니다. 언어 서비스 자체는 Visual Studio 편집기 세부 항목을 처리 하기 때문에 이전 처럼 작동 하는 데 계속 됩니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 되는 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 새로운 방법입니다. 언어 서비스를 구현 하는 새로운 방법에 대 한 자세한 내용을 참조 하십시오 [편집기와 언어 서비스 확장](../../extensibility/editor-and-language-service-extensions.md)합니다.  
  
> [!NOTE]
>  새 편집기 API를 최대한 빨리 사용을 시작 하는 것이 좋습니다. 이 언어 서비스의 성능을 향상 하 고 새로운 편집기 기능을 이용할 수 있도록 합니다.  
  
## 최신 버전에는 Visual Studio 2008 언어 서비스 솔루션 마이그레이션  
 다음 단계에는 RegExLanguageService 라는 Visual Studio 2008 샘플을 조정 하는 방법을 보여 줍니다. Visual Studio 2008 SDK 설치의 경우에이 샘플을 찾을 수는 *Visual Studio SDK 설치 경로*\\VisualStudioIntegration\\Samples\\IDE\\CSharp\\Example.RegExLanguageService\\ 폴더입니다.  
  
> [!IMPORTANT]
>  언어 서비스 색을 정의 하지 않는 경우 명시적으로 설정 해야 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute.RequestStockColors%2A> 를 `true` VSPackage에서:  
  
```  
[Microsoft.VisualStudio.Shell.ProvideLanguageService(typeof(YourLanguageService), YourLanguageServiceName, 0, RequestStockColors = true)]  
```  
  
#### Visual Studio 2008 언어 서비스 이후 버전으로 마이그레이션  
  
1.  최신 버전의 Visual Studio 및 Visual Studio SDK를 설치 합니다. SDK를 설치 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio SDK 설치](../../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
2.  Visual Studio에서 로드 \(없이 RegExLangServ.csproj 파일을 편집 합니다. 합니다.  
  
     에 `Import` Microsoft.VsSDK.targets 파일을 참조 하는 노드 값을 다음 텍스트로로 바꿉니다.  
  
    ```  
    $(MSBuildExtensionsPath)\Microsoft\VisualStudio\v14.0\VSSDK\Microsoft.VsSDK.targets  
    ```  
  
3.  파일을 저장 한 다음 닫습니다.  
  
4.  RegExLangServ.sln 솔루션을 엽니다.  
  
5.  **단방향 업그레이드가** 창이 나타납니다.**확인**을 클릭합니다.  
  
6.  프로젝트 속성을 업데이트 합니다. 열기는 **프로젝트 속성** 창에서 프로젝트 노드를 선택 하 여는 **솔루션 탐색기**, 마우스, 및 선택 **속성**합니다.  
  
    -   에 **응용 프로그램** 탭에서 변경 **대상 프레임 워크** 를 **4.6.1**합니다.  
  
    -   에 **디버그** 탭에 **시작 외부 프로그램** 상자에 입력 합니다 **\< Visual Studio 설치 경로 \> \\Common7\\IDE\\devenv.exe.**합니다.  
  
         에 **명령줄 인수** 상자에서 입력 \/**rootsuffix Exp**합니다.  
  
7.  다음 참조를 업데이트 합니다.  
  
    -   Microsoft.VisualStudio.Shell.9.0.dll에 대 한 참조를 제거 합니다. 다음 Microsoft.VisualStudio.Shell.14.0.dll 및 Microsoft.VisualStudio.Shell.Immutable.11.0.dll 참조를 추가 합니다.  
  
    -   Microsoft.VisualStudio.Package.LanguageService.9.0.dll에 대 한 참조를 제거 합니다. 다음 Microsoft.VisualStudio.Package.LanguageService.14.0.dll에 대 한 참조를 추가 합니다.  
  
    -   Microsoft.VisualStudio.Shell.Interop.10.0.dll에 대 한 참조를 추가 합니다.  
  
8.  VsPkg.cs 파일을 열고 값을 변경 하는 `DefaultRegistryRoot` 특성을  
  
    ```  
    "Software\\Microsoft\\VisualStudio\\14.0Exp"  
    ```  
  
9. 원래 샘플 VsPkg.cs에 다음 특성을 추가 해야 하므로 해당 언어 서비스를 등록 하지 않습니다.  
  
    ```  
    [ProvideLanguageService(typeof(RegularExpressionLanguageService), "RegularExpressionLanguage", 0, RequestStockColors=true)]  
    ```  
  
10. Source.extension.vsixmanifest 파일을 추가 해야 합니다.  
  
    -   기존 확장 프로그램에서이 파일을 프로젝트 디렉터리에 복사 합니다. \(이 파일을 한 가지 방법은 VSIX 프로젝트를 만들 수는 \(아래 **파일**, 를 클릭 **새로**, 를 클릭 한 다음 **프로젝트**합니다. 아래에서 Visual Basic 또는 C\# 클릭 **확장성**, 을 선택한 다음 **VSIX 프로젝트**.\)  
  
    -   파일을 프로젝트에 추가 합니다.  
  
    -   파일의 **속성**, 설정, **빌드 작업** 를 **None**합니다.  
  
    -   파일을 여는 **VSIX 매니페스트 편집기**합니다.  
  
    -   다음 필드를 변경 합니다.  
  
    -   **ID**: RegExLangServ  
  
    -   **제품 이름**: RegExLangServ  
  
    -   **설명**: 정규식 언어 서비스입니다.  
  
    -   아래에서 **자산**, 클릭 **새로**, 선택는 **형식** 를 **Microsoft.VisualStudio.VsPackage**, 로 설정는 **소스** 를 **현재 솔루션의 프로젝트**, 로 설정한는 **프로젝트** 를 **RegExLangServ**.  
  
    -   파일을 저장한 후 닫습니다.  
  
11. 솔루션을 빌드합니다. 빌드 파일에 배포 된 **%USERPROFILE%\\AppData\\Local\\Microsoft\\VisualStudio\\14.0Exp\\Extensions\\MSIT\\ RegExLangServ\\**합니다.  
  
12. 디버깅을 시작합니다. Visual Studio의 두 번째 인스턴스가 열립니다.  
  
## 참고 항목  
 [레거시 언어 서비스 확장](../../extensibility/internals/legacy-language-service-extensibility.md)