---
title: "값을 변경할 수 없음 대화 상자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.variables.failededit"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "값을 변경할 수 없음 대화 상자"
  - "변수[디버거], 편집"
ms.assetid: 19e930c2-5fbf-4c83-aae8-a1dc3f8fcae8
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 값을 변경할 수 없음 대화 상자
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

## 오류  
 `The value of this variable cannot be changed`  &#124; `The name` *name* `does not exist in the current context` &#124; *various other messages*  
  
 이 메시지 상자는 디버거 창\(자동, 조사식 또는 지역 창\)이나 간략한 조사식 대화 상자에서 변수의 내용을 잘못된 값으로 변경하려고 할 때 나타납니다.  예를 들어 정수 변수의 값을 문자열로 설정하려고 하면 이 메시지 상자가 나타납니다.  
  
## 해결책  
 디버거 창이나 간략한 조사식 대화 상자에 입력한 값이 설정하려는 변수에 적합한 값인지 확인하십시오.  
  
## 참고 항목  
 [디버거에서 사용하는 식](../debugger/expressions-in-the-debugger.md)