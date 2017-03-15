---
title: "GetReferenceAssemblyPaths Task | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 178ef49c-5dee-405b-a14b-a37f41dc0609
caps.latest.revision: 4
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 4
---
# GetReferenceAssemblyPaths Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

여러 프레임워크의 참조 어셈블리 경로를 반환합니다.  
  
## 매개 변수  
 다음 표에서는 `GetReferenceAssemblyPaths` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`ReferenceAssemblyPaths`|선택적 `String[]` 출력 매개 변수입니다.<br /><br /> `TargetFrameworkMoniker` 매개 변수를 기반으로 경로를 반환합니다.  `TargetFrameworkMoniker`가 null이거나 비어 있는 경우 이 경로는 `String.Empty`가 됩니다.|  
|`FullFrameworkReferenceAssemblyPaths`|선택적 `String[]` 출력 매개 변수입니다.<br /><br /> 모니커의 프로필 요소를 고려하지 않고, `TargetFrameworkMoniker` 매개 변수를 기반으로 경로를 반환합니다.  `TargetFrameworkMoniker`가 null이거나 비어 있는 경우 이 경로는 `String.Empty`가 됩니다.|  
|`TargetFrameworkMoniker`|선택적 `String` 매개 변수입니다.<br /><br /> 참조 어셈블리 경로에 연결된 대상 프레임워크 모니커를 지정합니다.|  
|`RootPath`|선택적 `String` 매개 변수입니다.<br /><br /> 참조 어셈블리 경로를 생성하는 데 사용할 루트 경로를 지정합니다.|  
|`BypassFrameworkInstallChecks`|선택적 [Boolean](assetId:///Boolean?qualifyHint=False&autoUpgrade=True) 매개 변수입니다.<br /><br /> `true`인 경우 대상 프레임워크에 따라 특정 런타임 프레임워크가 설치되었는지 확인하기 위해 `GetReferenceAssemblyPaths`에서 수행하는 단순 검사를 건너뜁니다.|  
|`TargetFrameworkMonikerDisplayName`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 대상 프레임워크 모니커의 표시 이름을 지정합니다.|  
  
## 설명  
 이 표에 나열된 매개 변수를 갖는 것 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)