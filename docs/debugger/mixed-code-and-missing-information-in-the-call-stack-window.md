---
title: "호출 스택 창의 혼합 코드 및 누락된 정보 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
  - "SQL"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "관리 코드, 한 단계 실행"
  - "호출 스택 창, 혼합 모드 디버깅"
  - "호출 스택 창, 문제 해결"
  - "네이티브 프레임"
  - "관리되는 호출 스택"
  - "혼합 모드 디버깅, 호출 스택"
  - "실행 종료, 관리 코드"
ms.assetid: dd628427-e8d6-4fc2-b524-9d6393ea5376
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 호출 스택 창의 혼합 코드 및 누락된 정보
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

관리 코드에 대한 호출 스택과 네이티브 코드에 대한 호출 스택은 서로 다르기 때문에 코드 형식이 혼합된 경우 디버거에서 전제 호출 스택이 표시되지 않을 수 있습니다.  네이티브 코드가 관리 코드를 호출하면 **호출 스택** 창이 다음과 같이 변경될 수 있습니다.  
  
-   관리 코드 바로 위의 네이티브 프레임이 **호출 스택** 창에서 없어질 수 있습니다.  자세한 내용은 [방법: 호출 스택 창에 네이티브 프레임이 없을 때 관리 코드에서 나가기](../debugger/how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window.md)을 참조하십시오.  
  
-   디버거 외부에서 실행된 혼합 모드 응용 프로그램의 경우, **호출 스택** 창에 관리 코드만 표시될 수 있으며 네이티브 프레임은 표시되지 않습니다.  
  
 두 경우 모두 아주 드문 경우입니다.  관리 코드에 대한 대부분의 네이티브 호출에서는 호출 스택이 올바르게 나타납니다.  
  
## 참고 항목  
 [방법: 호출 스택 창 사용](../debugger/how-to-use-the-call-stack-window.md)