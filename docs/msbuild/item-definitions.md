---
title: "항목 정의 | Microsoft Docs"
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
  - "msbuild, 항목 정의"
ms.assetid: 8e3dc223-f9e5-4974-aa0e-5dc7967419cb
caps.latest.revision: 21
caps.handback.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 항목 정의
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 2.0에서는 [ItemGroup](../msbuild/itemgroup-element-msbuild.md) 요소를 사용하여 프로젝트 파일의 항목을 정적으로 선언할 수 있지만  메타데이터가 모든 항목에 대해 동일한 경우에도 항목 수준에만 메타데이터를 추가할 수 있습니다.  [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 3.5에서 시작하여, [ItemDefinitionGroup](../msbuild/itemdefinitiongroup-element-msbuild.md) 라는 프로젝트 요소가 이 한계를 극복합니다.  *ItemDefinitionGroup*을 사용하면 명명된 항목 형식의 모든 항목에 기본 메타데이터 값을 추가하는 항목 정의 집합을 정의할 수 있습니다.  
  
 *ItemDefinitionGroup* 요소는 프로젝트 파일의 [Project](../msbuild/project-element-msbuild.md) 요소 바로 뒤에 표시됩니다.  항목 정의는 다음과 같은 기능을 제공합니다.  
  
-   대상 밖에 있는 항목에 대한 전역 메타데이터 기본값을 정의할 수 있습니다.  즉, 동일한 메타데이터가 지정된 형식의 모든 항목에 적용됩니다.  
  
-   항목 형식에 여러 정의가 있을 수 있습니다.  항목 형식에 추가 메타데이터 사양을 추가하면 마지막 사양이 우선적으로 적용됩니다. 메타데이터는 속성과 동일한 가져오기 순서를 따릅니다.  
  
-   메타데이터를 누적할 수 있습니다.  예를 들어, CDefines 값은 설정하고 있는 속성에 따라 조건부로 누적됩니다.  예를 들면 `MT;STD_CALL;DEBUG;UNICODE`와 같습니다.  
  
-   메타데이터를 제거할 수 있습니다.  
  
-   조건을 사용하여 메타데이터의 포함 여부를 제어할 수 있습니다.  
  
## 항목 메타데이터 기본값  
 ItemDefinitionGroup에 정의된 항목 메타데이터는 단지 기본 메타데이터의 선언입니다.  메타데이터는 ItemGroup을 사용하여 메타데이터 값을 포함하는 항목을 정의할 경우에만 적용됩니다.  
  
> [!NOTE]
>  이 항목의 많은 예제에는 ItemDefinitionGroup 요소가 나오지만 해당 ItemGroup 정의는 혼동을 피하기 위해 생략되었습니다.  
  
 ItemGroup에 명시적으로 정의된 메타데이터는 ItemDefinitionGroup에 있는 메타데이터보다 우선합니다.  ItemDefinitionGroup에 있는 메타데이터는 ItemGroup에 있는 정의되지 않은 메타데이터에 대해서만 적용됩니다.  예를 들면 다음과 같습니다.  
  
```  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
        <n>n1</n>  
    </i>        
</ItemDefinitionGroup>  
<ItemGroup>  
    <i Include="a">  
        <o>o1</o>  
        <n>n2</n>  
    </i>  
</ItemGroup>  
```  
  
 이 예제에서 기본 메타데이터 "m"은 항목 "i"에 의해 명시적으로 정의되지 않으므로 항목 "i"에 적용됩니다.  그러나 기본 메타데이터 "n"은 항목 "i"에 의해 이미 정의되어 있으므로 항목 "i"에 적용되지 않습니다.  
  
> [!NOTE]
>  XML 요소 및 매개 변수 이름은 대\/소문자를 구분합니다.  항목 메타데이터 및 항목\/속성 이름은 대\/소문자를 구분하지 않습니다.  따라서 이름이 대\/소문자만 다른 ItemDefinitionGroup 항목은 동일한 ItemGroup으로 처리되어야 합니다.  
  
## 값 소스  
 ItemDefinitionGroup에 정의된 메타데이터 값은 다음과 같은 다양한 소스에서 가져올 수 있습니다.  
  
-   PropertyGroup 속성  
  
-   ItemDefinitionGroup 항목  
  
-   ItemDefinitionGroup 항목의 항목 변환  
  
-   환경 변수  
  
-   전역 속성\(MSBuild.exe 명령줄\)  
  
-   예약 속성  
  
-   ItemDefinitionGroup 항목의 잘 알려진 메타데이터  
  
-   CDATA 섹션 \<\!\[CDATA\[여기에 있는 내용은 구문 분석되지 않음\]\]\>  
  
> [!NOTE]
>  ItemDefinitionGroup 요소가 ItemGroup 요소보다 먼저 처리되기 때문에 ItemGroup의 항목 메타데이터는 ItemDefinitionGroup 메타데이터 선언에 도움이 되지 않습니다.  
  
## 누적 및 다중 정의  
 정의를 추가하거나 여러 ItemDefinitionGroup을 사용할 때는 다음 사항을 고려해야 합니다.  
  
-   추가 메타데이터 사양이 형식에 추가됩니다.  
  
-   마지막 사양이 우선적으로 적용됩니다.  
  
 여러 ItemDefinitionGroup이 있을 경우 이후의 각 사양을 통해 이전 정의에 해당 메타데이터가 추가됩니다.  예를 들면 다음과 같습니다.  
  
```  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
        <n>n1</n>  
    </i>  
</ItemDefinitionGroup>  
<ItemDefinitionGroup>  
    <i>  
        <o>o1</o>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 이 예제에서는 메타데이터 "o"가 "m"과 "n"에 추가됩니다.  
  
 또한 이전에 정의된 메타데이터 값이 추가될 수도 있습니다.  예를 들면 다음과 같습니다.  
  
```  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
    </i>  
</ItemDefinitionGroup>  
<ItemDefinitionGroup>  
    <i>  
        <m>%(m);m2</m>  
    </i>  
</ItemDefinitionGroup>    
```  
  
 이 예제에서는 메타데이터 "m"\(m1\)에 대해 이전에 정의된 값이 새 값\(m2\)에 추가되어 최종 값은 "m1;m2"입니다.  
  
> [!NOTE]
>  이것은 동일한 ItemDefinitionGroup에서도 발생할 수 있습니다.  
  
 이전에 정의된 메타데이터를 재정의하면 마지막 사양이 우선적으로 적용됩니다.  다음 예제에서는 메타데이터 "m"의 최종 값이 "m1"에서 "m1a"로 변경됩니다.  
  
```  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
    </i>  
</ItemDefinitionGroup>  
<ItemDefinitionGroup>  
    <i>  
        <m>m1a</m>  
    </i>  
</ItemDefinitionGroup>    
```  
  
## ItemDefinitionGroup의 조건 사용  
 ItemDefinitionGroup의 조건을 사용하여 메타데이터의 포함 여부를 제어할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
<ItemDefinitionGroup Condition="'$(Configuration)'=='Debug'">  
    <i>  
        <m>m1</m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 이 예제에서는 "Configuration" 속성의 값이 "Debug"일 경우에만 항목 "i"의 기본 메타데이터 "m1"이 포함됩니다.  
  
> [!NOTE]
>  조건에서는 로컬 메타데이터 참조만 지원됩니다.  
  
 이전 ItemDefinitionGroup에 정의된 메타데이터에 대한 참조는 정의 그룹이 아니라 항목에 로컬입니다.  즉, 참조 범위는 항목을 기준으로 결정됩니다.  예를 들면 다음과 같습니다.  
  
```  
<ItemDefinitionGroup>  
    <test>  
        <yes>1</yes>  
    </test>  
    <i>  
        <m Condition="'%(test.yes)'=='1'">m1</m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 이 예제에서는 항목 "i"가 Condition에 있는 항목 "test"를 참조합니다.  
  
## 메타데이터 재정의 및 삭제  
 ItemDefinitionGroup 요소에 정의된 메타데이터는 해당 메타데이터 값을 빈 값으로 설정하여 이후 ItemDefinitionGroup 요소에서 재정의할 수 있습니다.  또한 빈 값으로 설정하여 메타데이터 항목을 효과적으로 삭제할 수도 있습니다.  예를 들면 다음과 같습니다.  
  
```  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
    </i>  
</ItemDefinitionGroup>  
<ItemDefinitionGroup>  
    <i>  
        <m></m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 항목 "i"는 메타데이터 "m"을 여전히 포함하고 있지만 해당 값은 이제 비어 있습니다.  
  
## 메타데이터 범위  
 ItemDefinitionGroup은 정의된 위치에 관계없이 정의된 속성과 전역 속성에서 전역 범위를 갖습니다.  ItemDefinitionGroup의 기본 메타데이터 정의는 자체 참조될 수 있습니다.  예를 들어, 다음 예제에서는 단순 메타데이터 참조를 사용합니다.  
  
```  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
        <m>%(m);m2</m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 또한 다음과 같은 정규화된 메타데이터 참조를 사용할 수도 있습니다.  
  
```  
<ItemDefinitionGroup>  
    <i>  
      <m>m1</m>  
      <m>%(i.m);m2</m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 그러나 다음 예제는 올바르지 않습니다.  
  
```  
<ItemDefinitionGroup>  
    <i>  
        <m>m1</m>  
        <m>@(x)</m>  
    </i>  
</ItemDefinitionGroup>  
```  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 3.5부터는 ItemGroup도 자체 참조될 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
<ItemGroup>  
    <item Include="a">  
        <m>m1</m>  
        <m>%(m);m2</m>  
    </item>  
</ItemGroup>  
```  
  
## 참고 항목  
 [일괄 처리](../msbuild/msbuild-batching.md)