---
title: "오류: ASP.NET이 설치되어 있지 않습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.error.http_not_supported"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ASP.NET, 설치 오류 메시지"
  - "디버거, 웹 응용 프로그램 오류"
  - "오류 메시지, ASP.NET"
  - "웹 응용 프로그램, 오류"
ms.assetid: 6286dd3d-3e2b-4edd-959d-81e0ed45500b
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 오류: ASP.NET이 설치되어 있지 않습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 오류는 디버깅하려는 컴퓨터에 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]이 제대로 설치되어 있지 않을 때 발생합니다.  [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]이 설치되지 않았거나 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]을 먼저 설치하고 나중에 IIS를 설치했을 수 있습니다.  
  
### ASP.NET을 다시 설치하려면  
  
1.  명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
    ```  
    \WINDOWS\Microsoft.NET\Framework\version\aspnet_regiis -i  
    ```  
  
     여기에서 *version*은 컴퓨터에 설치된 .NET Framework의 버전 번호\(예: v1.0.370\)입니다.  프레임워크 버전은 `\WINDOWS\Microsoft.NET\Framework` 디렉터리에서 확인할 수 있습니다.  
  
    > [!NOTE]
    >  Windows Server 2003에서는 제어판의 **프로그램 추가\/제거**를 사용하여 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]을 설치할 수 있습니다.  
  
## 참고 항목  
 [웹 응용 프로그램 디버깅: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)