---
title: "별칭 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tools.alias"
helpviewer_keywords: 
  - "별칭 명령"
  - "별칭, Visual Studio 명령"
  - "명령 별칭"
  - "명령, 별칭"
  - "Tools.Alias 명령"
ms.assetid: bdf857df-b5d5-450f-8c10-a6fd4dccc130
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 12
---
# 별칭 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

전체 명령, 전체 명령 및 인수 또는 다른 별칭에 대한 새 별칭까지도 만듭니다.  
  
> [!TIP]
>  `>alias` 를 인수 없이 입력하면 별칭과 해당 정의의 현재 목록이 표시됩니다.  
  
## 구문  
  
```  
Tools.Alias [/delete] [/reset] [aliasname] [aliasstring]  
```  
  
## 인수  
 `aliasname`  
 선택적 요소.  새 별칭의 이름입니다.  `aliasname`에 대한 값을 지정하지 않으면 현재 별칭 및 해당 정의에 대한 목록이 표시됩니다.  
  
 `aliasstring`  
 선택적 요소.  전체 명령 이름 또는 기존 별칭 및 별칭으로 만들려는 매개 변수입니다.  `aliasstring`에 대한 값을 지정하지 않으면 지정된 별칭에 대한 별칭 이름과 별칭 문자열이 표시됩니다.  
  
## 스위치  
 \/delete 또는 \/del 또는 \/d 또는 \/삭제  
 선택적 요소.  지정된 별칭을 자동 완성에서 제거하여 삭제합니다.  
  
 \/reset 또는 \/다시설정  
 선택적 요소.  미리 정의된 별칭을 원래 설정으로 되돌립니다.  즉, 미리 정의된 모든 별칭을 복원하고 모든 사용자 정의 별칭을 제거합니다.  
  
## 설명  
 별칭은 명령을 나타내므로 명령줄의 시작 부분에 있어야 합니다.  
  
 이 명령을 발행하는 경우, 별칭 다음이 아닌 명령 바로 다음에 스위치를 사용해야 합니다. 그렇지 않으면 스위치가 별칭 문자열의 일부로 포함될 것입니다.  
  
 `/reset` 스위치는 별칭을 복원하기 전에 확인을 요청합니다.  `/reset`의 약식 표현은 없습니다.  
  
## 예제  
 다음 예제에서는 전체 명령 편집.대문자로에 대해 `upper`라는 새로운 별칭을 만듭니다.  
  
```  
>Tools.Alias upper Edit.MakeUpperCase  
```  
  
 다음 예제에서는 `upper` 별칭을 삭제합니다.  
  
```  
>Tools.alias /delete upper  
```  
  
 다음 예제에서는 현재의 모든 별칭 및 정의에 대한 목록을 표시합니다.  
  
```  
>Tools.Alias  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)