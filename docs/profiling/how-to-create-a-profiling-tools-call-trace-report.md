---
title: "방법: 프로파일링 도구 호출 추적 보고서 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ETW[Visual Studio ALM], 데이터 보기"
  - "성능 도구, ETW 데이터 보기"
ms.assetid: 7640520a-7d3c-456c-b184-872a5d2f82f3
caps.latest.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 19
---
# 방법: 프로파일링 도구 호출 추적 보고서 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구의 *호출 추적 보고서*에는 응용 프로그램 함수의 각 진입 및 종료 지점과 해당 함수에서 실행되는 다른 함수에 대한 각 호출과 관련된 타이밍 정보가 나열됩니다.  호출 추적 보고서는 계측 방법으로 수집한 프로파일링 데이터에만 사용할 수 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 호출 추적 보고서를 표시할 수 없습니다.  **VSPerfReport** 명령줄 도구를 사용하여 쉼표로 구분된 값 파일\(.csv\)이나 Xml 파일을 생성해야 합니다.  이 도구에 대한 자세한 내용은 [VSPerfReport](../profiling/vsperfreport.md)를 참조하십시오.  
  
### 호출 추적 보고서를 만들려면  
  
1.  **명령 프롬프트** 창을 엽니다.  
  
2.  명령 프롬프트에 다음 명령을 입력합니다.  
  
     *ToolsPath* **VSPerfReport** *VSPFile* **\/CallTrace \[\/Xml\]**  
  
    |||  
    |-|-|  
    |*ToolsPath*|프로파일링 도구의 명령줄 도구 경로입니다.  자세한 내용은 [명령줄 도구의 경로 지정](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)을 참조하십시오.|  
    |*VSPFile*|프로파일링 데이터 파일\(.vsp 또는 .vsps\)입니다.  전체 및 부분 경로를 사용할 수 있습니다.|  
    |Xml|Xml 형식의 보고서를 생성합니다.|  
  
## 참고 항목  
 [방법: ETW\(Windows용 이벤트 추적\) 데이터 수집](../Topic/How%20to:%20Collect%20Event%20Tracing%20for%20Windows%20\(ETW\)%20Data.md)   
 [프로파일링 도구 API](../profiling/profiling-tools-apis.md)