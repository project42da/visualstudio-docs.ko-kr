---
title: "FormatVersion Task | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
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
ms.assetid: 96e692f6-b581-46ca-8cc9-441a1861e371
caps.latest.revision: 5
caps.handback.revision: 5
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# FormatVersion Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

버전 번호에 수정 번호를 추가합니다.  
  
-   사례 \#1: Input: Version\=\<undefined\>;  Revision\=\<don't care\>;   Output: OutputVersion\="1.0.0.0"  
  
-   사례 \#2: Input: Version\="1.0.0.\*"  Revision\="5"  Output: OutputVersion\="1.0.0.5"  
  
-   사례 \#3: Input: Version\="1.0.0.0"  Revision\=\<don't care\>;  Output: OutputVersion\="1.0.0.0"  
  
## 매개 변수  
 다음 표에서는 `FormatVersion` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`FormatType`|선택적 `String` 매개 변수입니다.<br /><br /> 형식을 지정합니다.<br /><br /> -   "버전" \= 버전.<br />-   "경로" \= "."를 "\_"로 바꿈;|  
|`OutputVersion`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 수정 번호를 포함하는 결과 버전을 지정합니다.|  
|`Revision`|선택적 `Int32` 매개 변수입니다.<br /><br /> 버전에 추가할 버전을 지정합니다.|  
|`Version`|선택적 `String` 매개 변수입니다.<br /><br /> 서식을 지정할 버전 번호 문자열을 지정합니다.|  
  
## 설명  
 이 표에 나열된 매개 변수를 갖는 것 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.TaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)를 참조하십시오.  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)