---
title: "Visual Studio is waiting for an operation to complete. If you regularly encounter this delay during normal usage please report this problem to Microsoft. Please include a description of the work you’re doing in Visual Studio and when possible instruction | Microsoft Docs"
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
  - "vs.message.VB_E_IDWOLEBUSY"
  - "vs.message.0x800A002B"
ms.assetid: 688fdf7e-c3ef-41f1-bc22-9f88f8f5b353
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Visual Studio is waiting for an operation to complete. If you regularly encounter this delay during normal usage please report this problem to Microsoft. Please include a description of the work you’re doing in Visual Studio and when possible instruction
서버 응용 프로그램이 사용 중이며 현재 요청을 완료할 수 없습니다.  
  
 이 오류는 일부 devenv.exe 프로세스를 차단하는 안티바이러스 소프트웨어 때문에 발생할 수도 있습니다.  제품의 몇몇 기능에서는 스크립트를 사용하며, 안티바이러스 소프트웨어에서 이러한 스크립트를 차단할 수도 있습니다.  관련 정보는 온라인 [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;306905&Product\=vsnet](http://support.microsoft.com/default.aspx?scid=kb;en-us;306905&Product=vsnet)에서 "PRB: Visual IDE does not open when started or application cannot start error message"를 참조하십시오.  
  
### 서버 응용 프로그램 관련 오류를 해결하려면  
  
1.  전환을 선택하여 응용 프로그램을 열고 문제를 확인하십시오.  
  
     — 또는 —  
  
     다시 시도를 선택하여 서버 응용 프로그램이 요청을 처리할 때까지 기다리십시오.  
  
     — 또는 —  
  
     취소를 선택하여 요청을 끝내십시오.  
  
### 안티바이러스 관련 오류를 해결하려면  
  
-   사용 중인 안티바이러스 소프트웨어에서, devenv.exe에서 시작되는 스크립트가 실행되도록 지정합니다.  자세한 지침을 보려면 안티바이러스 소프트웨어 제품 설명서를 참조하십시오.