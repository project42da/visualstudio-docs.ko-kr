---
title: "VSPerfMon | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "VSPerfMon 도구"
  - "명령줄, 도구"
  - "명령줄 도구, VSPerfMon 도구"
  - "데이터[Visual Studio ALM], VSPerfMon 도구"
  - "성능 데이터, VSPerfMon 도구"
  - "성능 도구, VSPerfMon 도구"
  - "프로파일링 도구, VSPerfCmd"
ms.assetid: 37052afb-7a58-441f-bb17-f1587cc57068
caps.latest.revision: 30
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 30
---
# VSPerfMon
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSPerfMon 도구를 사용하여 응용 프로그램의 성능 데이터를 수집할 수 있습니다. 일반적으로 이 도구는 VSPerfCmd.exe에 의해 시작됩니다.  VSPerfMon은 VSPerfCmd 도구를 사용할 경우 제공되지 않는 프로세스 연결 또는 분리에 대한 추가 정보를 표시합니다.  이 정보를 보려면 별도의 창에서 VSPerfMon을 시작합니다.  VSPerfMon을 호출하려면 다음 구문을 사용합니다.  
  
```  
VSPerfMon [/U] </TRACE [/COUNTER:cfg] | /SAMPLE | /COVERAGE> /CROSSSESSION /OUTPUT <file name> [/WINCOUNTER:cfg] [/USER [DOMAIN\]username]  
```  
  
 다음 표에서는 VSPerfMon 도구 옵션에 대해 설명합니다.  
  
|옵션|설명|  
|--------|--------|  
|**U**|리디렉션된 콘솔 출력은 유니코드로 기록됩니다.  이 옵션을 가장 먼저 지정해야 합니다.|  
|**OUTPUT:** `<` *file name* `>`|출력을 지정된 파일 이름으로 리디렉션합니다.|  
|**TRACE**|계측된 프로파일링에 대해 성능 모니터를 시작합니다.|  
|**SAMPLE**|샘플링 프로파일링에 대해 성능 모니터를 시작합니다.|  
|**COVERAGE**|코드 검사 모음에 대해 성능 모니터를 시작합니다.|  
|**CONCURRENCY**|리소스 경합 프로 파일링에 대해 성능 모니터를 시작 합니다.|  
|**USER:** `[` *domain* `\]` *username*|지정된 계정으로부터 클라이언트가 성능 모니터에 액세스할 수 있도록 합니다.|  
|**CROSSSESSION**|상호 세션 프로파일링을 사용합니다.|  
|**COUNTER** `:cfg`|계측\(TRACE\) 프로파일링 방법을 사용하는 경우에는 계측 지점마다 수집할 CPU 카운터를 지정합니다.  여러 개의 카운터 옵션을 지정하면 여러 카운터 데이터를 수집할 수 있습니다.<br /><br /> 카운터\(*cfg*\) 데이터를 지정하려면 다음 구문을 사용합니다.<br /><br /> CounterName\[**,**Reload\[,FriendlyName\]\]<br /><br /> -   CounterName은 VSPerfCmd \/QueryCounters 명령을 통해 반환되는 카운터 이름입니다.<br />-   다시 로드는 카운터 이벤트 샘플링 간격입니다.  계측 방법에는 *Reload*과 이 매개 변수를 사용하지 마십시오.<br />-   값을 지정하면 FriendlyName이 프로파일링 도구 보고서 열 이름의 CounterName을 대체합니다.|  
|**WINCOUNTER** `:path`|표시 데이터와 함께 포함할 Windows 성능 카운터를 지정합니다.  `path`는 PDH 카운터 경로 형식의 Windows 성능 카운터입니다.  예를 들면 다음과 같습니다.<br /><br /> \\Processor\(0\)\\% Processor Time<br /><br /> \\System\\Context Switches\/sec|  
|**AUTOMARK** `:n`|\/WINCOUNTER를 사용하는 경우 자동 표시 간의 시간 간격\(밀리초\)을 지정합니다.  가장 가까운 500ms까지 반올림됩니다.<br /><br /> 자동 표시를 사용하지 않으려면 0을 사용합니다. \(값을 지정하지 않는 경우 기본값\=500ms\)|  
  
## 참고 항목  
 [VSInstr](../profiling/vsinstr.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [VSPerfReport](../profiling/vsperfreport.md)   
 [프로파일링 도구 보고서 뷰](../profiling/performance-report-views.md)