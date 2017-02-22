---
title: "VSPerf | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b5854e62-279e-4850-bfeb-0c6ef82f4805
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# VSPerf
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**VsPerf** 명령줄 도구를 사용하십시오:  
  
1.  Visual Studio가 장치에 설치되어 있지 않으면 명령줄에서 부터 Windows 저장소 응용 프로그램을 프로 파일링 합니다.  
  
2.  샘플링 프로 파일링 방법을 사용하여 Windows Server 2012 응용 프로그램 및 Windows 8 데스크톱 응용 프로그램을 프로 파일링 합니다.  
  
 프로파일링에 대한 정보를 [Windows 8 및 Windows Server 2012 응용 프로그램 프로파일링](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)에서 참조하십시오.  
  
##  <a name="BKMK_In_this_topic"></a> 항목 내용  
 이 항목은 `vsperf.exe` 명렬줄 도구와 함께 사용할 수 있는 옵션을 설명합니다.  이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
 [Windows 스토어 응용 프로그램](#BKMK_windows_store_apps_only)  
  
 [Windows 8 데스크톱 응용 프로그램 및 응용 프로그램 전용 Windows Server 2012](#BKMK_Windows_8_classic_applications_and_Windows_Server_2012_applications_only)  
  
 [모든 응용 프로그램.](#BKMK_All_applications)  
  
##  <a name="BKMK_windows_store_apps_only"></a> Windows 스토어 응용 프로그램  
 이러한 옵션 Windows 저장소 응용 프로그램에만 적용 됩니다.  
  
|||  
|-|-|  
|**\/app:{AppName}**|프로파일러를 시작하고 지정된 응용 프로그램에서 시작 메뉴에서 시작할 때까지 기다립니다.<br /><br /> `vsperf /listapps` 을 실행하여 응용 프로그램 이름 및 설치된 앱의 PackageFullName을 볼 수 있습니다.|  
|**\/package:{PackageFullName}**|프로파일러를 시작하고 지정된 응용 프로그램에서 시작 메뉴에서 시작할 때까지 기다립니다.<br /><br /> `vsperf /listapps` 을 실행하여 응용 프로그램 이름 및 설치된 앱의 PackageFullName을 볼 수 있습니다.|  
|**\/js**|JavaScript 응용 프로그램을 프로 파일링 하는 데 필요 합니다.<br /><br /> JavaScript 응용 프로그램에서 성능 데이터를 수집 합니다.<br /><br /> \/Package 또는 \/attach만 사용합니다.|  
|**\/noclr**|선택적 요소로서,  CLR 데이터를 수집하지 않습니다.<br /><br /> \/Package 또는 \/attach만 사용합니다.<br /><br /> 최적화, 관리되는 기호가 확인되지 않습니다.|  
|**\/listapps**|설치된 응용 프로그램 이름 및 PackageFullNames를 나열 합니다.|  
  
##  <a name="BKMK_Windows_8_classic_applications_and_Windows_Server_2012_applications_only"></a> Windows 8 데스크톱 응용 프로그램 및 응용 프로그램 전용 Windows Server 2012  
 Windows 저장소 응용 프로그램에서 이러한 옵션을 작동하지 않습니다.  
  
|||  
|-|-|  
|**\/launch:{Executable}**|시작하고 지정된 실행 파일을 프로 파일링을 시작 합니다.|  
|**\/args:{ExecutableArguments}**|**\/launch** 대상을 전달할 명령줄 인수를 지정합니다.|  
|**\/console**|**\/launch** 대상을 새 명령 창에서 실행합니다.|  
  
##  <a name="BKMK_All_applications"></a> 모든 응용 프로그램.  
 이 옵션은 Windows Server 2012 또는 Windows 응용 프로그램에 적용합니다.  
  
|||  
|-|-|  
|**\/attach:{PID&#124;ProcessName}\[,PID&#124;ProcessName\]...**|지정한 프로세스에서 데이터를 수집합니다.<br /><br /> 프로세스 실행 중인 응용 프로그램의 이름 및 프로세스 id \(PID\)를 확인하려면 작업 관리자를 사용합니다.|  
|**\/file:{ReportName}**|선택적 요소로서,  \(기존 파일을 덮어씁니다\) 출력 파일을 지정 합니다.<br /><br /> \/Package 또는 \/attach만 사용합니다.|  
|**\/pause**|데이터 수집을 일시 중지 합니다.|  
|**\/resume**|데이터 수집을 다시 시작 합니다.|  
|**\/stop**|데이터 수집을 중지하고 대상 프로세스를 종료합니다.|  
|**\/detach**|데이터 수집을 중지하지만 대상 프로세스는 계속 실행되도록 둡니다.|  
|**\/status**|프로파일러 상태를 표시 합니다.|  
  
## 참고 항목  
 [Windows 8 및 Windows Server 2012 응용 프로그램 프로파일링](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)   
 [명령줄에서 프로파일링](../profiling/using-the-profiling-tools-from-the-command-line.md)