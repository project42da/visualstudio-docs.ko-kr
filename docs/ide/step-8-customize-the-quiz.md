---
title: "8단계: 퀴즈 사용자 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: dc8edb13-1b23-47d7-b859-8c6f7888c1a9
caps.latest.revision: 12
caps.handback.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 8단계: 퀴즈 사용자 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

튜토리얼의 마지막 부분에서, 이미 배운 내용에 대해 확장하고 퀴즈를 사용자 지정 하는 몇 가지 방식들을 살펴보도록 하겠습니다.  예를 들어, 답이 분수가 아닌 임의의 나누기 문제를 어떻게 만드는지에 대해 생각해봅시다.  보다 더 자세한 내용은, `timeLabel` 컨트롤의 색을 변경하고 사용자에게 힌트를 제공합니다.  
  
### 퀴즈의 사용자 지정  
  
-   퀴즈가 5초 남았을 때, **timeLabel** 컨트롤의 **BackColor** 속성을 빨강으로 설정합니다. \(`timeLabel.BackColor = Color.Red;`\).  퀴즈가 끝나면 색을 다시 설정합니다.  
  
-   NumericUpDown 컨트롤로 올바른 답이 입력되면 소리가 나게 하여 사용자에게 힌트를 제공합니다. 여러분은 사용자가 컨트롤의 값을 변경할 때마다, 발생하는 각 컨트롤의 `ValueChanged()` 이벤트에 대한 이벤트 처리기를 작성해야 합니다.  
  
### 계속하거나 검토하려면  
  
-   퀴즈의 전체 버전을 다운로드하려면 [전체 수학 퀴즈 자습서 샘플](http://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c)을 참조하십시오.  
  
-   다음 자습서로 이동하려면 [자습서 3: 일치 게임 만들기](../ide/tutorial-3-create-a-matching-game.md)를 참조하십시오.  
  
-   이전 자습서 단계로 돌아가려면 [7단계: 곱하기 및 나누기 문제 추가](../ide/step-7-add-multiplication-and-division-problems.md)를 참조하십시오.