---
title: "새 프로젝트 생성: 내부적으로 1 부 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio], new project dialog
- projects [Visual Studio], new project generation
ms.assetid: 66778698-0258-467d-8b8b-c351744510eb
caps.latest.revision: "29"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: efe08d9e23f1a77fd68df2bdba4389e7b7955b11
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="new-project-generation-under-the-hood-part-one"></a>새 프로젝트 생성: 내부적으로 1 부
사용자 고유의 프로젝트 형식을 만드는 방법에 대 한 것? 새 프로젝트를 만들 때 실제로 일어나 궁금해? 기본적인 이해 보아 하 고 실제로 실행 중인 참조 살펴보겠습니다.  
  
 Visual Studio 좌표 여러 작업이 있습니다.  
  
-   모든 사용 가능한 프로젝트 형식 트리가 표시 됩니다.  
  
-   각 프로젝트 형식에 대 한 응용 프로그램 템플릿 목록을 표시 하 고 하나를 선택할 수 있습니다.  
  
-   프로젝트 이름 및 경로 등과 같은 응용 프로그램에 대 한 프로젝트 정보를 수집합니다.  
  
-   프로젝트 팩터리에 로그온이 정보를 전달합니다.  
  
-   현재 솔루션의 프로젝트 항목 및 폴더를 생성합니다.  
  
## <a name="the-new-project-dialog-box"></a>새 프로젝트 대화 상자  
 모든 새 프로젝트에 대 한 프로젝트 형식을 선택 하는 경우 시작 합니다. 클릭 하 여 시작 하겠습니다 **새 프로젝트** 에 **파일** 메뉴. **새 프로젝트** 대화 상자가 나타나면을 다음과 같이 결과 보기:  
  
 ![새 프로젝트 대화 상자](../../extensibility/internals/media/newproject.gif "새 프로젝트")  
  
 자세히 살펴보겠습니다. **프로젝트 형식** 트리에 나열 다양 한 프로젝트 형식을 만들 수 있습니다. 같은 프로젝트 형식을 선택 하면 **Visual C# Windows**를 시작 하기 위한 응용 프로그램 템플릿 목록이 표시 됩니다. **Visual Studio 설치 되어 있는 템플릿** Visual Studio가 설치 되어 있고 컴퓨터의 모든 사용자에 게 사용할 수 있습니다. 만들거나 수집 하는 새 템플릿을 추가할 수 **내 템플릿** 에 사용할 수 있습니다.  
  
 템플릿을 선택 하면 **Windows 응용 프로그램**, 대화 상자에서,이 경우 응용 프로그램 종류에 대 한 설명을 표시 **Windows 사용자 인터페이스를 사용 하 여 응용 프로그램 만들기에 대 한 프로젝트**합니다.  
  
 맨 아래에 **새 프로젝트** 대화 상자에서 추가 정보를 수집 하는 여러 컨트롤 표시 됩니다. 표시 컨트롤 프로젝트 형식에 따라 달라 지지만 프로젝트가 포함 되어 일반적으로 **이름** 텍스트 상자는 **위치** 텍스트 상자 및 관련 **찾아보기** 단추 및는 **솔루션 이름** 텍스트 상자 및 관련 **솔루션용 디렉터리 만들기** 확인란 합니다.  
  
## <a name="populating-the-new-project-dialog-box"></a>새 프로젝트 대화 상자 채우기  
 여기서는 **새 프로젝트** 대화 상자에서 해당 정보를 가져오도록? 여기서 작업을 더 이상 사용 되지 둘 중 하나에 두 가지 메커니즘 있습니다. **새 프로젝트** 대화 상자 결합 하 고 두 메커니즘은 모두에서 가져온 정보를 표시 합니다.  
  
 시스템 레지스트리 항목 및.vsdir 파일을 사용 하는 이전 (deprecated) 됩니다. 이 메커니즘에는 Visual Studio에 열려 있을 때 실행 됩니다. 최신 메서드.vstemplate 파일을 사용합니다. Visual Studio 초기화 될 때 예를 들어,를 실행 하 여이 메커니즘 실행  
  
