---
title: "새 프로젝트 생성: 내부적으로 1 부 | Microsoft Docs"
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
ms.assetid: 66778698-0258-467d-8b8b-c351744510eb
caps.latest.revision: 29
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 29
---
# 새 프로젝트 생성: 내부적으로 1 부
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

고유의 프로젝트 형식을 만드는 방법에 대해 생각해 본 적이 있습니까? 새 프로젝트를 만들 때 실제로 일어나 궁금 하십니까? 사용 하 내부적인 보기는 실제로 무슨 일을 참조 하십시오.  
  
 Visual Studio를 조정 하는 몇 가지 작업 가지가 있습니다.  
  
-   모든 사용 가능한 프로젝트 유형의 트리 표시 됩니다.  
  
-   각 프로젝트 형식에 대 한 응용 프로그램 템플릿의 목록을 표시 하 고 하나를 선택할 수 있습니다.  
  
-   프로젝트 이름 및 경로 같은 응용 프로그램에 대 한 프로젝트 정보를 수집합니다.  
  
-   프로젝트 팩터리에이 정보를 전달 합니다.  
  
-   현재 솔루션의 프로젝트 항목 및 폴더를 생성합니다.  
  
## 새 프로젝트 대화 상자  
 새 프로젝트에 대 한 프로젝트 형식을 선택 하면 모든 것을 시작 합니다. 클릭 하 여 시작 하겠습니다 **새 프로젝트** 에 **파일** 메뉴.**새 프로젝트** 대화 상자가 나타나면 다음과 같이 결과 보기:  
  
 ![새 프로젝트 대화 상자](~/extensibility/internals/media/newproject.gif "NewProject")  
  
 자세히 살펴보겠습니다.**프로젝트 형식** 트리에 나열 다양 한 프로젝트 형식을 만들 수 있습니다. 같은 프로젝트 형식을 선택 하면 **Visual C\# Windows**, 를 시작 하기 위한 응용 프로그램 템플릿 목록이 표시 됩니다.**Visual Studio 설치 되어 있는 템플릿** Visual Studio가 설치 되어 있고 컴퓨터의 모든 사용자에 게 사용할 수 있습니다. 만들거나 수집 하는 새 템플릿을 추가할 수 **내 템플릿** 에 사용할 수 있습니다.  
  
 와 같은 서식 파일을 선택 하면 **Windows 응용 프로그램**, 대화 상자에서,이 경우 응용 프로그램 종류에 대 한 설명을 표시 **Windows 사용자 인터페이스를 사용 하 여 응용 프로그램 만들기에 대 한 프로젝트**합니다.  
  
 맨 아래에 **새 프로젝트** 대화 상자에서 자세한 정보를 수집 하는 몇 가지 컨트롤 표시 됩니다. 표시 컨트롤 프로젝트 형식에 따라 달라 지지만 프로젝트를 포함 하는 일반적으로 **이름** 텍스트 상자는 **위치** 텍스트 상자 및 관련 **찾아보기** 단추 및 **솔루션 이름** 텍스트 상자 및 관련 **솔루션용 디렉터리 만들기** 확인란.  
  
## 새 프로젝트 대화 상자 채우기  
 여기서는 **새 프로젝트** 대화 상자에서 해당 정보를 가져오도록? 여기서 작업을 더 이상 사용 되지 그 중 하나에 두 가지 메커니즘이 있습니다.**새 프로젝트** 대화 상자를 결합 하 고 두 메커니즘에서 얻은 정보를 표시 합니다.  
  
 시스템 레지스트리 항목 및.vsdir 파일을 사용 하는 이전 버전 \(사용 되지 않음된\) 됩니다. 이 메커니즘에는 Visual Studio를 열 때 실행 됩니다. 최신 메서드.vstemplate 파일을 사용합니다. 이 메커니즘을 Visual Studio 초기화 되 면 예를 들어 실행 하 여 실행  
  
```  
devenv /setup  
```  
  
 또는  
  
