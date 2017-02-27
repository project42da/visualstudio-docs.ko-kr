---
title: "명령 창 출력 로그 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tools.logcommandwindowoutput"
helpviewer_keywords: 
  - "명령 창 출력 로그 명령"
  - "View.LogCommandWindowOutput 명령"
ms.assetid: d4ecec35-5af4-4954-8d60-2cd24583fbb4
caps.latest.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 10
---
# 명령 창 출력 로그 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

**명령** 창의 모든 입력과 출력을 파일에 복사합니다.  
  
## 구문  
  
```  
Tools.LogCommandWindowOutput [filename] [/on|/off] [/overwrite]  
```  
  
## 인수  
 `filename`  
 선택적 요소.  로그 파일의 이름입니다.  기본적으로 파일은 사용자의 프로필 폴더에 만들어집니다.  파일 이름이 이미 존재하는 경우에는 기존 파일의 끝에 로그가 추가됩니다.  파일을 지정하지 않으면 마지막으로 지정된 파일이 사용되며,  이전 파일이 없는 경우에는 cmdline.log라는 기본 로그 파일이 만들어집니다.  
  
> [!TIP]
>  로그 파일의 저장 위치를 변경하려면 파일의 전체 경로를 입력합니다. 공백을 포함하는 경로는 따옴표로 묶습니다.  
  
## 스위치  
 \/on 또는 \/설정  
 선택적 요소.  지정된 파일에서 **명령** 창에 대한 로깅을 시작하고 파일에 새 정보를 추가합니다.  
  
 \/off 또는 \/해제  
 선택적 요소.  **명령** 창에 대한 로깅을 중지합니다.  
  
 \/overwrite 또는 \/덮어쓰기  
 선택적 요소.  `filename` 인수에 지정한 파일이 기존 파일과 일치하는 경우 이 파일은 기존 파일을 덮어씁니다.  
  
## 설명  
 파일을 지정하지 않으면 기본적으로 cmdline.log 파일이 만들어집니다.  이 명령에 대한 기본 별칭은 Log입니다.  
  
## 예제  
 다음 예제에서는 cmdlog라는 새 로그 파일을 만들고 명령 로깅을 시작합니다.  
  
```  
>Tools.LogCommandWindowOutput cmdlog  
```  
  
 다음 예제에서는 명령 로깅을 중지합니다.  
  
```  
>Tools.LogCommandWindowOutput /off  
```  
  
 다음 예제에서는 이전에 사용된 로그 파일에 명령 로깅을 다시 시작합니다.  
  
```  
>Tools.LogCommandWindowOutput /on  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)