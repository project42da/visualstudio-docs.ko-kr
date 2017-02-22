---
title: "연습: 계측을 사용하여 명령줄 프로파일링 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로파일링 도구, 연습"
  - "성능 도구, 연습"
  - "성능 도구, 명령줄 도구"
ms.assetid: 1c6f1586-3d6a-431f-bedf-c54088e280ba
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 연습: 계측을 사용하여 명령줄 프로파일링
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 연습에서는 프로파일링 도구의 계측 방법으로 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 독립 실행형 응용 프로그램을 프로파일링하여 자세한 타이밍 및 호출 수 데이터를 수집하는 과정을 보여 줍니다.  이 연습에서는 다음 작업을 수행합니다.  
  
-   [VSInstr](../profiling/vsinstr.md) 명령줄 도구를 사용하여 계측된 이진 파일을 생성합니다.  
  
-   [VSPerfCLREnv](../profiling/vsperfclrenv.md) 도구를 사용하여 .NET 프로파일링 데이터를 수집하기 위한 환경 변수를 설정합니다.  
  
-   [VSPerfCmd](../profiling/vsperfcmd.md) 도구를 사용하여 프로파일링 데이터를 수집합니다.  
  
-   [VSPerfReport](../profiling/vsperfreport.md) 도구를 사용하여 프로파일링 데이터의 파일 기반 보고서를 생성합니다.  
  
## 사전 요구 사항  
  
-   [!INCLUDE[vsprvsts](../code-quality/includes/vsprvsts_md.md)]  
  
-   C\#에 대한 약간의 이해  
  
-   명령줄 도구를 사용하는 작업 방법에 대한 약간의 이해  
  
-   [PeopleTrax 샘플](../profiling/peopletrax-sample-profiling-tools.md) 복사본  
  
-   프로파일링으로 제공된 정보를 사용하여 작업할 때는 디버깅 기호 정보도 필요합니다.  자세한 내용은 [방법: Windows 기호 정보 참조](../profiling/how-to-reference-windows-symbol-information.md)을 참조하십시오.  
  
## 계측 방법을 사용한 명령줄 프로파일링  
 계측은 함수 시작 및 종료 시 계측된 모듈의 함수에 타이밍 정보를 수집하는 프로브 함수를 특별히 빌드된 버전의 프로파일링된 이진 파일에 포함시키는 프로파일링 방법입니다.  이 프로파일링 방법은 샘플링에 비해 간섭이 심하므로 오버헤드가 많이 발생합니다.  또한 계측된 이진 파일은 디버그 또는 릴리스 이진 파일보다 크며 개발용이 아닙니다.  
  
> [!NOTE]
>  계측된 이진 파일을 고객에게 보내지 마십시오.  계측된 이진 파일에는 여러 가지 위험한 요소가 포함될 수 있습니다.  이 이진 파일에 포함된 정보는 응용 프로그램을 더 쉽게 리버스 엔지니어링하거나 보안에 위협을 가하는 데 악용될 수 있습니다.  
  
#### 계측 방법을 사용하여 PeopleTrax 응용 프로그램을 프로파일링하려면  
  
1.  PeopleTrax 샘플 응용 프로그램을 설치하고 릴리스 버전을 빌드합니다.  
  
2.  명령 프롬프트 창을 열고 로컬 경로 환경 변수에 **프로파일링 도구** 디렉터리를 추가합니다.  
  
3.  작업 디렉터리를 PeopleTrax 이진 파일이 들어 있는 디렉터리로 변경합니다.  
  
4.  파일 기반 보고서를 포함할 디렉터리를 만듭니다.  다음 명령을 입력합니다.  
  
    ```  
    md Reports  
    ```  
  
5.  VSInstr 명령줄 도구를 사용하여 응용 프로그램의 이진 파일을 계측합니다.  다음 명령을 개별 명령 줄에 입력합니다.  
  
    ```  
    VSInstr PeopleTrax.exe  
    VSInstr PeopleTrax.exe  
    VSInstr People.dll  
    VSInstr Person.dll  
    VSInstr Operation.dll  
    ```  
  
     **참고** 기본적으로 VSInstr에서는 원본 파일의 계측되지 않은 백업을 저장합니다.  이 백업 파일 이름의 확장명은 .orig입니다.  예를 들어 "MyApp.exe"의 원본 버전은 "MyApp.exe.orig"로 저장됩니다.  
  
6.  다음 명령을 입력하여 적절한 환경 변수를 설정합니다.  
  
    ```  
    VsPerfCLREnv /traceon  
    ```  
  
7.  프로파일러를 시작하려면 다음 명령을 입력합니다.  
  
    ```  
    VsPerfCmd /start:trace /output:Reports\Report.vsp  
    ```  
  
8.  추적 모드로 프로파일러를 시작한 다음 계측된 버전의 PeopleTrax.exe 프로세스를 실행하여 데이터를 수집합니다.  
  
     **PeopleTrax** 응용 프로그램 창이 나타납니다.  
  
9. **Get People**을 클릭합니다.  
  
     PeopleTrax 데이터 표에 데이터가 채워집니다.  
  
10. **데이터 내보내기**를 클릭합니다.  
  
     메모장이 열리고 **PeopleTrax** 응용 프로그램의 인물 목록이 포함된 새 파일이 메모장에 표시됩니다.  
  
11. 메모장을 닫고 **PeopleTrax** 응용 프로그램을 닫습니다.  
  
12. 프로파일러를 종료합니다.  다음 명령을 입력합니다.  
  
    ```  
    VSPerfCmd /shutdown  
    ```  
  
13. 다음 명령을 입력하여 환경 변수를 다시 설정합니다.  
  
    ```  
    VSPerfCLREnv /off  
    ```  
  
14. VSPerfReport 도구를 사용하여 쉼표로 구분된 값\(.csv\) 보고서 파일을 생성합니다.  다음을 입력합니다.  
  
    ```  
    VSPerfReport Reports\Report.vsp /output:Reports /summary:all  
    ```  
  
     생성된 보고서를 스프레드시트 프로그램에서 분석하거나 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE를 사용하여 Report.vsp 파일의 프로파일링 데이터를 분석할 수 있습니다.  자세한 내용은 [프로파일링 도구 데이터 분석](../profiling/analyzing-performance-tools-data.md)을 참조하십시오.  
  
## 참고 항목  
 [성능 세션 개요](../profiling/performance-session-overview.md)   
 [명령줄에서 프로파일링](../profiling/using-the-profiling-tools-from-the-command-line.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [샘플링 데이터 값 이해](../profiling/understanding-sampling-data-values.md)   
 [프로파일링 도구 보고서 뷰](../profiling/performance-report-views.md)