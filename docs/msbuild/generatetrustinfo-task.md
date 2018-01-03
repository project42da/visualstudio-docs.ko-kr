---
title: "GenerateTrustInfo 작업 | Microsoft Docs"
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
- MSBuild, GenerateTrustInfo task
- GenerateTrustInfo task [MSBuild]
ms.assetid: 3ca60816-4bb0-4fef-ae43-ca0bfb63def3
caps.latest.revision: "4"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 614ace0800393b6c584da4cf4d85edfa7ea11b33
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="generatetrustinfo-task"></a>GenerateTrustInfo 작업
기본 매니페스트, `TargetZone` 및 `ExcludedPermissions` 매개 변수에서 응용 프로그램 신뢰를 생성합니다.  
  
## <a name="parameters"></a>매개 변수  
 다음 표에서는 `GenerateTrustInfo` 작업의 매개 변수에 대해 설명합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`ApplicationDependencies`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 종속 어셈블리를 지정합니다.|  
|`BaseManifest`|선택적 <xref:Microsoft.Build.Framework.ITaskItem> 매개 변수입니다.<br /><br /> 응용 프로그램 신뢰를 생성할 기본 매니페스트를 지정합니다.|  
|`ExcludedPermissions`|선택적 `String` 매개 변수입니다.<br /><br /> 영역 기본 권한 집합에서 제외할 하나 이상의 세미콜론으로 구분된 권한 ID 값을 지정합니다.|  
|`TargetZone`|선택적 `String` 매개 변수입니다.<br /><br /> 컴퓨터 정책에서 가져온 영역 기본 권한 집합을 지정합니다.|  
|`TrustInfoFile`|필수 <xref:Microsoft.Build.Framework.ITaskItem> 출력 매개 변수입니다.<br /><br /> 응용 프로그램 보안 신뢰 정보가 포함된 파일을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 작업은 표에 나열된 매개 변수 외에, <xref:Microsoft.Build.Utilities.Task> 클래스에서 직접 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수도 상속합니다. 이러한 추가 매개 변수 및 해당 설명이 포함된 목록은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)