---
title: "이벤트(VSPerfCmd) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eb139327-4783-4f2a-874c-efad377a7be4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 이벤트(VSPerfCmd)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSPerfCmd.exe **Events** 옵션은 ETW\(Windows용 이벤트 추적\) 로깅을 제어합니다.  ETW 데이터는 프로파일러 데이터 파일과는 별개인 .etl 파일에 저장됩니다.  이 데이터는 [VSPerfReport](../profiling/vsperfreport.md) \/summary:etw 명령을 사용하여 보고서에서 볼 수 있습니다.  
  
 **Events** 옵션은 VSPerfCmd **Shutdown** 명령을 호출하여 프로파일링을 중지하기 전에 언제든지 호출할 수 있습니다.  
  
## 구문  
  
```  
VSPerfCmd.exe /events {On|Off} {Guid|ProviderName} [,Flags[,Level]  
```  
  
#### 매개 변수  
 **On**&#124;**Off**  
 이벤트 데이터 수집을 시작하거나 중지합니다.  
  
 `Guid`  
 공급자 컨트롤의 GUID입니다.  
  
 `ProviderName`  
 WMI\(Windows Management Instrumentation\)에 등록된 공급자의 이름입니다.  
  
 `Flags`  
 이벤트 공급자에 의해 정의되고 "0x" 접두사가 지정된 16진수 플래그 값입니다.  
  
 `Level`  
 수집되는 데이터의 크기를 지정합니다.  `Level`은 이벤트 공급자에 의해 정의됩니다.  
  
 **Events** 옵션은 다음과 같은 커널 키워드를 공급자 이름으로 인식합니다.  
  
 **Process**  
 프로세스 이벤트입니다.  
  
 **Thread**  
 스레드 이벤트입니다.  
  
 **Image**  
 이미지 로드 및 언로드 이벤트입니다.  
  
 **Disk**  
 디스크 I\/O 이벤트입니다.  
  
 **File**  
 파일 I\/O 이벤트입니다.  
  
 **Hardfault**  
 하드 페이지 폴트입니다.  
  
 **Pagefault**  
 소프트 페이지 폴트입니다.  
  
 **Network**  
 네트워크 이벤트입니다.  
  
 **Registry**  
 레지스트리 액세스 이벤트입니다.  
  
 커널 공급자는 활성화만 가능합니다.  모니터를 종료하기 전까지는 커널 공급자를 비활성화할 수 없으며 해당 플래그를 수정할 수도 없습니다.  
  
## 설명  
  
> [!NOTE]
>  CLR ETW 이벤트가 활성화되면 추적 뷰 보고서에 추가적인 시작 데이터도 수집됩니다.  시작 이벤트가 보고서에 나타나지 않도록 하려면 다음 명령을 사용합니다.  
  
```  
C:\<path>VSPerfCmd -events on, \".NET Common Language Runtime\", 0x7fffffff, 5  
```  
  
> [!IMPORTANT]
>  시작 이벤트를 제외하지 않으면 시작 이벤트가 MOF\(Managed Object Format\) 파일에 나열되지 않았기 때문에 보고서에 GUID로 나타납니다.  자세한 내용은 이 페이지에서 Microsoft 웹 사이트를 [샘플 관리 되는 개체 서식 \(MOF\) 파일](http://go.microsoft.com/fwlink/?linkid=37118)를 참조하십시오.  
  
## 참고 항목  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [독립 실행형 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [ASP.NET 웹 응용 프로그램 프로파일링](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [서비스 프로파일링](../profiling/command-line-profiling-of-services.md)