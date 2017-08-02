---
title: "새 프로젝트 생성: 내부적으로 2 부 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio], new project dialog
- projects [Visual Studio], new project generation
ms.assetid: 73ce91d8-0ab1-4a1f-bf12-4d3c49c01e13
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5581224b17a7b42f65b69f741f984a144d78fc26
ms.openlocfilehash: 859eeac9c2fd322dcf231e9c70fe83b92b099111
ms.lasthandoff: 04/04/2017

---
# <a name="new-project-generation-under-the-hood-part-two"></a>새 프로젝트 생성: 내부적으로 2 부
[새 프로젝트 생성: 고급, 1 부](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md) 줄이는 방법을 **새 프로젝트** 대화 상자가 채워집니다. 선택한를 가정해 보겠습니다는 **Visual C# Windows 응용 프로그램**, 입력 한는 **이름** 및 **위치** 텍스트 상자 및 확인을 클릭된 합니다.  
  
## <a name="generating-the-solution-files"></a>솔루션 파일을 생성  
 응용 프로그램 템플릿을 선택 하도록 지시 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 풀고 해당.vstemplate 파일을 엽니다 하 고이 파일에 XML 명령을 해석 하는 템플릿을 시작할 수 있습니다. 이러한 명령은 새로운 또는 기존 솔루션에 프로젝트와 프로젝트 항목을 만듭니다.  
  
 템플릿의는.vstemplate 파일을 보유 하는 동일한.zip 폴더에서 항목 템플릿 라는 소스 파일, 압축을 풉니다. 서식 파일을 그에 따라 사용자 지정 새 프로젝트에 이러한 파일을 복사 합니다. 프로젝트 및 항목 템플릿 개요를 참조 하십시오. [NIB: Visual Studio 템플릿](http://msdn.microsoft.com/en-us/141fccaa-d68f-4155-822b-27f35dd94041)합니다.  
  
### <a name="template-parameter-replacement"></a>템플릿 매개 변수를 대체  
 서식 파일을 새 프로젝트 항목 템플릿의 복사할 때 템플릿 매개 변수를 파일을 사용자 지정 하는 문자열로 바꿉니다. 템플릿 매개 변수는이 앞과 뒤에 예를 들어 달러 기호는 특수 토큰, $date $는 합니다.  
  
 일반적인 프로젝트 항목 템플릿을 살펴보겠습니다. 압축을 풀고 Program Files\Microsoft Visual Studio 8\Common7\IDE\ProjectTemplates\CSharp\Windows\1033\WindowsApplication.zip 폴더에서 Program.cs를 검사 합니다.  
  
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
  
 대체 단순 라는 새 Windows 응용 프로그램 프로젝트를 만들면는 `$safeprojectname$` 매개 변수는 프로젝트의 이름입니다.  
  
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
  
## <a name="a-look-inside-a-vstemplate-file"></a>내 보기는 합니다. VSTemplate 파일  
 기본.vstemplate 파일에 있는이 형식  
  
```  
<VSTemplate Version="2.0.0"     xmlns="http://schemas.microsoft.com/developer/vstemplate/2005"     Type="Project">  
    <TemplateData>  
    </TemplateData>  
    <TemplateContent>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 에 \<TemplateData > 섹션에서 [새 프로젝트 생성: 고급, 1 부](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md)합니다. 이 섹션의 태그는의 모양을 제어 하는 데 사용 되는 **새 프로젝트** 대화 상자.  
  
 태그는 \<TemplateContent > 새 프로젝트 및 프로젝트 항목의 생성 제어 섹션. 다음은 \<TemplateContent > files\microsoft Visual Studio 8\Common7\IDE\ProjectTemplates\CSharp\Windows\1033\WindowsApplication.zip 폴더에서 cswindowsapplication.vstemplate 파일에서 섹션.  
  
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
  
 \<프로젝트 > 태그는 프로젝트의 생성을 제어 및 \<ProjectItem > 태그는 프로젝트 항목의 생성을 제어 합니다. 매개 변수 ReplaceParameters true 이면 모든 템플릿 매개 변수는 프로젝트 파일 또는 항목에 서식 파일에 사용자 지정 합니다. 이 경우 모든 프로젝트 항목 사용자 지정 된, Settings.settings 제외 하 고 있습니다.  
  
 TargetFileName 매개 변수는 생성 되는 프로젝트 파일 또는 항목의 상대 경로 이름을 지정합니다. 이 프로젝트에 대 한 폴더 구조를 만들 수 있습니다. 이 인수를 지정 하지 않으면 하는 경우 프로젝트 항목이 프로젝트 항목 템플릿 동일한 이름을 갖습니다.  
  
 결과 Windows 응용 프로그램 폴더 구조는 다음과 같습니다.  
  
 ![SimpleSolution](~/docs/extensibility/internals/media/simplesolution.png "SimpleSolution")  
  
 첫 번째이자 유일한 \<프로젝트 > 태그에 서식 파일 읽기:  
  
```  
<Project File="WindowsApplication.csproj" ReplaceParameters="true">  
```  
  
 이 템플릿 항목 windowsapplication.csproj를 지정 하 고 복사 함으로써 Simple.csproj 프로젝트 파일을 만들려면 새 프로젝트 템플릿은 지시 합니다.  
  
### <a name="designers-and-references"></a>디자이너 및 참조  
 속성 폴더 표시 되며 예상 파일이 솔루션 탐색기에서 볼 수 있습니다. 하지만 프로젝트에 대 한 내용을 참조 하 고 디자이너 파일 종속성에 Resources.resx, Resources.Designer.cs 및 Form1.cs에 form1. designer.cs 등?  이러한 속성은 설정 Simple.csproj 파일에서 생성 될 경우.  
  
 다음은 \<ItemGroup > 프로젝트 참조를 만드는 Simple.csproj에서:  
  
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
  
 이 솔루션 탐색기에 표시 되는 6 개의 프로젝트 참조를 확인할 수 있습니다. 다음에서 다른 섹션은 \<ItemGroup >. 코드의 줄 수를 이해 하기 쉽도록 삭제 되었습니다. 이 섹션에서는 Settings.Designer.cs Settings.settings에 의존 합니다.  
  
```  
<ItemGroup>  
    <Compile Include="Properties\Settings.Designer.cs">  
        <DependentUpon>Settings.settings</DependentUpon>  
    </Compile>  
</ItemGroup>  
```  
  
## <a name="see-also"></a>참고 항목  
 [새 프로젝트 생성: 내부 살펴보기, 1부](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md)  
 [MSBuild](../../msbuild/msbuild.md)
