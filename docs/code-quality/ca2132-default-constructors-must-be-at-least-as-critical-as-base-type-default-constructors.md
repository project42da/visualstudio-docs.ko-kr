---
title: "CA2132: 기본 생성자는 최소한 기본 형식 기본 생성자만큼 중요해야 합니다. | Microsoft Docs"
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
  - "CA2132"
ms.assetid: e758afa1-8bde-442a-8a0a-bd1ea7b0ce4d
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2132: 기본 생성자는 최소한 기본 형식 기본 생성자만큼 중요해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DefaultConstructorsMustHaveConsistentTransparency|  
|CheckId|CA2132|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
> [!NOTE]
>  이 경고는 CoreCLR\(Silverlight 웹 응용 프로그램에 특정한 CLR 버전\)을 실행하는 코드에만 적용됩니다.  
  
## 원인  
 파생된 클래스의 기본 생성자의 투명도 특성은 기본 클래스의 투명도 만큼 중요하지 않습니다.  
  
## 규칙 설명  
 <xref:System.Security.SecurityCriticalAttribute>가 있는 형식 및 멤버는 Silverlight 응용 프로그램 코드에서 사용할 수 없습니다.  보안에 중요한 형식 및 멤버는 .NET Framework for Silverlight 클래스 라이브러리의 신뢰할 수 있는 코드에서만 사용할 수 있습니다.  파생 클래스의 public 또는 protected 구성 요소는 투명성이 기본 클래스보다 높거나 같아야 하기 때문에 응용 프로그램의 클래스는 SecurityCritical로 표시된 클래스에서 파생될 수 없습니다.  
  
 CoreCLR 플랫폼 코드에 대해 기본 형식에 공용 또는 보호된 불투명한 기본 생성자가 있는 경우 파생된 형식은 기본 생성자 상속 규칙을 준수해야 합니다.  또한 파생된 형식은 기본 생성자가 있어야 하며 해당 생성자는 최소한 기본 형식의 중요한 기본 생성자가 되어야 합니다.  
  
## 위반 문제를 해결하는 방법  
 위반 문제를 해결하려면 형식을 제거하거나 보안 불투명한 형식에서 파생하지 마십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  <xref:System.TypeLoadException>가 있는 형식을 로드하는 것을 거부하는 응용 프로그램 코드에 의한 이 규칙 위반이 CoreCLR에서 발생합니다.  
  
### 코드  
 [!CODE [FxCop.Security.CA2132.DefaultConstructorsMustHaveConsistentTransparency#1](../CodeSnippet/VS_Snippets_CodeAnalysis/fxcop.security.ca2132.defaultconstructorsmusthaveconsistenttransparency#1)]  
  
### 설명