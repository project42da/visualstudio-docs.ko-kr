---
title: "/Out (devenv.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "/out Devenv 스위치"
  - "빌드[Visual Studio], 오류"
  - "빌드[Visual Studio], 로그"
  - "Devenv, /out 스위치"
  - "오류 로그[Visual Studio]"
  - "오류 로그[Visual Studio], 명령줄 빌드 오류"
  - "오류[Visual Studio], 빌드"
  - "out Devenv 스위치"
  - "출력 파일, 빌드 오류"
ms.assetid: 9002d8c2-36d4-451c-b489-8f01932f31f7
caps.latest.revision: 11
caps.handback.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /Out (devenv.exe)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

솔루션을 실행, 빌드, 다시 빌드 또는 배포할 때 오류를 저장하고 표시할 파일을 지정합니다.  
  
## 구문  
  
```  
devenv /out FileName  
```  
  
## 인수  
 `FileName`  
 필수 요소.  실행 파일을 빌드할 때 오류를 수신하는 파일의 이름과 경로입니다.  
  
## 설명  
 존재하지 않는 파일 이름을 지정한 경우에는 파일이 자동으로 만들어지며,  파일이 이미 존재하는 경우에는 파일의 기존 내용에 결과가 추가됩니다.  
  
 명령줄 빌드 오류는 **명령** 창 및 **출력** 창의 솔루션 빌더 뷰에 표시됩니다.  이 옵션은 무인 빌드 실행 중에 결과를 확인해야 하는 경우 유용합니다.  
  
## 예제  
 다음 예제에서는 `MySolution`을 실행하고 `MyErrorLog.txt`파일에 오류를 기록합니다.  
  
```  
devenv /run "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /out "C:\MyErrorLog.txt"  
```  
  
## 참고 항목  
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)   
 [\/Run](../../ide/reference/run-devenv-exe.md)   
 [\/Build](../../ide/reference/build-devenv-exe.md)   
 [\/Rebuild](../../ide/reference/rebuild-devenv-exe.md)   
 [\/Deploy](../../ide/reference/deploy-devenv-exe.md)