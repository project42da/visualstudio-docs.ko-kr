---
title: "내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrDiagnosticInfo_FullOSName"
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다.
내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다. 이는 현재 컴퓨터에 존재하지 않는 WMI에 의해 발생할 수 있습니다.  
  
 `My.Computer.Info.OSFullName` 속성 호출이 실패했습니다. 현재 컴퓨터에 WMI\(Windows Management Instrumentation\)가 설치되지 않아서 이 오류가 발생했을 수 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  `My.Computer.Info.OSFullName` 속성을 호출하는 주변에 `Try...Catch` 블록을 추가합니다.  
  
2.  WMI 및 이것을 설치하는 방법에 대한 자세한 내용은 에서 "Windows Management Instrumentation Core"를 검색하세요.  
  
## 참고 항목  
 [My.Computer.Info.OSFullName 속성](http://msdn.microsoft.com/ko-kr/b3b0fbd1-4dc5-428a-ad04-0d9fc9c2a9be)   
 [Visual Basic에서 예외 및 오류 처리](http://msdn.microsoft.com/ko-kr/3e351e73-cf23-40ab-8b60-05794160529e)   
 [Try...Catch...Finally Statement](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)