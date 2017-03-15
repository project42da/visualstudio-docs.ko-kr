---
title: "VSPerfCLREnv | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "명령줄 도구, VSPerfCLREnv"
  - "명령줄, 도구"
  - "성능 도구, VSPerfCLREnv"
  - "프로파일링 도구, VSPerfCLREnv"
  - "VSPerfCLREnv 도구"
ms.assetid: 4bc9dd6e-379c-4930-9bba-59a4faa93303
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# VSPerfCLREnv
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSPerfCLREnv 도구는 .NET Framework 응용 프로그램을 프로파일링하는 데 필요한 환경 변수를 설정하는 데 사용됩니다.  다음 구문이 사용됩니다.  
  
```  
VsPerfCLREnv [/option]  
```  
  
 샘플링, 계측 또는 전역 프로파일링 중 사용할 프로파일링 형식에 따라 옵션을 다르게 선택할 수 있습니다.  프로파일링 데이터에서 계층 상호 작용을 포함하려면 별도의 옵션이 필요합니다.  각 옵션에 대한 구문이 다음 표에 설명되어 있습니다.  
  
> [!NOTE]
>  프로파일링이 완료되면 **\/off** 또는 **\/globaloff** 옵션을 통해 **VSPerfCLREnv** 를 실행하여 프로파일링에 필요한 환경 변수를 삭제할 수 있습니다.  자세한 내용은 여기에 나와 있는 환경 설정을 삭제하기 위한 VSPerfCLREnv 옵션을 참조하십시오.  
  
 **계층 상호 작용 데이터를 포함하기 위한 VSPerfCLREnv 옵션**  
  
> [!WARNING]
>  계층 상호 작용 프로파일링은 [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], 또는 [!INCLUDE[vs_pro_current_short](../profiling/includes/vs_pro_current_short_md.md)] 을 사용하여 수집 될 수 있습니다.  하지만, 계층 상호 작용 프로 파일링 데이터는 [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)] 및 [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] 에서만 볼 수 있습니다.  
  
 상호 작용 계층 프로파일링은 다중 계층 응용 프로그램에서는 ADO.NET 쿼리에 대한 추가 정보를 제공합니다.  동기 함수 호출에 대한 데이터만 수집됩니다.  모든 프로파일링 방법으로, 모든 프로파일링 실행에 상호 작용 데이터를 추가할 수 있습니다.  
  
 **InteractionOn** 및 **GlobalInteractionOn** 옵션을 사용하면 계층 상호 작용 데이터를 수집할 수 있습니다.  상호 작용 옵션을 설정하려면 먼저 응용 프로그램을 프로파일링하는 데 필요한 VSPerfCLREnv 환경 변수를 설정해야 합니다.  
  
 다음 예제에서는 샘플링 방법을 사용하는 프로파일링 실행 시 계층 상호 작용 데이터를 포함합니다.  
  
```  
VSPerfCLREnv /SampleOn  
VSPerfCLREnv /InteractionOn  
VSPerfCmd /Start:Sample /Output:MyApp.exe.vsp /Launch:MyApp.exe  
```  
  
 다음 예제에서는 Windows 서비스에 대해 프로파일링 실행 시 계층 상호 작용 데이터를 포함합니다.  
  
```  
VSPerfCLREnv /GlobalSampleOn  
VSPerfCLREnv /GlobalInteractionOn  
REM Restart the computer and start the service  
VSPerfCmd /Start:Sample /Output:MyService.exe.vsp   
VSPerfCmd /Attach:MyService.exe  
```  
  
 **프로세스 계측 프로파일링을 위한 VSPerfCLREnv 옵션**  
  
 다음 표에서는 계측 프로파일링을 위한 VSPerfCLREnv 옵션에 대해 설명합니다.  
  
|옵션|설명|  
|--------|--------|  
|**TraceOn**|계측 방법을 통해 프로파일링을 사용합니다.  메모리 할당 프로파일링 또는 개체 수명 데이터 수집은 허용하지 않습니다.|  
|**TraceGC**|계측 방법을 통해 메모리 할당 프로파일링을 사용합니다.  개체 수명 데이터 수집을 허용하지 않습니다.|  
|**TraceGCLife**|계측 방법을 통한 메모리 할당 프로파일링 및 개체 수명 데이터 수집을 허용합니다.|  
  
 **프로세스 샘플링 프로파일링을 위한 VSPerfCLREnv 옵션**  
  
 다음 표에서는 샘플링 프로파일링을 위한 VSPerfCLREnv 옵션에 대해 설명합니다.  
  
