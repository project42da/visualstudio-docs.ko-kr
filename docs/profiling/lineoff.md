---
title: "LineOff | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 76082063-20ef-47ae-ad64-81b43b654865
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# LineOff
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

기본적으로 프로파일러에서는 프로파일링 샘플링 방법을 사용할 때 소스 코드 줄 번호 및 줄 번호 오프셋 데이터를 수집합니다.  VSPerfCmd **LineOff** 옵션을 사용하면 VSPerfCmd를 사용하여 응용 프로그램을 시작할 때 줄 번호 데이터가 수집되지 않습니다.  **LineOff**가 지정된 경우 프로파일링 데이터는 함수 수준까지 수집됩니다.  
  
 **LineOff**는 **Launch** 옵션과 함께만 사용할 수 있으며 **Start**:**Sample** 옵션을 사용하여 프로파일러가 샘플링으로 초기화된 경우에만 사용할 수 있습니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /Launch:AppName /LineOff [Options]  
```  
  
#### 매개 변수  
 없음  
  
## 필수 옵션  
 **LineOff** 옵션은 **Launch** 옵션을 포함하는 명령줄에서만 사용할 수 있습니다.  
  
 **Launch:** `AppName`  
 지정된 응용 프로그램을 시작하고 샘플링 방법으로 프로파일링을 시작합니다.  
  
## 예제  
 이 예제에서는 응용 프로그램과 프로파일러를 시작하고 줄 수준 샘플링을 사용하지 않도록 설정합니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /LineOff  
```  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)