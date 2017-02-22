---
title: "파일 추적 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "msbuild, 파일 추적"
ms.assetid: e6c66ac0-3464-451f-9192-3b98dca21b4a
caps.latest.revision: 6
caps.handback.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 파일 추적
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

파일 추적은 특정 프로세스와 해당 자식 프로세스를 처리하기 위해 수행된 Windows 파일 시스템에 대한 호출을 로깅합니다.  아래에 나와 있는 함수를 호출하면 프로그램에서 이 로깅의 설정 및 해제 시기를 제어하고 사용할 로그 파일을 지정합니다.  
  
## 단원 내용  
 [EndTrackingContext](../msbuild/endtrackingcontext.md)  
 현재 컨텍스트의 추적을 중지합니다.  
  
 [ResumeTracking](../msbuild/resumetracking.md)  
 [SuspendTracking](../msbuild/suspendtracking.md) 호출 후에 추적을 다시 시작합니다.  
  
 [SetThreadCount](../msbuild/setthreadcount.md)  
 추적에 사용할 스레드 수를 설정합니다.  
  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)  
 새 추적 컨텍스트를 시작합니다.  
  
 [StartTrackingContextWithRoot](../msbuild/starttrackingcontextwithroot.md)  
 지정된 루트에서 새 추적 컨텍스트를 시작합니다.  
  
 [StopTrackingAndCleanup](../msbuild/stoptrackingandcleanup.md)  
 추적을 종료하고 사용된 리소스를 해제합니다.  
  
 [SuspendTracking](../msbuild/suspendtracking.md)  
 추적을 일시 중단합니다.  
  
 [WriteAllTLogs](../msbuild/writealltlogs.md)  
 모든 컨텍스트에 대한 추적 로그를 씁니다.  
  
 [WriteContextTLogs](../msbuild/writecontexttlogs.md)  
 현재 컨텍스트에 대한 추적 로그를 씁니다.