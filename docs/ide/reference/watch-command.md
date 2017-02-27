---
title: "조사식 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "debug.watch"
helpviewer_keywords: 
  - "Debug.Watch 명령"
  - "조사식 명령"
ms.assetid: aa02e647-d9f5-4905-a651-52a8df595795
caps.latest.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# 조사식 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

**조사식** 창의 지정한 인스턴스를 만들고 엽니다.  **조사식** 창을 사용하면 변수, 식, 레지스터의 값을 계산하여 이러한 값을 편집하고 결과를 저장할 수 있습니다.  
  
## 구문  
  
```  
Debug.Watch[index]  
```  
  
## 인수  
 `index`  
 필수 요소.  조사식 창의 인스턴스 번호입니다.  
  
## 설명  
 `index`는 정수여야 하며  올바른 값은 1, 2, 3, 4입니다.  
  
## 예제  
  
```  
>Debug.Watch1  
```  
  
## 참고 항목  
 [자동 및 지역 창](../../debugger/autos-and-locals-windows.md)   
 [방법: 변수 창에서 값 편집](../Topic/How%20to:%20Edit%20a%20Value%20in%20a%20Variable%20Window.md)   
 [방법: 간략한 조사식 대화 상자 사용](../Topic/How%20to:%20Use%20the%20QuickWatch%20Dialog%20Box.md)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)