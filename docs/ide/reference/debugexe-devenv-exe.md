---
title: "/DebugExe(devenv.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "/DebugExe[devenv.exe]"
  - "DebugExe 스위치"
  - "Devenv, /DebugExe 스위치"
ms.assetid: cd700006-1648-418f-924b-4b1e5c1412ab
caps.latest.revision: 4
caps.handback.revision: 4
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /DebugExe(devenv.exe)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버그할 지정된 실행 파일을 엽니다.  
  
## 구문  
  
```  
Devenv /debugexe ExecutableFile  
```  
  
## 인수  
 `ExecutableFile`  
 필수 요소.  .exe 파일의 경로와 파일 이름입니다.  
  
 .exe 파일을 찾을 수 없거나 이 파일이 없어도 경고 또는 오류가 표시되지 않고 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]가 정상적으로 시작됩니다.  
  
## 설명  
 `ExecutableFile` 매개 변수 뒤에 오는 모든 문자열은 해당 파일에 인수로 전달됩니다.  
  
## 예제  
 다음 예제에서는 디버깅을 위해 `MyApplication.exe` 파일을 엽니다.  
  
```  
Devenv.exe /debugexe MyApplication.exe  
```  
  
## 참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)