---
title: "중단점이 적중될 때 대화 상자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.whenbreakpointishit"
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
ms.assetid: 476e3d98-cf35-4338-b124-cd0f3010d854
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 중단점이 적중될 때 대화 상자
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 대화 상자를 사용하여 중단점에 도달할 때 발생하는 동작을 사용자 지정할 수 있습니다.  
  
## UI 요소 목록  
 **메시지 표시**  
 DebuggerDisplay 구문을 사용하여 메시지를 표시합니다.  자세한 내용은 [DebuggerDisplay 특성 사용](../debugger/using-the-debuggerdisplay-attribute.md)을 참조하십시오.  
  
 또한 이 텍스트 상자에서는 자체적으로 또는 DebuggerDisplay 식의 중괄호 안에 사용할 수 있는 $ADDRESS 같은 특수 키워드를 지원합니다.  사용할 수 있는 키워드는 대화 상자에 나열됩니다.  
  
 **계속 실행**  
 이 컨트롤은 **메시지 표시** 을 선택한 경우에만 활성화됩니다.  이 컨트롤을 선택하면 위치에 도달할 때 중단하는 대신 중단점을 추적점으로 사용하여 프로그램 실행 과정을 추적할 수 있습니다.  
  
## 참고 항목  
 [중단점 사용](../debugger/using-breakpoints.md)   
 [DebuggerDisplay 특성 사용](../debugger/using-the-debuggerdisplay-attribute.md)