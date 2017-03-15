---
title: "GC(VSPerfCmd) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7c81e88b-a748-4cf5-a7a1-3429608e1b54
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# GC(VSPerfCmd)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**GC** 옵션을 사용하면 .NET Framework 메모리 할당 데이터 및 개체 수명 데이터를 수집할 수 있습니다.  **GC** 옵션은 샘플링 프로파일링 방법을 사용할 경우 **Launch** 옵션과 함께만 사용할 수 있습니다.  
  
 **GC** 옵션을 사용할 경우 VSPerfClrEnv **\/sampleon** 명령은 필요하지 않습니다.  
  
 매개 변수를 전혀 지정하지 않거나 **Allocation** 매개 변수를 지정한 경우에는 .NET Framework 메모리 할당 데이터만 수집됩니다.  **Lifetime** 매개 변수를 지정한 경우에는 .NET Framework 메모리 할당 데이터와 .NET Framework 개체 수명 데이터가 모두 수집됩니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /Launch:AppName /GC[:{Allocation|Lifetime}] [Options]  
```  
  
#### 매개 변수  
 **Allocation**  
 기본값입니다.  .NET Framework 메모리 할당 데이터를 수집합니다.  
  
 **Lifetime**  
 .NET Framework 메모리 할당 데이터와 .NET Framework 개체 수명 데이터를 모두 수집합니다.  
  
## 필수 옵션  
 **GC** 옵션은 **Launch** 옵션과 함께만 사용할 수 있습니다.  
  
 **Launch:** `AppName`  
 지정된 응용 프로그램을 시작하고 샘플링 방법으로 프로파일링을 시작합니다.  
  
## 예제  
 다음 예제에서는 응용 프로그램을 시작하고 .NET Framework 메모리 할당 데이터를 수집합니다.  
  
```  
VSPerfCmd.exe /Launch:TestApp.exe /gc  
```  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)