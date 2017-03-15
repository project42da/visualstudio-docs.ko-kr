---
title: "CA1725: 매개 변수 이름은 기본 선언과 일치해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ParameterNamesShouldMatchBaseDeclaration"
  - "CA1725"
helpviewer_keywords: 
  - "CA1725"
  - "ParameterNamesShouldMatchBaseDeclaration"
ms.assetid: 9b657ab0-fe81-4f4c-9481-ba746988c922
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 11
---
# CA1725: 매개 변수 이름은 기본 선언과 일치해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ParameterNamesShouldMatchBaseDeclaration|  
|CheckId|CA1725|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## 원인  
 외부에서 볼 수 있는 메서드 재정의의 매개 변수 이름이 메서드 기본 선언의 매개 변수 이름 또는 메서드의 인터페이스 선언에 있는 매개 변수 이름과 일치하지 않습니다.  
  
## 규칙 설명  
 재정의 계층 구조에서 매개 변수 이름을 일관되게 지정하면 메서드 재정의를 더 편리하게 사용할 수 있습니다.  파생된 메서드의 매개 변수 이름이 기본 선언의 이름과 다르면 메서드가 기본 메서드의 재정의인지 메서드의 새 오버로드인지를 혼동할 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 매개 변수 이름을 기본 선언에 맞게 변경합니다.  이러한 수정은 COM 노출 메서드에 대한 주요 변경 내용에 해당합니다.  
  
## 경고를 표시하지 않는 경우  
 이전에 제공된 라이브러리에 있는 COM 노출 메서드 이외에는 이 규칙에서 경고를 표시하십시오.