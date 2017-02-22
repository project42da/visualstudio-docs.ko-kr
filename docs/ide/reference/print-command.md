---
title: "인쇄 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "debug.print"
helpviewer_keywords: 
  - "Debug.Print 명령"
  - "인쇄 명령"
  - "Print 메서드"
ms.assetid: 0412d381-590a-483f-bab4-6e1cca095645
caps.latest.revision: 10
caps.handback.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 인쇄 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

식을 계산하거나 지정한 텍스트를 표시합니다.  
  
## 구문  
  
```  
Debug.Print text  
```  
  
## 인수  
 `text`  
 필수 요소.  계산할 식 또는 표시할 텍스트입니다.  
  
## 설명  
 물음표\(?\)를 이 명령의 별칭으로 사용할 수 있습니다.  예를 들어,  
  
```  
>Debug.Print expA  
```  
  
 위의 명령을 다음과 같이 쓸 수도 있습니다.  
  
```  
>? expA  
```  
  
 이 명령의 두 버전 모두 `expA` 식의 현재 값을 반환합니다.  
  
## 예제  
  
```  
>Debug.Print varA  
```  
  
## 참고 항목  
 [문 실행 명령](../../ide/reference/evaluate-statement-command.md)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)