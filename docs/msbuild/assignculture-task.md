---
title: "AssignCulture Task | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#AssignCulture"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MSBuild, AssignCulture task"
  - "AssignCulture task [MSBuild]"
ms.assetid: 8f8314cc-82a6-4f16-a62d-b9f0d1d5e274
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 10
---
# AssignCulture Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 작업에서는 파일 이름의 일부에 유효한 .NET culture 식별자 문자열이 포함되어 있는 항목의 목록을 전달받고, 해당 culture 식별자가 포함된 `Culture`라는 메타데이터가 있는 항목을 생성합니다.  예를 들어, 파일 이름 Form1.fr\-fr.resx에는 "fr\-fr"이라는 culture 식별자가 삽입되어 있으므로 이 작업에서는 메타데이터 `Culture`가 `fr-fr`인 동일한 파일 이름이 있는 항목을 생성합니다.  또한 이 작업은 파일 이름에서 culture를 제거한 파일 이름 목록을 생성합니다.  
  
## 작업 매개 변수  
 다음 표에서는 `AssignCulture` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`AssignedFiles`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> `Files` 매개 변수에서 받은 항목의 목록이 각 항목에 `Culture` 메타데이터 엔트리가 추가된 상태로 들어 있습니다.<br /><br /> `Files` 매개 변수에서 가져오는 항목에 이미 `Culture` 메타데이터 엔트리가 들어 있으면 원래 메타데이터 엔트리가 사용됩니다.<br /><br /> 이 작업에서는 파일 이름에 유효한 문화권 식별자가 포함되어 있는 경우에만 `Culture` 메타데이터 엔트리를 할당합니다.  culture 식별자는 파일 이름에서 마지막 두 개의 마침표 사이에 있어야 합니다.|  
|`AssignedFilesWithCulture`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> `Culture` 메타데이터 엔트리가 있는 `AssignedFiles` 매개 변수의 하위 항목 집합이 들어 있습니다.|  
|`AssignedFilesWithNoCulture`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> `Culture` 메타데이터 엔트리가 없는 `AssignedFiles` 매개 변수의 하위 항목 집합이 들어 있습니다.|  
|`CultureNeutralAssignedFiles`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 파일 이름에서 culture가 제거되어 있다는 점을 제외하고는 `AssignedFiles` 매개 변수에서 생성한 것과 동일한 항목 집합이 들어 있습니다.<br /><br /> 이 작업에서는 유효한 culture 식별자인 경우에만 파일 이름에서 culture를 제거합니다.|  
|`Files`|필수적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> culture를 할당할, culture 이름이 포함된 파일 목록을 지정합니다.|  
  
## 설명  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `ResourceFiles` 항목 컬렉션과 함께 `AssignCulture` 작업을 실행합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <ResourceFiles Include="MyResource1.fr.resx"/>  
        <ResourceFiles Include="MyResource2.XX.resx"/>  
    </ItemGroup>  
  
    <Target Name="Culture">  
        <AssignCulture  
            Files="@(ResourceFiles)"  
            <Output TaskParameter="AssignedFiles"  
                ItemName="OutAssignedFiles"/>  
            <Output TaskParameter="AssignedFilesWithCulture"  
                ItemName="OutAssignedFilesWithCulture"/>  
            <Output TaskParameter="AssignedFilesWithNoCulture"  
                ItemName="OutAssignedFilesWithNoCulture"/>  
            <Output TaskParameter="CultureNeutralAssignedFiles"  
                ItemName="OutCultureNeutralAssignedFiles"/>  
        </AssignCulture>  
    </Target>  
</Project>  
```  
  
 다음 표에서는 작업을 실행한 후의 출력 항목에 대한 값을 설명합니다.  항목 메타데이터는 항목 뒤에 괄호로 표시되어 있습니다.  
  
|항목 컬렉션|내용|  
|------------|--------|  
|`OutAssignedFiles`|`MyResource1.fr.resx (Culture="fr")`<br /><br /> `MyResource2.XX.resx` \(추가 메타데이터 없음\)|  
|`OutAssignedFilesWithCulture`|`MyResource1.fr.resx (Culture="fr")`|  
|`OutAssignedFilesWithNoCulture`|`MyResource2.XX.resx` \(추가 메타데이터 없음\)|  
|`OutCultureNeutralAssignedFiles`|`MyResource1.resx (Culture="fr")`<br /><br /> `MyResource2.XX.resx (`추가 메타데이터 없음\)|  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)