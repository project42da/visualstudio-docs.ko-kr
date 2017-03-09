---
title: "MSBuild 항목 | Microsoft Docs"
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
  - "MSBuild 항목"
ms.assetid: d762eff4-c92a-4b5f-a944-1ca30aa22319
caps.latest.revision: 35
caps.handback.revision: 35
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# MSBuild 항목
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

MSBuild 항목은 빌드 시스템에 대 한 입력 하 고 파일을 일반적으로 나타냅니다. 항목은 해당 요소 이름에 따라 항목 형식으로 그룹화 됩니다. 항목 형식에는 작업에 대 한 매개 변수로 사용할 수 있는 항목 목록 이름이 지정 됩니다. 작업 항목 값을 사용 하 여 빌드 프로세스의 단계를 수행 하 합니다.  
  
 항목은 속하는 항목 형식에 의해 이름이 지정, 때문에 "item" 및 "항목 값"를 서로 교환해 서 사용할 수 있습니다.  
  
 **이 항목의**  
  
-   [프로젝트 파일에 항목 만들기](#BKMK_Creating1)  
  
-   [실행 중에 항목 만들기](#BKMK_Creating2)  
  
-   [프로젝트 파일의 참조 항목](#BKMK_ReferencingItems)  
  
-   [와일드 카드를 사용 하 여 항목을 지정 하려면](#BKMK_Wildcards)  
  
-   [Exclude 특성을 사용 하 여](#BKMK_ExcludeAttribute)  
  
-   [항목 메타 데이터](#BKMK_ItemMetadata)  
  
    -   [프로젝트 파일에서 항목 메타 데이터 참조](#BKMK_ReferencingItemMetadata)  
  
    -   [잘 알려진 항목 메타 데이터](#BKMK_WellKnownItemMetadata)  
  
    -   [메타 데이터를 사용 하 여 항목 형식 변환](#BKMK_Transforming)  
  
-   [항목 정의](#BKMK_ItemDefinitions)  
  
-   [대상의 항목 그룹에 있는 항목에 대 한 특성](#BKMK_AttributesWithinTargets)  
  
    -   [특성을 제거](#BKMK_RemoveAttribute)  
  
    -   [KeepMetadata 특성](#BKMK_KeepMetadata)  
  
    -   [RemoveMetadata 특성](#BKMK_RemoveMetadata)  
  
    -   [KeepDuplicates 특성](#BKMK_KeepDuplicates)  
  
##  <a name="a-namebkmkcreating1a-creating-items-in-a-project-file"></a><a name="BKMK_Creating1"></a> 프로젝트 파일에 항목 만들기  
 요소 자식으로 프로젝트 파일에서 항목을 선언 하는 [ItemGroup](../msbuild/itemgroup-element-msbuild.md) 요소입니다. 자식 요소의 이름은 항목의 형식입니다.  `Include` 요소의 특성에 해당 항목 형식에 포함 될 항목 (파일)를 지정 합니다. 예를 들어, 다음 XML 만듭니다 이라는 항목 형식을 `Compile`, 두 개의 파일 포함 합니다.  
  
```  
<ItemGroup>  
    <Compile Include = "file1.cs"/>  
    <Compile Include = "file2.cs"/>  
</ItemGroup>  
```  
  
 "File2.cs" 항목을 대체 하기 위한 항목 "file1.cs"; 파일 이름에 대 한 값의 목록에 추가 됩니다 대신는 `Compile` 항목 유형입니다. 빌드 실행 단계 중 항목 형식에서 항목을 제거할 수 없습니다.  
  
 다음 XML에서는 동일한 항목 형식 하나에 파일을 모두 선언 하 여 `Include` 특성입니다. 파일 이름은 세미콜론으로 구분 됩니다 있는지 확인 합니다.  
  
```  
<ItemGroup>  
    <Compile Include = "file1.cs;file2.cs"/>  
</ItemGroup>  
```  
  
##  <a name="a-namebkmkcreating2a-creating-items-during-execution"></a><a name="BKMK_Creating2"></a> 실행 중에 항목 만들기  
 외부에 있는 항목 [대상](../msbuild/target-element-msbuild.md) 빌드의 평가 단계에서 요소 값이 할당 됩니다. 후속 실행 단계에서 항목 수 만들거나 수정할 수는 다음과 같은 방법으로:  
  
-   모든 작업 항목을 내보낼 수 있습니다. 항목을 내보낼 수는 [작업](../msbuild/task-element-msbuild.md) 요소에 자식이 있어야 [출력](../msbuild/output-element-msbuild.md) 있는 요소는 `ItemName` 특성.  
  
-    [CreateItem](../msbuild/createitem-task.md) 작업 항목을 내보낼 수 있습니다. 이 사용법은 사용 되지 않습니다.  
  
-   .NET Framework 3.5 부터는 `Target` 요소가 포함 될 수 있습니다 [ItemGroup](../msbuild/itemgroup-element-msbuild.md) 요소를 포함할 수 있는 항목 요소입니다.  
  
##  <a name="a-namebkmkreferencingitemsa-referencing-items-in-a-project-file"></a><a name="BKMK_ReferencingItems"></a> 프로젝트 파일의 참조 항목  
 프로젝트 파일 전체에서 항목 형식을 참조 하는 구문을 사용 @(`ItemType`). 예를 들어 이전 예제에서 항목 형식을 사용 하 여 참조할 수 있습니다 `@(Compile)`합니다. 이 구문을 사용 하 여 해당 작업의 매개 변수로 항목 형식을 지정 하 여 작업 항목을 전달할 수 있습니다. 자세한 내용은 참조 [하는 방법: 빌드할 파일 선택](../msbuild/how-to-select-the-files-to-build.md)합니다.  
  
 기본적으로 항목 형식 항목의 확대 된 경우에 세미콜론 (;)으로 구분 됩니다. 구문을 사용할 수 @(*ItemType*, '*구분 기호*')를 기본값 이외의 다른 구분 기호를 지정 합니다. 자세한 내용은 참조 [하는 방법: 표시 된 항목 목록을 쉼표로 구분 하 여](../msbuild/how-to-display-an-item-list-separated-with-commas.md)합니다.  
  
##  <a name="a-namebkmkwildcardsa-using-wildcards-to-specify-items"></a><a name="BKMK_Wildcards"></a> 와일드 카드를 사용 하 여 항목을 지정 하려면  
 사용할 수는 * *, \*, 하 고 있습니까? 각 파일을 개별적으로 나열 하는 대신 빌드에 대 한 입력으로 파일 그룹을 지정 하려면 와일드 카드 문자입니다.  
  
-   ? 와일드 카드 문자는 단일 문자를 찾습니다.  
  
-   * 와일드 카드 문자 0 개 이상의 문자를 찾습니다.  
  
-   * * 부분 경로 일치 하는 와일드 카드 문자 시퀀스입니다.  
  
 예를 들어, 프로젝트 파일에 다음 요소를 사용 하 여 프로젝트 파일을 포함 하는 디렉터리에서 모든.cs 파일을 지정할 수 있습니다.  
  
```  
<CSFile Include="*.cs"/>  
```  
  
 다음 요소는 d: 드라이브에 있는 모든.vb 파일을 선택합니다.  
  
```  
<VBFile Include="D:/**/*.vb"/>  
```  
  
 와일드 카드 문자에 대 한 자세한 내용은 참조 [하는 방법: 빌드할 파일 선택](../msbuild/how-to-select-the-files-to-build.md)합니다.  
  
##  <a name="a-namebkmkexcludeattributea-using-the-exclude-attribute"></a><a name="BKMK_ExcludeAttribute"></a> Exclude 특성을 사용 하 여  
 항목 요소를 포함할 수는 `Exclude` 항목 형식에서 특정 항목 (파일)을 제외 하는 특성입니다.  `Exclude` 특성은 일반적으로 와일드 카드 문자와 함께 사용 됩니다. 예를 들어 다음 XML 디렉터리의 모든.cs 파일에 추가 CSFile 항목 형식을 제외 하 고는 `DoNotBuild.cs` 파일입니다.  
  
```  
<ItemGroup>  
    <CSFile  Include="*.cs"  Exclude="DoNotBuild.cs"/>  
</ItemGroup>  
```  
  
  `Exclude` 특성에 추가 된 항목에만 영향을 줍니다는 `Include` 특성을 모두 포함 하는 항목 요소에 있습니다. 다음 예제에서는 Form1.cs 이전 항목 요소에서 추가 된 파일을 제외 하지 않습니다.  
  
```  
<Compile Include="*.cs" />  
<Compile Include="*.res" Exclude="Form1.cs">  
```  
  
 자세한 내용은 참조 [하는 방법: 빌드에서 파일 제외](../msbuild/how-to-exclude-files-from-the-build.md)합니다.  
  
##  <a name="a-namebkmkitemmetadataa-item-metadata"></a><a name="BKMK_ItemMetadata"></a> 항목 메타 데이터  
 항목의 정보 외에도 메타 데이터를 포함할 수 있습니다는 `Include` 및 `Exclude` 특성입니다. 이 메타 데이터 또는 일괄 처리 작업 및 대상 항목에 대 한 자세한 정보를 필요로 하는 작업에서 사용할 수 있습니다. 자세한 내용은 참조 [일괄 처리가](../msbuild/msbuild-batching.md)합니다.  
  
 메타 데이터는 프로젝트 파일에 있는 항목 요소의 자식 요소로 선언 된 키-값 쌍의 컬렉션입니다. 자식 요소의 이름은 메타 데이터의 이름 및 자식 요소의 값은 메타 데이터의 값입니다.  
  
 메타 데이터를 포함 하는 항목 요소와 연결 됩니다. 예를 들어, 다음 XML 추가 `Culture` 메타 데이터 값을 가진 `Fr` "one.cs"와 "two.cs" 항목에서 CSFile의 항목 유형입니다.  
  
```  
<ItemGroup>  
    <CSFile Include="one.cs;two.cs">  
        <Culture>Fr</Culture>  
    </CSFile>  
</ItemGroup>  
```  
  
 항목 메타 데이터 값이 0 개 이상 있을 수 있습니다. 언제 든 지 메타 데이터 값을 변경할 수 있습니다. 메타 데이터는 빈 값으로 설정 하면 효과적으로 제거할 있습니다 빌드.  
  
###  <a name="a-namebkmkreferencingitemmetadataa-referencing-item-metadata-in-a-project-file"></a><a name="BKMK_ReferencingItemMetadata"></a> 프로젝트 파일에서 항목 메타 데이터 참조  
 %(구문을 사용 하 여 프로젝트 파일 전체에서 항목 메타 데이터를 참조할 수 있습니다`ItemMetadataName`). 모호함이 존재 하는 경우에 항목 형식의 이름을 사용 하 여 대 한 참조를 한정할 수 있습니다. 예를 들어 지정할 수 있습니다 %(*ItemType.ItemMetaDataName*). 다음 예제에서는 메시지 작업을 일괄 처리 하는 디스플레이 메타 데이터를 사용 합니다. 일괄 처리에 대 한 항목 메타 데이터를 사용 하는 방법에 대 한 자세한 내용은 참조 [작업 일괄 처리의 항목 메타 데이터](../msbuild/item-metadata-in-task-batching.md)합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Stuff Include="One.cs" >  
            <Display>false</Display>  
        </Stuff>  
        <Stuff Include="Two.cs">  
            <Display>true</Display>  
        </Stuff>  
    </ItemGroup>  
    <Target Name="Batching">  
        <Message Text="@(Stuff)" Condition=" '%(Display)' == 'true' "/>  
    </Target>  
</Project>  
```  
  
###  <a name="a-namebkmkwellknownitemmetadataa-well-known-item-metadata"></a><a name="BKMK_WellKnownItemMetadata"></a> 잘 알려진 항목 메타 데이터  
 항목 형식에는 항목이 추가 될 때 해당 항목에는 잘 알려진 일부 메타 데이터가 할당 됩니다. 예를 들어 모든 항목에는 잘 알려진 메타 데이터 `%(Filename)`, 값은 항목의 파일 이름입니다. 자세한 내용은 참조 [잘 알려진 항목 메타 데이터](../msbuild/msbuild-well-known-item-metadata.md)합니다.  
  
###  <a name="a-namebkmktransforminga-transforming-item-types-by-using-metadata"></a><a name="BKMK_Transforming"></a> 메타 데이터를 사용 하 여 항목 형식 변환  
 메타 데이터를 사용 하 여 항목 목록의 새 항목 목록으로 변환할 수 있습니다. 예를 들어 항목 형식을 변환할 수 있습니다 `CppFiles` 식을 사용 하 여.obj 파일의 해당 목록에.cpp 파일을 표시 하는 항목이 포함 된 `@(CppFiles -> '%(Filename).obj')`합니다.  
  
 다음 코드에서는 `CultureResource` 항목의 모든 복사본을 포함 하는 형식 `EmbeddedResource` 항목 `Culture` 메타 데이터입니다.  `Culture` 메타 데이터 값은 새 메타 데이터의 값이 됩니다 `CultureResource.TargetDirectory`합니다.  
  
```  
<Target Name="ProcessCultureResources">  
    <ItemGroup>  
        <CultureResource Include="@(EmbeddedResource)"  
            Condition="'%(EmbeddedResource.Culture)' != ''">  
            <TargetDirectory>%(EmbeddedResource.Culture) </TargetDirectory>  
        </CultureResource>  
    </ItemGroup>  
</Target>  
```  
  
 자세한 내용은 참조 [변환](../msbuild/msbuild-transforms.md)합니다.  
  
##  <a name="a-namebkmkitemdefinitionsa-item-definitions"></a><a name="BKMK_ItemDefinitions"></a> 항목 정의  
 .NET Framework 3.5 부터는 수 기본 메타 데이터 모든 항목 형식에 사용 하 여 추가한는 [ItemDefinitionGroup 요소](../msbuild/itemdefinitiongroup-element-msbuild.md)합니다. 잘 알려진 메타 데이터와 마찬가지로 기본 메타 데이터가 사용자가 지정한 항목 형식의 모든 항목에 연관 됩니다. 항목 정의에서 기본 메타 데이터를 명시적으로 재정의할 수 있습니다. 예를 들어, 다음 XML 제공는 `Compile` "one.cs" 및 "three.cs" 메타 데이터 항목 `BuildDay` "Monday" 값을 사용 합니다. 이 코드는 "two.cs" 항목 메타 데이터를 통해 `BuildDay` "화요일" 값을 사용 합니다.  
  
```  
<ItemDefinitionGroup>  
    <Compile>  
        <BuildDay>Monday</BuildDay>  
    </Compile>  
</ItemDefinitionGroup>  
<ItemGroup>  
    <Compile Include="one.cs;three.cs" />  
    <Compile Include="two.cs">  
        <BuildDay>Tuesday</BuildDay>  
    </Compile>  
</ItemGroup>  
```  
  
 자세한 내용은 참조 [항목 정의](../msbuild/item-definitions.md)합니다.  
  
##  <a name="a-namebkmkattributeswithintargetsa-attributes-for-items-in-an-itemgroup-of-a-target"></a><a name="BKMK_AttributesWithinTargets"></a> 대상의 항목 그룹에 있는 항목에 대 한 특성  
 .NET Framework 3.5 부터는 `Target` 요소가 포함 될 수 있습니다 [ItemGroup](../msbuild/itemgroup-element-msbuild.md) 요소를 포함할 수 있는 항목 요소입니다. 이 섹션의 특성은 항목에 대해 지정 된 경우에 유효는 `ItemGroup` 에 `Target`합니다.  
  
###  <a name="a-namebkmkremoveattributea-remove-attribute"></a><a name="BKMK_RemoveAttribute"></a> 특성을 제거  
 항목에 `ItemGroup` 대상의 포함 될 수 있습니다는 `Remove` 항목 형식에서 특정 항목 (파일)를 제거 하는 특성입니다. 이 특성은.NET Framework 3.5에 도입 되었습니다.  
  
 다음 예에서는 컴파일 항목 형식에서 모든.config 파일을 제거합니다.  
  
```  
<Target>  
    <ItemGroup>  
        <Compile Remove="*.config"/>  
    </ItemGroup>  
</Target>  
```  
  
###  <a name="a-namebkmkkeepmetadataa-keepmetadata-attribute"></a><a name="BKMK_KeepMetadata"></a> KeepMetadata 특성  
 항목 요소에 포함 될 수 있습니다 항목 대상 내에서 생성 되 면는 `KeepMetadata` 특성입니다. 이 특성을 지정 하는 경우 세미콜론으로 구분 된 이름 목록에 지정 된 메타 데이터만 소스 항목에서 대상 항목으로 전송 됩니다. 이 특성에 대 한 빈 값을 지정 하지 않는 것과 같습니다.  `KeepMetadata` 특성은.NET Framework 4.5에서 도입 되었습니다.  
  
 사용 하는 방법을 보여 주는 다음 예제는 `KeepMetadata` 특성입니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003"  
ToolsVersion="4.0">  
  
    <ItemGroup>  
        <FirstItem Include="rhinoceros">  
            <Class>mammal</Class>  
            <Size>large</Size>  
        </FirstItem>  
  
    </ItemGroup>  
    <Target Name="MyTarget">  
        <ItemGroup>  
            <SecondItem Include="@(FirstItem)" KeepMetadata="Class" />  
        </ItemGroup>  
  
        <Message Text="FirstItem: %(FirstItem.Identity)" />  
        <Message Text="  Class: %(FirstItem.Class)" />  
        <Message Text="  Size:  %(FirstItem.Size)"  />  
  
        <Message Text="SecondItem: %(SecondItem.Identity)" />  
        <Message Text="  Class: %(SecondItem.Class)" />  
        <Message Text="  Size:  %(SecondItem.Size)"  />  
    </Target>  
</Project>  
  
<!--  
Output:  
  FirstItem: rhinoceros  
    Class: mammal  
    Size:  large  
  SecondItem: rhinoceros  
    Class: mammal  
    Size:   
-->  
```  
  
###  <a name="a-namebkmkremovemetadataa-removemetadata-attribute"></a><a name="BKMK_RemoveMetadata"></a> RemoveMetadata 특성  
 항목 요소에 포함 될 수 있습니다 항목 대상 내에서 생성 되 면는 `RemoveMetadata` 특성입니다. 이 특성을 지정 하는 경우 모든 메타 데이터는 소스 항목에서 메타 데이터를 제외 하 고 대상 항목에 이름이 포함 되어 전송 이름 세미콜론으로 구분 된 목록에. 이 특성에 대 한 빈 값을 지정 하지 않는 것과 같습니다.  `RemoveMetadata` 특성은.NET Framework 4.5에서 도입 되었습니다.  
  
 사용 하는 방법을 보여 주는 다음 예제는 `RemoveMetadata` 특성입니다.  
  
```  
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <PropertyGroup>  
        <MetadataToRemove>Size;Material</MetadataToRemove>  
    </PropertyGroup>  
  
    <ItemGroup>  
        <Item1 Include="stapler">  
            <Size>medium</Size>  
            <Color>black</Color>  
            <Material>plastic</Material>  
        </Item1>  
    </ItemGroup>  
  
    <Target Name="MyTarget">  
        <ItemGroup>  
            <Item2 Include="@(Item1)" RemoveMetadata="$(MetadataToRemove)" />  
        </ItemGroup>  
  
        <Message Text="Item1: %(Item1.Identity)" />  
        <Message Text="  Size:     %(Item1.Size)" />  
        <Message Text="  Color:    %(Item1.Color)" />  
        <Message Text="  Material: %(Item1.Material)" />  
        <Message Text="Item2: %(Item2.Identity)" />  
        <Message Text="  Size:     %(Item2.Size)" />  
        <Message Text="  Color:    %(Item2.Color)" />  
        <Message Text="  Material: %(Item2.Material)" />  
    </Target>  
</Project>  
  
<!--  
Output:   
  Item1: stapler  
    Size:     medium  
    Color:    black  
    Material: plastic  
  Item2: stapler  
    Size:       
    Color:    black  
    Material:   
-->  
```  
  
###  <a name="a-namebkmkkeepduplicatesa-keepduplicates-attribute"></a><a name="BKMK_KeepDuplicates"></a> KeepDuplicates 특성  
 항목 요소에 포함 될 수 있습니다 항목 대상 내에서 생성 되 면는 `KeepDuplicates` 특성입니다. `KeepDuplicates` 한 `Boolean` 항목이 기존 항목의 정확한 복제본 인 경우 대상 그룹에 항목을 추가 할지 여부를 지정 하는 특성입니다.  
  
 항목이 추가 되는 원본 및 대상 항목 Include 값은 같지만 다른 메타 데이터를 있으면 경우에 `KeepDuplicates` 로 설정 된 `false`합니다. 이 특성에 대 한 빈 값을 지정 하지 않는 것과 같습니다.  `KeepDuplicates` 특성은.NET Framework 4.5에서 도입 되었습니다.  
  
 사용 하는 방법을 보여 주는 다음 예제는 `KeepDuplicates` 특성입니다.  
  
```  
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <Item1 Include="hourglass;boomerang" />  
        <Item2 Include="hourglass;boomerang" />  
    </ItemGroup>  
  
    <Target Name="MyTarget">  
        <ItemGroup>  
            <Item1 Include="hourglass" KeepDuplicates="false" />  
            <Item2 Include="hourglass" />  
        </ItemGroup>  
  
        <Message Text="Item1: @(Item1)" />  
        <Message Text="  %(Item1.Identity)  Count: @(Item1->Count())" />  
        <Message Text="Item2: @(Item2)" />  
        <Message Text="  %(Item2.Identity)  Count: @(Item2->Count())" />  
    </Target>  
</Project>  
  
<!--  
Output:   
  Item1: hourglass;boomerang  
    hourglass  Count: 1  
    boomerang  Count: 1  
  Item2: hourglass;boomerang;hourglass  
    hourglass  Count: 2  
    boomerang  Count: 1  
-->  
```  
  
## <a name="see-also"></a>참고 항목  
 [MSBuild 개념](../msbuild/msbuild-concepts.md)  
 [MSBuild](../msbuild/msbuild1.md)   
 [방법: 빌드할 파일 선택](../msbuild/how-to-select-the-files-to-build.md)   
 [방법: 빌드에서 파일 제외](../msbuild/how-to-exclude-files-from-the-build.md)   
 [방법: 쉼표로 구분 하는 항목 목록을 표시](../msbuild/how-to-display-an-item-list-separated-with-commas.md)   
 [항목 정의](../msbuild/item-definitions.md)   
 [일괄 처리](../msbuild/msbuild-batching.md)   
 [Item 요소 (MSBuild)](../msbuild/item-element-msbuild.md)