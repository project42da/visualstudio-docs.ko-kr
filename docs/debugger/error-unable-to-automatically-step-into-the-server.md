---
title: "오류: 서버에 대해 자동으로 한 단계씩 코드를 실행할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.error.causality_no_server_response"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "원격 디버깅, 알림 오류"
ms.assetid: 9a370ccc-d358-429c-b285-9b6c0649bc68
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# 오류: 서버에 대해 자동으로 한 단계씩 코드를 실행할 수 없습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 오류 메시지는 다음과 같습니다.  
  
 서버에 대해 자동으로 한 단계씩 코드를 실행할 수 없습니다. 원격 프로시저가 실행되기 전에 디버거에 알리지 않았습니다.  
  
 이 오류는 웹 서비스를 한 단계씩 실행하려 할 때 발생할 수 있습니다. [한 단계씩 XML Web Services 실행](http://msdn.microsoft.com/ko-kr/8e67de38-bf5f-41cc-a457-1b88ce63d764)을 참조하세요. 이 오류는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]이 잘못 설정된 경우에 발생할 수 있습니다.  
  
 가능한 원인은 다음과 같습니다.  
  
-   [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램의 web.config 파일에서 디버그 모드를 "true"로 설정하지 않았습니다. [ASP.NET 응용 프로그램의 디버그 모드](../debugger/how-to-enable-debugging-for-aspnet-applications.md)를 참조하세요.  
  
-   Visual Studio가 설치된 후 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 버전이 설치되었습니다.[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]은 Visual Studio보다 먼저 설치해야 합니다. 이 문제를 해결하려면 Windows **제어판**, **프로그램 및 기능**을 사용하여 Visual Studio 설치를 복구합니다.  
  
## 참고 항목  
 [원격 디버깅 오류 및 문제 해결](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [원격 디버깅](../debugger/remote-debugging.md)