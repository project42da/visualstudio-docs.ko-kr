---
title: "선행 &#39;.&#39; 또는 &#39;!&#39;는 상수 식에 표시할 수 없습니다. | Microsoft Docs"
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
  - "vbc30995"
  - "bc30995"
helpviewer_keywords: 
  - "BC30995"
ms.assetid: eed62684-66db-4fdb-9da7-f1407a55b172
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 선행 &#39;.&#39; 또는 &#39;!&#39;는 상수 식에 표시할 수 없습니다.
멤버 액세스\(.\) 및 사전 멤버 액세스\(\!\)에는 상수 식을 포함하여 대부분의 경우에 멤버가 포함된 요소를 지정하는 식이 필요합니다. 다음 선언은 올바르지 않습니다.  
  
```  
' Not valid. Const c As String = .name  
```  
  
 **오류 ID:** BC30995  
  
### 이 오류를 해결하려면  
  
-   액세스하려는 멤버를 포함하는 인스턴스를 지정합니다.  
  
## 참고 항목  
 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)   
 [방법: 무명 형식의 인스턴스 선언\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/119f616c-9bcd-4731-ac00-4285be5959f7)   
 [Const Statement](/dotnet/visual-basic/language-reference/statements/const-statement)