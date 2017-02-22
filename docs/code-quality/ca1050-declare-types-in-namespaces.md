---
title: "CA1050: 네임스페이스에 형식을 선언하십시오. | Microsoft Docs"
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
  - "CA1050"
  - "DeclareTypesInNamespaces"
helpviewer_keywords: 
  - "CA1050"
  - "DeclareTypesInNamespaces"
ms.assetid: 1002748d-ac8d-404f-85dd-7a12d1ad3e05
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1050: 네임스페이스에 형식을 선언하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DeclareTypesInNamespaces|  
|CheckId|CA1050|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 public 또는 protected 형식이 명명된 네임스페이스 외부에 정의되어 있습니다.  
  
## 규칙 설명  
 이름 충돌을 방지하고 관련된 형식을 개체 계층 구조로 구성하기 위해 형식은 네임스페이스에 선언됩니다.  명명된 네임스페이스 외부에 있는 형식은 코드에서 참조할 수 없는 전역 네임스페이스에 있는 형식입니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 형식을 네임스페이스에 넣어야 합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서 경고를 반드시 표시하지 않아야 하는 것은 아니지만 어셈블리를 다른 어셈블리와 함께 사용하지 않을 경우에는 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 형식이 네임스페이스 외부에 잘못 선언되어 있는 라이브러리와 동일한 이름으로 네임스페이스에 선언된 형식을 보여 줍니다.  
  
 [!code-cs[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_1.cs)]
 [!code-vb[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_1.vb)]  
  
## 예제  
 다음 응용 프로그램에서는 이전에 정의된 라이브러리를 사용합니다.  `Test`라는 이름이 네임스페이스로 정규화되지 않은 경우 네임스페이스 외부에 선언된 형식이 만들어지는 것을 볼 수 있습니다.  또한 `Goodspace`의 `Test` 형식에 액세스하려면 네임스페이스 이름이 필요하다는 것을 알 수 있습니다.  
  
 [!code-cs[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_2.cs)]
 [!code-vb[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_2.vb)]