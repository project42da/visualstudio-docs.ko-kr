---
title: "방법: 코드 분석 체크 인 정책을 통해 유지 관리할 수 있는 코드 적용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "코드 분석, 체크 인 정책"
ms.assetid: d1b3b04f-4dd9-40e6-b2d4-b414d33fb647
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 코드 분석 체크 인 정책을 통해 유지 관리할 수 있는 코드 적용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

개발자는 코드 메트릭 도구를 사용하여 코드의 복잡성 및 유지 관리 편의성을 측정할 수 있지만 코드 메트릭을 체크 인 정책의 일부로 호출할 수는 없습니다.  그러나 팀에서는 코드가 코드 메트릭 표준을 준수하는지 여부를 확인하는 코드 분석 규칙을 사용하도록 설정하고 체크 인 정책을 통해 해당 규칙을 적용할 수 있습니다.  코드 메트릭에 대한 자세한 내용은 [코드 메트릭 값](../code-quality/code-metrics-values.md)를 참조하십시오.  
  
 개발자는 상속 수준, 클래스 결합, 유지 관리 인덱스 및 복잡성 규칙을 사용함으로써 코드 분석 체크 인 정책을 통해 유지 관리 가능한 코드를 적용할 수 있습니다.  이 네 가지 규칙은 모두 코드 분석 정책 편집기의 "유지 관리 규칙" 범주에 있습니다.  
  
 [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] 버전 제어 관리자는 코드 분석 유지 관리 규칙을 체크 인 정책 요구 사항에 추가할 수 있습니다.  이러한 체크 인 정책에서는 개발자가 체크 인을 시작하기 전에 규칙 변경 사항에 따라 코드 분석을 실행하도록 요구하고 있습니다.  
  
### 코드 분석 정책 편집기를 열려면  
  
1.  **팀 탐색기**에서 팀 프로젝트를 마우스 오른쪽 단추로 클릭하고 **팀 프로젝트 설정**을 클릭한 다음 **소스 제어**를 클릭합니다.  
  
     **소스 제어** 대화 상자가 나타납니다.  
  
2.  **체크 인 정책** 탭에서 **추가**를 클릭합니다.  
  
     **체크 인 정책 추가** 대화 상자가 나타납니다.  
  
3.  **체크 인 정책** 목록에서 **코드 분석** 확인란을 선택하고 **확인**을 클릭합니다.  
  
     **코드 분석 정책 편집기** 대화 상자가 나타납니다.  
  
### 코드 분석 유지 관리 규칙을 활성화하려면  
  
1.  **코드 분석 정책 편집기** 대화 상자의 **규칙 설정** 아래에서 **유지 관리 규칙** 노드를 확장합니다.  
  
2.  다음 규칙에 대한 확인란을 선택합니다.  
  
    -   상속 수준: **CA1501 AvoidExcessiveInheritance** \- 임계값: 깊이가 5단계를 초과하면 경고  
  
    -   복잡성: **CA1502 AvoidExcessiveComplexity** \- 임계값: 깊이가 25단계를 초과하면 경고  
  
    -   유지 관리 인덱스: **CA1505 AvoidUnmaintainableCode** \- 임계값: 깊이가 20단계 미만이면 경고  
  
    -   클래스 결합: **CA1506 AvoidExcessiveClassCoupling** \- 임계값: 깊이가 80단계\(클래스\) 및 30단계\(메서드\)를 초과하면 경고  
  
    -   또한 규칙 위반 시 빌드를 방지하려면 규칙 설명 옆에 있는 **경고를 오류로 처리** 확인란을 선택합니다.  
  
3.  **확인**을 클릭합니다.  이후의 체크 인에 대해서는 새 체크 인 정책이 적용됩니다.  
  
## 참고 항목  
 [코드 메트릭 값](../code-quality/code-metrics-values.md)   
 [코드 분석 체크 인 정책 만들기 및 사용](../code-quality/creating-and-using-code-analysis-check-in-policies.md)