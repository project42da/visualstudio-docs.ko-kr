---
title: "Visual Studio Modelbus를 사용 하 여 모델 통합 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2ff722f3-21d6-44e2-9efd-f6694aee9987
caps.latest.revision: 26
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 26
---
# Visual Studio Modelbus를 사용 하 여 모델 통합
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus는 모델에 다른 도구 및 모델 간의 링크를 만드는 방법을 제공 합니다. 예를 들어 도메인 관련 언어 \(DSL\) 모델과 UML 모델을 연결할 수 있습니다. Dsl의 통합된 된 집합을 만들 수 있습니다.  
  
 ModelBus는 모델 또는 모델 내의 특정 요소에 대 한 고유 참조를 만들 수 있습니다. 이 참조에에서 저장할 수 모델 외부의 예를 들어, 다른 모델의 요소입니다. 는 뒷부분에 나오는 경우에는 도구를 하려는 경우 요소에 대 한 액세스 권한을 얻을 Modelbus 인프라 적합 한 모델을 로드 되 고 요소를 반환 합니다. 원하는 경우에 사용자에 게 모델을 표시할 수 있습니다. 이전 위치에 파일을 액세스할 수 없으면, ModelBus를 찾는 사용자를 묻습니다. 사용자 파일을 찾으면 해당 파일에 대 한 모든 참조가 수정 됩니다.  
  
> [!NOTE]
>  현재에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus 연결된 되는 모델의 구현 항목에서 동일 해야 합니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 솔루션입니다.  
  
 추가 정보 및 예제 코드를 참조 합니다.  
  
-   [방법: 끌어서 놓기 처리기 추가](../modeling/how-to-add-a-drag-and-drop-handler.md)  
  
