---
title: "배열 차원이 일치하지 않으므로 &#39;&lt;variablename&gt;&#39;의 데이터 형식을 유추할 수 없습니다. | Microsoft Docs"
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
  - "bc36909"
  - "vbc36909"
helpviewer_keywords: 
  - "BC36909"
ms.assetid: e41fec81-efec-4395-a0a5-d81906a2d4f1
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 배열 차원이 일치하지 않으므로 &#39;&lt;variablename&gt;&#39;의 데이터 형식을 유추할 수 없습니다.
배열을 초기화하는 데 사용하는 차원이 선언의 차원과 일치하지 않는 경우 컴파일러에서 해당 배열에 대한 데이터 형식을 유추할 수 없습니다. 예를 들어 다음 코드에서는 이 오류를 생성합니다.  
  
```vb#  
' Valid. exampleArray1 is a one-dimensional array of integers. Dim exampleArray1() = New Integer() {1, 2, 3} ' Not valid. 'Dim exampleArray2(,) = New Integer() {1, 2, 3} 'Dim exampleArray3(,) = New Integer() {}  
```  
  
 **오류 ID:** BC36909  
  
## 참고 항목  
 [Local Type Inference](/dotnet/visual-basic/programming-guide/language-features/variables/local-type-inference)   
 [NOTINBUILD 방법: 다차원 배열 초기화](http://msdn.microsoft.com/ko-kr/502dcf8b-d86c-46f1-ad7d-3ce809645774)