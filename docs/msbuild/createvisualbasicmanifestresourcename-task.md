---
title: "CreateVisualBasicManifestResourceName 작업 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CreateVisualBasicManifestResourceName task
- CreateVisualBasicManifestResourceName task [MSBuild]
ms.assetid: 251c47b9-de32-414b-a138-bf45290af12e
caps.latest.revision: 8
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 5edc245c56e198b974f9f406c42a4e0340f266d8
ms.lasthandoff: 02/22/2017

---
# <a name="createvisualbasicmanifestresourcename-task"></a>CreateVisualBasicManifestResourceName 작업
지정된 .resx 파일 이름 또는 기타 리소스에서 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 스타일 매니페스트 이름을 만듭니다.  
  
## <a name="parameters"></a>매개 변수  
 다음 표에서는 [CreateVisualBasicManifestResourceName 작업](../msbuild/createvisualbasicmanifestresourcename-task.md)의 매개 변수에 대해 설명합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`ManifestResourceNames`|<xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 읽기 전용 매개 변수입니다.<br /><br /> 결과 매니페스트 이름입니다.|  
|`ResourceFiles`|필수 `String` 매개 변수입니다.<br /><br /> 리소스 파일의 이름입니다. 이 이름에서 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 매니페스트 이름을 만듭니다.|  
|`RootNamespace`|선택적 `String` 매개 변수입니다.<br /><br /> 일반적으로 프로젝트 파일에서 가져온 리소스 파일의 루트 네임스페이스입니다. `null`일 수 있습니다.|  
|`PrependCultureAsDirectory`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 문화권 이름이 매니페스트 리소스 이름 바로 앞에 디렉터리 이름으로 추가됩니다. 기본값은 `true`입니다.|  
|`ResourceFilesWithManifestResourceNames`|선택적 읽기 전용 `String` 출력 매개 변수입니다.<br /><br /> 이제 매니페스트 리소스 이름을 포함하는 리소스 파일의 이름을 반환합니다.|  
  
## <a name="remarks"></a>설명  
 [CreateVisualBasicManifestResourceName 작업](../msbuild/createvisualbasicmanifestresourcename-task.md)은 지정된 .resx 또는 기타 리소스 파일에 할당할 적절한 매니페스트 리소스 이름을 결정합니다. 이 작업은 리소스 파일에 대한 논리적 이름을 제공한 후 출력 매개 변수에 메타데이터로 추가합니다.  
  
 이 작업은 위에 나와 있는 매개 변수 외에 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다. 이 클래스는 <xref:Microsoft.Build.Utilities.Task> 클래스에서 매개 변수를 상속합니다. 이러한 추가 매개 변수 및 해당 설명이 포함된 목록은 [TaskExtension 기본 클래스](../msbuild/taskextension-base-class.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)