-   [Visual Studio 용 모델링 SDK](http://www.microsoft.com/download/details.aspx?id=40754)  
  
##  <a name="provide"></a> DSL에 액세스 제공  
 모델 또는 요소에 ModelBus 참조를 만들기 전에 DSL에 대해 ModelBusAdapter를 정의 해야 합니다. 이 작업을 수행 하는 가장 쉬운 방법은 사용 하는 것은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 모델 버스 확장명은 DSL 디자이너에 명령을 추가 합니다.  
  
###  <a name="expose"></a> Modelbus에 DSL 정의 노출 하려면  
  
1.  다운로드 하 여 이미 설치 된 경우가 아니라면 Visual Studio Modelbus 확장을 설치 합니다. 자세한 내용은 참조 [Visualization and Modeling SDK](http://go.microsoft.com/fwlink/?LinkID=185579)합니다.  
  
2.  DSL 정의 파일을 엽니다. 디자인 화면을 마우스 오른쪽 단추로 누른 **Modelbus**합니다.  
  
3.  대화 상자에서 선택 **이 DSL을 ModelBus에 표시 하려는**합니다. 이 DSL 모델에 표시 하 고 다른 Dsl에 대 한 참조를 사용 하는 경우 두 옵션을 선택할 수 있습니다.  
  
4.  **확인**을 클릭합니다. "Modelbusadapter 라는" 새 프로젝트가 DSL 솔루션에 추가 됩니다.  
  
5.  텍스트 템플릿에서 DSL에 액세스 하려는 경우에 새 프로젝트에서 AdapterManager.tt를 수정 해야 합니다. 명령 및 이벤트 처리기와 같은 기타 코드에서 DSL에 액세스 하려는 경우이 단계를 생략 합니다. 자세한 내용은 [텍스트 템플릿에서 Visual Studio ModelBus 사용](../modeling/using-visual-studio-modelbus-in-a-text-template.md)을 참조하세요.  
  
    1.  에 AdapterManagerBase의 기본 클래스를 변경 <xref:Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager>합니다.  
  
    2.  파일의 끝 AdapterManager 클래스 앞에 다음 추가 특성을 삽입 합니다.  
  
         `[Microsoft.VisualStudio.Modeling.Integration.HostSpecific(HostName)]`  
  
    3.  참조의 ModelBusAdapter 프로젝트에서 추가 **Microsoft.VisualStudio.TextTemplating.Modeling.11.0**합니다.  
  
     텍스트 템플릿 및 다른 코드에서 DSL에 액세스 하려는 경우 두 개의 어댑터, 수정 및 수정 되지 않은 필요 합니다.  
  
6.  클릭 **모든 템플릿 변환**합니다.  
  
7.  솔루션을 다시 빌드합니다.  
  
 Modelbus에서이 DSL의 인스턴스를 열 수 있게 되었습니다.  
  
 폴더 `ModelBusAdapters\bin\*` 에서 작성 한 어셈블리가 포함 된 `Dsl` 프로젝트 및 `ModelBusAdapters` 프로젝트. 다른 DSL에서이 DSL을 참조 하려면 이러한 어셈블리를 가져와야 합니다.  
  
### 요소를 참조할 수 있도록  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus 어댑터를 기본적으로 식별 요소 guid를 사용 합니다. 따라서 모델 파일에 이러한 식별자를 유지 해야 합니다.  
  
##### Id 유지 되는 해당 요소를 확인 하려면  
  
1.  DslDefinition.dsl을 엽니다.  
  
2.  DSL 탐색기에서 **Xml Serialization 동작**, 다음 **클래스 데이터**합니다.  
  
3.  모델 버스 만들려는 각 클래스에 대해 다음을 참조 합니다.  
  
     클래스 노드를 클릭 하 고 속성 창에서 다음 사항을 확인 **Id Serialize** 로 설정 된 `true`합니다.  
  
 또는 요소 이름을 사용 하 여 guid 대신 요소를 식별 하려는 경우에 생성 된 어댑터의 부분을 재정의할 수 있습니다. 어댑터 클래스에 다음 메서드를 재정의 합니다.  
  
-   재정의 `GetElementId` 를 사용 하려면 식별자를 반환 합니다. 이 메서드는 참조를 만들 때 호출 됩니다.  
  
-   재정의 `ResolveElementReference` 모델 버스 참조에서 올바른 요소를 찾습니다.  
  
##  <a name="editRef"></a> 다른 DSL에서 DSL 액세스  
 DSL의 도메인 속성에 modelbus 참조를 저장할 수 및을 사용 하는 사용자 지정 코드를 작성할 수 있습니다. 또한 사용자가 모델 파일과 내의 요소를 선택 하 여 모델 버스 참조를 만들 하도록 할 수 있습니다.  
  
 다른 DSL에 대 한 참조를 사용 하 여 DSL을 사용 하려면 먼저 확인 해야 하는 *소비자* 모델 버스 참조입니다.  
  
#### 표시 되는 DSL에 대 한 참조를 사용 하는 DSL을 사용 하도록 설정 하려면  
  
1.  DSL 정의 다이어그램에서 다이어그램의 주요 부분을 마우스 오른쪽 단추로 클릭 하 고 클릭 **Modelbus**합니다.  
  
2.  대화 상자에서 선택 **modelbus 참조를이 모델을 사용 하도록 설정 하려는**합니다.  
  
3.  사용 하는 DSL의 Dsl 프로젝트에서 프로젝트 참조에 다음 어셈블리를 추가 합니다. 표시 되는 DSL의 ModelBusAdapter\\bin\\ \* 디렉터리에 이러한 어셈블리 \(.dll 파일\)를 찾을 수 있습니다.  
  
    -   예를 들어 표시 된 DSL 어셈블리 **Fabrikam.FamilyTree.Dsl.dll**  
  
    -   노출 된 모델 어댑터 어셈블리를 예를 들어 버스 **Fabrikam.FamilyTree.ModelBusAdapter.dll**  
  
4.  다음.NET 어셈블리를 사용 하는 DSL 프로젝트의 프로젝트 참조를 추가 합니다.  
  
    1.  **Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0.dll**  
  
    2.  **Microsoft.VisualStudio.Modeling.Sdk.Integration.Shell.11.0.dll**  
  
#### 도메인 속성에 Modelbus 참조를 저장 하려면  
  
1.  사용 하는 DSL의 DSL 정의에서 도메인 클래스에 도메인 속성에 추가 하 고 해당 이름을 설정 합니다.  
  
2.  속성에서 창에서 도메인 속성을 선택 하 고, 설정 **형식** 를 `ModelBusReference`합니다.  
  
 이 단계에서 프로그램 코드에는 속성 값을 설정할 수 있지만 속성 창에서 읽기 전용으로 설정 됩니다.  
  
 사용자가 특수 한 ModelBus 참조 편집기를 사용 하 여 속성을 설정할 수 있습니다. 이 편집기의 두 버전 또는 *선택:* 하나를 사용 하면 모델 파일을 선택 하 고 다른 작업 사용자가 모델 파일과 모델 내의 요소를 선택할 수 있도록 합니다.  
  
#### 사용자가 도메인 속성에 Modelbus 참조를 설정 하도록 허용 하려면  
  
1.  도메인 속성을 마우스 오른쪽 단추로 누른 **ModelBusReference 관련 속성 편집**합니다. 대화 상자가 열립니다. 이 *모델 버스 선택*합니다.  
  
2.  적절 한 **ModelBusReference의 종류**: 모델 또는 모델 내 요소입니다.  
  
3.  파일 대화 상자의 필터 문자열에서 문자열을 같은 입력 `Family Tree files |*.ftree`합니다. 표시 된 DSL의 파일 확장명을 바꿉니다.  
  
4.  모델에서 요소를 참조 하려는 경우 Company.FamilyTree.Person 예를 들어 사용자가 선택할 수 있는 형식 목록을 추가할 수 있습니다.  
  
5.  클릭 **확인**, 를 클릭 하 고 **모든 템플릿 변환** 솔루션 탐색기 도구 모음에서입니다.  
  
    > [!WARNING]
    >  올바른 모델이 나 엔터티를 선택 하지 않은 경우 것 처럼 사용 하는 경우에 확인 단추가 아무런 효과가 없으며을 갖습니다.  
  
6.  Company.FamilyTree.Person 같은 대상 형식 목록을 지정 하는 경우 다음 추가 해야 DSL 프로젝트에 어셈블리 참조 Company.FamilyTree.Dsl.dll 대상 DSL의 DLL을 참조  
  
#### Modelbus 참조를 테스트 하려면  
  
1.  노출 및 이용 Dsl을 빌드하십시오.  
  
2.  실험적 모드에서 Dsl 중 하나 F5 또는 CTRL \+ f 5를 눌러 실행 합니다.  
  
3.  실험적 인스턴스에서 디버깅 프로젝트 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 각 DSL의 인스턴스인 파일을 추가 합니다.  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus는 모델의 동일한 항목에 대 한 참조만 해결할 수 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 솔루션입니다. 예를 들어 파일 시스템의 다른 부분에는 모델 파일에 대 한 참조를 만들 수 없습니다.  
  
4.  표시 되는 DSL의 인스턴스에서 일부 요소와 링크를 만들고 저장 합니다.  
  
5.  사용 하는 DSL의 인스턴스를 열고 모델 버스 참조 속성이 있는 모델 요소를 선택 합니다.  
  
6.  속성 창에서 모델 버스 참조 속성을 두 번 클릭 합니다. 선택 대화 상자가 열립니다.  
  
7.  클릭 **찾아보기** DSL의 인스턴스를 선택 합니다.  
  
     Picker도 선택할 수 있습니다 항목 모델에서 요소 관련 modelbus 참조 종류를 지정 합니다.  
  
## 프로그램 코드에서 참조 만들기  
 만들 모델 또는 모델 내 요소에 대 한 참조를 저장 하려는 경우는 `ModelBusReference`합니다. 두 가지의 `ModelBusReference`: 모델 요소 참조와 참조 합니다.  
  
 모델 참조를 만들려면 모델입니다, 인스턴스 및 파일 이름을 DSL의 AdapterManager 해야 하거나 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 모델의 프로젝트 항목입니다.  
  
 요소 참조를 만들려면에 모델 파일 및를 참조 하는 요소에 대 한 어댑터가 필요 합니다.  
  
> [!NOTE]
>  와 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus에 동일 항목에만 참조를 만들 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 솔루션입니다.  
  
### 노출 된 DSL 어셈블리 가져오기  
 사용 하는 프로젝트에서 DSL의 DSL 및 ModelBusAdapter 어셈블리에 프로젝트 참조를 추가 합니다.  
  
 예를 들어 MusicLibrary DSL의 요소에 ModelBus 참조를 저장 한다고 가정 합니다. ModelBus 참조는 FamilyTree DSL의 요소를 참조 합니다. 에 `Dsl` 참조 노드에 MusicLibrary 솔루션의 프로젝트에 다음 어셈블리에 대 한 참조를 추가 합니다.  
  
-   Fabrikam.FamilyTree.Dsl.dll\-표시 되는 DSL입니다.  
  
-   Fabrikam.FamilyTree.ModelBusAdapters.dll\-표시 되는 DSL의 ModelBus 어댑터입니다.  
  
-   Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0  
  
-   Microsoft.VisualStudio.Modeling.Sdk.Integration.Shell.11.0  
  
 이러한 어셈블리를 찾을 수는 `ModelBusAdapters` DSL의 프로젝트 아래에서 `bin\*`합니다.  
  
 참조를 만들 코드 파일에서 이러한 네임 스페이스를 가져와야 할 일반적으로:  
  
```  
// The namespace of the DSL you want to reference:  
using Fabrikam.FamilyTree;  // Exposed DSL  
using Fabrikam.FamilyTree.ModelBusAdapters;  
using Microsoft.VisualStudio.Modeling.Integration;  
using System.Linq;  
...  
```  
  
### 모델에 대 한 참조를 만들려면  
 모델 참조를 만들려면 AdapterManager 표시 되는 DSL에 대 한 액세스 및를 모델에 대 한 참조를 만들 때 사용 합니다. 중 하나는 파일 경로 지정할 수 또는 `EnvDTE.ProjectItem`합니다.  
  
 Adaptermanager에서 모델의 개별 요소에 대 한 액세스를 제공 하는 어댑터를 가져올 수 있습니다.  
  
> [!NOTE]
>  종료 되었음을 때 어댑터를 삭제 해야 합니다. 이 작업을 수행 하는 가장 편리한 방법은 인 한 `using` 문입니다. 다음은 이에 대한 예입니다.  
  
```  
// The file path of a model instance of the FamilyTree DSL:  
string targetModelFile = "TudorFamilyTree.ftree";  
// Get the ModelBus service:  
IModelBus modelBus =   
    this.Store.GetService(typeof(SModelBus)) as IModelBus;  
// Get an adapterManager for the target DSL:  
FamilyTreeAdapterManager manager =   
    (modelbus.GetAdapterManager(FamilyTreeAdapter.AdapterId)   
     as FamilyTreeAdapterManager;  
// or: (modelBus.FindAdapterManagers(targetModelFile).First())  
// or could provide an EnvDTE.ProjectItem  
  
// Create a reference to the target model:  
// NOTE: the target model must be a file in this project.  
ModelBusReference modelReference =  
     manager.CreateReference(targetModelFile);  
// or can use an EnvDTE.ProjectItem instead of the filename  
  
// Get the root element of this model:  
using (FamilyTreeAdapter adapter =   
     modelBus.CreateAdapter(modelReference) as FamilyTreeAdapter)  
{  
  FamilyTree modelRoot = adapter.ModelRoot;  
  // Access elements under the root in the usual way:  
  foreach (Person p in modelRoot.Persons) {...}  
  // You can create adapters for individual elements:  
  ModelBusReference elementReference =  
     adapter.GetElementReference(person);  
  ...  
} // Dispose adapter  
  
```  
  
 사용 하려는 경우 `modelReference` 나중 외부 형식이 지정 된 도메인 속성에 저장할 수 `ModelBusReference`:  
  
```  
using Transaction t = this.Store.TransactionManager  
    .BeginTransaction("keep reference"))  
{  
  artist.FamilyTreeReference = modelReference;  
  t.Commit();  
}  
```  
  
 사용 하 여 사용자가이 도메인 속성을 편집할 수 있도록 `ModelReferenceEditor` 편집기 특성의 매개 변수로 합니다. 자세한 내용은 참조 [사용자 참조를 편집할 수 있도록](#editRef)합니다.  
  
### 요소에 대 한 참조를 만들려면  
 만들고 참조를 확인 하는 모델에 대해 만든 어댑터를 사용할 수 있습니다.  
  
```  
// person is an element in the FamilyTree model:  
ModelBusReference personReference =   
  adapter.GetElementReference(person);  
```  
  
 사용 하려는 경우 `elementReference` 나중 외부 형식이 지정 된 도메인 속성에 저장할 수 `ModelBusReference`합니다. 사용 하 여 사용자가 편집할 수 있도록 `ModelElementReferenceEditor` 편집기 특성의 매개 변수로 합니다. 자세한 내용은 참조 [사용자 참조를 편집할 수 있도록](#editRef)합니다.  
  
### 참조 확인  
 있는 경우는 `ModelBusReference` \(MBR\)는 모델 또는 모델 요소를 참조 하는 가져올 수 있습니다. 요소, 다이어그램 또는 다이어그램의 다른 보기에서 제시 하는 경우 보기 열고 요소를 선택 합니다.  
  
 MBR에서 어댑터를 만들 수 있습니다. 어댑터에서 모델의 루트를 가져올 수 있습니다. 또한 모델 내의 특정 요소를 참조 하는 Mbr을 해결할 수 있습니다.  
  
```  
using Microsoft.VisualStudio.Modeling.Integration; ...  
ModelBusReference elementReference = ...;  
  
// Get the ModelBus service:  
IModelBus modelBus =   
    this.Store.GetService(typeof(SModelBus)) as IModelBus;  
// Use a model reference or an element reference  
// to obtain an adapter for the target model:  
using (FamilyTreeAdapter adapter =   
   modelBus.CreateAdapter(elementReference) as FamilyTreeAdapter)  
   // or CreateAdapter(modelReference)  
{  
  // Get the root of the model:  
  FamilyTree tree = adapter.ModelRoot;  
  
  // Get a model element:  
  MyDomainClass mel =  
    adapter.ResolveElementReference<MyDomainClass>(elementReference);  
  if (mel != null) {...}  
  
  // Get the diagram or other view, if there is one:  
  ModelBusView view = adapter.GetDefaultView();  
  if (view != null)   
  {  
   view.Open();  
   // Display the diagram:  
   view.Show();   
   // Attempt to select the shape that presents the element:  
   view.SetSelection(elementReference);  
  }  
} // Dispose the adapter.  
```  
  
##### 텍스트 템플릿에서 ModelBus 참조를 해결 하려면  
  
1.  액세스 하려는 DSL 텍스트 템플릿이 액세스 하도록 구성 된 ModelBus 어댑터가 있어야 합니다. 자세한 내용은 [DSL에 액세스 제공](#provide)을 참조하세요.  
  
2.  일반적으로 하면 액세스 하는 소스 DSL에에서 저장 된 모델 버스 참조 \(MBR\)를 사용 하 여 DSL 대상입니다. 서식 파일에 MBR을 해결 하는 소스 DSL와 코드의 지시문을 포함 합니다. 텍스트 템플릿에 대 한 자세한 내용은 참조 [도메인별 언어에서 코드 생성](../modeling/generating-code-from-a-domain-specific-language.md)합니다.  
  
    ```  
    <#@ template debug="true" hostspecific="true"   
    inherits="Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation" #>   
    <#@ SourceDsl processor="SourceDslDirectiveProcessor" requires="fileName='Sample.source'" #>  
    <#@ output extension=".txt" #>  
    <#@ assembly name = "Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0" #>  
    <#@ assembly name = "System.Core" #>  
    <#@ assembly name = "Company.CompartmentDragDrop.Dsl.dll" #>  
    <#@ assembly name = "Company.CompartmentDragDrop.ModelBusAdapter.dll" #>  
    <#@ import namespace="Microsoft.VisualStudio.Modeling.Integration" #>  
    <#@ import namespace="System.Linq" #>  
    <#@ import namespace="Company.CompartmentDragDrop" #>  
    <#@ import namespace="Company.CompartmentDragDrop.ModelBusAdapters" #>  
    <# // Get source root from directive processor:  
      ExampleModel source = this.ExampleModel;   
      // This DSL has a MBR in its root:  
    using (ModelBusAdapter adapter = this.ModelBus.CreateAdapter(source.ModelReference) as ModelBusAdapter)   
      {  
      ModelBusAdapterManager manager = this.ModelBus.FindAdapterManagers(this.Host.ResolvePath("Sample.compDD1")).FirstOrDefault();  
      ModelBusReference modelReference =  
        manager.CreateReference(this.Host.ResolvePath("Sample.compDD1"));  
  
      // Get the root element of this model:  
      using (CompartmentDragDropAdapter adapter =   
         this.ModelBus.CreateAdapter(modelReference) as CompartmentDragDropAdapter)  
      {  
        ModelRoot root = adapter.ModelRoot;  
    #>  
    [[<#= root.Name #>]]  
    <#  
      }  
    #>  
  
    ```  
  
 자세한 내용 및 연습을 참조 하십시오. [텍스트 템플릿에서 Visual Studio ModelBus 사용](../modeling/using-visual-studio-modelbus-in-a-text-template.md)  
  
## ModelBusReference를 직렬화 하는 작업  
 저장 하려는 경우는 `ModelBusReference` \(MBR\)는 문자열의 형태로 serialize 하면:  
  
```  
string serialized = modelBus.SerializeReference(elementReference);  
// Store it anywhere, then get it back again:  
ModelBusReference elementReferenceRestored =  
    modelBus.DeserializeReference(serialized, null);  
```  
  
 이러한 방식으로 serialize 한 MBR은 컨텍스트의 무관 합니다. 단순 파일 기반 모델 버스 어댑터를 사용 하는 경우 MBR에는 절대 파일 경로 포함 합니다. 이 인스턴스 모델 파일을 이동 하지 않으려는 경우에 충분 합니다. 그러나 모델 파일 같아야 합니다. 항목에는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트입니다. 사용자가 파일 시스템의 다른 부분에 전체 프로젝트를 이동 하려면 필요 합니다. 소스 제어에서 프로젝트를 유지 하 고 서로 다른 컴퓨터에서 열 수 있으려면 또한 기대할 것입니다. 따라서 파일을 포함 하는 프로젝트의 위치를 기준으로 경로 이름은 serialize 합니다.  
  
### 지정된 된 파일 경로에 상대적인을 직렬화 하는 작업  
 A `ModelBusReference` 포함 한 `ReferenceContext`, 사전 파일 경로 기준으로 serialize 되어야 한다는 등의 정보를 저장할 수 있습니다.  
  
 에 경로 기준으로 serialize 합니다.  
  
```  
elementReference.ReferenceContext.Add(  
   ModelBusReferencePropertySerializer.FilePathSaveContextKey,   
   currentProjectFilePath);  
string serialized = modelBus.SerializeReference(elementReference);  
```  
  
 에 문자열에서 참조를 검색 합니다.  
  
```  
ReferenceContext context = new ReferenceContext();  
context.Add(ModelBusReferencePropertySerializer.FilePathLoadContextKey,  
    currentProjectFilePath);  
ModelBusReference elementReferenceRestored =  
    modelBus.DeserializeReference(serialized, context);  
```  
  
### 다른 어댑터를 통해 만든 Modelbusreference  
 다음 정보는 어댑터를 직접 만들려는 경우에 유용 합니다.  
  
 A `ModelBusReference` 두 부분으로 구성 됩니다 \(MBR\): 모델 버스에서 deserialize 되는 MBR 헤더 및 특정 어댑터 관리자에서 처리 하는 어댑터 관련 됩니다. 이렇게 하면 사용자 고유의 어댑터 serialization 형식을 제공할 수 있습니다. 예를 들어 파일을 대신 데이터베이스를 참조 하거나 어댑터 참조에 추가 정보를 저장할 수 있습니다. 고유한 어댑터에 대 한 추가 정보를 배치할 수는 `ReferenceContext`합니다.  
  
 MBR을 deserialize 하는 경우 다음는 MBR 개체에 저장 된 ReferenceContext를 제공 해야 합니다. MBR을 serialize 하는 경우 저장 된 ReferenceContext 문자열을 생성 하려면 어댑터에서 사용 됩니다. 직렬화 된 문자열에 ReferenceContext의 모든 정보가 없습니다. 예를 들어 단순 파일 기반 어댑터에서 ReferenceContext에 serialize 된 MBR 문자열에 저장 되지 않은 루트 파일 경로 포함 합니다.  
  
 MBR에는 두 단계로 deserialize 됩니다.  
  
-   `ModelBusReferencePropertySerializer` MBR 헤더를 처리 하는 표준 serializer가입니다. 표준 DSL을 사용 하 여 `SerializationContext` 속성 모음에 저장 되는 `ReferenceContext` 키를 사용 하 여 `ModelBusReferencePropertySerializer.ModelBusLoadContextKey`합니다. 특히,는 `SerializationContext` 의 인스턴스를 포함 해야 `ModelBus`합니다.  
  
-   ModelBus 어댑터는 MBR의 어댑터 관련 부분에서는 처리합니다. MBR의 ReferenceContext에 저장 된 추가 정보를 사용할 수 있습니다. 키를 사용 하 여 루트 파일 경로 유지 하는 간단한 파일 기반 어댑터 `FilePathLoadContextKey` 및 `FilePathSaveContextKey`합니다.  
  
     모델 파일의 어댑터 참조로 사용 될 때만 deserialize 됩니다.  
  
## 모델을 만들려면  
  
### 만들기, 열기 및 모델을 편집 합니다.  
 다음 조각은 VMSDK 웹 사이트에서 상태 시스템 샘플에서 가져옵니다. Modelbusreference 만들고 모델을 하 고 모델에 연결 된 다이어그램의 사용을 보여 줍니다.  
  
 이 샘플에서는 대상 DSL의 이름은 StateMachine입니다. 여러 개의 이름은 모델 클래스의 이름과 ModelBusAdapter의 이름 등이 콘솔에서 파생 됩니다.  
  
```  
using Fabrikam.StateMachine.ModelBusAdapters;   
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Diagrams;  
using Microsoft.VisualStudio.Modeling.Integration;  
using Microsoft.VisualStudio.Modeling.Integration.Shell;  
using Microsoft.VisualStudio.Modeling.Shell;  
...  
// Create a new model.  
ModelBusReference modelReference =   
   StateMachineAdapterManager    .CreateStateMachineModel(modelName, fileName);  
//Keep reference of new model in this model.  
using (Transaction t = ...)  
{  
  myModelElement.ReferenceProperty = modelReference;  
  t.Commit();  
}  
// Get the ModelBus service from Visual Studio.  
IModelBus modelBus = Microsoft.VisualStudio.Shell.Package.  
    GetGlobalService(typeof(SModelBus)) as IModelBus;  
// Get a modelbus adapter on the new model.  
ModelBusAdapter modelBusAdapter;  
modelBus.TryCreateAdapter(modelReference,   
    this.ServiceProvider, out modelBusAdapter);  
using (StateMachineAdapter adapter =   
      modelBusAdapter as StateMachineAdapter)  
{  
    if (adapter != null)  
    {  
        // Obtain a Diagram from the adapter.  
        Diagram targetDiagram =   
           ((StandardVsModelingDiagramView)  
                 adapter.GetDefaultView()  
            ).Diagram;  
  
        using (Transaction t =   
             targetDiagram.Store.TransactionManager  
                .BeginTransaction("Update diagram"))  
        {  
            DoUpdates(targetDiagram);  
            t.Commit();  
        }  
  
        // Display the new diagram.  
        adapter.GetDefaultView().Show();  
    }  
}  
```  
  
## 참조 유효성 검사  
 BrokenReferenceDetector는 Modelbusreference를 포함할 수 있는 저장소에 모든 도메인 속성을 테스트 합니다. 작업을 호출 작업이 발견 되는 위치를 제공 하는 있습니다. 유효성 검사 메서드의 경우 특히 유용합니다. 다음 유효성 검사 메서드는 저장소 모델을 저장 하려고 할 때 테스트 하 고 오류 창에 대 한 손상 된 참조가 보고:  
  
```  
[ValidationMethod(ValidationCategories.Save)]  
public void ValidateModelBusReferences(ValidationContext context)  
{  
  BrokenReferenceDetector.DetectBrokenReferences(this.Store,  
    delegate(ModelElement element, // parent of property  
             DomainPropertyInfo property, // identifies property  
             ModelBusReference reference) // invalid reference  
    {   
      context.LogError(string.Format(INVALID_REF_FORMAT,   
             property.Name,   
             referenceState.Name,   
             new ModelBusReferenceTypeConverter().  
                 ConvertToInvariantString(reference)),   
         "Reference",   
         element);  
      });  
}}  
private const string INVALID_REF_FORMAT =   
    "The '{0}' domain property of ths ReferenceState instance "  
  + "named '{1}' contains reference value '{2}' which is invalid";  
```  
  
## ModelBus 확장이 수행 된 작업  
 다음 정보가 필요 하지만 ModelBus 광범위 하 게 사용 하는 경우에 유용할 수 있습니다.  
  
 ModelBus 확장에서는 DSL 솔루션에는 다음과 같이 변경 합니다.  
  
 DSL 정의 다이어그램을 마우스 오른쪽 단추로 클릭 하 여 **Modelbus**, 를 선택한 다음 **이 DSL의 ModelBus를 사용 하도록 설정**:  
  
-   DSL 프로젝트에 대 한 참조에 추가 됩니다 **Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0.dll**  
  
-   DSL 정의에서 외부 형식 참조 추가 됩니다: `Microsoft.VisualStudio.Modeling.Integration.ModelBusReference`합니다.  
  
     참조를 확인할 수 **DSL 탐색기**, 아래에서 **도메인 형식**합니다. 외부 형식 참조를 수동으로 추가 하려면 루트 노드를 마우스 오른쪽 단추로 클릭 합니다.  
  
-   새 템플릿 파일이 추가 되 **Dsl\\GeneratedCode\\ModelBusReferencesSerialization.tt**합니다.  
  
 때 도메인 속성 형식을 modelbusreference로 설정 하 고 다음 속성을 마우스 오른쪽 단추로 클릭을 클릭 하면 **ModelBusReference 관련 속성**:  
  
-   여러 CLR 특성이 도메인 속성에 추가 됩니다. 속성 창에서 사용자 지정 특성 필드에 해당 데이터를 볼 수 있습니다.**Dsl\\GeneratedCode\\DomainClasses.cs**, 속성 선언에 특성을 볼 수 있습니다.  
  
    ```  
    [System.ComponentModel.TypeConverter(typeof(  
    Microsoft.VisualStudio.Modeling.Integration.ModelBusReferenceTypeConverter))]  
    [System.ComponentModel.Editor(typeof(  
      Microsoft.VisualStudio.Modeling.Integration.Picker  
      .ModelReferenceEditor // or ModelElementReferenceEditor  
      ), typeof(System.Drawing.Design.UITypeEditor))]  
    [Microsoft.VisualStudio.Modeling.Integration.Picker  
      .SupplyFileBasedBrowserConfiguration  
      ("Choose a model file", "Target model|*.target")]  
    ```  
  
 DSL 정의 다이어그램을 클릭 하 고 마우스 오른쪽 단추로 클릭 하 여 **ModelBus**, 를 선택 하 고 **이 Dsl을 ModelBus**:  
  
-   새 프로젝트 `ModelBusAdapter` 솔루션에 추가 됩니다.  
  
-   에 대 한 참조 `ModelBusAdapter` 에 추가 되는 `DslPackage` 프로젝트입니다.`ModelBusAdapter` 에 대 한 참조가 `Dsl` 프로젝트입니다.  
  
-   **DslPackage\\source.extention.tt**, `|ModelBusAdapter|` 를 MEF 구성 요소로 추가 됩니다.  
  
## 참고 항목  
 [방법: 프로그램 코드로 파일에서 모델 열기](../modeling/how-to-open-a-model-from-file-in-program-code.md)   
 [UML 모델을 다른 모델 및 도구와 통합](../modeling/integrate-uml-models-with-other-models-and-tools.md)   
 [방법: 끌어서 놓기 처리기 추가](../modeling/how-to-add-a-drag-and-drop-handler.md)   
 [텍스트 템플릿에서 Visual Studio ModelBus 사용](../modeling/using-visual-studio-modelbus-in-a-text-template.md)