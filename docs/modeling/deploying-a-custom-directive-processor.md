---
title: "사용자 지정 지시문 처리기 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "텍스트 템플릿, 사용자 지정 지시문 처리기"
ms.assetid: 80c28722-a630-47b5-923b-024dc3f2c940
caps.latest.revision: 18
caps.handback.revision: 18
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 사용자 지정 지시문 처리기 배포
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

임의의 컴퓨터의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 사용자 지정 지시문 프로세서를 사용하려면 이 항목에서 설명하는 방법 중 하나로 해당 프로세서를 등록해야 합니다.  
  
 이러한 방법은 다음과 같습니다.  
  
-   [VSIX\(Visual Studio Extension\)](http://msdn.microsoft.com/ko-kr/64ff1452-f7d5-42d9-98b8-76f769f76832).  자신이 사용하는 컴퓨터와 다른 컴퓨터 둘 다에 지시문 프로세서를 설치하고 제거하는 방법을 제공합니다.  일반적으로 동일한 VSIX에 다른 기능을 패키지할 수도 있습니다.  
  
-   [VSPackage](../extensibility/internals/vspackages.md).  지시문 프로세서 외에 다른 기능이 포함된 VSPackage를 정의하는 경우 지시문 프로세서를 등록하는 간편한 방법이 있습니다.  
  
-   레지스트리 키 설정.  이 방법에서는 지시문 프로세서에 대한 레지스트리 항목을 추가합니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 또는 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서 텍스트 템플릿을 변환하려는 경우에만 이러한 방법 중 하나를 사용해야 합니다.  응용 프로그램에서 사용자 지정 호스트를 사용하는 경우 사용자 지정 호스트는 각 지시문의 지시문 프로세서를 찾는 작업을 담당합니다.  
  
## VSIX로 지시문 프로세서 배포  
 사용자 지정 지시문 프로세서를 [VSIX\(Visual Studio Extension\)](http://msdn.microsoft.com/ko-kr/64ff1452-f7d5-42d9-98b8-76f769f76832)에 추가할 수 있습니다.  
  
 다음 두 항목이 .vsix 파일에 포함되어 있는지 확인해야 합니다.  
  
-   사용자 지정 지시문 프로세서 클래스가 포함된 어셈블리\(.dll\)  
  
-   지시문 프로세서를 등록하는 .pkgdef 파일.  이 파일의 루트 이름은 어셈블리와 동일해야 합니다.  예를 들어, 파일의 이름을 CDP.dll 및 CDP.pkgdef로 지정할 수 있습니다.  
  
 .vsix 파일의 내용을 검사하거나 변경하려면 파일 확장명을 .zip으로 변경한 다음 파일을 엽니다.  내용을 편집한 후 파일 이름을 다시 .vsix로 변경합니다.  
  
 여러 가지 방법으로 .vsix 파일을 만들 수 있습니다.  다음 절차에서는 한 가지 방법을 설명합니다.  
  
#### VSIX 프로젝트에서 사용자 지정 지시문 프로세서를 개발하려면  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 VSIX 프로젝트를 만듭니다.  
  
    -   **새 프로젝트** 대화 상자에서 **Visual Basic** 또는 **Visual C\#**을 확장한 다음 **확장성**을 확장합니다.  **VSIX 프로젝트**를 클릭합니다.  
  
2.  **source.extension.vsixmanifest**에서 콘텐츠 형식과 지원되는 버전을 설정합니다.  
  
    1.  VSIX 매니페스트 편집기의 **자산** 탭에서 **새로 만들기**를 선택하여 새 항목의 속성을 설정합니다.  
  
         **콘텐츠 형식** \= **VSPackage**  
  
         **소스 프로젝트** \= \<*the current project*\>  
  
    2.  **선택된 버전**을 클릭하고 지시문 프로세서를 사용하도록 할 설치 유형을 선택합니다.  
  
3.  .pkgdef 파일을 추가하고 VSIX에 포함할 속성을 설정합니다.  
  
    1.  텍스트 파일을 만들고 \<*assemblyName*\>.pkgdef로 이름을 지정합니다.  
  
         일반적으로 \<*assemblyName*\>은 프로젝트의 이름과 동일합니다.  
  
    2.  솔루션 탐색기에서 이 파일을 선택하고 다음과 같이 속성을 설정합니다.  
  
         **빌드 작업** \= **내용**  
  
         **출력 디렉터리에 복사** \= **항상 복사**  
  
         **Include in VSIX** \= **True**  
  
    3.  VSIX의 이름을 설정하고 ID가 고유한지 확인합니다.  
  
4.  .pkgdef 파일에 다음 텍스트를 추가합니다.  
  
    ```  
    [$RootKey$\TextTemplating]  
    [$RootKey$\TextTemplating\DirectiveProcessors]  
    [$RootKey$\TextTemplating\DirectiveProcessors\ CustomDirectiveProcessorName]  
    @="Custom Directive Processor description"  
    "Class"="NamespaceName.ClassName"  
    "CodeBase"="$PackageFolder$\AssemblyName.dll"  
    ```  
  
     `CustomDirectiveProcessorName`, `NamespaceName`, `ClassName`, `AssemblyName`을 사용자 고유의 이름으로 바꿉니다.  
  
5.  프로젝트에 다음 참조를 추가합니다.  
  
    -   **Microsoft.VisualStudio.TextTemplating.\*.0**  
  
    -   **Microsoft.VisualStudio.TextTemplating.Interfaces.\*.0**  
  
    -   **Microsoft.VisualStudio.TextTemplating.VSHost.\*.0**  
  
6.  사용자 지정 지시문 프로세서 클래스를 프로젝트에 추가합니다.  
  
     이 클래스는 <xref:Microsoft.VisualStudio.TextTemplating.DirectiveProcessor> 또는 <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor>를 구현해야 하는 공용 클래스입니다.  
  
#### 사용자 지정 지시문 프로세서를 설치하려면  
  
1.  Windows 탐색기\(Windows 8의 파일 탐색기\)에서 빌드 디렉터리\(일반적으로 bin\\Debug 또는 bin\\Release\)를 엽니다.  
  
2.  다른 컴퓨터에 지시문 프로세서를 설치하려면 .vsix 파일을 해당 컴퓨터에 복사합니다.  
  
3.  .vsix 파일을 두 번 클릭합니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Extension 설치 관리자가 나타납니다.  
  
4.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 다시 시작합니다.  이제 사용자 지정 지시문 프로세서를 참조하는 지시문이 포함된 텍스트 템플릿을 실행할 수 있습니다.  각 지시문의 형식은 다음과 같습니다.  
  
     `<#@ CustomDirective Processor="CustomDirectiveProcessorName" parameter1="value1" … #>`  
  
#### 사용자 지정 지시문 프로세서를 제거하거나 임시로 사용하지 않도록 설정하려면  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] **도구** 메뉴에서 **확장 관리자**를 클릭합니다.  
  
2.  지시문 프로세서가 포함된 VSIX를 선택한 다음 **제거** 또는 **사용 안 함**을 클릭합니다.  
  
### VSIX에서 지시문 프로세서 문제 해결  
 지시문 프로세서가 작동하지 않으면 다음 제안 사항이 도움이 될 수 있습니다.  
  
-   사용자 지정 지시문에서 지정하는 프로세서 이름이 .pkgdef 파일에서 지정한 `CustomDirectiveProcessorName`과 일치해야 합니다.  
  
-   `IsDirectiveSupported` 메서드가 `CustomDirective`의 이름이 전달될 때 `true`를 반환해야 합니다.  
  
-   확장 관리자에서 확장이 표시되지 않고 시스템에서 확장을 설치할 수 없는 경우 **%localappdata%\\Microsoft\\VisualStudio\\\*.0\\Extensions\\**에서 확장을 삭제합니다.  
  
-   .vsix 파일을 열고 파일 내용을 검사합니다.  이 파일을 열려면 파일 확장명을 .zip으로 변경합니다.  이 파일에 .dll, .pkgdef 및 extension.vsixmanifest 파일이 포함되어 있는지 확인합니다.  extension.vsixmanifest 파일은 SupportedProducts 노드에 적절한 목록을 포함해야 하며 Content 노드 아래에 VsPackage 노드를 포함해야 합니다.  
  
     `<Content>`  
  
     `<VsPackage>CustomDirectiveProcessor.dll</VsPackage>`  
  
     `</Content>`  
  
## VSPackage에서 지시문 프로세서 배포  
 지시문 프로세서가 GAC에서 설치될 VSPackage에 포함된 경우 시스템에서 .pkgdef 파일을 자동으로 생성할 수 있습니다.  
  
 패키지 클래스에 다음 특성을 배치합니다.  
  
```  
[ProvideDirectiveProcessor(typeof(DirectiveProcessorClass), "DirectiveProcessorName", "Directive processor description.")]  
```  
  
> [!NOTE]
>  이 특성은 지시문 프로세서 클래스가 아니라 패키지 클래스에 배치됩니다.  
  
 .pkgdef 파일은 프로젝트를 빌드할 때 생성됩니다.  VSPackage를 설치하면 .pkgdef 파일이 지시문 프로세서를 등록합니다.  
  
 .pkgdef 파일이 빌드 폴더에 나타나는지 확인합니다. 빌드 폴더는 대개 bin\\Debug 또는 bin\\Release입니다.  이 파일이 나타나지 않으면 텍스트 편집기에서 .csproj 파일을 열고 `<GeneratePkgDefFile>false</GeneratePkgDefFile>` 노드를 제거합니다.  
  
 자세한 내용은 [Vspackage](../extensibility/internals/vspackages.md)를 참조하십시오.  
  
## 레지스트리 키 설정  
 사용자 지정 지시문 프로세서를 설치하는 이 방법은 가장 선호되지 않는 방법입니다.  이 방법으로는 간편하게 지시문 프로세서를 사용하거나 사용하지 않도록 설정할 수 없으며 지시문 프로세서를 다른 사용자에게 배포할 수 없습니다.  
  
> [!CAUTION]
>  레지스트리를 올바르게 편집하지 않으면 시스템을 심각하게 손상시킬 수 있습니다.  따라서 레지스트리를 변경하기 전에 컴퓨터에 있는 중요한 데이터를 백업해야 합니다.  
  
#### 레지스트리 키를 설정하여 지시문 프로세서를 등록하려면  
  
1.  `regedit`를 실행합니다.  
  
2.  regedit에서 다음 레지스트리 키로 이동합니다.  
  
     **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\\*.0\\TextTemplating\\DirectiveProcessors**  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 실험적 버전에서 지시문 프로세서를 설치하려면 "11.0" 뒤에 ."Exp"를 삽입합니다.  
  
3.  지시문 프로세서 클래스와 이름이 같은 레지스트리 키를 추가합니다.  
  
    -   레지스트리 트리에서 **DirectiveProcessors** 노드를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **키**를 클릭합니다.  
  
4.  새 노드에서 다음 표에 따라 Class와 CodeBase 또는 Assembly의 문자열 값을 추가합니다.  
  
    1.  만든 노드를 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 다음 **문자열 값**을 클릭합니다.  
  
    2.  값의 이름을 편집합니다.  
  
    3.  이름을 두 번 클릭하고 데이터를 편집합니다.  
  
 사용자 지정 지시문 프로세서가 GAC에 없는 경우 레지스트리 하위 키는 다음 표와 같습니다.  
  
|Name|형식|데이터|  
|----------|--------|---------|  
|\(기본값\)|REG\_SZ|\(값 설정 안 됨\)|  
|클래스|REG\_SZ|\<네임스페이스 이름\>.\<클래스 이름\>|  
|CodeBase|REG\_SZ|\<경로\>\\\<어셈블리 이름\>|  
  
 어셈블리가 GAC에 있는 경우 레지스트리 하위 키는 다음 표와 같습니다.  
  
|Name|형식|데이터|  
|----------|--------|---------|  
|\(기본값\)|REG\_SZ|\(값 설정 안 됨\)|  
|클래스|REG\_SZ|\<정규화된 클래스 이름\>|  
|어셈블리|REG\_SZ|\<GAC에서 어셈블리 이름\>|  
  
## 참고 항목  
 [사용자 지정 T4 텍스트 템플릿 지시문 프로세서 만들기](../modeling/creating-custom-t4-text-template-directive-processors.md)