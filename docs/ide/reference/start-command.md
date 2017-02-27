---
title: "시작 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "debug.start"
helpviewer_keywords: 
  - "Debug.Start 명령"
  - "시작 명령"
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# 시작 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

시작 프로젝트 디버깅을 시작합니다.  
  
## 구문  
  
```  
Debug.Start [address]  
```  
  
## 인수  
 `address`  
 선택적 요소.  프로그램에서 명령을 일시 중단하는 주소입니다. 이 주소는 소스 코드의 중단점과 비슷합니다.  이 인수는 디버그 모드에서만 사용할 수 있습니다.  
  
## 설명  
 **Start** 명령이 실행되면 지정된 주소에 커서까지실행 작업을 수행합니다.  
  
## 예제  
 다음 예제에서는 디버거를 시작하고 발생하는 예외를 모두 무시합니다.  
  
```  
>Debug.Start  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)