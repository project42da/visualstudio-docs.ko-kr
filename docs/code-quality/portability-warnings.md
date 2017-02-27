---
title: "이식성 경고 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.codeanalysis.PortabilityRules"
helpviewer_keywords: 
  - "이식성 경고"
  - "관리 코드 분석 경고, 이식성 경고"
  - "경고, 이식성"
ms.assetid: 902e859a-2153-4970-baaa-8a5b4a11806f
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 18
---
# 이식성 경고
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이식성 경고는 여러 운영 체제 간의 이식성을 지원합니다.  
  
## 단원 내용  
  
|규칙|설명|  
|--------|--------|  
|[CA1900: 값 형식 필드는 이식 가능해야 합니다.](../code-quality/ca1900-value-type-fields-should-be-portable.md)|이 규칙에서는 명시적 레이아웃 특성으로 선언된 구조체가 64비트 운영 체제에서 비관리 코드로 마샬링될 때 올바르게 맞춰지는지 검사합니다.|  
|[CA1901: P\/Invoke 선언은 이식 가능해야 합니다.](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)|이 규칙은 P\/Invoke의 반환 값과 각 매개 변수의 크기를 계산하여 32비트 및 64비트 운영 체제에서 비관리 코드로 마샬링될 때 그 크기가 올바른지 확인합니다.|  
|[CA1903: 대상 프레임워크에서 API만 사용하십시오.](../code-quality/ca1903-use-only-api-from-targeted-framework.md)|멤버 또는 형식이 프로젝트의 대상 프레임워크에 함께 포함되지 않은 서비스 팩에 도입된 멤버 또는 형식을 사용합니다.|