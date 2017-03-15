---
title: "VSPerfASPNETCmd를 사용한 빠른 웹 사이트 프로파일링 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로파일링 도구, VSPerfASPNETCmd"
  - "VSPerfASPNETCmd"
ms.assetid: 9a9d62a6-549a-45ac-a948-76eb98586ac5
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# VSPerfASPNETCmd를 사용한 빠른 웹 사이트 프로파일링
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**VSPerfASPNETCmd** 명령줄 도구를 사용하면 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램을 쉽게 프로파일링할 수 있습니다.  이 명령줄 도구는 [VSPerfCmd](../profiling/vsperfcmd.md) 명령줄 도구에 비해 옵션 수가 적고, 환경 변수를 설정할 필요가 없으며, 컴퓨터를 다시 부팅할 필요가 없습니다.  따라서 독립 실행형 프로파일러를 사용하여 프로파일링할 때는 **VSPerfASPNETCmd**를 사용하는 것이 좋은 방법입니다.  자세한 내용은 [방법: 독립 실행형 프로파일러 설치](../profiling/how-to-install-the-stand-alone-profiler.md)을 참조하십시오.  
  
> [!NOTE]
>  Windows 8 및 Windows Server 2012의 강화된 보안 기능으로 Visual Studio 프로파일러가 해당 플랫폼에서 데이터를 수집하는 방식에 중요한 변경 사항이 발생합니다.  Windows 스토어 응용 프로그램에는 또한 새 컬렉션 기술이 필요합니다.  [Windows 8 및 Windows Server 2012 응용 프로그램 프로파일링](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)를 참조하십시오.  
  
 동시성 데이터를 수집하거나 프로파일링을 일시 중지했다가 다시 시작해야 하는 경우를 비롯한 일부 경우에는 **VSPerfCmd**를 사용하는 것이 좋은 프로파일링 방법입니다.  
  
> [!NOTE]
>  프로파일링 도구의 명령줄 도구는 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 설치 디렉터리의 \\Team Tools\\Performance Tools 하위 디렉터리에 있습니다.  64비트 컴퓨터에서는 32비트 \\Team Tools\\Performance Tools 디렉터리에 있는 VSPerfASPNETCmd 도구를 사용합니다.  프로파일러 명령줄 도구를 사용하려면 해당 도구 경로를 명령 프롬프트 창의 PATH 환경 변수에 추가하거나 명령 자체에 추가해야 합니다.  자세한 내용은 [명령줄 도구의 경로 지정](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)을 참조하십시오.  
  
## ASP.NET 응용 프로그램 프로파일링  
 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램을 프로파일링하려면 다음 단원에서 설명하는 명령 중 하나를 입력합니다.  그러면 웹 사이트가 시작되고 프로파일러에서 데이터 수집이 시작됩니다.  응용 프로그램을 실행한 다음 브라우저를 닫습니다.  프로파일링을 중지하려면 명령 프롬프트 창에서 Enter 키를 누릅니다.  
  
