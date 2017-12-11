---
title: "XmlPeek 작업 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XmlPeek task [MSBuild]
- MSBuild, XmlPeek task
ms.assetid: 19196031-a3bc-41b5-9c4a-f2572630e179
caps.latest.revision: "4"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 7238e549011d5f80ce2c8f006f56f6bb0f2de58d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="xmlpeek-task"></a>XmlPeek 작업
XML 파일에서 XPath 쿼리에 의해 지정된 대로 값을 반환합니다.  
  
## <a name="parameters"></a>매개 변수  
 다음 표에서는 `XmlPeek` 작업의 매개 변수에 대해 설명합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`Namespaces`|선택적 `String` 매개 변수입니다.<br /><br /> XPath 쿼리 접두사에 대한 네임스페이스를 지정합니다.|  
|`Query`|선택적 `String` 매개 변수입니다.<br /><br /> XPath 쿼리를 지정합니다.|  
|`Result`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 이 작업으로 반환되는 결과를 포함합니다.|  
|`XmlContent`|선택적 `String` 매개 변수입니다.<br /><br /> XML 입력을 문자열로 지정합니다.|  
|`XmlInputPath`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> XML 입력을 파일 경로로 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 작업은 표에 나열된 매개 변수 외에, <xref:Microsoft.Build.Utilities.Task> 클래스에서 직접 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수도 상속합니다. 이러한 추가 매개 변수 및 해당 설명이 포함된 목록은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)