```  
devenv /setup  
```  
  
 또는  
  
```  
devenv /installvstemplates  
```  
  
### <a name="project-types"></a>프로젝트 형식  
 이름과 위치는 **프로젝트 형식** 와 같은 루트 노드의 **Visual C#** 및 **다른 언어**, 시스템 레지스트리 항목에 의해 결정 됩니다. 자식 노드의 조직와 같은 **데이터베이스** 및 **스마트 장치**, 해당.vstemplate 파일을 포함 하는 폴더 계층 구조를 반영 합니다. 보겠습니다 루트 노드를 먼저 확인 합니다.  
  
#### <a name="project-type-root-nodes"></a>프로젝트 유형 루트 노드  
 때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 은 시스템 레지스트리 키를 빌드하고의 루트 노드 이름을 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\NewProjectTemplates\TemplateDirs의 하위 키 트래버스할 초기화는 **프로젝트형식** 트리 합니다. 이 정보는 나중에 캐시 됩니다. TemplateDirs 살펴보고\\{FAE04EC1-301F-11D3-BF4B-00C04F79EFBC} \\ /1 키입니다. 각 항목에는 VSPackage GUID입니다. 하위 키의 이름 (/ 1)은 무시 되 고 존재 임을 나타냅니다. 하지만 **프로젝트 형식** 루트 노드. 루트 노드에 있을 수의 모양을 제어 하는 여러 하위 키의 **프로젝트 형식** 트리 합니다. 그 중 일부에 대해 살펴보겠습니다.  
  
##### <a name="default"></a>(기본값)  
 루트 노드 이름을 지정 하는 지역화 된 문자열의 리소스 ID입니다. 문자열 리소스는 위성 DLL VSPackage GUID에 의해 선택에 있습니다.  
  
 예제에서 VSPackage GUID는  
  
 {FAE04EC1-301F-11D3-BF4B-00C04F79EFBC}  
  
 루트 노드의 리소스 ID (기본값) 및 (/ 1)은 #2345  
  
 주변 패키지 키의 GUID를 조회 하 고 SatelliteDll 하위 키를 검사 하는 경우에 문자열 리소스를 포함 하는 어셈블리의 경로 찾을 수 있습니다.  
  
 \<Visual Studio 설치 경로 > \VC#\VCSPackages\1033\csprojui.dll  
  
 이 확인 하려면 파일 탐색기를 열고 및 Visual Studio 디렉터리 csprojui.dll 끌어... 문자열 테이블 리소스 #2345 캡션을 있는지를 보여 줍니다 **Visual C#**합니다.  
  
##### <a name="sortpriority"></a>SortPriority  
 루트 노드는 위치를 결정은 **프로젝트 형식** 트리 합니다.  
  
 SortPriority REG_DWORD 0x00000014 (20)  
  
 우선 순위 번호가 작을수록 트리에 높을수록 위치입니다.  
  
##### <a name="developeractivity"></a>DeveloperActivity  
 이 하위 키가 있는 경우 루트 노드의 위치 개발자 설정 대화 상자에 의해 제어 됩니다. 예를 들면 다음과 같습니다.  
  
 DeveloperActivity REG_SZ VC #  
  
 나타냅니다 Visual C# 루트 노드 Visual Studio에 대해 설정 된 경우 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 개발 합니다. 그렇지 않으면의 자식 노드로 됩니다 **다른 언어**합니다.  
  
##### <a name="folder"></a>폴더  
 이 하위 키가 있는 경우 루트 노드는 지정한 폴더의 자식 노드를 됩니다. 해당 키 아래에서 가능한 폴더 목록이 표시 됩니다.  
  
 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\11.0\NewProjectTemplates\PseudoFolders  
  
 예를 들어 데이터베이스 프로젝트 항목에 PseudoFolders의 기타 프로젝트 형식 항목과 일치 하는 폴더 키입니다. 따라서는 **프로젝트 형식** 트리에서 **데이터베이스 프로젝트** 의 자식 노드로 사용할 **기타 프로젝트 형식**합니다.  
  
