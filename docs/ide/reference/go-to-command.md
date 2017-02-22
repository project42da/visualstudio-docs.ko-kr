---
title: "이동 명령 | Microsoft Docs"
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
  - "edit.goto"
helpviewer_keywords: 
  - "Debug.Goto 명령"
  - "이동 명령"
ms.assetid: 201e1dd2-6701-467d-8cc1-faec2ef20511
caps.latest.revision: 10
caps.handback.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 이동 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

커서를 지정된 줄로 이동합니다.  
  
## 구문  
  
```  
Edit.GoTo [linenumber]  
```  
  
## 인수  
 `linenumber`  
 선택적 요소.  이동할 줄 번호를 나타내는 정수입니다.  
  
## 설명  
 줄 번호는 1부터 시작합니다.  `linenumber` 값이 1미만인 경우에는 첫째 줄이 표시되고,  `linenumber` 값이 마지막 줄 번호보다 큰 경우에는 마지막 줄이 표시됩니다.  
  
 `linenumber` 값을 지정하지 않으면 **줄 이동** 대화 상자가 표시됩니다.  
  
 이 명령의 별칭은 GoToLn입니다.  
  
## 예제  
  
```  
>Edit.GoTo 125  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)