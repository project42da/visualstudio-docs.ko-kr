---
title: "CA2207: 값 형식 정적 필드를 인라인으로 초기화하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "InitializeValueTypeStaticFieldsInline"
  - "CA2207"
helpviewer_keywords: 
  - "CA2207"
  - "InitializeValueTypeStaticFieldsInline"
ms.assetid: d1ea9d8b-ecc2-46ca-86e2-c41dd0e76658
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 14
---
# CA2207: 값 형식 정적 필드를 인라인으로 초기화하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|InitializeValueTypeStaticFieldsInline|  
|CheckId|CA2207|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 값 형식에서 명시적인 정적 생성자를 선언합니다.  
  
## 규칙 설명  
 값 형식이 선언된 경우 모든 값 형식 필드가 0으로 설정되고 모든 참조 형식 필드가 `null`\(Visual Basic에서는 `Nothing`\)로 설정되는 기본 초기화를 거치게 됩니다.  명시적인 정적 생성자는 인스턴스 생성자 또는 형식의 정적 멤버가 호출되기 전에만 실행됩니다.  따라서 인스턴스 생성자 호출 없이 형식을 만들면 정적 생성자가 실행된다고 보장할 수 없습니다.  
  
 모든 정적 데이터가 인라인으로 초기화되고 명시적인 정적 생성자가 선언되어 있지 않으면 C\# 및 Visual Basic 컴파일러는 `beforefieldinit` 플래그를 MSIL 클래스 정의에 추가합니다.  또한 컴파일러는 정적 초기화 코드가 들어 있는 전용 정적 생성자를 추가합니다.  이 전용 정적 생성자는 형식의 정적 필드가 액세스되기 전에 실행됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 모든 정적 데이터를 선언할 때 초기화하고 정적 생성자를 제거합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 관련 규칙  
 [CA1810: 참조 형식 정적 필드를 인라인으로 초기화하십시오.](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)