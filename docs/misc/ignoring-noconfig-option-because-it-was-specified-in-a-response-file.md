---
title: "지시 파일에 지정되었기 때문에 /noconfig 옵션을 무시합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc2025"
  - "bc2025"
helpviewer_keywords: 
  - "BC2025"
ms.assetid: 87fb393d-e17f-4e50-8d98-d9dfeba30c3e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 지시 파일에 지정되었기 때문에 /noconfig 옵션을 무시합니다.
`/noconfig` 옵션은 Vbc.rsp 파일을 사용하여 컴파일하지 않도록 컴파일러에 지시합니다. 그러나 컴파일러에서는 다른 지시 파일을 처리하기 전에 Vbc.rsp 파일을 처리하므로 컴파일러에서 지시 파일의 `/noconfig` 옵션을 사용할 수 없습니다.  
  
 **오류 ID:** BC2025  
  
### 이 오류를 해결하려면  
  
1.  지시 파일에서 `/noconfig` 옵션을 제거합니다.  
  
2.  명령줄 컴파일러를 호출할 때 `/noconfig` 옵션을 지정합니다.  
  
## 참고 항목  
 [\/noconfig](/dotnet/visual-basic/reference/command-line-compiler/noconfig)   
 [@ \(Specify Response File\)](/dotnet/visual-basic/reference/command-line-compiler/specify-response-file)