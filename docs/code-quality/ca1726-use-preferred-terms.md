---
title: "CA1726: 기본 설정 용어를 사용하십시오. | Microsoft Docs"
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
  - "UsePreferredTerms"
  - "CA1726"
helpviewer_keywords: 
  - "UsePreferredTerms"
ms.assetid: 642b2acd-3a33-4d1f-b0a7-67073ae73be2
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1726: 기본 설정 용어를 사용하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|UsePreferredTerms|  
|CheckId|CA1726|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경 \- 어셈블리에서 발생한 경우,<br /><br /> 주요 변경 아님 \- 형식 매개 변수에서 발생한 경우|  
  
## 원인  
 외부에서 볼 수 있는 식별자의 이름에 특정 용어가 포함되어 있는데, 이 용어에는 기본 설정된 대체 용어가 있습니다.  또는 이름에 Flag나 Flags라는 용어가 포함되어 있습니다.  
  
## 규칙 설명  
 이 규칙에서는 식별자를 토큰으로 구문 분석합니다.  각 토큰 및 연속되는 각 이중 토큰 조합을 사용자 지정 사전의 사용되지 않음 섹션 및 규칙에 있는 용어와 비교합니다.  다음 표에서는 규칙에 있는 용어와 해당 용어 대신 사용할 수 있는 대체 용어를 보여 줍니다.  
  
|사용되지 않는 용어|기본 설정 용어|  
|----------------|--------------|  
|Arent|AreNot|  
|취소됨|Canceled|  
|Cant|Cannot|  
|ComPlus|EnterpriseServices|  
|Couldnt|CouldNot|  
|Didnt|DidNot|  
|Doesnt|DoesNot|  
|Dont|DoNot|  
|Flag 또는 Flags|대신 사용할 수 있는 용어가 없습니다.  사용하지 마십시오.|  
|Hadnt|HadNot|  
|Hasn’t|HasNot|  
|Havent|HaveNot|  
|Indices|인덱스|  
|Isnt|IsNot|  
|LogIn|LogOn|  
|LogOut|LogOff|  
|Shouldnt|ShouldNot|  
|SignOn|SignIn|  
|SignOff|SignOut|  
|Wasnt|WasNot|  
|Werent|WereNot|  
|Wont|WillNot|  
|Wouldnt|WouldNot|  
|Writeable|Writable|  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 해당 용어를 기본 설정된 대체 용어로 바꿉니다.  
  
## 경고를 표시하지 않는 경우  
 식별자의 이름을 원래 이름과 의도적으로 특별히 연관시키려는 경우에만 이 규칙에서 경고를 표시하지 마십시오.  
  
## 관련 규칙  
 [이름 지정 경고](../code-quality/naming-warnings.md)