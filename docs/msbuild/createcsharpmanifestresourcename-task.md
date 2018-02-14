---
title: "CreateCSharpManifestResourceName 작업 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CreateCSharpManifestResourceName task
- CreateCSharpManifestResourceName task [MSBuild]
ms.assetid: 2ace88c1-d757-40a7-8158-c1d3f5ff0511
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0b178ce637c53f01ca53df89f82995dfdcfc8258
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="createcsharpmanifestresourcename-task"></a>CreateCSharpManifestResourceName 작업
지정된 .resx 파일 이름 또는 기타 리소스에서 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 스타일 매니페스트 이름을 만듭니다.  
  
## <a name="parameters"></a>매개 변수  
 다음 표에서는 [CreateCSharpManifestResourceName 작업](../msbuild/createcsharpmanifestresourcename-task.md)의 매개 변수에 대해 설명합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`ManifestResourceNames`|<xref:Microsoft.Build.Framework.ITaskItem> `[]` 읽기 전용 출력 매개 변수입니다.<br /><br /> 결과 매니페스트 이름입니다.|  
|`ResourceFiles`|필수 `String` 매개 변수입니다.<br /><br /> 리소스 파일의 이름입니다. 이 이름에서 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 매니페스트 이름을 만듭니다.|  
|`RootNamespace`|선택적 `String` 매개 변수입니다.<br /><br /> 일반적으로 프로젝트 파일에서 가져온 리소스 파일의 루트 네임스페이스입니다. `null`일 수 있습니다.|  
|`PrependCultureAsDirectory`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 문화권 이름이 매니페스트 리소스 이름 바로 앞에 디렉터리 이름으로 추가됩니다. 기본값은 `true`입니다.|  
|`ResourceFilesWithManifestResourceNames`|선택적 읽기 전용 `String` 출력 매개 변수입니다.<br /><br /> 이제 매니페스트 리소스 이름을 포함하는 리소스 파일의 이름을 반환합니다.|  
  
## <a name="remarks"></a>설명  
 [CreateVisualBasicManifestResourceName 작업](../msbuild/createvisualbasicmanifestresourcename-task.md)은 지정된 .resx 또는 기타 리소스 파일에 할당할 적절한 매니페스트 리소스 이름을 결정합니다. 이 작업은 리소스 파일에 대한 논리적 이름을 제공한 후 출력 매개 변수에 메타데이터로 추가합니다.  
  
 이 작업은 위에 나와 있는 매개 변수 외에 <xref:Microsoft.Build.Utilities.Task> 클래스에서 직접 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수도 상속합니다. 이러한 추가 매개 변수 및 해당 설명이 포함된 목록은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)