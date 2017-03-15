---
title: "&lt;name&gt; is not a valid solution name. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.VS_E_INVALIDSOLUTIONNAME"
  - "vs.message.0x800A00D3"
ms.assetid: 79b7870d-16bd-4527-8ce6-ffb015e7e330
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# &lt;name&gt; is not a valid solution name.
이 오류는 **명령** 창 또는 **찾기\/명령** 상자에 `File.NewProject` 명령을 입력할 때 \/sln:*solutionname* 인수 값의 서식을 잘못 지정한 경우 발생합니다.  
  
### 이 오류를 해결하려면  
  
1.  명령 구문을 다시 입력하고 선택적 인수 \/sln:*solutionname*을 생략하십시오.  고유한 솔루션 이름이 자동으로 생성됩니다.  
  
     — 또는 —  
  
     솔루션 이름에 선행 또는 후행 공백이 없는지 및 예약어가 아닌지 확인하십시오.  예약어에는 NUL, CON, AUX, COM*x* 또는 LPT*x*가 있으며 여기서 *x*는 1에서 9까지 숫자입니다.  
  
## 참고 항목  
 [명령 창](../ide/reference/command-window.md)