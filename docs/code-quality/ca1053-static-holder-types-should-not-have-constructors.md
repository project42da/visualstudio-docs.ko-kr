---
title: "CA1053: 정적 소유자 형식에는 생성자를 사용하면 안 됩니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "StaticHolderTypesShouldNotHaveConstructors"
  - "CA1053"
helpviewer_keywords: 
  - "CA1053"
  - "StaticHolderTypesShouldNotHaveConstructors"
ms.assetid: 10302b9a-fa5e-4935-a06a-513d9600f613
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1053: 정적 소유자 형식에는 생성자를 사용하면 안 됩니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|StaticHolderTypesShouldNotHaveConstructors|  
|CheckId|CA1053|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 중첩된 public 형식에서 정적 멤버만 선언하며 public 또는 protected 기본 생성자를 사용합니다.  
  
## 규칙 설명  
 호출하는 정적 멤버에 형식의 인스턴스가 필요하지 않기 때문에 생성자가 필요 없습니다.  또한 형식에 비정적 멤버가 없기 때문에 인스턴스를 만들어도 형식의 멤버에 액세스할 수 없습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 기본 생성자를 제거하거나 private으로 지정합니다.  
  
> [!NOTE]
>  일부 컴파일러에서는 형식에서 생성자를 정의하지 않는 경우 자동으로 public 기본 생성자를 만듭니다.  사용하고 있는 형식이 여기에 해당하는 경우 private 기본 생성자를 추가하여 위반 문제를 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  생성자가 있다는 것은 해당 형식이 static이 아님을 의미합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 형식을 보여 줍니다.  이 소스 코드에는 기본 생성자가 없습니다.  이 코드를 어셈블리로 컴파일하면 C\# 컴파일러에서 기본 생성자를 삽입하여 이 규칙을 위반하게 됩니다.  이를 해결하려면 private 생성자를 선언합니다.  
  
 [!code-cs[FxCop.Design.StaticTypes#1](../code-quality/codesnippet/CSharp/ca1053-static-holder-types-should-not-have-constructors_1.cs)]