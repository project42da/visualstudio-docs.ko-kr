---
title: "다른 생성자를 호출하는 동안에는 생성 중인 개체를 참조할 수 없습니다. | Microsoft Docs"
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
  - "bc31095"
  - "vbc31095"
helpviewer_keywords: 
  - "BC31095"
ms.assetid: 68be49f1-e662-45c7-9998-e0006324535d
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 다른 생성자를 호출하는 동안에는 생성 중인 개체를 참조할 수 없습니다.
개체의 생성자가 개체 만들기를 완료하기 전에 개체 멤버를 참조해야 합니다.  
  
 **오류 ID:** BC31095  
  
### 이 오류를 해결하려면  
  
-   다른 생성자에서 생성자를 호출하는 경우 `MyBase`, `MyClass` 또는 `Me`를 사용하지 마세요.  
  
## 참고 항목  
 [Object Lifetime: How Objects Are Created and Destroyed](../Topic/Object%20Lifetime:%20How%20Objects%20Are%20Created%20and%20Destroyed%20\(Visual%20Basic\).md)   
 [빌드에 없음: 생성자 및 소멸자 사용](http://msdn.microsoft.com/ko-kr/548eebe1-86c4-4377-b2f5-447cb8be3d90)