```  
devenv /installvstemplates  
```  
  
### 프로젝트 형식  
 이름과 위치는 **프로젝트 형식** 와 같은 루트 노드의 **Visual C\#** 및 **다른 언어**, 시스템 레지스트리 항목에 의해 결정 됩니다. 자식 노드의 조직 같은 **데이터베이스** 및 **스마트 장치**, 해당.vstemplate 파일을 포함 하는 폴더 계층 구조를 반영 합니다. 루트 노드 먼저 살펴보겠습니다.  
  
#### 프로젝트 유형 루트 노드  
 때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 은 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\14.0\\NewProjectTemplates\\TemplateDirs 빌드하고의 루트 노드 이름을 지정 하는 시스템 레지스트리 키의 하위 키를 통과할 초기화는 **프로젝트 형식** 트리. 이 정보는 나중에 사용할 캐시 됩니다. {FAE04EC1\-301F\-11D3\-BF4B\-00C04F79EFBC} TemplateDirs\\ \\\/1 키를 살펴봅니다. 각 항목에는 VSPackage GUID입니다. 하위 키의 이름 \(\/ 1\)은 무시 되 고 존재 임을 나타냅니다. 하지만 **프로젝트 형식** 루트 노드. 루트 노드에 있을 수의 모양을 제어 하는 여러 하위 키의 **프로젝트 형식** 트리. 그 중 일부에 대해 살펴보겠습니다.  
  
##### \(기본값\)  
 루트 노드 이름을 지정 하는 지역화 된 문자열의 리소스 ID입니다. 문자열 리소스는 위성 DLL VSPackage GUID가 선택한에 있습니다.  
  
 예제에서 VSPackage GUID는  
  
 {FAE04EC1\-301F\-11D3\-BF4B\-00C04F79EFBC}  
  
 루트 노드를의 리소스 ID \(기본값\) 및 \(\/ 1\)은 \#2345  
  
 인접 패키지 키의 GUID를 조회 하 고 SatelliteDll 하위 키를 검사 하는 경우에 문자열 리소스를 포함 하는 어셈블리의 경로 찾을 수 있습니다.  
  
 \< visual Studio 설치 경로 \> \\VC\#\\VCSPackages\\1033\\csprojui.dll  
  
 이 확인 하 고, 파일 탐색기를 열고, Visual Studio 디렉터리 csprojui.dll 끌어... 문자열 테이블 리소스 \#2345 캡션을 있는지 보여 줍니다. **Visual C\#**합니다.  
  
##### SortPriority  
 루트 노드는 위치를 결정은 **프로젝트 형식** 트리.  
  
 SortPriority REG\_DWORD 0x00000014 \(20\)  
  
 우선 순위 번호가 작을수록 트리에서 높을수록 위치 합니다.  
  
##### DeveloperActivity  
 이 하위 키가 있는 경우에 루트 노드의 위치를 개발자 설정 대화 상자에 의해 제어 됩니다. 예를 들면 다음과 같습니다.  
  
 DeveloperActivity REG\_SZ VC \#  
  
 Visual C\# 되도록 루트 노드에 대해 Visual Studio 설정 되어 있으면 나타냅니다 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 개발 합니다. 그렇지 않은 경우의 자식 노드가 됩니다 **다른 언어**합니다.  
  
##### 폴더  
 이 하위 키가 있는 경우 루트 노드는 지정된 된 폴더의 자식 노드가 됩니다. 가능한 폴더 목록이 키 아래에 나타납니다.  
  
 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\11.0\\NewProjectTemplates\\PseudoFolders  
  
 예를 들어 데이터베이스 프로젝트 항목에는 PseudoFolders의 기타 프로젝트 형식 항목과 일치 하는 폴더 키를 있습니다. 따라서에서 **프로젝트 형식** 트리에서 **데이터베이스 프로젝트** 의 자식 노드가 됩니다 **기타 프로젝트 형식**합니다.  
  
