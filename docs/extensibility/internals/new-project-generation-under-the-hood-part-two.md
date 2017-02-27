---
title: "새 프로젝트 생성: 내부적으로 2 부 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 [Visual Studio], 새 프로젝트 대화 상자"
  - "프로젝트 [Visual Studio] 새 프로젝트 생성"
ms.assetid: 73ce91d8-0ab1-4a1f-bf12-4d3c49c01e13
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# 새 프로젝트 생성: 내부적으로 2 부
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

 [새 프로젝트 생성: 깊숙한, 1 부](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md) 살펴본 방법을 **새 프로젝트** 대화 상자에 채워집니다. 선택한 있다고 가정해 보겠습니다는 **Visual C# Windows 응용 프로그램**, 작성 한는 **이름** 및 **위치** 텍스트 상자 및 확인을 클릭된 합니다.  
  
## <a name="generating-the-solution-files"></a>솔루션 파일을 생성  
 응용 프로그램 템플릿을 선택 하도록 지시 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 압축을 풀고 해당.vstemplate 파일을 열고 하 고이 파일의 XML 명령을 해석 하는 템플릿을 시작 합니다. 이러한 명령은 새로운 또는 기존 솔루션에 프로젝트 및 프로젝트 항목을 만듭니다.  
  
 서식 파일의 압축을 푼 소스 파일인.vstemplate 파일을 보유 하는 동일한 zip 폴더에서 항목 템플릿을 호출 합니다. 서식 파일을 적절 하 게 사용자 지정 하 여 새 프로젝트에 이러한 파일을 복사 합니다. 프로젝트 및 항목 템플릿 개요를 참조 하십시오. [NIB: Visual Studio 템플릿](http://msdn.microsoft.com/ko-kr/141fccaa-d68f-4155-822b-27f35dd94041)합니다.  
  
### <a name="template-parameter-replacement"></a>템플릿 매개 변수 대체  
 서식 파일을 새 프로젝트에 항목 템플릿을 복사할 때 파일을 사용자 지정 하는 문자열이 포함 된 모든 템플릿 매개 변수를 대체 합니다. 템플릿 매개 변수는 특별 한 토큰을 앞에 고 예를 들어 달러 기호 뒤 $date$입니다.  
  
 일반적인 프로젝트 항목 템플릿을 살펴보겠습니다. 추출 하 고 Program Files\Microsoft Visual Studio 8\Common7\IDE\ProjectTemplates\CSharp\Windows\1033\WindowsApplication.zip 폴더에서 Program.cs를 검토 합니다.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Windows.Forms;  
  
namespace $safeprojectname$  
{  
    static class Program  
    {  
        // source code deleted here for brevity  
    }  
}  
```  
  
 대체 단순 라는 새 Windows 응용 프로그램 프로젝트를 만드는 경우는 `$safeprojectname$` 매개 변수는 프로젝트의 이름입니다.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Windows.Forms;  
  
namespace Simple  
{  
    static class Program  
    {  
        // source code deleted here for brevity  
    }  
}  
```  
  
 템플릿 매개 변수 목록은 전체 참조 [템플릿 매개 변수](../../ide/template-parameters.md)합니다.  
  
## <a name="a-look-inside-a-vstemplate-file"></a>내부를 살펴보면서는 합니다. VSTemplate 파일  
 기본.vstemplate 파일에는이 형식  
  
```  
<VSTemplate Version="2.0.0"     xmlns="http://schemas.microsoft.com/developer/vstemplate/2005"     Type="Project">  
    <TemplateData>  
    </TemplateData>  
    <TemplateContent>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 에 대해 살펴보았습니다는 \< TemplateData> 섹션은 [새 프로젝트 생성: 깊숙한, 1 부](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md)합니다. 이 섹션에서는 태그를 사용 하는 데 문제가의 모양을 제어 하는 **새 프로젝트** 대화 상자입니다.  
  
 태그는 \< TemplateContent> 새 프로젝트 및 프로젝트 항목의 생성 제어 섹션입니다. 다음은 \< TemplateContent> files\microsoft Visual Studio 8\Common7\IDE\ProjectTemplates\CSharp\Windows\1033\WindowsApplication.zip 폴더에서 cswindowsapplication.vstemplate 파일에서 섹션입니다.  
  
```  
<TemplateContent>  
  <Project File="WindowsApplication.csproj" ReplaceParameters="true">  
    <ProjectItem ReplaceParameters="true"  
      TargetFileName="Properties\AssemblyInfo.cs">  
      AssemblyInfo.cs  
    </ProjectItem>  
    <ProjectItem TargetFileName="Properties\Resources.resx">  
      Resources.resx  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true"       TargetFileName="Properties\Resources.Designer.cs">  
      Resources.Designer.cs  
    </ProjectItem>  
    <ProjectItem TargetFileName="Properties\Settings.settings">  
      Settings.settings  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true"       TargetFileName="Properties\Settings.Designer.cs">  
      Settings.Designer.cs  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true" OpenInEditor="true">  
      Form1.cs  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true">  
      Form1.Designer.cs  
    </ProjectItem>  
    <ProjectItem ReplaceParameters="true">  
      Program.cs  
    </ProjectItem>  
  </Project>  
</TemplateContent>  
```  
  
 \< 프로젝트> 프로젝트의 생성을 제어 하는 태그와 \< ProjectItem> 태그 프로젝트 항목의 생성을 제어 합니다. ReplaceParameters 매개 변수가 true 이면 모든 템플릿 매개 변수는 프로젝트 파일 또는 항목에 서식 파일에 사용자 지정 합니다. 이 경우 모든 프로젝트 항목 사용자 지정 된, Settings.settings 제외 하 고 있습니다.  
  
 TargetFileName 매개 변수 이름 및 결과 프로젝트 파일 또는 항목의 상대 경로 지정합니다. 이 프로젝트에 대 한 폴더 구조를 만들 수 있습니다. 이 인수를 지정 하지 않으면, 프로젝트 항목의 프로젝트 항목 템플릿으로 동일한 이름을 갖습니다.  
  
 결과 Windows 응용 프로그램 폴더 구조는 다음과 같습니다.  
  
 ![SimpleSolution](../../extensibility/internals/media/simplesolution.png "SimpleSolution")  
  
 첫 번째이자 유일한 \< 프로젝트> 템플릿 읽기에서 태그:  
  
```  
<Project File="WindowsApplication.csproj" ReplaceParameters="true">  
```  
  
 이 템플릿 항목 windowsapplication.csproj를 지정 하 고 복사 함으로써 Simple.csproj 프로젝트 파일을 만들려면 새 프로젝트 템플릿은 지시 합니다.  
  
### <a name="designers-and-references"></a>디자이너 및 참조  
 속성 폴더 있고와 예상된 된 파일이 포함 된 솔루션 탐색기에서 볼 수 있습니다. 하지만 프로젝트에 대 한 내용을 참조 하 고, Resources.resx에 Resources.Designer.cs 및 form1. designer.cs Form1.cs와 같은 디자이너 파일 종속성?  생성 되 면 Simple.csproj 파일에 설정이 됩니다.  
  
 다음은 \< ItemGroup> 프로젝트 참조를 만드는 Simple.csproj에서:  
  
```  
<ItemGroup>  
    <Reference Include="System" />  
    <Reference Include="System.Data" />  
    <Reference Include="System.Deployment" />  
    <Reference Include="System.Drawing" />  
    <Reference Include="System.Windows.Forms" />  
    <Reference Include="System.Xml" />  
</ItemGroup>  
```  
  
 이 솔루션 탐색기에 표시 되는 6 개의 프로젝트 참조를 확인할 수 있습니다. 다음은 다른 섹션 \< ItemGroup>합니다. 여러 줄의 코드 명확성을 위해 삭제 되었습니다. 이 섹션에서는 Settings.Designer.cs Settings.settings에 의존 합니다.  
  
```  
<ItemGroup>  
    <Compile Include="Properties\Settings.Designer.cs">  
        <DependentUpon>Settings.settings</DependentUpon>  
    </Compile>  
</ItemGroup>  
```  
  
## <a name="see-also"></a>참고 항목  
 [새 프로젝트 생성: 내부적으로 1 부](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md)  
 [MSBuild](../../msbuild/msbuild1.md)