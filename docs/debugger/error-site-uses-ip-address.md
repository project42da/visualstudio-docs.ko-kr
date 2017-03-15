---
title: "오류: 사이트에서 IP 주소를 사용합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.error.webdbg_siteusesipaddress"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "디버거, 웹 응용 프로그램 오류"
ms.assetid: b2b8ddc8-746d-46e3-87a6-b956b1ee048d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# 오류: 사이트에서 IP 주소를 사용합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 오류는 디버거에서 IP 주소를 사용하는 웹 응용 프로그램에 자동으로 연결하려고 할 때 발생합니다.  IIS에서 **웹 사이트 확인**을 **특정 IP 주소 사용**으로 변경하는 경우가 이에 해당합니다.  
  
 자동 연결이 제대로 동작하기 위해서는 컴퓨터 이름뿐 아니라 특정 IP 주소도 함께 사용하여 프로젝트를 만들어야 합니다.  그렇지 않으면 디버거에서 컴퓨터 이름을 localhost로 변경하므로 DEBUG 동사를 IIS로 보낼 수 없게 됩니다.  
  
### 이 오류를 해결하려면  
  
1.  디버그 메뉴에서 **프로세스에 연결**을 선택하여 자동 연결 대신 수동 연결을 사용합니다.  
  
     —또는—  
  
2.  **IIS 웹 사이트 확인** 설정을 변경합니다.  
  
## 참고 항목  
 [웹 응용 프로그램 디버깅: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)