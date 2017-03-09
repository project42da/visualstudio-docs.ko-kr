---
title: "속성 및 항목 비교 | Microsoft Docs"
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
  - "msbuild를 msbuild 속성"
ms.assetid: b9da45ae-d6a6-4399-8628-397deed31486
caps.latest.revision: 16
caps.handback.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 속성 및 항목 비교
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

MSBuild 속성 및 항목은 둘 다 하는 데 사용 작업에 정보를 전달 하 고, 조건을 확인 한 다음 프로젝트 파일 전체에서 참조할 수 있는 값을 저장 합니다.  
  
-   속성은 이름-값 쌍입니다. 자세한 내용은 참조 [MSBuild 속성](../msbuild/msbuild-properties.md)합니다.  
  
-   항목은 일반적으로 파일을 나타내는 개체입니다. 메타 데이터 컬렉션 항목 개체를 연결 될 수 있습니다. 메타 데이터는 이름-값 쌍입니다. 자세한 내용은 참조 [항목](../msbuild/msbuild-items.md)합니다.  
  
## <a name="scalars-and-vectors"></a>스칼라 및 벡터  
 MSBuild 속성은 문자열 값이 하나만 있는 이름-값 쌍을 하기 때문에 종종로 설명는 *스칼라*합니다. 로 설명 종종는 MSBuild 항목 형식이 나열 된 항목 목록을 않으므로 *벡터*합니다. 그러나 실제로 속성이 여러 값을 나타낼 수 있으며 항목 형식에는 0 개 또는 한 개의 항목이 있을 수 있습니다.  
  
### <a name="target-dependency-injection"></a>대상 종속성 주입  
 속성에서 여러 값을 나타낼 수는 방법을 알아보려면 대상을 빌드할 대상의 목록에 추가 하는 데 사용 되는 일반적인 사용 패턴을 것이 좋습니다. 이 목록은 일반적으로 대상 이름을 세미콜론으로 구분 된 속성 값으로 표시 됩니다.  
  
```  
<PropertyGroup>  
    <BuildDependsOn>  
        BeforeBuild;  
        CoreBuild;  
        AfterBuild  
    </BuildDependsOn>  
</PropertyGroup>  
```  
  
  `BuildDependsOn` 속성은 일반적으로 대상의 인수로 사용 `DependsOnTargets` 특성을 효과적으로 항목 목록으로 변환 합니다. 대상을 추가 하거나 대상 실행 순서를 변경 하려면이 속성을 재정의할 수 있습니다. 예를 들면 다음과 같습니다.  
  
```  
<PropertyGroup>  
    <BuildDependsOn>  
        $(BuildDependsOn);  
        CustomBuild;  
    </BuildDependsOn>  
</PropertyGroup>  
```  
  
 대상 목록에 CustomBuild 대상을 추가 제공 `BuildDependsOn` 값 `BeforeBuild;CoreBuild;AfterBuild;CustomBuild`합니다.  
  
 MSBuild 4.0 부터는 대상 종속성 주입 사용 되지 않습니다. 사용 하는 `AfterTargets` 및 `BeforeTargets` 특성을 대신 합니다. 자세한 내용은 참조 [대상 빌드 순서](../msbuild/target-build-order.md)합니다.  
  
### <a name="conversions-between-strings-and-item-lists"></a>문자열과 항목 목록 간의 변환  
 MSBuild 항목 형식 및 필요에 따라 문자열 값 사이에 변환이 수행 합니다. 항목 목록을 문자열 값을 변환할 수 있는 방법을 알아보려면 항목 형식을 MSBuild 속성의 값으로 사용 되는 경우 고려해 야 합니다.  
  
```  
<ItemGroup>  
    <OutputDir Include="KeyFiles\;Certificates\" />  
  </ItemGroup>  
<PropertyGroup>  
    <OutputDirList>@(OutputDir)</OutputDirList>  
</PropertyGroup>  
```  
  
 출력 디렉터리에 있는 항목 형식의 `Include` 특성 값이 "키\\; 인증서\\"입니다. MSBuild는 두 개의 항목으로이 문자열을 구문 분석: KeyFiles\ 및 인증서\\합니다. MSBuild 변환 또는 항목 형식에는 세미콜론으로 구분 된 문자열입니다 "평면화" 출력 디렉터리 항목 형식 OutputDirList 속성의 값으로 사용 되 면 "키\\; 인증서\\"입니다.  
  
