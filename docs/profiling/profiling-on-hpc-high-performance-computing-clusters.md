---
title: "HPC(High Performance Computing) 클러스터에서 프로파일링 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.hpc.wizard.exeoptions"
  - "vs.performance.hpc.wizard.summary"
  - "vs.performance.hpc.wizard.startoptions"
  - "vs.performance.hpc.wizard.intro"
  - "vs.performance.hpc.property.basic"
  - "vs.performance.hpc.wizard.application"
  - "vs.performance.hpc.wizard.clusteroptions"
  - "vs.performance.hpc.property.advanced"
helpviewer_keywords: 
  - "프로파일링 도구,HPC"
  - "HPC 프로파일링"
ms.assetid: 1525bbdb-27da-4088-8487-a486cee5e7b3
caps.latest.revision: 22
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 22
---
# HPC(High Performance Computing) 클러스터에서 프로파일링
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsPreExt](../profiling/includes/vspreext_md.md)] 또는 [!INCLUDE[vsUltExt](../profiling/includes/vsultext_md.md)] 프로파일링 도구의 샘플링 방법을 사용하여 Microsoft Windows HPC 클러스터의 계산 노드에 대해 프로파일링할 수 있습니다.  HPC에 대한 자세한 내용은 Microsoft 웹 사이트에서 [Windows HPC](http://go.microsoft.com/fwlink/?LinkId=165393) 를 참조하십시오.  
  
## 필수 구성 요소  
 HPC 계산 노드에 대해 프로파일링하려면 다음을 수행해야 합니다.  
  
-   [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)]과 동일한 컴퓨터에 Microsoft HPC 팩 2008을 설치합니다.  이 컴퓨터는 HPC 클러스터의 일부가 아니어도 됩니다.  [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/?LinkID=177414) 에서 HPC 팩을 설치할 수 있습니다.  
  
