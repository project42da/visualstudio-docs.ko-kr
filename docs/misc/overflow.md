---
title: "Overflow. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.VB_E_OVERFLOW"
  - "vs.message.0x800A0097"
ms.assetid: 632387b9-be9c-4744-bcc5-842c45582347
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Overflow.
할당이 할당 대상의 제한을 초과하였습니다.  이 오류는 다음 중 하나가 참일 경우 발생합니다.  
  
-   할당, 계산 또는 데이터 형식 변환 결과가 너무 커서 해당 변수 형식에 허용하는 범위의 값으로 나타낼 수 없습니다.  
  
-   속성에 대한 할당이 속성에서 허용하는 최대값을 초과합니다.  
  
-   정수로 변환된 숫자를 계산에 사용하려고 했지만 그 결과가 정수보다 큽니다.  
  
### 이 오류를 해결하려면  
  
1.  더 큰 범위의 값을 가질 수 있는 변수 형식에 값을 할당하십시오.  
  
     — 또는 —  
  
     할당이 속성 범위에 맞는지 확인하십시오.