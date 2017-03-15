---
title: "관리 코드에 대한 관리 최소 규칙 규칙 집합 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 44a50c54-8dd3-42b2-8387-532a150e5a6c
caps.latest.revision: 2
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 2
---
# 관리 코드에 대한 관리 최소 규칙 규칙 집합
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이러한 관리된 최소한의 규칙들은 잠재적 보안 허점, 응용 프로그램 충돌, 기타 중요한 논리 및 디자인 오류를 비롯하여 코드의 가장 중요한 문제에 초점을 맞춥니다.  프로젝트에 대해 만드는 모든 사용자 지정 규칙 집합에 이 규칙 집합을 포함해야 합니다.  
  
|규칙|설명|  
|--------|--------|  
|[CA1001](../Topic/CA1001:%20Types%20that%20own%20disposable%20fields%20should%20be%20disposable.md)|삭제 가능한 필드가 있는 형식은 삭제 가능해야 합니다.|  
|[CA1821](../code-quality/ca1821-remove-empty-finalizers.md)|빈 종료자를 제거하십시오.|  
|[CA2213](../code-quality/ca2213-disposable-fields-should-be-disposed.md)|삭제 가능한 필드는 삭제해야 합니다.|  
|[CA2231](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)|ValueType.Equals를 재정의할 때 같음 연산자를 오버로드하십시오.|