#### 프로젝트 형식 자식 노드 및.vstdir 파일  
 자식 노드 위치는 **프로젝트 형식** 트리 ProjectTemplates 폴더에 있는 폴더의 계층 구조를 따릅니다. 컴퓨터 템플릿의 \(**Visual Studio 설치 되어 있는 템플릿**\), 일반적인 위치는 files\\microsoft Visual Studio 14.0\\Common7\\IDE\\ProjectTemplates\\ 및 사용자 서식 파일 \(**내 템플릿**\), 일반적인 위치는 documents\\visual Studio 14.0\\Templates\\ProjectTemplates\\ 합니다. 이 두 위치에서 폴더 계층 구조를 만들려면 병합 되는 **프로젝트 형식** 트리.  
  
 C\# 개발자 설정 사용 하 여 Visual studio는 **프로젝트 형식** 트리 모습은 다음과 같습니다.  
  
 ![프로젝트 형식](~/extensibility/internals/media/projecttypes.png "ProjectTypes")  
  
 해당 ProjectTemplates 폴더는 다음과 같습니다.  
  
 ![프로젝트 템플릿](~/extensibility/internals/media/projecttemplates.png "ProjectTemplates")  
  
 때는 **새 프로젝트** 대화 상자가 열리고 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ProjectTemplates 폴더를 트래버스하 고에서 해당 구조를 다시 만드는 **프로젝트 형식** 일부 변경 내용으로 트리:  
  
-   루트 노드는 **프로젝트 형식** 트리는 응용 프로그램 템플릿에 따라 결정 됩니다.  
  
-   노드 이름을 지역화할 수 및 특수 문자를 포함할 수 있습니다.  
  
-   정렬 순서를 변경할 수 있습니다.  
  
##### 프로젝트 형식에 대 한 루트 노드 찾기  
 ProjectTemplates 폴더를 이동 하는 Visual Studio를 모든.zip 파일 열리고 모든.vstemplate 파일을 추출 합니다. .Vstemplate 파일을 XML를 사용 하 여 응용 프로그램 템플릿에 대해 설명 합니다. 자세한 내용은 [새 프로젝트 생성: 내부적으로 2 부](../../extensibility/internals/new-project-generation-under-the-hood-part-two.md)을 참조하십시오.  
  
 \< ProjectType \> 태그에는 응용 프로그램에 대 한 프로젝트 형식을 결정합니다. 예를 들어 \\CSharp\\SmartDevice\\WindowsCE\\1033\\WindowsCE\-EmptyProject.zip 파일에는이 태그는 EmptyProject.vstemplate 파일이 포함 되어 있습니다.  
  
```  
<ProjectType>CSharp</ProjectType>  
```  
  
 \< ProjectType \> 태그 및 ProjectTemplates 폴더에 하위 폴더 하지 결정에서 응용 프로그램의 루트 노드는 **프로젝트 형식** 트리. 예제에서는 Windows CE 응용 프로그램에서 표시는 **Visual C\#** 루트 노드를 WindowsCE 폴더 VisualBasic 폴더를 이동 하는, 경우에 Windows CE 응용 프로그램이 여전히는 아래에 표시 하 고는 **Visual C\#** 루트 노드.  
  
##### 노드 이름을 지역화  
 ProjectTemplates 폴더를 이동 하는 Visual Studio를 찾으면 모든.vstdir 파일을 검사 합니다. .Vstdir 파일은 XML 파일에서 프로젝트 형식의 모양을 제어 하는 **새 프로젝트** 대화 상자입니다. .Vstdir 파일의 이름으로 \< LocalizedName \> 태그를 사용 하 여는 **프로젝트 형식** 노드.  
  
 예를 들어 \\CSharp\\Database\\TemplateIndex.vstdir 파일에는이 태그가 포함 되어 있습니다.  
  
