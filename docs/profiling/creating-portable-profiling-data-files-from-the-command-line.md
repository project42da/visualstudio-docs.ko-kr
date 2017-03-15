---
title: "명령줄에서 이식 가능한 프로파일링 데이터 파일 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2ceb63a7-b835-4988-b756-2afc3fcc4808
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# 명령줄에서 이식 가능한 프로파일링 데이터 파일 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

프로파일링 데이터를 보다 쉽게 공유하려면 [VSPerfReport](../profiling/vsperfreport.md) 명령줄 도구를 사용하여 .vsp 파일에 프로파일링 실행에 대한 기호를 포함합니다.  
  
 크기가 작고 IDE에 빠르게 로드할 수 있는 미리 분석된 프로파일링 데이터 파일\(.vsps\)을 만들 수도 있습니다.  
  
> [!NOTE]
>  **VSPerfReport**에 기호 파일\(.pdb\)을 사용할 수 있는지 확인하십시오.  자세한 내용은 [방법: 명령줄에서 기호 파일 위치 지정](../profiling/how-to-specify-symbol-file-locations-from-the-command-line.md)을 참조하십시오.  
>   
>  **VSReport**의 경로에 대한 자세한 내용은 [명령줄 도구의 경로 지정](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)을 참조하십시오.  
>   
>  .vsps 파일의 프로파일링 데이터는 필터링할 수 없습니다.  
  
### 프로파일링 데이터 파일\(.vsp\)에 프로파일링 실행에 대한 기호를 포함하려면  
  
-   명령 프롬프트 창에서 다음 명령을 입력합니다.  
  
     \<Path\>**VSPerfReport \<**VSP File\> **\/PackSymbols**  
  
     기본적으로 .vsps 파일의 이름은 .vsp 파일의 기본 이름으로 지정됩니다.  **Output** 옵션을 사용하여 다른 이름을 지정할 수 있습니다.  
  
### 요약 프로파일링 데이터 파일을 만들려면  
  
-   명령 프롬프트 창에서 다음 명령을 입력합니다.  
  
     \<Path\>**VSPerfReport \<**VSP File\> **\/SummaryFile** \[**\/Output:**\<File Name\>\]  
  
     기본적으로 .vsps 파일의 이름은 .vsp 파일의 기본 이름으로 지정됩니다.  **Output** 옵션을 사용하여 다른 이름을 지정할 수 있습니다.