---
title: "항목 함수 | Microsoft Docs"
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
  - "msbuild, 항목 함수"
ms.assetid: 5e6df3cc-2db8-4cbd-8fdd-3ffd03ac0876
caps.latest.revision: 28
caps.handback.revision: 28
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 항목 함수
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

MSBuild 4.0부터는 작업 및 대상의 코드가 항목 함수를 호출하여 프로젝트에 있는 항목에 대한 정보를 가져올 수 있습니다.  이러한 함수를 사용하면 Distinct\(\) 항목을 간단하게 가져올 수 있으며, 항목에 대해 루프를 수행하는 것보다 속도가 빠릅니다.  
  
## 문자열 항목 함수  
 .NET Framework 문자열 메서드 및 속성이 모든 항목 값에 작동 수 있습니다.  에 대 한 <xref:System.String> 메서드의 메서드 이름을 지정 합니다.  에 대 한 <xref:System.String> 속성은 속성 이름 "get\_" 후 지정 합니다.  
  
 여러 문자열을 한 항목에 대해 각 문자열에서 문자열 메서드 또는 속성을 실행 합니다.  
  
 다음 예제에서는 이러한 문자열 항목 함수를 사용 하는 방법을 보여 줍니다.  
  
```  
<ItemGroup>  
    <theItem Include="andromeda;tadpole;cartwheel" />  
</ItemGroup>  
  
<Target Name = "go">  
    <Message Text="IndexOf  @(theItem->IndexOf('r'))" />  
    <Message Text="Replace  @(theItem->Replace('tadpole', 'pinwheel'))" />  
    <Message Text="Length   @(theItem->get_Length())" />  
    <Message Text="Chars    @(theItem->get_Chars(2))" />  
</Target>  
  
  <!--  
  Output:  
    IndexOf  3;-1;2  
    Replace  andromeda;pinwheel;cartwheel  
    Length   9;7;9  
    Chars    d;d;r  
  -->  
```  
  
## 항목 함수 내장  
 아래 표에서는 항목에 사용할 수 있는 내장 함수를 보여 줍니다.  
  
|Function|예제|설명|  
|--------------|--------|--------|  
|`Count`|`@(MyItem->Count())`|있는 항목의 개수를 반환합니다.|  
|`DirectoryName`|`@(MyItem->DirectoryName())`|에 해당 하는 반환 `Path.DirectoryName` 각 항목에 대해.|  
|`Distinct`|`@(MyItem->Distinct())`|고유한 반환 항목 `Include` 값입니다.  메타 데이터는 무시 됩니다.  비교 시 대\/소문자는 구분되지 않습니다.|  
|`DistinctWithCase`|`@(MyItem->DistinctWithCase())`|고유한 반환 항목 `itemspec` 값입니다.  메타 데이터는 무시 됩니다.  비교 시 대\/소문자가 구분됩니다.|  
|`Reverse`|`@(MyItem->Reverse())`|반대 순서로 항목을 반환합니다.|  
|`AnyHaveMetadataValue`|`@(MyItem->AnyHaveMetadataValue("MetadataName", "MetadataValue"))`|반환 된 `boolean` 항목에 지정 된 메타 데이터 이름과 값이 있는지 여부를 나타냅니다.  비교 시 대\/소문자는 구분되지 않습니다.|  
|`ClearMetadata`|`@(MyItem->ClearMetadata())`|항목 삭제 해당 메타 데이터를 반환 합니다.  만 `itemspec` 유지 됩니다.|  
|`HasMetadata`|`@(MyItem->HasMetadataValue("MetadataName")`|지정 된 메타 데이터 이름이 들어 있는 항목을 반환 합니다.  비교 시 대\/소문자는 구분되지 않습니다.|  
|`Metadata`|`@(MyItem->Metadata("MetadataName"))`|메타 데이터 이름을 가진 메타 데이터의 값을 반환 합니다.|  
|`WithMetadataValue`|`@(MyItem->WithMetadataValue("MetadataName", "MetadataValue")`|지정 된 메타 데이터 이름과 값을 갖는 항목을 반환 합니다.  비교 시 대\/소문자는 구분되지 않습니다.|  
  
 다음 예제에서는 내장 항목 함수를 사용 하는 방법을 보여 줍니다.  
  
```  
<ItemGroup>  
    <TheItem Include="first">  
        <Plant>geranium</Plant>  
    </TheItem>  
    <TheItem Include="second">  
        <Plant>algae</Plant>  
    </TheItem>  
    <TheItem Include="third">  
        <Plant>geranium</Plant>  
    </TheItem>  
</ItemGroup>  
  
<Target Name="go">  
    <Message Text="MetaData:    @(TheItem->Metadata('Plant'))" />  
    <Message Text="HasMetadata: @(theItem->HasMetadata('Plant'))" />  
    <Message Text="WithMetadataValue: @(TheItem->WithMetadataValue('Plant', 'geranium'))" />  
    <Message Text=" " />  
    <Message Text="Count:   @(theItem->Count())" />  
    <Message Text="Reverse: @(theItem->Reverse())" />  
</Target>  
  
  <!--   
  Output:  
    MetaData:    geranium;algae;geranium  
    HasMetadata: first;second;third  
    WithMetadataValue: first;third  
  
    Count:   3  
    Reverse: third;second;first  
  -->  
```  
  
## 참고 항목  
 [항목](../msbuild/msbuild-items.md)