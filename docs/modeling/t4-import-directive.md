---
title: "T4 Import 지시문 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 713ca975-b9aa-4210-bf6d-b7660f5b193b
caps.latest.revision: 3
caps.handback.revision: 3
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# T4 Import 지시문
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] T4 텍스트 템플릿의 코드 블록에서 `import` 지시문을 사용하면 정규화된 이름을 제공하지 않고 다른 네임스페이스의 요소를 참조할 수 있습니다.  이 지시문은 C\#의 `using` 또는 [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)]의 `imports`에 해당합니다.  
  
 T4 텍스트 템플릿 작성에 대한 일반적인 개요를 보려면 [T4 텍스트 템플릿 쓰기](../modeling/writing-a-t4-text-template.md)을 참조하십시오.  
  
## Import 지시문 사용  
  
```  
<#@ import namespace="namespace" #>  
```  
  
 이 예제에서는 다음과 같이 템플릿 코드에서 System.IO의 멤버에 대한 명시적 네임스페이스를 생략할 수 있습니다.  
  
```  
<#@ import namespace="System.IO" #>  
<#   
   string fileContent = File.ReadAllText("C:\x.txt"); // System.IO.File  
#>   
The file contains: <#=  fileContent #>  
```  
  
## 표준 가져오기  
 다음 네임스페이스를 자동으로 가져오므로 해당 네임스페이스에 대한 import 지시문을 작성할 필요가 없습니다.  
  
-   `System`  
  
 또한 사용자 지정 지시문을 사용하는 경우 지시문 프로세서에서 일부 네임스페이스를 자동으로 가져올 수 있습니다.  
  
 예를 들어 DSL\(도메인별 언어\)을 위한 템플릿을 작성하는 경우 다음 네임스페이스에 대한 import 지시문을 작성할 필요가 없습니다.  
  
-   `Microsoft.VisualStudio.Modeling`  
  
-   DSL의 네임스페이스  
  
## 참고 항목  
 [T4 Assembly 지시문](../modeling/t4-assembly-directive.md)