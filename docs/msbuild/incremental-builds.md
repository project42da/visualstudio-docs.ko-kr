---
title: "증분 빌드 | Microsoft Docs"
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
  - "msbuild, 증분 빌드"
ms.assetid: 325e28c7-4838-4e3f-b672-4586adc7500c
caps.latest.revision: 8
caps.handback.revision: 8
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 증분 빌드
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

증분 빌드는 해당 입력 파일과 비교했을 때 최신 상태인 출력 파일이 있는 대상은 실행되지 않도록 최적화된 빌드입니다.  대상 요소에는 대상이 입력으로 예상하는 항목을 나타내는 `Inputs` 특성과 대상이 출력으로 생성하는 항목을 나타내는 `Outputs` 특성이 모두 포함될 수 있습니다.  MSBuild는 이러한 특성의 값 사이에서 일대일 매핑을 찾으려고 합니다.  일대일 매핑이 있을 경우 MSBuild는 모든 입력 항목의 타임스탬프를 해당 출력 항목의 타임스탬프와 비교합니다.  일대일 매핑이 없는 출력 파일은 모든 입력 파일과 비교됩니다.  출력 파일이 해당 입력 파일과 만들어진 시기가 같거나 보다 이후인 경우에는 항목이 최신 상태인 것으로 간주됩니다.  
  
 모든 출력 항목이 최신 상태이면 MSBuild는 대상을 건너뜁니다.  이러한 대상 *증분 빌드*는 빌드 속도를 획기적으로 높일 수 있습니다.  일부 파일만 최신 상태이면 MSBuild는 대상을 실행하지만 최신 항목은 건너뛰어 모든 항목을 최신 상태로 만듭니다.  이러한 작업을 *부분 증분 빌드*라고 합니다.  
  
 일대일 매핑은 일반적으로 항목 변환을 통해 생성됩니다.  자세한 내용은 [변환](../msbuild/msbuild-transforms.md)을 참조하십시오.  
  
 다음 대상을 살펴보십시오.  
  
```  
<Target Name="Backup" Inputs="@(Compile)"   
    Outputs="@(Compile->'$(BackupFolder)%(Identity).bak')">  
    <Copy SourceFiles="@(Compile)" DestinationFiles=  
        "@(Compile->'$(BackupFolder)%(Identity).bak')" />  
</Target>  
```  
  
 `Compile` 항목 형식으로 표시되는 파일 집합이 백업 디렉터리에 복사됩니다.  백업 파일의 확장명은 .bak입니다.  `Compile` 항목 형식으로 표시되는 파일 또는 해당 백업 파일이 대상 백업 작업을 실행한 후에도 삭제 또는 수정되지 않으면 후속 빌드에서 대상 백업 작업을 건너뛰게 됩니다.  
  
## 출력 유추  
 MSBuild는 대상의 `Inputs` 특성과 `Outputs` 특성을 비교하여 대상을 실행해야 하는지 여부를 결정합니다.  이상적으로는, 증분 빌드가 완료된 후 존재하는 파일 집합이 연결 대상의 실행 여부와 관계없이 동일하게 유지되어야 합니다.  작업에 의해 만들어지거나 변경되는 속성 및 항목이 빌드에 영향을 줄 수 있으므로 MSBuild는 해당 값을 유추해야 하며 이는 이러한 값에 영향을 주는 대상을 건너뛰는 경우에도 마찬가지입니다.  이를 *출력 유추*라고 합니다.  
  
 다음과 같은 세 가지 경우가 있습니다.  
  
-   대상에 `false`인 `Condition` 특성이 있는 경우.  이 경우 대상이 실행되지 않고 빌드에 영향을 주지 않습니다.  
  
-   대상에 최신 상태가 아닌 출력이 있어 출력을 최신 상태로 만들기 위해 대상이 실행되는 경우  
  
-   대상에 최신 상태가 아닌 출력이 없어 대상을 건너뛰는 경우.  MSBuild는 대상을 확인하여 대상이 실행된 것처럼 항목 및 속성을 변경합니다.  
  
 증분 컴파일을 지원하려면 작업을 통해 모든 `Output` 요소의 `TaskParameter` 특성 값이 작업 입력 매개 변수와 같은지 확인해야 합니다.  예를 들면 다음과 같습니다.  
  
```  
<CreateProperty Value="123">  
    <Output PropertyName="Easy" TaskParameter="Value" />  
</CreateProperty>  
```  
  
 위 코드를 실행하면 대상을 실행하는지, 아니면 건너뛰는지에 관계없이 "123"이라는 값이 지정된 Easy 속성이 만들어집니다.  
  
```  
<CreateItem Include="a.cs;b.cs">  
    <Output ItemName="Simple" TaskParameter="Include" />  
</CreateItem>  
```  
  
 위 코드를 실행하면 대상을 실행하는지, 아니면 건너뛰는지에 관계없이 "a.cs"와 "b.cs"라는 두 항목이 포함된 항목 형식 Simple이 만들어집니다.  
  
 MSBuild 3.5에서 출력 유추는 대상의 항목 및 속성 그룹에 대해 자동으로 수행됩니다.  `CreateItem` 작업은 대상에 필요하지 않으며 사용하지 말아야 합니다.  또한 `CreateProperty` 작업은 대상의 실행 여부를 확인하기 위해서만 대상에 사용해야 합니다.  
  
## 대상의 실행 여부 확인  
 출력 유추로 인해 `CreateProperty` 작업을 대상에 추가해야 대상의 실행 여부를 확인할 수 있도록 속성 및 항목을 검사할 수 있습니다.  `CreateProperty` 작업을 대상에 추가하고 이 대상에 `TaskParameter`가 "ValueSetByTask"인 `Output` 요소를 지정합니다.  
  
```  
<CreateProperty Value="true">  
    <Output TaskParameter="ValueSetByTask" PropertyName="CompileRan" />  
</CreateProperty>  
```  
  
 위 코드를 실행하면 CompileRan 속성이 만들어지고 `true` 값이 지정됩니다. 이때 대상을 실행해야 합니다.  대상을 건너뛰면 CompileRan이 만들어지지 않습니다.  
  
## 참고 항목  
 [대상](../msbuild/msbuild-targets.md)