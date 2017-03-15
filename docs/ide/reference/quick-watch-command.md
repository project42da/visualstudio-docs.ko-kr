---
title: "간략한 조사식 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "debug.quickwatch"
helpviewer_keywords: 
  - "Debug.Quickwatch 명령"
  - "간략한 조사식 명령"
ms.assetid: 9670ac3a-8f2f-4874-974d-cb87d3b0cde1
caps.latest.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# 간략한 조사식 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[간략한 조사식 대화 상자](../Topic/How%20to:%20Use%20the%20QuickWatch%20Dialog%20Box.md)의 식 필드에 선택했거나 지정한 텍스트를 표시합니다.  이 대화 상자를 사용하면 디버거에 인식된 변수나 식의 현재 값 또는 레지스터 내용을 계산하고,  비 const 변수의 값이나 모든 레지스터 내용을 변경할 수 있습니다.  
  
## 구문  
  
```  
Debug.QuickWatchq [text]  
```  
  
## 인수  
 `text`  
 선택적 요소.  **간략한 조사식** 대화 상자에 추가할 텍스트입니다.  
  
## 설명  
 `text`를 생략하면 커서 위치에 있는 현재 선택된 텍스트나 단어가 조사식 창에 추가됩니다.  
  
## 예제  
  
```  
>Debug.QuickWatch  
```  
  
## 참고 항목  
 [방법: 간략한 조사식 대화 상자 사용](../Topic/How%20to:%20Use%20the%20QuickWatch%20Dialog%20Box.md)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)