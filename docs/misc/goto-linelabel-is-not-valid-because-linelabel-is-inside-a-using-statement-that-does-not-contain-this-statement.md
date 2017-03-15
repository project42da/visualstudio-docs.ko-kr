---
title: "&#39;&lt;linelabel&gt;&#39;이 이 문을 포함하지 않는 &#39;Using&#39; 문 내부에 있으므로 &#39;GoTo &lt;linelabel&gt;&#39;은 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc36009"
  - "vbc36009"
helpviewer_keywords: 
  - "BC36009"
ms.assetid: ebec3cac-d378-4e9b-a792-12e9ece5599e
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;linelabel&gt;&#39;이 이 문을 포함하지 않는 &#39;Using&#39; 문 내부에 있으므로 &#39;GoTo &lt;linelabel&gt;&#39;은 사용할 수 없습니다.
`Using` 생성 외부의 `GoTo` 문이 생성 내부의 줄 레이블로 분기하려고 합니다.  
  
 `Using`...`End Using` 생성 외부의 원하는 위치에서 생성 내부의 원하는 위치로 분기하는 것은 유효하지 않습니다.  
  
 **오류 ID:** BC36009  
  
### 이 오류를 해결하려면  
  
-   `GoTo` 문의 줄 레이블을 `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With` 또는 `Using`...`End Using` 생성 내부에 있지 않은 레이블로 변경합니다.  
  
     또는  
  
-   `GoTo` 문을 완전히 제거합니다.`Using`...`End Using` 생성을 입력할 수 있는 유일한 방법은 컨트롤이 `Using` 문 자체에 전달하는 것을 허용하는 것입니다.  
  
## 참고 항목  
 [GoTo Statement](/dotnet/visual-basic/language-reference/statements/goto-statement)   
 [Using Statement](/dotnet/visual-basic/language-reference/statements/using-statement)