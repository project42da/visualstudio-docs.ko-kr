---
title: "SetEnv Task | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.task.setenv"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
  - "C++"
helpviewer_keywords: 
  - "MSBuild (Visual C++), tasks"
  - "SetEnv task (MSBuild (Visual C++))"
ms.assetid: fd9e4225-68cb-4608-8b27-468b0218c936
caps.latest.revision: 6
caps.handback.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# SetEnv Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지정한 환경 변수의 값을 설정하거나 삭제합니다.  
  
## 매개 변수  
 다음 표에서는 **SetEnv**  작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|**Name**|필수적 **String** 매개 변수입니다.<br /><br /> 환경 변수의 이름입니다.|  
|**OutputEnvironmentVariable**|선택적 **String** 출력 매개 변수입니다.<br /><br /> **Name** 매개 변수에 지정된 환경 변수에 할당된 값을 포함합니다.|  
|**Prefix**|필수 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 **Name** 매개 변수에 지정된 환경 변수의 값 앞에 **Value** 매개 변수의 값을 연결한 다음 결과를 환경 변수에 할당합니다.  `false`인 경우 **Value** 매개 변수의 값만 환경 변수에 할당합니다.|  
|**Target**|선택적 **String** 매개 변수입니다.<br /><br /> 환경 변수가 저장되는 위치를 지정합니다.  "`사용자`" 또는 "`컴퓨터`"를 지정합니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "EnvironmentVariableTarget Enumeration"을 참조하십시오.|  
|**Value**|선택적 **String** 매개 변수입니다.<br /><br /> **Name** 매개 변수에 의해 지정된 환경 변수에 할당된 값입니다.  **Value**가 비어 있고 변수가 존재하는 경우 변수가 삭제됩니다.  변수가 없는 경우 작업을 수행할 수 없는 경우에도 오류가 발생하지 않습니다.<br /><br /> 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트의 "Environment::SetEnvironmentVariable Method"를 참조하십시오.|  
  
## 설명  
  
## 참고 항목  
 [Task Reference](../msbuild/msbuild-task-reference.md)