---
title: "&#39;Get&#39; 문은 더 이상 지원되지 않습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30829"
  - "bc30829"
helpviewer_keywords: 
  - "BC30829"
ms.assetid: 8d798357-7efb-4423-9808-8b20777b97ba
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Get&#39; 문은 더 이상 지원되지 않습니다.
`Get` 문은 더 이상 지원되지 않습니다. 파일 I\/O 기능은 `Microsoft.VisualBasic` 네임스페이스에서 사용할 수 있습니다.  
  
 `Get`은 파일 작업에 지원되지 않으며 속성 프로시저 구문에만 사용할 수 있습니다.  
  
 **오류 ID:** BC30829  
  
### 이 오류를 해결하려면  
  
1.  `System.IO`, `FileSystemObject` 및 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 런타임 함수의 멤버를 사용하여 파일 작업을 수행합니다.  
  
## 참고 항목  
 [Processing Drives, Directories, and Files](/dotnet/visual-basic/developing-apps/programming/drives-directories-files/index)   
 [Get Statement](/dotnet/visual-basic/language-reference/statements/get-statement)   
 [File Access with Visual Basic](/dotnet/visual-basic/developing-apps/programming/drives-directories-files/file-access)