## <a name="properties-and-items-in-tasks"></a>작업의 속성 및 항목  
 속성 및 항목은 입력 및 출력 MSBuild 작업에 사용 됩니다. 자세한 내용은 참조 [작업](../msbuild/msbuild-tasks.md)합니다.  
  
 속성은 특성으로 작업에 전달 됩니다. 작업 내에서 MSBuild 속성은 문자열에서 해당 값을 변환할 수 있는 속성 형식으로 표시 됩니다. 지원 되는 속성 형식에는 `bool`, `char`, `DateTime`, `Decimal`, `Double`, `int`, `string`, 하는 모든 형식 및 <xref:System.Convert.ChangeType%2A> 처리할 수 있습니다.  
  
 항목으로 작업에 전달 됩니다 <xref:Microsoft.Build.Framework.ITaskItem> 개체입니다. 작업 내에서 <xref:Microsoft.Build.Framework.ITaskItem.ItemSpec%2A> 항목의 값을 나타내는 및 <xref:Microsoft.Build.Framework.ITaskItem.GetMetadata%2A> 해당 메타 데이터를 검색 합니다.  
  
 항목 목록 항목 형식의 배열로 서 전달할 수 있습니다 `ITaskItem` 개체입니다. .NET Framework 3.5 부터는 항목을 제거할 수는 대상의 항목 목록에서 사용 하 여는 `Remove` 특성입니다. 없기 때문에 항목 목록에서 항목을 제거할 수, 항목 형식의 0 개의 항목이 있을 수 있습니다. 항목 목록에는 작업에 전달 되 면 이러한 가능성에 대 한 작업의 코드를 확인 해야 합니다.  
  
## <a name="property-and-item-evaluation-order"></a>속성 및 항목 평가 순서  
 빌드의 평가 단계 가져온된 파일은 나타나는 순서 대로 빌드에 통합 됩니다. 속성 및 항목은 다음과 같은 순서로 세 단계에 정의 됩니다.  
  
-   속성 정의 되 고 표시 된 순서 대로 수정 합니다.  
  
-   항목 정의 정의 되 고 표시 된 순서 대로 수정 합니다.  
  
-   항목 정의 되 고 표시 된 순서 대로 수정 합니다.  
  
 빌드 실행 단계 중 대상 내에 정의 된 속성 및 항목이 함께 평가 됩니다 나타나는 순서는 단일 단계에서.  
  
 그러나 전체 내용 아닙니다. 속성, 항목 정의 또는 항목에 정의 되는 값이 계산 됩니다. 식 계산기의 값을 지정 하는 문자열을 확장 합니다. 문자열 확장 작성 단계에 따라 달라 집니다. 보다 상세한 속성 및 항목 평가 순서는 다음과 같습니다.  
  
-   평가 단계 중 빌드:  
  
    -   속성 정의 되 고 표시 된 순서 대로 수정 합니다. 속성 함수를 실행 합니다. 양식 $(PropertyName)의 속성 값은 식 내에서 확장 됩니다. 속성 값이 확장된 된 식으로 설정 합니다.  
  
    -   항목 정의 정의 되 고 표시 된 순서 대로 수정 합니다. 속성 함수 식 내에서 이미 확장 되어 있습니다. 메타 데이터 값은 확장된 된 식으로 설정 됩니다.  
  
    -   항목 형식 정의 되 고 표시 된 순서 대로 수정 합니다. 양식 값 항목 @(ItemType) 확장 됩니다. 항목 변환도 확장 합니다. 속성 함수 및 값 식 내에서 확장 된 이미 있습니다. 항목 목록 및 메타 데이터 값은 확장된 된 식으로 설정 됩니다.  
  
