---
title: "XmlPoke 작업 | Microsoft Docs"
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
- XmlPoke task [MSBuild]
- MSBuild, XmlPoke task
ms.assetid: 6ba1953c-be3b-4df8-8561-e133408f8270
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3b189fbaa7cb03b8a20f67c0f57d19fa9c304c1b
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="xmlpoke-task"></a>XmlPoke 작업
XML 파일로의 XPath 쿼리에 의해 지정된 대로 값을 반환합니다.  
  
## <a name="parameters"></a>매개 변수  
 다음 표에서는 `XmlPoke` 작업의 매개 변수에 대해 설명합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Namespaces`|선택적 `String` 매개 변수입니다.<br /><br /> XPath 쿼리 접두사에 대한 네임스페이스를 지정합니다.|  
|`Query`|선택적 `String` 매개 변수입니다.<br /><br /> XPath 쿼리를 지정합니다.|  
|`Value`|필수 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> 출력 파일을 지정합니다.|  
|`XmlInputPath`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> XML 입력을 파일 경로로 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 작업은 표에 나열된 매개 변수 외에, <xref:Microsoft.Build.Utilities.Task> 클래스에서 직접 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수도 상속합니다. 이러한 추가 매개 변수 및 해당 설명이 포함된 목록은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)