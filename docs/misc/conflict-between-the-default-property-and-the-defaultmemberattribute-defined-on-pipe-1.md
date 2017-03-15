---
title: "&#39;|1&#39;에 정의된 &#39;DefaultMemberAttribute&#39;와 기본 속성이 충돌합니다. | Microsoft Docs"
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
  - "vbc32304"
  - "bc32304"
helpviewer_keywords: 
  - "BC32304"
ms.assetid: 42803d13-ff1d-40ed-a4a8-269e2fb4aa01
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;|1&#39;에 정의된 &#39;DefaultMemberAttribute&#39;와 기본 속성이 충돌합니다.
클래스, 구조체 또는 인터페이스는 [Default](/dotnet/visual-basic/language-reference/modifiers/default) 키워드를 사용하여 기본 속성을 선언하지만 <xref:System.Reflection.DefaultMemberAttribute>를 적용하여 다른 멤버를 기본 멤버로 지정하기도 합니다.  
  
 형식은 최대 하나의 기본 멤버를 사용할 수 있습니다. 기본 속성을 선언하면 Visual Basic에서 해당 속성을 지정하는 <xref:System.Reflection.DefaultMemberAttribute>를 클래스, 구조체 또는 인터페이스에 자동으로 적용합니다.  
  
 **오류 ID:** BC32304  
  
### 이 오류를 해결하려면  
  
1.  클래스, 구조체 또는 인터페이스의 기본 멤버로 지정할 멤버를 확인합니다.  
  
2.  충돌하는 선언\(`Default` 키워드 또는 <xref:System.Reflection.DefaultMemberAttribute>\)을 제거합니다.  
  
## 참고 항목  
 <xref:System.Reflection.DefaultMemberAttribute>   
 [Default](/dotnet/visual-basic/language-reference/modifiers/default)   
 [빌드에 없음: 기본 속성](http://msdn.microsoft.com/ko-kr/a70f2a27-8176-4858-935e-f25afdd43ab5)   
 [How to: Declare and Call a Default Property in Visual Basic](../Topic/How%20to:%20Declare%20and%20Call%20a%20Default%20Property%20in%20Visual%20Basic.md)