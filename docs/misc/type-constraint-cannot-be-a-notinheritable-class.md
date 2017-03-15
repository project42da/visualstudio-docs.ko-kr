---
title: "형식 제약 조건은 &#39;NotInheritable&#39; 클래스일 수 없습니다. | Microsoft Docs"
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
  - "vbc32060"
  - "bc32060"
helpviewer_keywords: 
  - "BC32060"
ms.assetid: f45cc0b6-7df1-462a-b3df-c526c143e16a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식 제약 조건은 &#39;NotInheritable&#39; 클래스일 수 없습니다.
제약 조건 목록에 [NotInheritable](/dotnet/visual-basic/language-reference/modifiers/notinheritable)로 표시된 클래스가 포함되어 있습니다.  
  
 형식 매개 변수의 제약 조건 목록은 최대 하나의 클래스만 허용합니다. 해당 형식 매개 변수에 제공되는 형식 인수는 해당 클래스에서 상속해야 합니다. 따라서 형식 매개 변수는 제약 조건으로 *봉인* 또는 `NotInheritable`, 클래스를 허용할 수 없습니다.  
  
 **오류 ID:** BC32060  
  
### 이 오류를 해결하려면  
  
-   형식 매개 변수가 클래스에서 상속할 수 있어야 하는 상황에서 클래스의 정의를 제어할 수 있는 경우 클래스에서 `NotInheritable` 선언을 제거합니다.  
  
-   클래스가 `NotInheritable`을 계속 유지해야 하는 경우 제약 조건으로 사용할 수 없습니다. 제약 조건 목록에서 클래스 이름을 제거합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)