---
title: "방법: 대상 및 작업 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 92814100-392a-471d-96fd-e26f637d6cc2
caps.latest.revision: 5
caps.handback.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 방법: 대상 및 작업 구성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

선택한 MSBuild 작업은 개발 컴퓨터의 환경에 관계 없이 대상 환경에서 실행 되도록 설정할 수 있습니다.  예를 들어, 64 비트 컴퓨터를 사용 하 여 해당 대상을 32 비트 아키텍처는 응용 프로그램을 빌드하는 경우 선택한 작업 32 비트 프로세스에서 실행 됩니다.  
  
> [!NOTE]
>  빌드 작업을 작성 하는 경우에.C\# 또는 Visual Basic 같은 언어를 NET 하 고 하지 않는 네이티브 리소스를 사용 하거나 도구, 다음이 실행 될 대상 컨텍스트에서 적응 하지 않고 있습니다.  
  
## UsingTask 특성 및 작업 매개 변수  
 다음 `UsingTask` 특성이 특정 빌드 프로세스에서 작업의 모든 작업에 영향을 줍니다.  
  
-   `Runtime` 특성에 있는 경우 공용 언어 런타임 \(CLR\) 버전을 설정 하는 및 이러한 값 중 하나를 사용할 수 있습니다: `CLR2`, `CLR4`, `CurrentRuntime`, 또는 `*` \(런타임\).  
  
-   `Architecture` 특성에 있는 경우 플랫폼 및 비트를 설정 하는 및 다음이 값 중 하나를 사용할 수 있습니다: `x86`, `x64`, `CurrentArchitecture`, 또는 `*` \(아키텍처\).  
  
-   `TaskFactory` 특성이 있을 경우 설정 만듭니다 및 작업 인스턴스가 실행 되 고 값만을 사용 하는 작업 팩토리의 `TaskHostFactory`.  자세한 내용은이 문서의 뒷부분에 나오는 작업 팩토리 섹션을 참조 하십시오.  
  
```  
<UsingTask TaskName="SimpleTask"   
   Runtime="CLR2"  
   Architecture="x86"  
   AssemblyFile="$(MSBuildToolsPath)\Microsoft.Build.Tasks.v3.5.dll" />  
```  
  
 수도 있습니다의 `MSBuildRuntime` 및 `MSBuildArchitecture` 개별 작업의 대상 컨텍스트를 설정 하는 매개 변수입니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
   <Target Name="MyTarget">  
      <SimpleTask MSBuildRuntime="CLR2" MSBuildArchitecture= "x86"/>  
   </Target>  
</Project>  
```  
  
 MSBuild 작업을 실행 하기 전에, 일치를 보이는 `UsingTask` 는 동일한 대상 컨텍스트를가지고 있습니다.  지정 된 매개 변수는 `UsingTask` 일치 하는 해당 작업이 아닌로 간주 됩니다.  작업이 있지만 해당 하는 지정 된 매개 변수 `UsingTask` 도 일치할 것으로 간주 됩니다.  매개 변수 값을 지정 하지 않은 경우는 `UsingTask` 작업 기본 값 또는 `*` \(매개 변수\)입니다.  
  
> [!WARNING]
>  두 개 이상의 경우 `UsingTask` 존재와 모두 일치 하는 `TaskName`, `Runtime`, 및 `Architecture` 특성을 마지막으로 평가 될 대신 다른.  
  
 MSBuild 작업의 매개 변수를 설정 하는 경우 찾으려고 시도 `UsingTask` 는 이러한 매개 변수를 일치 하 또는 적어도 충돌 하 게 아닙니다.  두 개 이상의 `UsingTask` 같은 작업의 대상 컨텍스트를 지정할 수 있습니다.  예를 들어, 다른 실행 가능한 다른 대상 환경에 대 한 작업에이 유사할 수 있습니다.  
  
```  
<UsingTask TaskName="MyTool"   
   Runtime="CLR2"  
   Architecture="x86"  
   AssemblyFile="$(MyToolsPath)\MyTool.v2.0.dll" />  
  
