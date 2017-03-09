---
title: "로그에 대한 스트림을 가져올 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrApplicationLog_ExhaustedPossibleStreamNames"
ms.assetid: 33994f52-8efb-4790-a459-033e5c1db632
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 로그에 대한 스트림을 가져올 수 없습니다.
로그에 대한 스트림을 가져올 수 없습니다. \<name\>을 기반으로 한 파일 이름이 이미 사용 중입니다.  
  
 \<name\>을 기반으로 한 모든 잠재적 로그 파일 이름이 이미 사용 중이므로 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 클래스에서 새 로그 파일을 만들 수 없습니다.  
  
 로그 파일이 너무 많으면 응용 프로그램의 아키텍처 문제를 나타낼 수도 있습니다. 자세한 내용은 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 클래스에 대한 설명서를 참조하세요.  
  
### 이 오류를 해결하려면  
  
1.  <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A> 속성을 <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption> 또는 <xref:Microsoft.VisualBasic.Logging.LogFileCreationScheduleOption>로 설정하여 로그 파일 이름에 날짜 스탬프를 포함합니다.  
  
2.  <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 개체가 새 로그를 만들 수 있도록 기존 로그를 보관하고 컴퓨터에서 제거합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>   
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.LogFileCreationSchedule%2A>   
 [My.Application.Log 개체](/dotnet/visual-basic/language-reference/objects/my-application-log-object)   
 [My.Log Object](/dotnet/visual-basic/language-reference/objects/my-log-object)