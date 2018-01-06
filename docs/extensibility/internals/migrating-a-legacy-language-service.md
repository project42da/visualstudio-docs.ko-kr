---
title: "레거시 언어 서비스 마이그레이션 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: language services, migrating
ms.assetid: e0f666a0-92a7-4f9c-ba79-d05b13fb7f11
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4f5f7cff29dd368acbbc3f599ec0cf623343031f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="migrating-a-legacy-language-service"></a>레거시 언어 서비스 마이그레이션
프로젝트를 업데이트 하는 프로젝트 source.extension.vsixmanifest 파일을 추가 하 여 Visual Studio의 이후 버전으로 레거시 언어 서비스를 마이그레이션할 수 있습니다. Visual Studio 편집기에 맞게 변경 하기 때문에 자체 언어 서비스는 이전과 같이 작동 계속 됩니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 된 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 최신 방법입니다. 언어 서비스를 구현 하는 새로운 방법에 대해 자세히 알아보려면 참조 [편집기와 언어 서비스 확장](../../extensibility/editor-and-language-service-extensions.md)합니다.  
  
> [!NOTE]
>  편집기를 사용 하 여 새 API 가능한 한 빨리 시작 하는 것이 좋습니다. 언어 서비스의 성능이 향상 되 고 새 편집기 기능을 이용할 수 있도록 합니다.  
  
## <a name="migrating-a-visual-studio-2008-language-service-solution-to-a-later-version"></a>최신 버전에는 Visual Studio 2008 언어 서비스 솔루션 마이그레이션  
 다음 단계에는 RegExLanguageService 라는 Visual Studio 2008 샘플을 조정 하는 방법을 보여 줍니다. Visual Studio 2008 SDK 설치 시에이 샘플을 찾을 수는 *Visual Studio SDK 설치 경로*\VisualStudioIntegration\Samples\IDE\CSharp\Example.RegExLanguageService\ 폴더입니다.  
  
> [!IMPORTANT]
>  언어 서비스 색을 정의 하지 않는 경우 명시적으로 설정 해야 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute.RequestStockColors%2A> 를 `true` VSPackage에서:  
  
```  
[Microsoft.VisualStudio.Shell.ProvideLanguageService(typeof(YourLanguageService), YourLanguageServiceName, 0, RequestStockColors = true)]  
```  
  
#### <a name="to-migrate-a-visual-studio-2008-language-service-to-a-later-version"></a>최신 버전에는 Visual Studio 2008 언어 서비스를 마이그레이션하려면  
  
1.  최신 버전의 Visual Studio 및 Visual Studio SDK를 설치 합니다. SDK를 설치 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio SDK 설치](../../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
2.  Visual Studio에서 로드 (없이 RegExLangServ.csproj 파일을 편집 합니다. 합니다.  
  
     에 `Import` Microsoft.VsSDK.targets 파일을 참조 하는 노드를 다음 텍스트로 값을 바꿉니다.  
  
    ```  
    $(MSBuildExtensionsPath)\Microsoft\VisualStudio\v14.0\VSSDK\Microsoft.VsSDK.targets  
    ```  
  
3.  파일을 저장 한 다음 닫습니다.  
  
4.  RegExLangServ.sln 솔루션을 엽니다.  
  
5.  **단방향 업그레이드가** 창이 나타납니다. **확인**을 클릭합니다.  
  
6.  프로젝트 속성을 업데이트 합니다. 열기는 **프로젝트 속성** 창에서 프로젝트 노드를 선택 하 여는 **솔루션 탐색기**, 단추로 클릭 한 다음를 선택 하 고 **속성**합니다.  
  
    -   에 **응용 프로그램** 탭으로 변경 **대상 프레임 워크** 를 **4.6.1**합니다.  
  
    -   에 **디버그** 탭에 **시작 외부 프로그램** 상자에 입력 합니다  **\<Visual Studio 설치 경로 > \Common7\IDE\devenv.exe.**합니다.  
  
         에 **명령줄 인수** 상자에서 입력 /**rootsuffix Exp**합니다.  
  
7.  다음 참조를 업데이트 합니다.  
  
    -   Microsoft.VisualStudio.Shell.9.0.dll에 대 한 참조를 제거 합니다. 다음 Microsoft.VisualStudio.Shell.14.0.dll 및 Microsoft.VisualStudio.Shell.Immutable.11.0.dll에 대 한 참조를 추가 합니다.  
  
    -   Microsoft.VisualStudio.Package.LanguageService.9.0.dll에 대 한 참조를 제거 합니다. 다음 Microsoft.VisualStudio.Package.LanguageService.14.0.dll에 대 한 참조를 추가 합니다.  
  
    -   Microsoft.VisualStudio.Shell.Interop.10.0.dll에 대 한 참조를 추가 합니다.  
  
8.  VsPkg.cs 파일을 열고의 값 변경의 `DefaultRegistryRoot` 특성을  
  
    ```  
    "Software\\Microsoft\\VisualStudio\\14.0Exp"  
    ```  
  
9. 원래 샘플 VsPkg.cs에 다음 특성을 추가 해야 하므로 해당 언어 서비스를 등록 하지 않습니다.  
  
    ```  
    [ProvideLanguageService(typeof(RegularExpressionLanguageService), "RegularExpressionLanguage", 0, RequestStockColors=true)]  
    ```  
  
10. Source.extension.vsixmanifest 파일을 추가 해야 합니다.  
  
    -   기존 확장 프로그램에서이 파일을 프로젝트 디렉터리에 복사 합니다. (이 파일을 가져오는 한 가지 방법은 VSIX 프로젝트를 만드는 것 (아래 **파일**, 클릭 **새로**, 클릭 **프로젝트**합니다. 아래에서 Visual Basic 또는 C# 클릭 **확장성**을 선택한 후 **VSIX 프로젝트**.)  
  
    -   파일을 프로젝트에 추가 합니다.  
  
    -   파일의 **속성**설정, **빌드 작업** 를 **None**합니다.  
  
    -   파일을 여는 **VSIX 매니페스트 편집기**합니다.  
  
    -   다음 필드를 변경 합니다.  
  
    -   **ID**: RegExLangServ  
  
    -   **제품 이름**: RegExLangServ  
  
    -   **설명**: 정규식 언어 서비스입니다.  
  
    -   **자산**, 클릭 **새로**을 선택는 **형식** 를 **Microsoft.VisualStudio.VsPackage**설정는 **소스** 를 **현재 솔루션의 프로젝트**, 다음 설정의 **프로젝트** 를 **RegExLangServ**합니다.  
  
    -   파일을 저장한 후 닫습니다.  
  
11. 솔루션을 빌드합니다. 빌드된 파일에 배포 된 **%USERPROFILE%\AppData\Local\Microsoft\VisualStudio\14.0Exp\Extensions\MSIT\ RegExLangServ\\**합니다.  
  
12. 디버깅을 시작합니다. Visual Studio의 두 번째 인스턴스가 열립니다.  
  
## <a name="see-also"></a>참고 항목  
 [레거시 언어 서비스 확장성](../../extensibility/internals/legacy-language-service-extensibility.md)