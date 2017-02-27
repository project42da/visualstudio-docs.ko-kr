---
title: "GenerateTrustInfo Task | Microsoft Docs"
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
helpviewer_keywords: 
  - "MSBuild, GenerateTrustInfo task"
  - "GenerateTrustInfo task [MSBuild]"
ms.assetid: 3ca60816-4bb0-4fef-ae43-ca0bfb63def3
caps.latest.revision: 4
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 4
---
# GenerateTrustInfo Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

기본 메니페스트와 `TargetZone` 및 `ExcludedPermissions` 매개 변수로부터 응용 프로그램 신뢰를 생성합니다.  
  
## 매개 변수  
 다음 표에서는 `GenerateTrustInfo` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`ApplicationDependencies`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 종속 어셈블리를 지정합니다.|  
|`BaseManifest`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> 응용 프로그램 신뢰를 생성할 기본 매니페스트를 지정합니다.|  
|`ExcludedPermissions`|선택적 `String` 매개 변수입니다.<br /><br /> 영역 기본 권한 집합에서 제외될 하나 이상의 권한 ID 값\(세미콜론으로 구분\)을 지정합니다.|  
|`TargetZone`|선택적 `String` 매개 변수입니다.<br /><br /> 컴퓨터 정책에서 가져온 영역 기본 권한 집합을 지정합니다.|  
|`TrustInfoFile`|필수적 <xref:Microsoft.Build.Framework.ITaskItem> 출력 매개 변수입니다.<br /><br /> 응용 프로그램 보안 신뢰 정보를 포함하는 파일을 지정합니다.|  
  
## 설명  
 이 표에 나열된 매개 변수를 갖는 것 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)