-   실행 단계 중 빌드:  
  
    -   대상 내에 정의 된 속성 및 항목이 나타나는 순서 대로 함께 평가 됩니다. 속성 함수를 실행 하 고 속성 값은 식 내에서 확장 됩니다. 항목 값 및 항목 변환이 확장 됩니다. 속성 값, 항목 형식 값 및 메타 데이터 값은 확장된 된 식으로 설정 됩니다.  
  
### <a name="subtle-effects-of-the-evaluation-order"></a>미묘한 효과의 평가 순서  
 빌드를 평가 단계에서 속성 확인을 항목 평가 앞에 옵니다. 그럼에도 불구 하 고 속성 항목 값에 따라 달라 지도록 표시 되는 값을 가질 수 있습니다. 다음 스크립트를 고려해 야 합니다.  
  
```  
<ItemGroup>  
    <KeyFile Include="KeyFile.cs">  
        <Version>1.0.0.3</Version>  
    </KeyFile>  
</ItemGroup>  
<PropertyGroup>  
    <KeyFileVersion>@(KeyFile->'%(Version)')</KeyFileVersion>  
</PropertyGroup>  
<Target Name="AfterBuild">  
    <Message Text="KeyFileVersion: $(KeyFileVersion)" />  
</Target>  
```  
  
 메시지 작업 실행이 메시지가 표시 됩니다.  
  
```  
KeyFileVersion: 1.0.0.3  
```  
  
 때문에 이것이 값 `KeyFileVersion` 실제로 문자열은 "@(KeyFile->'%(Version)')". 속성을 처음에 정의할 때 항목 및 항목 변환이 확장 되지 않은 않으므로 `KeyFileVersion` 속성 확장 되지 않은 문자열의 값이 할당 되었습니다.  
  
 빌드 실행 단계 메시지 작업을 처리할 때 MSBuild 문자열을 확장 "@(KeyFile->'%(Version)')" "1.0.0.3"를 생성 합니다.  
  
 속성 및 항목 그룹의 순서를 반대로 된 경우에 같은 오류 메시지가 표시 될 표시입니다.  
  
 두 번째 예제에서는 속성 및 항목 그룹은 대상 내에 있는 경우 발생할 수는 것이 좋습니다.  
  
```  
<Target Name="AfterBuild">  
    <PropertyGroup>  
        <KeyFileVersion>@(KeyFile->'%(Version)')</KeyFileVersion>  
    </PropertyGroup>  
    <ItemGroup>  
        <KeyFile Include="KeyFile.cs">  
            <Version>1.0.0.3</Version>  
        </KeyFile>  
    </ItemGroup>  
    <Message Text="KeyFileVersion: $(KeyFileVersion)" />  
</Target>  
```  
  
 메시지 작업에는이 메시지가 표시 됩니다.  
  
```  
KeyFileVersion:   
```  
  
 빌드 실행 단계 중 대상 내에 정의 된 속성 및 항목 그룹 평가 되기 때문이 위에서 아래로 동시에 있습니다. 때 `KeyFileVersion` 정의 된 `KeyFile` 를 알 수 없습니다. 따라서 항목 변환이 빈 문자열로 확장 됩니다.  
  
 이 경우에 속성 및 항목 그룹의 순서를 반대로 해도 원본 메시지를 복원 합니다.  
  
```  
<Target Name="AfterBuild">  
    <ItemGroup>  
        <KeyFile Include="KeyFile.cs">  
            <Version>1.0.0.3</Version>  
        </KeyFile>  
    </ItemGroup>  
    <PropertyGroup>  
        <KeyFileVersion>@(KeyFile->'%(Version)')</KeyFileVersion>  
    </PropertyGroup>  
    <Message Text="KeyFileVersion: $(KeyFileVersion)" />  
</Target>  
```  
  
 값 `KeyFileVersion` 가 아니라 "1.0.0.3"로 설정 하는 "@(KeyFile->'%(Version)')". The 메시지 작업에이 메시지가 표시 됩니다.  
  
```  
KeyFileVersion: 1.0.0.3  
```  
  
## <a name="see-also"></a>참고 항목  
 [고급 개념](../msbuild/msbuild-advanced-concepts.md)