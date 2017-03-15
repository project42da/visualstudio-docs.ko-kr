---
title: "&#39;Line&#39; 문은 더 이상 지원되지 않습니다(스마트 장치/Visual Basic 컴파일러 오류). | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30768"
  - "bc30768"
helpviewer_keywords: 
  - "BC30768"
ms.assetid: e7a17c77-06bb-4d33-966e-addb4f51caaf
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Line&#39; 문은 더 이상 지원되지 않습니다(스마트 장치/Visual Basic 컴파일러 오류).
`Line` 문이 더 이상 지원되지 않습니다. 파일 I\/O 기능은 <xref:Microsoft.VisualBasic.FileSystem.LineInput%2A?displayProperty=fullName>로 정상적으로 사용할 수 있지만 .NET Compact Framework의 지정된 버전에서 지원하지 않습니다.  
  
 **오류 ID:** BC30768  
  
### 이 오류를 해결하려면  
  
-   파일 액세스를 수행하는 경우 <xref:System.IO> 네임스페이스에 정의된 함수를 사용합니다.  
  
-   그래픽을 수행하는 경우 <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName>을 사용합니다.  
  
## 참고 항목  
 <xref:System.IO>   
 <xref:System.Drawing>   
 [File Access with Visual Basic](/dotnet/visual-basic/developing-apps/programming/drives-directories-files/file-access)