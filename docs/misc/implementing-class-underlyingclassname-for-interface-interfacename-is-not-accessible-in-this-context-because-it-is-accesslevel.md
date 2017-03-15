---
title: "&#39;&lt;interfacename&gt;&#39; 인터페이스에 대해 &#39;&lt;underlyingclassname&gt;&#39; 클래스 구현은 이 클래스가 &#39;&lt;accesslevel&gt;&#39;이기 때문에 이 컨텍스트에서 액세스할 수 없습니다. | Microsoft Docs"
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
  - "BC31109"
  - "vbc31109"
helpviewer_keywords: 
  - "BC31109"
ms.assetid: ab2a3bc3-b875-476f-b601-3e736ad2677e
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;interfacename&gt;&#39; 인터페이스에 대해 &#39;&lt;underlyingclassname&gt;&#39; 클래스 구현은 이 클래스가 &#39;&lt;accesslevel&gt;&#39;이기 때문에 이 컨텍스트에서 액세스할 수 없습니다.
인터페이스가 기본 클래스를 지정하는 <xref:System.Runtime.InteropServices.CoClassAttribute>로 선언되었지만 해당 클래스에는 사용 중인 코드의 액세스를 금지하는 액세스 수준이 있습니다.  
  
 <xref:System.Runtime.InteropServices.CoClassAttribute>를 인터페이스에 적용하면 기본 클래스가 인터페이스에 연결됩니다. 그러면 코드가 `New` 절을 사용하는 인터페이스에서 직접 개체를 만들 수 있습니다.  
  
 `New` 절을 사용하는 코드가 기본 클래스에 액세스할 수 없는 경우, 예를 들어 클래스가 `Private`이면 컴파일러가 이 오류를 생성합니다.  
  
 **오류 ID:** BC31109  
  
### 이 오류를 해결하려면  
  
1.  기본 클래스에 대한 소스 제어가 있는 경우 사용 중인 코드가 기본 클래스에 액세스할 수 있도록 해당 액세스 수준을 조정합니다.  
  
2.  어떤 이유로든 기본 클래스의 액세스 수준을 변경할 수 없는 경우 `New` 절을 제거합니다. 이 인터페이스에서 직접 개체를 만들 수 없습니다.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.CoClassAttribute>   
 [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator)   
 [Access Levels in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/access-levels)