---
title: "TargetCLR | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f9732480-287f-40f1-a4ff-b112e143b940
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# TargetCLR
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**TargetCLR** 옵션은 응용 프로그램에 둘 이상의 CLR\(공용 언어 런타임\) 버전이 로드될 때 프로파일링할 CLR 버전을 지정합니다.  
  
 기본적으로 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구는 응용 프로그램에서 첫 번째로 로드하는 CLR 버전을 대상으로 합니다.  
  
## 구문  
  
```  
VSPerfCmd.exe {/Launch:AppName | /Attach:PID} /TargetCLR[:ClrVersion] [Options]   
```  
  
#### 매개 변수  
 `ClrVersion`  
 CLR의 버전 번호입니다.  **vN.N.NNNNN** 버전 형식을 사용합니다.  
  
## 필수 옵션  
 **TargetCLR** 옵션은 **Launch** 또는 **Attach** 옵션과 함께만 사용할 수 있습니다.  
  
 **Launch:** `AppName`  
 지정된 응용 프로그램을 시작하고 프로파일링을 시작합니다.  
  
 **Attach:** `PID`  
 지정된 프로세스에 대한 프로파일링을 시작합니다.  
  
## 예제  
 이 예제에서는 TargetCLR 옵션을 사용하여 CLR 버전 4.0.11003이 프로파일링되도록 합니다.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /TargetCLR:v4.0.11003  
```