-   HPC 계산 노드에 [!INCLUDE[net_v40_long](../profiling/includes/net_v40_long_md.md)]와 독립 실행형 버전의 프로파일링 도구를 설치합니다.  프로그램을 두 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 에 설치합니다. 독립 실행형 프로파일러는 [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] 설치 미디어에서 사용할 수 있습니다.  **Note** [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 설치 후, 그리고 프로 파일링 도구를 설치하기 전에 계산을 다시 시작 해야 합니다.  
  
 활성 HPC 계산 노드에 [!INCLUDE[net_v40_long](../profiling/includes/net_v40_long_md.md)]와 독립 실행형 프로파일링 도구를 설치하고 클러스터 컴퓨터에서 프로파일링을 사용하도록 설정하려면 다음 단계를 수행합니다.  
  
1.  HPC 팩과 함께 설치된 명령 프롬프트 창을 엽니다.  
  
2.  다음 명령을 개별 명령 프롬프트에 입력합니다.  
  
    1.  `clusrun /all /scheduler:` *%HeadNode% %FxPath%* `/q /norestart`  
  
    2.  `clusrun /all /scheduler:` *%HeadNode%* `shutdown /r /t 0 /d u:4:2 /c "Microsoft .NET Framework install required restart"`  
  
    3.  `clusrun /all /scheduler:` *%HeadNode% %ProfilerPath%* `/q /norestart`  
  
|||  
|-|-|  
|*%HeadNode%*|클러스터의 헤드 노드 이름입니다.|  
|*%FxPath%*|[!INCLUDE[net_v40_long](../profiling/includes/net_v40_long_md.md)] 설치 관리자의 경로입니다.  [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] 설치 미디어의 경우 이 경로는 WCU\\dotNetFramework\\dotNetFx40\_Full\_x86\_x64.exe입니다.|  
|*%ProfilerPath%*|독립 실행형 버전 프로파일링 도구 설치 관리자의 경로입니다.  [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] 설치 미디어의 경우 이 경로는 Standalone Profiler\\x64\\vs\_profiler.exe입니다.|  
  
## HPC 계산 노드에 대한 프로파일링  
 HPC 성능 마법사에서 HPC 클러스터 및 대상 정보를 지정하여 프로파일링 세션을 구성할 수 있습니다.  성능 세션 속성 페이지에서는 추가 옵션을 설정할 수 있습니다.  프로파일링 도구에서는 자동으로 필요한 대상 이진 파일을 배포하고 프로파일러와 HPC 응용 프로그램을 시작합니다.  
  
#### HPC 계산 노드에 대해 프로파일링하려면  
  
1.  **분석** 메뉴에서 **HPC 성능 마법사 시작**을 클릭합니다.  이 명령이 표시되지 않으면 위의 사전 요구 사항이 충족되었는지 확인합니다.  
  
2.  마법사의 첫 번째 페이지에서 **다음**을 클릭합니다.  
  
3.  마법사의 두 번째 페이지에서 프로파일링할 응용 프로그램을 선택합니다.  
  
    -   [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]에 현재 열려 있는 프로젝트를 프로파일링하려면 **하나 이상의 사용 가능한 프로젝트** 옵션을 선택한 다음 목록에서 프로젝트 이름을 선택합니다.  
  
    -   열려 있는 프로젝트에 없는 이진 파일을 프로파일링하려면 **실행 파일\(.EXE 파일\)** 옵션을 선택합니다.  
  
4.  **다음**을 클릭합니다.  
  
5.  마법사의 세 번째 페이지에서 다음을 수행합니다.  
  
    -   열려 있는 프로젝트에 없는 실행 파일을 프로파일링하려면 **실행 파일의 전체 경로**에서 해당 이진 파일의 경로를 지정합니다.  
  
    -   열려 있는 프로젝트에 없는 실행 파일을 프로파일링할 경우 **명령줄 인수**에서 프로세스에 전달할 명령줄 인수를 지정할 수 있습니다.  
  
    -   **원격 작업 디렉터리**에서 개별 계산 노드의 프로세스 인스턴스가 사용하는 폴더의 경로를 지정합니다.  
  
    -   **배포 위치**에서 HPC 서버가 배포용 이미지를 스테이징하는 데 사용하는 디렉터리의 경로를 지정합니다.  
  
6.  **다음**을 클릭합니다.  
  
7.  마법사의 네 번째 페이지에서 다음을 수행합니다.  
  
    -   **헤드 노드** 목록에서 프로파일링 실행 시 HPC 헤드 노드로 사용할 컴퓨터를 클릭합니다.  헤드 노드를 "localhost"로 지정하면 클러스터 없이도 로컬 컴퓨터에 대해 프로파일링할 수 있습니다.  
  
    -   **프로세스 수** 목록에서 실행할 응용 프로그램의 인스턴스 수를 클릭합니다.  
  
    -   **프로파일링 옵션** 목록에서 프로파일링 대상을 선택합니다.  
  
         클러스터의 특정 프로세스를 프로파일링하려면 **순위의 프로필** 옵션을 선택한 다음 드롭다운 목록에서 프로세스 순위를 선택합니다.  
  
         HPC 클러스터의 특정 노드에서 실행되는 프로세스를 프로파일링하려면 **노드의 프로필** 옵션을 선택한 다음 드롭다운 목록에서 노드를 선택합니다.  
  
8.  **다음**을 클릭합니다.  
  
9. 마법사의 다섯 번째 페이지에서는 프로파일러와 프로파일링 프로세스를 즉시 시작할지, 나중에 성능 탐색기를 사용하여 프로파일링을 시작할지를 선택할 수 있습니다.  
  
    -   프로파일링을 즉시 시작하려면 **마법사를 완료한 후 프로파일링을 시작합니다.**를 선택하고, 프로파일링을 수동으로 시작하려면 이 확인란의 선택을 취소합니다.  
  
10. **마침**을 클릭합니다.  
  
## 성능 세션 속성 페이지를 사용하여 HPC 프로파일링 속성 설정  
 HPC 프로파일링 마법사에서 설정한 성능 세션 속성을 성능 세션 속성 페이지의 HPC 시작 속성 페이지에서 변경할 수 있습니다.  HPC 고급 속성 페이지에서는 추가 옵션을 설정할 수 있습니다.  
  
#### 성능 세션 속성 페이지를 열려면  
  
1.  필요한 경우 성능 탐색기에서 성능 세션 파일\(.psess\)을 엽니다.  **파일** 메뉴에서 **열기**를 클릭한 다음 파일을 찾습니다.  
  
2.  성능 탐색기에서 성능 세션 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
3.  속성 페이지 대화 상자에서 다음 방법 중 하나를 사용합니다.  
  
    -   **일반**을 클릭한 다음 **HPC 클러스터에서 수집**을 선택하여 HPC 프로파일링을 설정하거나, 이 확인란의 선택을 취소하여 HPC 프로파일링을 해제합니다.  
  
    -   **HPC 시작 속성**을 클릭하여 HPC 응용 프로그램을 시작하는 속성을 변경합니다.  
  
    -   **HPC 고급 속성**을 클릭하여 추가 옵션을 설정합니다.  
  
### HPC 시작 속성  
  
|Property|설명|  
|--------------|--------|  
|**헤드 노드**|프로파일링 실행 시 HPC 헤드 노드로 사용할 컴퓨터를 지정합니다.|  
|**프로세스 수**|프로파일링되는 응용 프로그램에서 실행할 응용 프로그램 인스턴스 수를 지정합니다.|  
|**순위의 프로필**|클러스터의 특정 프로세스를 프로파일링하려면 **순위의 프로필** 옵션을 선택한 다음 드롭다운 목록에서 프로세스 순위를 선택합니다.|  
|**노드의 프로필**|HPC 클러스터의 특정 노드에서 실행되는 프로세스를 프로파일링하려면 **노드의 프로필** 옵션을 선택한 다음 드롭다운 목록에서 노드를 선택합니다.|  
|**원격 작업 디렉터리**|개별 계산 노드의 프로세스 인스턴스가 사용하는 폴더의 경로를 지정합니다.|  
|**배포 위치**|HPC 서버가 배포용 이미지를 스테이징하는 데 사용하는 디렉터리의 경로를 지정합니다.|  
  
### 고급 속성  
  
|Property|설명|  
|--------------|--------|  
|**프로젝트 이름**|현재 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 프로젝트 또는 솔루션의 이름입니다.|  
|**프로파일러가 중지되면 정리**|true이면 실행 디렉터리에 배포된 이진 파일이 제거됩니다.  사용자 프로그램에서 만든 파일 및 디렉터리는 이 단계에서 제거되지 않습니다.  실행 디렉터리와 배포 디렉터리가 IDE에 의해 만들어진 경우 IDE에서는 이 디렉터리를 제거하려고 하지만 디렉터리에 IDE에 의해 배포되지 않은 파일이 들어 있으면 디렉터리를 제거하지 못합니다.|  
|**추가로 배포할 파일**|계산 노드에 추가로 배포할 파일의 세미콜론으로 구분된 목록을 지정합니다.  줄임표 단추\(**...**\)를 클릭하여 대화 상자에서 여러 파일을 선택할 수 있습니다.|  
|**Mpiexec 명령**|MPI 응용 프로그램을 시작하는 응용 프로그램을 지정합니다.  기본값은 **mpiexec.exe**입니다.|  
|**Mpiexec 인수**|mpiexec.exe 명령에 전달할 인수를 지정합니다.|  
|**클러스터에서 요청된 노드**|응용 프로그램을 실행할 클러스터의 노드 수를 지정합니다.|  
|**CRT 파일 배포**|true이면 클러스터에 C\/C\+\+ 런타임이 배포됩니다.|  
|**프로파일링 전 스크립트**|프로파일링 세션이 시작되기 전에 로컬 개발 컴퓨터에서 실행할 스크립트의 경로 및 파일 이름을 지정합니다.|  
|**프로파일링 전 스크립트 인수**|프로파일링 전 스크립트에 전달할 인수를 지정합니다.|  
|**프로파일링 후 스크립트**|프로파일링 세션이 종료된 후에 로컬 개발 컴퓨터에서 실행할 스크립트의 경로 및 파일 이름을 지정합니다.|  
|**프로파일링 후 스크립트 인수**|프로파일링 후 스크립트에 전달할 인수를 지정합니다.|