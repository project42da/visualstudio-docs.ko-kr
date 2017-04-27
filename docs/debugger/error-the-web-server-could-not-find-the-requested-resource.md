---
title: "오류: 요청한 리소스를 웹 서버에서 찾지 못했습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "디버거, 웹 응용 프로그램 오류"
ms.assetid: 1ceeaf30-918c-42bb-ace1-96944530fef3
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 오류: 요청한 리소스를 웹 서버에서 찾지 못했습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

보안 고려 사항 때문에 IIS에서 일반 오류를 반환했습니다.  
  
 한 가지 가능한 원인은 서버의 보안 구성입니다.  IIS 6.0 및 이전 버전에서는 URLScan이라는 추가 기능 프로그램을 사용하여 형식이 잘못된 의심스러운 요청을 필터링합니다.  IIS 7.0에서는 동일한 목적을 위해 요청 필터링이 기본적으로 제공됩니다.  두 경우 모두 요청 필터링이 지나치게 제한적이면 Visual Studio에서 서버를 디버깅하지 못할 수 있습니다.  
  
 이 오류의 가능한 원인은 매우 다양합니다.  가장 일반적인 원인 중 몇 가지는 IIS 설치 또는 구성 문제, 웹 사이트 구성 문제 또는 파일 시스템의 사용 권한 문제입니다.  브라우저를 사용하여 리소스에 액세스할 수 있습니다.  IIS가 구성된 방식에 따라 자세한 오류 메시지를 얻으려면 서버에서 로컬 브라우저를 사용하거나 IIS 오류 로그를 검사해야 할 수 있습니다.  
  
 IIS 문제 해결에 대한 자세한 내용은 [IIS Management and Administration](http://go.microsoft.com/fwlink/?LinkId=255872)을 참조하십시오.  
  
## 참고 항목  
 [UrlScan Security Tool](http://www.microsoft.com/technet/security/tools/urlscan.mspx)   
 [오류: 웹 서버가 잠겨 있기 때문에 디버깅을 사용하기 위해 필요한 DEBUG 동사를 사용할 수 없습니다.](../debugger/error-the-web-server-has-been-locked-down-and-is-blocking-the-debug-verb.md)