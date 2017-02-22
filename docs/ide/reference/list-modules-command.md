---
title: "모듈 목록 표시 명령 | Microsoft Docs"
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
  - "debug.listmodules"
helpviewer_keywords: 
  - "Debug.ListModules 명령"
  - "모듈 열거 명령"
  - "ListModules 명령"
ms.assetid: 3cb73774-6ac0-43b2-b781-75ed47175bfd
caps.latest.revision: 6
caps.handback.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 모듈 목록 표시 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

현재 프로세스에 해당하는 모듈을 나열합니다.  
  
## 구문  
  
```  
Debug.ListModules [/Address:yes|no] [/Name:yes|no] [/Order:yes|no]  
[/Path:yes|no] [/Process:yes|no] [/SymbolFile:yes|no]  
[/SymbolStatus:yes|no] [/Timestamp:yes|no] [/Version:yes|no]  
```  
  
#### 매개 변수  
 \/Address:`yes|no`  
 선택적 요소.  모듈의 메모리 주소를 표시할지 여부를 지정합니다.  기본값은 `yes`으로,  
  
 \/Name:`yes|no`  
 선택적 요소.  모듈 이름을 표시할지 여부를 지정합니다.  기본값은 `yes`으로,  
  
 \/Order:`yes|no`  
 선택적 요소.  모듈의 순서를 표시할지 여부를 지정합니다.  기본값은 `no`으로,  
  
 \/Path:`yes|no`  
 선택적 요소.  모듈의 경로를 표시할지 여부를 지정합니다.  기본값은 `yes`으로,  
  
 \/Process:`yes|no`  
 선택적 요소.  모듈의 프로세스를 표시할지 여부를 지정합니다.  기본값은 `no`으로,  
  
 \/SymbolFile:`yes|no`  
 선택적 요소.  모듈의 기호 파일을 표시할지 여부를 지정합니다.  기본값은 `no`으로,  
  
 \/SymbolStatus:`yes|no`  
 선택적 요소.  모듈의 기호 상태를 표시할지 여부를 지정합니다.  기본값은 `yes`으로,  
  
 \/Timestamp:`yes|no`  
 선택적 요소.  모듈의 타임스탬프를 표시할지 여부를 지정합니다.  기본값은 `no`으로,  
  
 \/Version:`yes|no`  
 선택적 요소.  모듈의 버전을 표시할지 여부를 지정합니다.  기본값은 `no`으로,  
  
## 설명  
  
## 예제  
 다음 예제에서는 현재 프로세스의 모듈 이름, 주소 및 타임스탬프를 표시합니다.  
  
```  
Debug.ListModules /Address:yes /Name:yes /Order:no /Path:no /Process:no /SymbolFile:no /SymbolStatus:no /Timestamp:yes /Version:no  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [방법: 모듈 창 사용](../../debugger/how-to-use-the-modules-window.md)