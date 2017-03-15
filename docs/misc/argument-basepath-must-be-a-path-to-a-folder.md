---
title: "인수 BasePath는 폴더에 대한 경로여야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b180ce60-ad57-41a6-a313-491d86d84cc7
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 인수 BasePath는 폴더에 대한 경로여야 합니다.
인수 `BasePath`는 폴더의 경로로 구성되어야 합니다. 문자열을 잘못 구문 분석하고 올바른 경로로 인식되지 않는 값을 제공할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   `BasePath`에 제공하는 값을 확인하여 폴더에 대한 올바른 경로인지 확인합니다.  
  
## 참고 항목  
 <xref:System.CodeDom.Compiler.TempFileCollection.BasePath%2A>   
 <xref:System.Resources.ResXResourceWriter.BasePath%2A>   
 <xref:System.Resources.ResXResourceReader.BasePath%2A>   
 [방법: 파일 경로의 구문 분석](../Topic/How%20to:%20Parse%20File%20Paths%20in%20Visual%20Basic.md)