#### <a name="project-type-child-nodes-and-vstdir-files"></a>프로젝트 유형 자식 노드 및.vstdir 파일  
 자식 노드 위치는 **프로젝트 형식** 트리 ProjectTemplates 폴더에 폴더 계층 구조를 따릅니다. 컴퓨터 템플릿에 (**Visual Studio 설치 되어 있는 템플릿**), 일반적인 위치는 files\microsoft Visual Studio 14.0\Common7\IDE\ProjectTemplates\ 및 사용자 서식 파일 (**내 템플릿**), 일반적인 위치는 documents\visual Studio 14.0\Templates\ProjectTemplates\\합니다. 이 두 위치에서 폴더 계층 구조를 만드는 병합 되 고 **프로젝트 형식** 트리 합니다.  
  
 C# 개발자 설정 사용 하 여 Visual Studio에 대 한는 **프로젝트 형식** 트리 다음과 같습니다.  
  
 ![프로젝트 형식](../../extensibility/internals/media/projecttypes.png "ProjectTypes")  
  
 해당 ProjectTemplates 폴더는 다음과 같습니다.  
  
 ![프로젝트 템플릿](../../extensibility/internals/media/projecttemplates.png "ProjectTemplates")  
  
 경우는 **새 프로젝트** 대화 상자가 열리고 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ProjectTemplates 폴더를 트래버스하 고 해당 구조에서 다시 만듭니다는 **프로젝트 형식** 일부 변경 내용으로 트리:  
  
-   루트 노드는 **프로젝트 형식** 트리 응용 프로그램 템플릿에 따라 결정 됩니다.  
  
-   노드 이름은 지역화할 수 및 특수 문자를 포함할 수 있습니다.  
  
-   정렬 순서를 변경할 수 있습니다.  
  
##### <a name="finding-the-root-node-for-a-project-type"></a>프로젝트 형식에 대 한 루트 노드 찾기  
 ProjectTemplates 폴더를 이동 하는 Visual Studio, 모든.zip 파일 열리고 모든.vstemplate 파일을 추출 합니다. .Vstemplate 파일을 XML를 사용 하 여 응용 프로그램 템플릿에 대해 설명 합니다. 자세한 내용은 참조 [새 프로젝트 생성: 고급, 2 부](../../extensibility/internals/new-project-generation-under-the-hood-part-two.md)합니다.  
  
 \<ProjectType > 태그에는 응용 프로그램에 대 한 프로젝트 형식을 결정 합니다. 예를 들어 \CSharp\SmartDevice\WindowsCE\1033\WindowsCE-EmptyProject.zip 파일을 EmptyProject.vstemplate 포함 한 파일을이 태그 포함 되어 있습니다.  
  
```  
<ProjectType>CSharp</ProjectType>  
```  
  
 \<ProjectType > 태그 및 ProjectTemplates 폴더에 하위 폴더 하지 결정에 응용 프로그램의 루트 노드는 **프로젝트 형식** 트리 합니다. 예제에서는 Windows CE 응용 프로그램 아래에 표시 됩니다는 **Visual C#** 루트 노드, WindowsCE 폴더 VisualBasic 폴더를 이동 인 경우에 Windows CE 응용 프로그램이 여전히는 아래에 표시 된  **Visual C#** 루트 노드.  
  
##### <a name="localizing-the-node-name"></a>노드 이름 지역화  
 ProjectTemplates 폴더를 이동 하는 Visual Studio를 찾으면.vstdir 파일을 검사 합니다. .Vstdir 파일은 XML 파일에서 프로젝트 형식의 모양을 제어 하는 **새 프로젝트** 대화 상자. .Vstdir 파일에서 사용 하 여는 \<LocalizedName > 태그 이름에는 **프로젝트 형식** 노드.  
  
 예를 들어 \CSharp\Database\TemplateIndex.vstdir 파일에는이 태그를 포함 되어 있습니다.  
  
