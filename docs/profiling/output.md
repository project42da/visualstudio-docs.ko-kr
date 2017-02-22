---
title: "출력 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5e286e61-4548-42cf-a635-e608c5edbe2b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 출력
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**Output** 옵션은 성능 세션에 대한 프로파일링 데이터 파일의 이름을 지정합니다.  **Output**은 **Start** 옵션과 함께 사용해야 합니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName [Options]  
```  
  
#### 매개 변수  
 `FileName`  
 데이터 파일의 이름입니다.  전체 및 부분 경로를 사용할 수 있습니다.  경로를 지정하지 않으면 현재 디렉터리에 파일이 만들어집니다.  
  
## 필수 옵션  
 **Output** 옵션은 **Start** 옵션과 함께 사용해야 합니다.  
  
 **Start:** `Method`  
 출력 파일 이름을 지정합니다.  
  
## 예제  
 다음 예제에서는 현재 디렉터리에 프로파일링 데이터 파일이 만들어집니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
```  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)