```  
<LocalizedName Package="{462b036f-7349-4835-9e21-bec60e989b9c}" ID="4598"/>  
```  
  
 이 경우 루트 노드 이름을 지정 하는 지역화 된 문자열의 위성 DLL 및 리소스 ID를 결정 **데이터베이스**합니다. 지역화 된 이름을 사용할 수 없는 폴더 이름에 같은 특수 문자를 포함할 수 있습니다 **.NET**합니다.  
  
 프로젝트 형식 자체 폴더로 명명 된 \< LocalizedName \> 태그가 있는 경우 **SmartPhone2003**합니다.  
  
##### 프로젝트 형식에 대 한 정렬 순서를 찾기  
 프로젝트 형식의 정렬 순서를 확인 하려면.vstdir 파일 \< SortOrder \> 태그를 사용 합니다.  
  
 예를 들어 \\CSharp\\Windows\\Windows.vstdir 파일에는이 태그가 포함 되어 있습니다.  
  
```  
<SortOrder>5</SortOrder>  
```  
  
 \\CSharp\\Database\\TemplateIndex.vstdir 파일에 더 큰 값을 가진 태그가 있습니다.  
  
```  
<SortOrder>5000</SortOrder>  
```  
  
 낮을수록 \< SortOrder \>에서 태그를 트리에서 높을수록 위치 이므로 **Windows** 노드 보다 위에 표시는 **데이터베이스** 의 노드는 **프로젝트 형식** 트리.  
  
 프로젝트 형식에 대 한 \< SortOrder \> 태그가 지정 되지, \< SortOrder \> 등의 사양이 포함 하는 모든 프로젝트 형식에 따라 사전순으로 나타납니다.  
  
 내 문서에.vstdir 파일이 없는지 확인 \(**내 템플릿**\) 폴더입니다. 사용자 응용 프로그램 프로젝트 형식 지역화 되지 않은 이름과 사전순으로 표시 합니다.  
  
#### 빠른 검토  
 수정 해 보겠습니다는 **새 프로젝트** 대화 상자와 새 사용자 프로젝트 템플릿을 만듭니다.  
  
1.  Files\\microsoft Visual Studio 14.0\\Common7\\IDE\\ProjectTemplates\\CSharp 폴더에 MyProjectNode 하위 폴더를 추가 합니다.  
  
2.  임의의 텍스트 편집기를 사용 하 여 MyProjectNode 폴더에 MyProject.vstdir 파일을 만듭니다.  
  
3.  .Vstdir 파일에 다음이 줄을 추가 합니다.  
  
    ```  
    <TemplateDir Version="1.0.0">  
        <SortOrder>6</SortOrder>  
    </TemplateDir>  
    ```  
  
4.  저장 하 고.vstdir 파일을 닫습니다.  
  
5.  임의의 텍스트 편집기를 사용 하 여 MyProjectNode 폴더에 MyProject.vstemplate 파일을 만듭니다.  
  
6.  .Vstemplate 파일에 다음이 줄을 추가 합니다.  
  
    ```  
    <VSTemplate Version="2.0.0" Type="Project" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <TemplateData>  
            <ProjectType>CSharp</ProjectType>  
        </TemplateData>  
    </VSTemplate>  
    ```  
  
7.  The.vstemplate 파일을 저장 하 고 편집기를 닫습니다.  
  
8.  새 압축 MyProjectNode\\MyProject.zip 폴더로.vstemplate 파일을 보냅니다.  
  
9. Visual Studio 명령 창에서 다음을 입력 합니다.  
  
    ```  
    devenv /installvstemplates  
    ```  
  
 Visual Studio를 엽니다.  
  
1.  열기는 **새 프로젝트** 대화 상자를 확장 하 고는 **Visual C\#** 프로젝트 노드.  
  
 ![MyProjectNode](~/extensibility/internals/media/myprojectnode.png "MyProjectNode")  
  
 **MyProjectNode** Windows 노드 바로 아래 Visual C\#의 자식 노드로 나타납니다.  
  
## 참고 항목  
 [새 프로젝트 생성: 내부적으로 2 부](../../extensibility/internals/new-project-generation-under-the-hood-part-two.md)