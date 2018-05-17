---
title: XmlPoke 작업 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XmlPoke task [MSBuild]
- MSBuild, XmlPoke task
ms.assetid: 6ba1953c-be3b-4df8-8561-e133408f8270
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3295a5aee03badc52b980183e88f484e0d4bcc3a
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="xmlpoke-task"></a>XmlPoke 작업

XML 파일로의 XPath 쿼리에 의해 지정된 대로 값을 반환합니다.

## <a name="parameters"></a>매개 변수

 다음 표에서는 `XmlPoke` 작업의 매개 변수에 대해 설명합니다.
  
|매개 변수|설명|
|---------------|-----------------|
|`Namespaces`|선택적 `String` 매개 변수입니다.<br /><br /> XPath 쿼리 접두사에 대한 네임스페이스를 지정합니다.|
|`Query`|선택적 `String` 매개 변수입니다.<br /><br /> XPath 쿼리를 지정합니다.|
|`Value`|필수 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> 지정된 경로에 삽입할 값을 지정합니다.|
|`XmlInputPath`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> XML 입력을 파일 경로로 지정합니다.|

## <a name="remarks"></a>설명

 이 작업은 표에 나열된 매개 변수 외에, <xref:Microsoft.Build.Utilities.Task> 클래스에서 직접 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수도 상속합니다. 이러한 추가 매개 변수 및 해당 설명이 포함된 목록은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

 [작업](../msbuild/msbuild-tasks.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)