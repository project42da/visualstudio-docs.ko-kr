---
title: "기본 프로젝트 시스템, 1 부 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 시스템을 작성"
  - "프로젝트 시스템"
  - "자습서"
ms.assetid: 882a10fa-bb1c-4b01-943a-7a3c155286dd
caps.latest.revision: 47
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 47
---
# 기본 프로젝트 시스템, 1 부
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio에서 프로젝트는 개발자가 소스 코드 파일 및 기타 자산을 구성 하는 데 사용할 컨테이너를 사용 합니다. 프로젝트에서 솔루션의 자식으로 표시 된 **솔루션 탐색기**합니다. 프로젝트에는 구성, 빌드, 디버그 및 소스 코드를 배포 및 웹 서비스, 데이터베이스 및 기타 리소스에 대 한 참조를 만들 수 있습니다.  
  
 프로젝트는 Visual C\# 프로젝트의.csproj 파일 예를 들어 프로젝트 파일에서 정의 됩니다. 사용자 고유의 프로젝트 파일 이름 확장명을 가진 고유의 프로젝트 형식을 만들 수 있습니다. 프로젝트 형식에 대 한 자세한 내용은 참조 [프로젝트 형식](../extensibility/internals/project-types.md)합니다.  
  
> [!NOTE]
>  사용자 지정 프로젝트 형식으로 Visual Studio를 확장 해야 할 경우 좋습니다 활용 하 여 [Visual Studio 프로젝트 시스템](https://github.com/Microsoft/VSProjectSystem) 다양 한 프로젝트 시스템을 처음부터 구축 하는 이점이 있는:  
>   
>  -   보다 쉽게 등록 합니다.  기본 프로젝트 시스템 에서도 수천 줄의 코드 필요합니다.  CPS를 활용 하 여 비용을 줄일 수 온 보 딩 몇 번의 클릭을 요구에 맞게 사용자 지정할 준비가 되었습니다. 전에 합니다.  
> -   보다 간편한 유지 관리 합니다.  CPS를 활용 하 여 실제 시나리오를 유지 관리 하기만 하면 됩니다.  프로젝트 시스템 인프라의 모든 유지를 처리 합니다.  
>   
>  대상 버전의 Visual Studio 2013 보다 오래 된 Visual Studio를 해야 하는 경우 Visual Studio 확장에서 CPS를 활용 하 수 없습니다.  있는 경우이 연습에서는 시작 하는 것이 좋습니다.  
  
 이 연습에서는 프로젝트 파일 이름 확장명.myproj 있는 프로젝트 형식을 만드는 방법을 보여 줍니다. 이 연습에서는 기존 Visual C\# 프로젝트 시스템에서 차용 합니다.  
  
> [!NOTE]
>  전체 언어 프로젝트 시스템의 종단 간 샘플을에 IronPython 샘플 심층 분석을 참조 하십시오. [VSSDK 샘플](../misc/vssdk-samples.md)합니다.  
  
 이 연습에서는 이러한 작업을 수행 하는 방법에 설명 합니다.  
  
-   기본 프로젝트 형식을 만듭니다.  
  
-   기본 프로젝트 템플릿을 만듭니다.  
  
-   Visual Studio 프로젝트 템플릿을 등록 합니다.  
  
-   열어 프로젝트 인스턴스를 만들기는 **새 프로젝트** 대화 상자와 템플릿을 사용 하 여 합니다.  
  
-   프로젝트 시스템에 대 한 프로젝트 팩터리를 만듭니다.  
  
-   프로젝트 시스템에 대 한 프로젝트 노드를 만듭니다.  
  
-   프로젝트 시스템에 대 한 사용자 지정 아이콘을 추가 합니다.  
  
-   기본 템플릿 매개 변수 대체를 구현 합니다.  
  
## 사전 요구 사항  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하세요.  
  
 또한 소스 코드를 다운로드 해야는 [프로젝트에 대 한 관리 되는 패키지 프레임 워크](http://mpfproj12.codeplex.com/)합니다. 만들 것인지 솔루션에 액세스할 수 있는 위치에 파일을 추출 합니다.  
  
## 기본 프로젝트 형식 만들기  
 라는 C\# VSIX 프로젝트를 만듭니다 **SimpleProject**합니다. \(**파일, 새로 만들기, 프로젝트** 차례로 **C\#, 확장, Visual Studio 패키지**\). Visual Studio 패키지 프로젝트 항목 템플릿을 추가 \(솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 \/ 새 항목**, 이동한 다음 **확장성 \/ Visual Studio 패키지**\). 파일 이름을 **SimpleProjectPackage**합니다.  
  
## 기본 프로젝트 템플릿 만들기  
 이제 새.myproj 프로젝트 형식을 구현 하는 VSPackage이 기본 수정할 수 있습니다. .Myproj 프로젝트 유형을 기반으로 하는 프로젝트를 만들려면 Visual Studio는 어떤 파일, 리소스 및 새 프로젝트에 추가에 대 한 참조는 그대로 유지 알아야 합니다. 이 정보를 제공 하려면 프로젝트 파일을 프로젝트 템플릿 폴더에 저장 합니다. 사용자는.myproj 프로젝트를 사용 하 여 프로젝트를 만들려면, 새 프로젝트에 파일 복사 됩니다.  
  
#### 기본 프로젝트 서식 파일을 만들려면  
  
1.  다른 하나는 프로젝트에 3 개의 폴더 추가: **Templates\\Projects\\SimpleProject**합니다. \(에서 **솔루션 탐색기**, 를 마우스 오른쪽 단추로 클릭는 **SimpleProject** 프로젝트 노드를 가리키는 **추가**, 를 클릭 하 고 **새 폴더**. 폴더 이름을 `Templates`합니다. 에 **템플릿** 폴더에서 라는 폴더를 추가 `Projects`합니다. 에 **프로젝트** 폴더에서 라는 폴더를 추가 `SimpleProject`.\)  
  
2.  에 **Projects\\SimpleProject** 폴더 명명 된 아이콘 파일을 추가할 `SimpleProject.ico`합니다. 클릭할 때 **추가**, 아이콘 편집기가 열립니다.  
  
3.  구별 되는 아이콘을 확인 합니다. 이 아이콘에 표시 됩니다는 **새 프로젝트** 자습서의 뒷부분에 나오는 대화 상자입니다.  
  
     ![간단한 프로젝트 아이콘](~/docs/extensibility/media/simpleprojicon.png "SimpleProjIcon")  
  
4.  아이콘을 저장 하 고 아이콘 편집기를 닫습니다.  
  
5.  에 **Projects\\SimpleProject** 폴더를 추가 **클래스** 이라는 항목이 `Program.cs`합니다.  
  
6.  기존 코드를 다음 줄으로 바꿉니다.  
  
    ```c#  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
  
    namespace $nameSpace$  
    {  
        public class $className$  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
    > [!IMPORTANT]
    >  Program.cs 코드;의 최종 형식을 아닙니다. 대체 매개 변수는 이후 단계에서 다루지 것입니다. 표시 될 수 있습니다 컴파일 오류, 하지만 하는 동안 파일의 **빌드 작업** 는 **콘텐츠**, 를 구축 하 고 프로젝트를 정상적으로 실행 해야 합니다.  
  
1.  파일을 저장합니다.  
  
2.  AssemblyInfo.cs 파일을 복사는 **속성** 폴더는 **Projects\\SimpleProject** 폴더입니다.  
  
3.  에 **Projects\\SimpleProject** 이라는 XML 파일을 추가 하는 폴더 `SimpleProject.myproj`합니다.  
  
    > [!NOTE]
    >  이 유형의 모든 프로젝트에 대 한 파일 이름 확장명.myproj입니다. 변경 하려는 경우 변경 해야 everywhere 연습에서 설명 합니다.  
  
4.  기존 콘텐츠를 다음 줄으로 바꿉니다.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
        <SchemaVersion>2.0</SchemaVersion>  
        <ProjectGuid></ProjectGuid>  
        <OutputType>Exe</OutputType>  
        <RootNamespace>MyRootNamespace</RootNamespace>  
        <AssemblyName>MyAssemblyName</AssemblyName>  
        <EnableUnmanagedDebugging>false</EnableUnmanagedDebugging>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)' == 'Debug' ">  
        <DebugSymbols>true</DebugSymbols>  
        <OutputPath>bin\Debug\</OutputPath>  
      </PropertyGroup>  
      <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">  
        <DebugSymbols>false</DebugSymbols>  
        <OutputPath>bin\Release\</OutputPath>  
      </PropertyGroup>  
      <ItemGroup>  
        <Reference Include="mscorlib" />  
        <Reference Include="System" />  
        <Reference Include="System.Data" />  
        <Reference Include="System.Xml" />  
      </ItemGroup>  
      <ItemGroup>  
        <Compile Include="AssemblyInfo.cs">  
          <SubType>Code</SubType>  
        </Compile>  
        <Compile Include="Program.cs">  
          <SubType>Code</SubType>  
        </Compile>  
      </ItemGroup>  
      <Import Project="$(MSBuildBinPath)\Microsoft.CSharp.targets" />  
    </Project>  
    ```  
  
5.  파일을 저장합니다.  
  
6.  에 **속성** 창의 설정는 **빌드 작업** AssemblyInfo.cs, Program.cs, SimpleProject.ico, 및를 SimpleProject.myproj **콘텐츠**, 설정 및 해당 **VSIX에 포함** 속성을 **True**합니다.  
  
 이 프로젝트 템플릿은 기본 Visual C\# 프로젝트는 디버그 구성 및 릴리스 구성을를 설명 합니다. 두 소스 파일, AssemblyInfo.cs 및 Program.cs 및 몇 가지 어셈블리 프로젝트에 대 한 참조입니다. 템플릿에서 프로젝트를 만들면 ProjectGuid 값은 새 GUID로 자동 교체 됩니다.  
  
 **솔루션 탐색기**, 확장 된 **템플릿** 폴더는 다음과 같이 표시 됩니다.  
  
 템플릿  
  
 프로젝트  
  
 SimpleProject  
  
 AssemblyInfo.cs  
  
 Program.cs  
  
 SimpleProject.ico  
  
 SimpleProject.myproj  
  
## 기본 프로젝트 팩터리 만들기  
 Visual Studio 프로젝트 템플릿 폴더의 위치를 알려야 합니다. 이렇게 하려면 VSPackage를 빌드할 때 템플릿 위치를 시스템 레지스트리에 기록 됩니다 있도록 프로젝트 팩터리를 구현 하는 VSPackage 클래스에 특성을 추가 합니다. 프로젝트 팩터리 GUID로 식별 되는 기본 프로젝트 팩터리를 만들어 시작 합니다. 사용 된 <xref:Microsoft.VisualStudio.Shell.ProvideProjectFactoryAttribute> 프로젝트 팩터리 SimpleProjectPackage 클래스에 연결 하는 특성입니다.  
  
#### 기본 프로젝트 팩터리를 만들기  
  
1.  SimpleProjectPackageGuids.cs 코드 편집기에서 엽니다.  
  
2.  프로젝트 팩터리의 Guid 만들기 \(에 **도구** 메뉴 클릭 **GUID 만들기**\), 하거나 다음 예제에서를 사용 합니다. Guid는 SimpleProjectPackageGuids 클래스에 추가 합니다. Guid는 GUID 형식 및 문자열 형식 모두에 있어야 합니다. 결과 코드는 다음 예제와 비슷해야 합니다.  
  
    ```  
    static class SimpleProjectPackageGuids  
    {  
        public const string guidSimpleProjectPkgString =   
            "96bf4c26-d94e-43bf-a56a-f8500b52bfad";  
        public const string guidSimpleProjectCmdSetString =   
            "72c23e1d-f389-410a-b5f1-c938303f1391";  
        public const string guidSimpleProjectFactoryString =   
            "471EC4BB-E47E-4229-A789-D1F5F83B52D4";  
  
        public static readonly Guid guidSimpleProjectCmdSet =   
            new Guid(guidSimpleProjectCmdSetString);  
        public static readonly Guid guidSimpleProjectFactory =   
            new Guid(guidSimpleProjectFactoryString);  
    }  
    ```  
  
3.  클래스 맨 위에 추가 **SimpleProject** 라는 폴더 `SimpleProjectFactory.cs`합니다.  
  
4.  다음 코드를 추가 문을 사용 하 여:  
  
    ```  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio.Shell;  
    ```  
  
5.  SimpleProjectFactory 클래스에는 Guid 특성을 추가 합니다. 특성의 값은 새 프로젝트 팩터리 GUID.  
  
    ```  
    [Guid(SimpleProjectGuids.guidSimpleProjectFactoryString)]  
    class SimpleProjectFactory  
    {  
    }  
    ```  
  
 이제 프로젝트 템플릿을 등록할 수 있습니다.  
  
#### 프로젝트 템플릿을 등록 하려면  
  
1.  SimpleProjectPackage.cs, 추가 된 <xref:Microsoft.VisualStudio.Shell.ProvideProjectFactoryAttribute> SimpleProjectPackage 클래스에 특성을 다음과 같이 합니다.  
  
    ```  
    [ProvideProjectFactory(    typeof(SimpleProjectFactory),     "Simple Project",   
        "Simple Project Files (*.myproj);*.myproj", "myproj", "myproj",   
        @"Templates\Projects\SimpleProject",     LanguageVsTemplate = "SimpleProject")]  
    [Guid(SimpleProjectGuids.guidSimpleProjectPkgString)]  
    public sealed class SimpleProjectPackage : Package  
    ```  
  
2.  솔루션을 다시 작성 하 고 오류 없이 빌드되는지 확인 합니다.  
  
     프로젝트 템플릿을 등록 다시 작성 합니다.  
  
 매개 변수 `defaultProjectExtension` 및 `possibleProjectExtensions` 프로젝트 파일 이름 확장명 \(.myproj\)으로 설정 됩니다.`projectTemplatesDirectory` 매개 변수는 템플릿 폴더의 상대 경로를 설정 합니다. 빌드 중에,이 경로 전체 빌드를로 변환 되며 프로젝트 시스템을 등록 하는 레지스트리에 추가 합니다.  
  
## 템플릿 등록 테스트  
 템플릿 등록 하면 Visual Studio 프로젝트 템플릿 폴더의 위치 Visual Studio 템플릿 이름 및 아이콘을 표시할 수 있도록는 **새 프로젝트** 대화 상자입니다.  
  
#### 템플릿 등록을 테스트 하려면  
  
1.  F5 키를 눌러 Visual Studio의 실험적 인스턴스를 디버깅을 시작 합니다.  
  
2.  실험적 인스턴스를 새로 만든 프로젝트 형식의 새 프로젝트를 만듭니다. 에 **새 프로젝트** 대화 상자, 표시 되어야 **SimpleProject** 아래 **설치 된 템플릿**합니다.  
  
 이제 프로젝트 팩터리를 등록 해야 합니다. 그러나 프로젝트를 만들 아직 없습니다. 프로젝트 패키지 및 프로젝트 팩터리를 만들고 프로젝트를 초기화할 함께 작동 합니다.  
  
## 관리 되는 패키지 프레임 워크 코드를 추가 합니다.  
 프로젝트 패키지와 프로젝트 팩터리 간의 연결을 구현 합니다.  
  
-   관리 되는 패키지 프레임 워크에 대 한 소스 코드 파일을 가져옵니다.  
  
    1.  SimpleProject 프로젝트 언로드 \(에서 **솔루션 탐색기**, 프로젝트 노드를 선택 하 고 상황에 맞는 메뉴에서 클릭 **프로젝트 언로드**.\) 및 XML 편집기에서 프로젝트 파일을 엽니다.  
  
    2.  \(바로 위의 \< 가져오기 \> 블록\)에서 프로젝트 파일에 다음 블록을 추가 합니다. ProjectBasePath 방금 다운로드 한 패키지 프레임 워크 관리 코드에서 ProjectBase.files 파일의 위치를 설정 합니다. 경로 이름에 백슬래시를 추가 해야 할 수 있습니다. 이렇게 하지 않으면 프로젝트는 관리 되는 패키지 프레임 워크 코드를 찾는 실패할 수 있습니다.  
  
        ```  
        <PropertyGroup>  
             <ProjectBasePath>your path here\</ProjectBasePath>  
             <RegisterWithCodebase>true</RegisterWithCodebase>  
          </PropertyGroup>  
          <Import Project="$(ProjectBasePath)\ProjectBase.Files" />  
        ```  
  
        > [!IMPORTANT]
        >  경로의 끝에 백슬래시를 잊지 마십시오.  
  
    3.  프로젝트를 다시 로드 합니다.  
  
    4.  다음 어셈블리에 대한 참조를 추가합니다.  
  
        -   Microsoft.VisualStudio.Designer.Interfaces \(\< VSSDK 설치 \> \\VisualStudioIntegration\\Common\\Assemblies\\v2.0\)에서  
  
        -   WindowsBase  
  
        -   Microsoft.Build.Tasks.v4.0  
  
#### 프로젝트 팩터리를 초기화 합니다.  
  
1.  SimpleProjectPackage.cs 파일에서 다음 추가 `using` 문입니다.  
  
    ```  
    using Microsoft.VisualStudio.Project;  
    ```  
  
2.  파생 된 `SimpleProjectPackage` 클래스에서 `Microsoft.VisualStudio.Package.ProjectPackage`합니다.  
  
    ```  
    public sealed class SimpleProjectPackage : ProjectPackage  
    ```  
  
3.  프로젝트 팩터리를 등록 합니다. 다음 줄을 추가 하는 `SimpleProjectPackage.Initialize` 메서드 바로 뒤 `base.Initialize`합니다.  
  
    ```  
    base.Initialize();  
    this.RegisterProjectFactory(new SimpleProjectFactory(this));  
    ```  
  
4.  추상 속성을 구현 `ProductUserContext`:  
  
    ```c#  
    public override string ProductUserContext  
        {  
            get { return ""; }  
    }  
    ```  
  
5.  SimpleProjectFactory.cs에서 다음 추가 `using` 문을 기존 `using` 문입니다.  
  
    ```  
    using Microsoft.VisualStudio.Project;  
    ```  
  
6.  파생 된 `SimpleProjectFactory` 클래스에서 `ProjectFactory`합니다.  
  
    ```  
    class SimpleProjectFactory : ProjectFactory  
    ```  
  
7.  다음 더미 메서드를 추가 `SimpleProjectFactory` 클래스입니다. 이후 섹션에서이 메서드를 구현 합니다.  
  
    ```  
    protected override ProjectNode CreateProject()  
    {  
        return null;  
    }  
    ```  
  
8.  다음 필드 및 생성자에 추가 된 `SimpleProjectFactory` 클래스입니다. 이 `SimpleProjectPackage` 참조 설정 서비스 공급자 사이트에서 사용할 수 있도록 개인 필드에 캐시 됩니다.  
  
    ```  
    private SimpleProjectPackage package;  
  
    public SimpleProjectFactory(SimpleProjectPackage package)  
        : base(package)  
    {  
        this.package = package;  
    }  
    ```  
  
9. 솔루션을 다시 작성 하 고 오류 없이 빌드되는지 확인 합니다.  
  
## 테스트 프로젝트 팩터리 구현  
 프로젝트 팩터리 구현을 위해 생성자를 호출 하는지 테스트 합니다.  
  
#### 프로젝트 팩터리 구현을 테스트 하려면  
  
1.  다음 줄에 중단점을 설정 SimpleProjectFactory.cs 파일에는 `SimpleProjectFactory` 생성자입니다.  
  
    ```  
    this.package = package;  
    ```  
  
2.  F5 키를 눌러 Visual Studio의 실험적 인스턴스를 시작 합니다.  
  
3.  실험적 인스턴스에서 새 프로젝트 만들기를 시작 합니다. 에 **새 프로젝트** 고 대화 상자를 선택 된 SimpleProject 프로젝트 형식을 클릭 한 다음 **확인**합니다. 중단점에서 실행이 중지됩니다.  
  
4.  중단점의 선택을 취소 하 고 디버깅을 중지 합니다. 우리를 만들지 않은 프로젝트 노드 아직 이후 프로젝트 생성 코드는 여전히 예외가 발생 합니다.  
  
## 프로젝트 노드 클래스를 확장합니다.  
 이제 구현할 수는 `SimpleProjectNode` 클래스에서 파생 되는 `ProjectNode` 클래스입니다.`ProjectNode` 기본 클래스는 프로젝트 만들기의 다음 작업을 처리 합니다.  
  
-   새 프로젝트 폴더에 SimpleProject.myproj, 프로젝트 템플릿 파일을 복사합니다. 복사본에 입력 된 이름에 따라 이름이 **새 프로젝트** 대화 상자입니다.`ProjectGuid` 속성 값이 새 GUID로 대체 됩니다.  
  
-   SimpleProject.myproj, 프로젝트 템플릿 파일의 MSBuild 요소를 트래버스하 고 찾고 `Compile` 요소입니다. 각 `Compile` 대상 파일을 새 프로젝트 폴더에 파일을 복사 합니다.  
  
 파생 된 `SimpleProjectNode` 클래스는 이러한 작업을 처리 합니다.  
  
-   프로젝트 및 파일 노드에 대 한 아이콘을 사용 하면 **솔루션 탐색기** 생성 또는 선택 하도록 합니다.  
  
-   추가 프로젝트 템플릿 매개 변수 대체를를 지정할 수 있습니다.  
  
#### 프로젝트 노드 클래스를 확장 하려면  
  
1.  
  
2.  라는 클래스를 추가 `SimpleProjectNode.cs`합니다.  
  
3.  기존 코드를 다음 코드로 바꿉니다.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using Microsoft.VisualStudio.Project;  
  
    namespace SimpleProject  
    {  
        public class SimpleProjectNode : ProjectNode  
        {  
            private SimpleProjectPackage package;  
  
            public SimpleProjectNode(SimpleProjectPackage package)  
            {  
                this.package = package;  
            }  
            public override Guid ProjectGuid  
            {  
                get { return SimpleProjectGuids.guidSimpleProjectFactory; }  
            }  
            public override string ProjectType  
            {  
                get { return "SimpleProjectType"; }  
            }  
  
            public override void AddFileFromTemplate(  
                string source, string target)  
            {  
                this.FileTemplateProcessor.UntokenFile(source, target);  
                this.FileTemplateProcessor.Reset();  
            }  
        }  
    }  
    ```  
  
 이 `SimpleProjectNode` 다음 재정의 된 메서드를 포함 하는 클래스를 구현 합니다.  
  
-   `ProjectGuid`, 프로젝트 팩터리 GUID를 반환 하는 합니다.  
  
-   `ProjectType`, 프로젝트 형식의 지역화 된 이름을 반환 합니다.  
  
-   `AddFileFromTemplate`, 를 대상 프로젝트에 템플릿 폴더에서 선택한 파일을 복사 하 합니다. 이 메서드는 이후 섹션에서 추가로 구현 됩니다.  
  
 `SimpleProjectNode` 생성자 마찬가지로 `SimpleProjectFactory` 생성자 캐시는 `SimpleProjectPackage` 나중에 사용할 개인 필드에 대 한 참조입니다.  
  
 연결 하는 `SimpleProjectFactory` 클래스는 `SimpleProjectNode` 클래스를 인스턴스화해야 합니다. 새 `SimpleProjectNode` 에 `SimpleProjectFactory.CreateProject` 메서드 하 고 나중에 사용할 개인 필드에 캐시 합니다.  
  
#### 노드 클래스와 프로젝트 팩터리 클래스를 연결 하려면  
  
1.  SimpleProjectFactory.cs 파일에서 다음 추가 `using` 문:  
  
    ```  
    using IOleServiceProvider =    Microsoft.VisualStudio.OLE.Interop.IServiceProvider;  
    ```  
  
2.  대체는 `SimpleProjectFactory.CreateProject` 메서드에 다음 코드를 사용 하 여 합니다.  
  
    ```  
    protected override ProjectNode CreateProject()  
    {  
        SimpleProjectNode project = new SimpleProjectNode(this.package);  
  
        project.SetSite((IOleServiceProvider)        ((IServiceProvider)this.package).GetService(            typeof(IOleServiceProvider)));  
        return project;  
    }  
    ```  
  
3.  솔루션을 다시 작성 하 고 오류 없이 빌드되는지 확인 합니다.  
  
## 프로젝트 노드 클래스를 테스트합니다.  
 테스트 프로젝트는 팩터리 프로젝트 계층 구조를 만들 있는지 확인 합니다.  
  
#### 프로젝트 노드 클래스를 테스트 하려면  
  
1.  F5 키를 눌러 디버깅을 시작합니다. 새 SimpleProject 실험적 인스턴스를 만듭니다.  
  
2.  Visual Studio 프로젝트는 프로젝트를 만드는 팩터리를 호출 해야 합니다.  
  
3.  Visual Studio의 실험적 인스턴스를 닫습니다.  
  
## 사용자 지정 프로젝트 노드 아이콘 추가  
 이전 섹션에서 프로젝트 노드 아이콘은 기본 아이콘입니다. 사용자 지정 아이콘을 변경할 수 있습니다.  
  
#### 사용자 지정 프로젝트 노드 아이콘을 추가 하려면  
  
1.  에 **리소스** 폴더 SimpleProjectNode.bmp 이라는 비트맵 파일을 추가 합니다.  
  
2.  에 **속성** windows, 16 x 16 픽셀에 비트맵을 줄입니다. 구별 되는 비트맵을 확인 합니다.  
  
     ![간단한 프로젝트 명령](~/docs/extensibility/media/simpleprojprojectcomm.png "SimpleProjProjectComm")  
  
3.  에 **속성** 창에서 변경 된 **빌드 작업** 비트맵의 **포함 리소스**합니다.  
  
4.  SimpleProjectNode.cs에서 다음 추가 `using` 문:  
  
    ```  
    using System.Drawing;  
    using System.Windows.Forms;  
    ```  
  
5.  다음과 같은 정적 필드와 생성자에 추가 된 `SimpleProjectNode` 클래스입니다.  
  
    ```  
    private static ImageList imageList;  
  
    static SimpleProjectNode()  
    {  
        imageList =        Utilities.GetImageList(            typeof(SimpleProjectNode).Assembly.GetManifestResourceStream(                "SimpleProject.Resources.SimpleProjectNode.bmp"));  
    }  
    ```  
  
6.  다음 속성의 시작 부분에 추가 된 `SimpleProjectNode` 클래스입니다.  
  
    ```  
    internal static int imageIndex;  
       public override int ImageIndex  
       {  
           get { return imageIndex; }  
       }  
    ```  
  
7.  인스턴스 생성자를 다음 코드로 바꿉니다.  
  
    ```  
    public SimpleProjectNode(SimpleProjectPackage package)  
    {  
        this.package = package;  
  
        imageIndex = this.ImageHandler.ImageList.Images.Count;  
  
        foreach (Image img in imageList.Images)  
        {  
            this.ImageHandler.AddImage(img);  
        }  
    }  
    ```  
  
 정적 생성 하는 동안 `SimpleProjectNode` 어셈블리 매니페스트 리소스에서 프로젝트 노드 비트맵을 검색 하 고 나중에 사용할 개인 필드에 캐시 합니다. 구문이 <xref:System.Reflection.Assembly.GetManifestResourceStream%2A> 이미지 경로입니다. 어셈블리에 포함 된 매니페스트 리소스의 이름을 보려면는 <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> 메서드. 이 메서드는 적용 되는 경우는 `SimpleProject` 어셈블리, 결과가 다음과 같아야 합니다.  
  
-   SimpleProject.Resources.resources  
  
-   VisualStudio.Project.resources  
  
-   SimpleProject.VSPackage.resources  
  
-   Resources.imagelis.bmp  
  
-   Microsoft.VisualStudio.Project.DontShowAgainDialog.resources  
  
-   Microsoft.VisualStudio.Project.SecurityWarningDialog.resources  
  
-   SimpleProject.Resources.SimpleProjectNode.bmp  
  
 인스턴스 생성 도중는 `ProjectNode` 기본 클래스를 있는 Resources\\imagelis.bmp에서 포함 된 자주 사용 되는 16 x 16 비트맵 Resources.imagelis.bmp를 로드 합니다. 이 비트맵 목록을 사용할 수 있도록 `SimpleProjectNode` ImageHandler.ImageList으로 합니다.`SimpleProjectNode` 목록에 프로젝트 노드 비트맵을 추가합니다. 나중에 사용할 공용의 값으로 캐시 되는 이미지 목록에서 프로젝트 노드 비트맵의 오프셋 `ImageIndex` 속성입니다. Visual Studio 프로젝트 노드 아이콘으로 표시 하는 비트맵을 확인 하려면이 속성을 사용 합니다.  
  
## 테스트를 사용자 지정 프로젝트 노드 아이콘  
 사용자 지정 프로젝트 노드 아이콘에 있는 프로젝트 계층 구조를 만들 있는지 확인 하 여 프로젝트 팩터리의 테스트 합니다.  
  
#### 사용자 지정 프로젝트 노드 아이콘을 테스트 하려면  
  
1.  디버깅을 시작 하 고 실험적 인스턴스에서 새 SimpleProject를 만듭니다.  
  
2.  새로 만든 프로젝트에서 프로젝트 노드 아이콘으로 SimpleProjectNode.bmp 사용 되도록를 확인 합니다.  
  
     ![간단한 프로젝트 새 프로젝트 노드](~/docs/extensibility/media/simpleprojnewprojectnode.png "SimpleProjNewProjectNode")  
  
3.  코드 편집기에서 Program.cs를 엽니다. 다음 코드와 같은 소스 코드를 표시 되어야 합니다.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
  
    namespace $nameSpace$  
    {  
        public class $className$  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
     $NameSpace$ 및 $ $className 템플릿 매개 변수 새 값이 있지는 않은지 확인 합니다. 다음 섹션에서 템플릿 매개 변수 대체를 구현 하는 방법을 알아봅니다.  
  
## 템플릿 매개 변수를 대체합니다.  
 이전 단원에서 있습니다 프로젝트 템플릿을 Visual Studio와 함께 사용 하 여 등록 된 `ProvideProjectFactory` 특성입니다. 재정의 하 고 확장 하 여 기본 템플릿 매개 변수 대체를 사용 하도록 설정 하면이 방식으로 템플릿 폴더의 경로 등록 하는 중 고 `ProjectNode.AddFileFromTemplate` 클래스입니다. 자세한 내용은 [새 프로젝트 생성: 내부적으로 2 부](../extensibility/internals/new-project-generation-under-the-hood-part-two.md)을 참조하십시오.  
  
 대체 코드를 추가 `AddFileFromTemplate` 클래스입니다.  
  
#### 템플릿 매개 변수를 대체  
  
1.  SimpleProjectNode.cs 파일에서 다음 추가 `using` 문입니다.  
  
    ```  
    using System.IO;  
    ```  
  
2.  대체는 `AddFileFromTemplate` 메서드에 다음 코드를 사용 하 여 합니다.  
  
    ```  
    public override void AddFileFromTemplate(  
        string source, string target)  
    {  
        string nameSpace =   
            this.FileTemplateProcessor.GetFileNamespace(target, this);  
        string className = Path.GetFileNameWithoutExtension(target);  
  
        this.FileTemplateProcessor.AddReplace("$nameSpace$", nameSpace);  
        this.FileTemplateProcessor.AddReplace("$className$", className);  
  
        this.FileTemplateProcessor.UntokenFile(source, target);  
        this.FileTemplateProcessor.Reset();  
    }  
    ```  
  
3.  바로 뒤 메서드에서 중단점을 설정 된 `className` 대입문 합니다.  
  
 할당 문을 네임 스페이스 및 클래스 이름을 대 한 적절 한 값을 결정 합니다. 두 `ProjectNode.FileTemplateProcessor.AddReplace` 메서드 호출 이러한 새 값을 사용 하 여 해당 템플릿 매개 변수 값을 대체 합니다.  
  
## 템플릿 매개 변수 대체를 테스트합니다.  
 이제 템플릿 매개 변수 대체를 테스트할 수 있습니다.  
  
#### 템플릿 매개 변수 대체를 테스트 하려면  
  
1.  디버깅을 시작 하 고 실험적 인스턴스에서 새 SimpleProject를 만듭니다.  
  
2.  실행이 중단점에서 중지 되는 `AddFileFromTemplate` 메서드.  
  
3.  에 대 한 값을 검사는 `nameSpace` 및 `className` 매개 변수입니다.  
  
    -   `nameSpace` \\Templates\\Projects\\SimpleProject\\SimpleProject.myproj 프로젝트 템플릿 파일에 있는 \< RootNamespace \> 요소의 값이 지정 됩니다. 이 경우에 값은 "MyRootNamespace"입니다.  
  
    -   `className` 클래스 소스 파일 이름, 파일 이름 확장명 없이 값이 지정 됩니다. 이 경우 첫 번째 대상 폴더에 복사할 파일이 AssemblyInfo.cs; 따라서 className의 값은 "AssemblyInfo".  
  
4.  중단점을 제거 하 고 f5 키를 눌러 실행을 계속 합니다.  
  
     Visual Studio 프로젝트 만들기를 완료 해야 합니다.  
  
5.  코드 편집기에서 Program.cs를 엽니다. 다음 코드와 같은 소스 코드를 표시 되어야 합니다.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
  
    namespace MyRootNamespace  
    {  
        public class Program  
        {  
            static void Main(string[] args)  
            {  
                Console.WriteLine("Hello VSX!!!");  
                Console.ReadKey();  
            }  
        }  
    }  
    ```  
  
     네임 스페이스는 이제 "MyRootNamespace" 클래스 이름은 "Program"에 유의 하십시오.  
  
6.  프로젝트 디버깅을 시작 합니다. 새 프로젝트를 컴파일, 실행 및 "VSX Hello\!"을 표시 콘솔 창에서.  
  
     ![간단한 프로젝트 명령](~/docs/extensibility/media/simpleprojcommand.png "SimpleProjCommand")  
  
 지금까지 관리 되는 기본 프로젝트 시스템을 구현 했습니다.