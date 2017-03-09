---
title: "줄 연속 문자 &#39;_&#39;은 하나 이상의 공백 뒤에 와야 하며 해당 줄에서 마지막 문자여야 합니다. | Microsoft Docs"
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
  - "vbc30999"
  - "bc30999"
helpviewer_keywords: 
  - "BC30999"
ms.assetid: 32caf62f-52e4-4acd-b40f-5af65e42e643
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 줄 연속 문자 &#39;_&#39;은 하나 이상의 공백 뒤에 와야 하며 해당 줄에서 마지막 문자여야 합니다.
밑줄\(\_\)인 줄 연속 문자를 사용하여 파일에서 긴 코드 줄을 여러 줄로 나눌 수 있습니다. 밑줄 바로 앞에는 공백이 오고 바로 뒤에는 줄 종결자\(캐리지 리턴\)가 와야 합니다. 예:  
  
```  
Dim books As XDocument = _ XDocument.Load(My.Application.Info.DirectoryPath & _ "\..\..\Data\books.xml")  
```  
  
 **오류 ID:** BC30999  
  
### 이 오류를 해결하려면  
  
1.  줄 연속 문자\(\_\)가 코드 줄에서 마지막 문자인지 확인합니다.  
  
2.  줄 연속 문자 앞에 줄의 다른 코드와 구분하는 공백이 있는지 확인합니다.  
  
## 참고 항목  
 [방법: 코드에서 문 분리 및 결합](../Topic/How%20to:%20Break%20and%20Combine%20Statements%20in%20Code%20\(Visual%20Basic\).md)