<UsingTask TaskName="MyTool"   
   Runtime="CLR4"  
   Architecture="x86"  
   AssemblyFile="$(MyToolsPath)\MyTool.4.0.dll" />  
  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
   <Target Name="MyTarget">  
      <MyTool MSBuildRuntime="CLR2" MSBuildArchitecture= "x86"/>  
   </Target>  
</Project>  
  
```  
  
## 작업 공장  
 이 작업을 실행 하기 전에 Msbuild는 현재 소프트웨어 컨텍스트에서 실행 하도록 지정 된 여부를 확인 합니다 확인 합니다.  작업 이므로 지정 된 경우 MSBuild 현재 프로세스에서 실행 되는 Assemblytaskfactory를 전달 합니다. 그렇지 않으면 MSBuild 작업 작업 대상 컨텍스트에 일치 하는 프로세스에서 실행 되는 Taskhostfactory를 전달 합니다.  현재 컨텍스트와 대상 컨텍스트를 일치 하는 경우에 작업이 실행 되도록 할 수 있습니다\-설정 하 여 out\-of\-process \(대 한 격리, 보안, 또는 다른 이유로\) `TaskFactory` 에 `TaskHostFactory`.  
  
```  
<UsingTask TaskName="MisbehavingTask"   
   TaskFactory="TaskHostFactory"  
   AssemblyFile="$(MSBuildToolsPath)\MyTasks.dll">  
</UsingTask>  
```  
  
## 존재 하지 않는 작업 매개 변수  
 와 같은 기타 작업 매개 `MSBuildRuntime` 및 `MSBuildArchitecture` 빌드 속성을 설정할 수 있습니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
   <PropertyGroup>  
      <FrameworkVersion>3.0</FrameworkVersion>  
   </PropertyGroup>  
   <Target Name="MyTarget">  
      <SimpleTask MSBuildRuntime="$(FrameworkVerion)" MSBuildArchitecture= "x86"/>  
   </Target>  
</Project>  
```  
  
 달리 다른 작업 매개 변수를 `MSBuildRuntime` 및 `MSBuildArchitecture` 작업에 표시 되지 않습니다.  실행 컨텍스트를 인식 하는 작업을 기록 하는 컨텍스트를 호출 하 여 테스트 해야를 합니다.NET Framework를 하거나 빌드 속성을 사용 하 여 컨텍스트 정보가 다른 작업 매개 변수를 통해 전달 합니다.  
  
> [!NOTE]
>  `UsingTask`도구 집합 및 환경 속성에서 특성을 설정할 수 있습니다.  
  
 `MSBuildRuntime` 및 `MSBuildArchitecture` 매개 변수를 대상 컨텍스트 있지만 가장 제한의 범위를 설정할 수 있는 가장 유연한 방법을 제공 합니다.  한편, 작업 인스턴스를 설정 하 고 작업을 실행 하려고 때까지 평가 되지 않습니다 때문에 값 평가 시간 및 빌드 시간에 모두 사용할 수 있는 속성의 전체 범위에서 파생할 수 있습니다.  반면, 이러한 매개 변수에 특정 인스턴스를 작업의 특정 대상에만 적용 됩니다.  
  
> [!NOTE]
>  작업 매개 변수는 부모 노드의 컨텍스트에, 호스트의 컨텍스트에서 않습니다 평가 됩니다.런타임 또는 아키텍처\-종속 \(프로그램 파일 위치\)와 같은 환경 변수를 부모 노드를 일치 하는 값을 평가 합니다.  그러나 같은 환경 변수를 작업에서 직접 읽으면 제대로 호스트의 컨텍스트에서 계산 됩니다.  
  
## 참고 항목  
 [대상 및 작업 구성](../msbuild/configuring-targets-and-tasks.md)