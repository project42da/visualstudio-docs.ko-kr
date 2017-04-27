---
title: "Task Base Class | Microsoft Docs"
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
ms.assetid: 6c3f6238-b9f0-4325-b8b0-de61090bd0a2
caps.latest.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 6
---
# Task Base Class
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

많은 작업은 궁극적으로 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속합니다.  이 클래스는 매개 변수에서 파생되는 작업에 해당 매개 변수 몇 개를 추가합니다.  이러한 매개 변수는 이 문서에 나열되어 있습니다.  
  
## 매개 변수  
 다음 표에서는 이 기본 클래스의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|선택적 <xref:Microsoft.Build.Framework.IBuildEngine> 매개 변수입니다.<br /><br /> 작업에 사용할 수 있는 빌드 엔진 인터페이스를 지정합니다.  빌드 엔진에서는 작업에서 빌드 엔진으로 다시 호출할 수 있도록 이 매개 변수를 자동으로 설정합니다.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|선택적 <xref:Microsoft.Build.Framework.IBuildEngine2> 매개 변수입니다.<br /><br /> 작업에 사용할 수 있는 빌드 엔진 인터페이스를 지정합니다.  빌드 엔진에서는 작업에서 빌드 엔진으로 다시 호출할 수 있도록 이 매개 변수를 자동으로 설정합니다.<br /><br /> 이는 이 클래스에서 상속하는 작업 작성자가 값을 `IBuildEngine`에서 `IBuildEngine2`로 캐스트하지 않아도 되도록 해 주는 편의 속성입니다.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|선택적 <xref:Microsoft.Build.Framework.IBuildEngine3> 매개 변수입니다.<br /><br /> 호스트에서 제공하는 빌드 엔진 인터페이스를 지정합니다.|  
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|선택적 <xref:Microsoft.Build.Framework.ITaskHost> 매개 변수입니다.<br /><br /> 호스트 개체 인스턴스를 지정합니다\(null일 수 있음\).  호스트 IDE에서 호스트 개체를 이 특정 작업과 연결한 경우 빌드 엔진에서 이 속성을 설정합니다.|  
|<xref:Microsoft.Build.Utilities.Task.Log%2A>|선택적 <xref:Microsoft.Build.Utilities.TaskLoggingHelper> 읽기 전용 매개 변수입니다.<br /><br /> 로깅 도우미 개체입니다.|  
  
## 참고 항목  
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [작업](../msbuild/msbuild-tasks.md)