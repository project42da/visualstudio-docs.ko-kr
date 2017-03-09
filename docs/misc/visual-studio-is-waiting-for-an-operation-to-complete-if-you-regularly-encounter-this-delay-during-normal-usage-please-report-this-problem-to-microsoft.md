---
title: "Visual Studio is waiting for an operation to complete. If you regularly encounter this delay during normal usage please report this problem to Microsoft. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.0x800A002A"
  - "vs.message.VB_E_IDWOLENOTRESPONDING"
ms.assetid: 0a4efbb7-72de-43a8-a51a-4a7a24ec743a
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Visual Studio is waiting for an operation to complete. If you regularly encounter this delay during normal usage please report this problem to Microsoft.
서버 응용 프로그램이 현재 요청을 완료하지 않았습니다.  
  
 이 오류는 일부 devenv.exe 프로세스를 차단하는 안티바이러스 소프트웨어 때문에 발생할 수도 있습니다.  제품의 몇몇 기능에서는 스크립트를 사용하며, 안티바이러스 소프트웨어에서 이러한 스크립트를 차단할 수도 있습니다.  관련 정보는 온라인 [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;306905&Product\=vsnet](http://support.microsoft.com/default.aspx?scid=kb;en-us;306905&Product=vsnet)에서 "PRB: Visual IDE does not open when started or application cannot start error message"를 참조하십시오.  
  
### 이 오류를 해결하려면  
  
-   전환을 선택하여 응용 프로그램을 열고 문제를 확인하십시오.  
  
     — 또는 —  
  
     다시 시도를 선택하여 서버 응용 프로그램이 요청을 처리할 때까지 기다리십시오.  
  
### 안티바이러스 관련 오류를 해결하려면  
  
-   사용 중인 안티바이러스 소프트웨어에서, devenv.exe에서 시작되는 스크립트가 실행되도록 지정합니다.  자세한 지침을 보려면 안티바이러스 소프트웨어 제품 설명서를 참조하십시오.