|옵션|설명|  
|--------|--------|  
|**SampleOn**|샘플링 방법을 통해 프로파일링을 사용합니다.  메모리 할당 프로파일링 또는 개체 수명 데이터 수집은 허용하지 않습니다.|  
|**SampleGC**|샘플링 방법을 통해 메모리 할당 프로파일링을 사용합니다.  개체 수명 데이터 수집을 허용하지 않습니다.|  
|**SampleGCLife**|샘플링 방법을 통해 메모리 할당 프로파일링을 사용합니다.  개체 수명 데이터 수집도 허용합니다.|  
|**SampleLineOff**|.NET 줄 수준 프로파일링 데이터의 수집을 사용하지 않습니다.|  
  
 **전역 프로파일링을 위한 VSPerfCLREnv 옵션**  
  
 사용자가 시작하지 않고 운영 체제에서 시작한 관리되는 서비스\(예: ASP.NET 웹 응용 프로그램\)를 프로파일링하려면 VSPerfCLREnv 옵션 중 전역 프로파일링을 위한 옵션을 사용합니다.  다음 표에서는 전역 버전의 VSPerfCLREnv 옵션에 대해 설명합니다.  이러한 옵션은 레지스트리에서 적절한 환경 변수를 설정합니다.  
  
|옵션|설명|  
|--------|--------|  
|**GlobalTraceOn**|계측 방법을 통해 전역 프로파일링을 사용합니다.  메모리 할당 이벤트 또는 개체 수명 데이터는 수집하지 않습니다.|  
|**GlobalTraceGC**|계측 방법을 통해 전역 메모리 할당 프로파일링을 사용합니다.  개체 수명 데이터 수집을 허용하지 않습니다.|  
|**GlobalTraceGCLife**|계측 방법을 통해 전역 메모리 할당 프로파일링을 사용합니다.  개체 수명 데이터 수집도 허용합니다.|  
|**GlobalSampleOn**|샘플링 방법을 통해 전역 프로파일링을 사용합니다.  메모리 할당 이벤트 또는 개체 수명 데이터는 수집하지 않습니다.|  
|**GlobalSampleGC**|샘플링 방법을 통해 전역 메모리 할당 프로파일링을 사용합니다.  개체 수명 데이터 수집을 허용하지 않습니다.|  
|**GlobalSampleGCLife**|샘플링 방법을 통해 전역 메모리 할당 프로파일링을 사용합니다.  개체 수명 데이터 수집도 허용합니다.|  
  
 **환경 설정을 삭제하기 위한 VSPerfCLREnv 옵션**  
  
 관리되는 응용 프로그램에 대한 프로파일링을 끝내면 다음 옵션 중 하나를 사용하여 VSPerfCLREnv에서 추가한 환경 변수를 삭제할 수 있습니다.  다음 표에서는 표준 환경 변수 및 전역 환경 변수를 삭제하는 방법을 설명합니다.  
  
|옵션|설명|  
|--------|--------|  
|**Off**|표준 .NET 프로파일링을 위한 환경 변수를 삭제합니다.  전역이 아닌 VSPerfClrEnv 옵션을 사용하여 프로파일러 환경 변수를 설정한 경우 이 옵션을 사용합니다.|  
|**GlobalOff**|전역 .NET 프로파일링을 위한 환경 변수를 삭제합니다.  프로파일러가 아닌 운영 체제에서 응용 프로그램을 시작했다면 이 옵션을 사용합니다.|  
  
## 설명  
 IDE에서 성능 탐색기를 사용하여 응용 프로그램을 시작하는 경우에는 관리되는 응용 프로그램을 프로파일링할 때 이러한 옵션을 사용할 필요가 없습니다.  성능 탐색기에서 사용자에게 필요한 환경 설정을 모두 설정합니다.  
  
 프로파일링하는 동안 환경이 제대로 설정되지 않은 경우 분석 도중 경고가 보고되고 관리되는 함수 이름이 제대로 확인되지 않습니다.  
  
## 참고 항목  
 [명령줄에서 프로파일링](../profiling/using-the-profiling-tools-from-the-command-line.md)