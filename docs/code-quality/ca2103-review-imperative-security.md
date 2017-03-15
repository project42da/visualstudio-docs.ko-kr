---
title: "CA2103: 명령적 보안을 검토하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2103"
  - "ReviewImperativeSecurity"
helpviewer_keywords: 
  - "CA2103"
  - "ReviewImperativeSecurity"
ms.assetid: d24fde71-bdf6-46c0-8965-9a73dc33c1aa
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2103: 명령적 보안을 검토하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ReviewImperativeSecurity|  
|CheckId|CA2103|  
|범주|Microsoft.Security|  
|변경 수준|주요 변경|  
  
## 원인  
 메서드가 명령적 보안을 사용하고, 요청이 활성 상태인 동안 변경될 수 있는 반환 값 또는 상태 정보를 사용하여 권한을 구성하고 있습니다.  
  
## 규칙 설명  
 명령적 보안에서는 관리되는 개체를 사용하여 코드 실행 중에 권한 및 보안 동작을 지정합니다. 이에 비해 선언적 보안에서는 특성을 사용하여 권한 및 작업을 메타데이터에 저장합니다.  명령적 보안은 사용자가 런타임이 되어야만 사용할 수 있는 정보를 사용하여 권한 개체의 상태를 설정하고 보안 동작을 선택할 수 있으므로 융통성이 매우 뛰어납니다.  이러한 융통성에는 권한의 상태를 확인하는 데 사용되는 런타임 정보가 작업이 적용되는 동안 그대로 유지되지 않는다는 위험이 따릅니다.  
  
 가능하면 선언적 보안을 사용합니다.  선언적 요청은 이해하기 쉽습니다.  
  
## 위반 문제를 해결하는 방법  
 명령적 보안 요청을 검토하여 권한이 사용되는 동안 변경될 가능성이 있는 정보에 의해 권한 상태가 좌우되지 않는지 확인합니다.  
  
## 경고를 표시하지 않는 경우  
 변경되는 데이터에 따라 권한이 좌우되지 않으면 이 규칙에 따른 경고를 표시하지 않아도 안전합니다.  그러나 가급적 명령적 요청을 동일한 기능의 선언적 요청으로 변경하는 것이 좋습니다.  
  
## 참고 항목  
 [보안 코딩 지침](../Topic/Secure%20Coding%20Guidelines.md)   
 [데이터 및 모델링](../Topic/Data%20and%20Modeling%20in%20the%20.NET%20Framework.md)