---
title: "VCMessage Task | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.task.vcmessage"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
  - "C++"
helpviewer_keywords: 
  - "VCMessage task (MSBuild (Visual C++))"
  - "MSBuild (Visual C++), VCMessage task"
ms.assetid: 956675fd-05dc-40b4-856f-616145103498
caps.latest.revision: 7
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 7
---
# VCMessage Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

빌드하는 동안 경고 및 오류 로그를 기록합니다.  
  
## 설명  
 이 작업은 Visual C\+\+용 MSBuild를 구현하는 데 도움이 되며 사용자가 호출될 수 없습니다.  자세한 내용은 <xref:Microsoft.Build.Utilities.TaskLoggingHelper>를 참조하십시오.  
  
## 매개 변수  
 다음 표에서는 **VCMessage**  작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|**Arguments**|선택적 **String** 매개 변수입니다.<br /><br /> 표시할 메시지의 세미콜론으로 구분된 목록입니다.|  
|**Code**|필수적 **String** 매개 변수입니다.<br /><br /> 메시지를 한정하는 오류 번호입니다.|  
|**Type**|선택적 **String** 매개 변수입니다.<br /><br /> 내보낼 메시지의 종류를 지정합니다.  경고 메시지를 생성하려면 `"경고"` 또는 오류 메시지를 생성하려면 `"오류"`를 지정합니다.|  
  
## 참고 항목  
 [Task Reference](../msbuild/msbuild-task-reference.md)