```  
<LocalizedName Package="{462b036f-7349-4835-9e21-bec60e989b9c}" ID="4598"/>  
```  
  
 이 경우 루트 노드 이름을 지정 하는 지역화 된 문자열의 위성 DLL 및 리소스 ID를 결정 **데이터베이스**합니다. 지역화 된 이름은 같은 폴더 이름에 사용할 수 없는 특수 문자를 포함할 수 **.NET**합니다.  
  
 없는 경우 \<LocalizedName > 태그가, 해당 폴더 자체에서 해당 프로젝트 형식을 명명 된 **SmartPhone2003**합니다.  
  
##### <a name="finding-the-sort-order-for-a-project-type"></a>프로젝트 형식에 대 한 정렬 순서를 찾기  
 .Vstdir 파일 프로젝트 형식의 정렬 순서를 확인 하려면 사용 된 \<SortOrder > 태그입니다.  
  
 예를 들어 \CSharp\Windows\Windows.vstdir 파일에는이 태그를 포함 되어 있습니다.  
  
```  
<SortOrder>5</SortOrder>  
```  
  
 \CSharp\Database\TemplateIndex.vstdir 파일에 더 큰 값을 가진 태그가 있습니다.  
  
```  
<SortOrder>5000</SortOrder>  
```  
  
 에 번호가 작을수록는 \<SortOrder > 트리에서 높을수록 위치, 태그 하므로 **Windows** 노드 보다 위에 표시 된 **데이터베이스** 의 노드는 **프로젝트 형식**  트리 합니다.  
  
 없는 경우 \<SortOrder > 프로젝트 형식에 대해 포함 하는 모든 프로젝트 형식에 따라 사전순으로 표시 하는 태그를 지정 \<SortOrder > 사양입니다.  
  
 내 문서에.vstdir 파일이 없는지 확인 (**내 템플릿**) 폴더입니다. 사용자 응용 프로그램 프로젝트 형식 이름 지역화 되지 않은 및 사전순으로 표시 합니다.  
  
#### <a name="a-quick-review"></a>빠르게 검토  
 수정 해 보겠습니다는 **새 프로젝트** 대화 상자와 새 사용자 프로젝트 템플릿을 만듭니다.  
  
1.  Files\microsoft Visual Studio 14.0\Common7\IDE\ProjectTemplates\CSharp 폴더로 MyProjectNode 하위 폴더를 추가 합니다.  
  
2.  임의의 텍스트 편집기를 사용 하 여 MyProjectNode 폴더에서 MyProject.vstdir 파일을 만듭니다.  
  
3.  .Vstdir 파일에 다음이 줄을 추가 합니다.  
  
    ```  
    <TemplateDir Version="1.0.0">  
        <SortOrder>6</SortOrder>  
    </TemplateDir>  
    ```  
  
4.  저장 하 고.vstdir 파일을 닫습니다.  
  
5.  임의의 텍스트 편집기를 사용 하 여 MyProjectNode 폴더에서 MyProject.vstemplate 파일을 만듭니다.  
  
6.  .Vstemplate 파일에 다음이 줄을 추가 합니다.  
  
    ```  
    <VSTemplate Version="2.0.0" Type="Project" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <TemplateData>  
            <ProjectType>CSharp</ProjectType>  
        </TemplateData>  
    </VSTemplate>  
    ```  
  
7.  The.vstemplate 파일을 저장 하 고 편집기를 닫습니다.  
  
8.  새 압축된 MyProjectNode\MyProject.zip 폴더에.vstemplate 파일을 보냅니다.  
  
9. Visual Studio 명령 창에서 다음을 입력 합니다.  
  
    ```  
    devenv /installvstemplates  
    ```  
  
 Visual Studio를 엽니다.  
  
1.  열기는 **새 프로젝트** 대화 상자를 확장 하 고는 **Visual C#** 프로젝트 노드.  
  
 ![MyProjectNode](../../extensibility/internals/media/myprojectnode.png "MyProjectNode")  
  
 **MyProjectNode** Windows 노드 바로 아래의 Visual C#의 자식 노드로 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 [새 프로젝트 생성: 내부 살펴보기, 2부](../../extensibility/internals/new-project-generation-under-the-hood-part-two.md)