> [!NOTE]
>  기본적으로 명령 프롬프트는 **vsperfaspnetcmd** 명령 후 반환되지 않습니다.  하지만 **\/nowait** 옵션을 사용하면 명령 프롬프트가 반환되도록 할 수 있습니다.  [/NoWait 옵션 사용](#UsingNoWait)을 확인하세요.  
  
## 샘플링 방법을 사용하여 응용 프로그램 통계를 수집하려면  
 샘플링은 **VSPerfASPNETCmd** 도구의 기본 프로파일링 방법이므로 명령줄에서 지정할 필요가 없습니다.  다음 명령줄은 지정된 웹 응용 프로그램에서 응용 프로그램 통계를 수집합니다.  
  
 **vsperfaspnetcmd**  *websiteUrl*  
  
## 계측 방법을 사용하여 자세한 타이밍 데이터를 수집하려면  
 다음 명령줄을 사용하여 동적으로 컴파일된 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램에서 자세한 타이밍 데이터를 수집할 수 있습니다.  
  
 **vsperfaspnetcmd \/trace**  *websiteUrl*  
  
 웹 응용 프로그램의 정적으로 컴파일된 .dll 파일을 프로파일링하려면 [VSInstr](../profiling/vsinstr.md) 명령줄 도구를 사용하여 파일을 계측해야 합니다.  vsperfaspnetcmd \/trace 명령은 계측된 파일에서 얻은 데이터를 포함합니다.  
  
## .NET 메모리 데이터를 수집하려면  
 **\/Memory** 옵션은 .NET 메모리의 개체 할당에 대한 데이터를 수집하며, 해당 개체의 수명에 대한 데이터도 수집할 수 있습니다.  할당 데이터 수집은 **\/Memory** 데이터 옵션의 기본 모드이므로 명령줄에서 지정할 필요가 없습니다.  
  
 **vsperfaspnetcmd \/memory** *websiteUrl*  
  
 할당 데이터 외에 개체 수명 데이터도 수집하려면 다음과 같이 **Lifetime** 매개 변수를 사용합니다.  
  
 **vsperfaspnetcmd \/memory:lifetime** *websiteUrl*  
  
 다음과 같이 **\/Trace** 옵션을 사용하여 .NET 메모리 데이터와 함께 자세한 타이밍 정보도 포함할 수 있습니다.  
  
 **vsperfaspnetcmd \/memory**\[**:lifetime**\] **\/trace** `websiteUrl`  
  
## 계층 상호 작용 데이터를 수집하려면  
  
> [!WARNING]
>  계층 상호 작용 프로파일링 \(TIP\) 데이터는 [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], 또는 [!INCLUDE[vs_pro_current_short](../profiling/includes/vs_pro_current_short_md.md)] 을 사용하여 수집 될 수 있습니다.  하지만, 계층 상호 작용 프로 파일링 데이터는 [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)] 및 [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] 에서만 볼 수 있습니다.  
>   
>  Windows 또는 Windows Server 2012 정보 데이터를 수집 하려면 \(**\/trace**\) 옵션을 사용해야 합니다.  
  
 샘플링 데이터와 함께 계층 상호 작용 데이터를 수집하려면 다음 명령을 사용합니다.  
  
 **vsperfaspnetcmd \/tip** `websiteUrl`  
  
 계측 데이터와 함께 계층 상호 작용 데이터를 수집하려면 다음 명령을 사용합니다.  
  
 **vsperfaspnetcmd \/trace \/tip** *websiteUrl*  
  
 .NET 메모리 데이터와 함께 계층 상호 작용 데이터를 수집하려면 다음 명령을 사용합니다.  
  
 **vsperfaspnetcmd \/memory**\[**:lifetime**\] **\/tip** *websiteUrl*  
  
##  <a name="UsingNoWait"></a> \/NoWait 옵션 사용  
 기본적으로 명령 프롬프트는 **vsperfaspnetcmd** 명령 후 반환되지 않습니다.  하지만 다음 구문 옵션을 사용하면 명령 프롬프트가 반환되도록 할 수 있습니다.  그러면 명령 프롬프트 창에서 다른 작업을 수행할 수 있습니다.  프로파일링을 종료하려면 별도의 **vsperfaspnetcmd** 명령에서 **\/shutdown** 옵션을 사용합니다.  
  
 프로파일링을 시작하려면 다음 명령을 사용합니다.  
  
 **vsperfaspnetcmd** \[*\/Options*\] **\/nowait** *websiteUrl*  
  
 프로파일링을 종료하려면 다음 명령을 사용합니다.  
  
 **vsperfaspnetcmd \/shutdown** *websiteUrl*  
  
## 추가 옵션  
 이 단원의 앞부분에 나열된 명령 중 **vsperfaspnetcmd \/shutdown** 명령을 제외한 모든 명령에 다음 옵션을 추가할 수 있습니다.  
  
|옵션|설명|  
|--------|--------|  
|**\/Output:** `VspFile`|기본적으로 프로파일링 데이터 파일\(.vsp\)은 현재 디렉터리에 **PerformanceReport.vsp**라는 파일 이름으로 만들어집니다.  위치, 파일 이름 또는 둘 모두를 다르게 지정하려면 \/output 옵션을 사용합니다.|  
|**\/PackSymbols:Off**|기본적으로 VsPerfASPNETCmd는 .vsp 파일에 함수, 매개 변수 이름 등의 기호를 포함합니다.  하지만 기호를 포함하면 프로파일링 데이터 파일의 크기가 매우 커질 수 있습니다.  데이터를 분석할 때 기호가 포함된 .pdb 파일에 액세스할 수 있으면 \/packsymbols:off 옵션을 사용하여 기호를 포함하지 않도록 설정합니다.|