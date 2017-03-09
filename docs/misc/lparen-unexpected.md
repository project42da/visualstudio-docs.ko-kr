---
title: "예기치 않은 &#39;(&#39;입니다. | Microsoft Docs"
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
  - "vbc32095"
  - "bc32095"
helpviewer_keywords: 
  - "BC32095"
ms.assetid: a47ad15a-2cfc-4d17-9012-27ba85b7d783
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 예기치 않은 &#39;(&#39;입니다.
예기치 않은 '\('입니다. 인스턴스화되지 않은 제네릭 형식의 배열은 사용할 수 없습니다.  
  
 특정 데이터 형식이 아니면 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 배열을 컴파일할 수 없습니다. 제네릭 형식의 데이터 형식 매개 변수를 배열 데이터 형식으로 사용할 수 없습니다.  
  
 **오류 ID:** BC32095  
  
### 이 오류를 해결하려면  
  
-   배열을 사용해야 하는 경우 특정 데이터 형식으로 선언해야 합니다. 데이터 형식 매개 변수를 사용할 수 없습니다.  
  
-   데이터 형식 매개 변수에 대해 제공해야 하는 데이터 형식의 요소 그룹이 필요한 경우 배열 대신 컬렉션을 사용해야 합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Visual Basic의 NIB 컬렉션](http://msdn.microsoft.com/ko-kr/8b2b7845-2251-4573-8dd3-c9f9c0a66a21)   
 [Visual Basic에서 개체 그룹 관리](http://msdn.microsoft.com/ko-kr/50be4910-4732-4d5f-a18a-055a162e9037)