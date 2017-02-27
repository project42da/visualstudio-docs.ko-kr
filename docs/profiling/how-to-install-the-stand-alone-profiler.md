---
title: "방법: 독립 실행형 프로파일러 설치 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "성능 도구, 독립 실행형 프로파일러 설치"
  - "프로파일링 도구, 독립 실행형 프로파일러"
ms.assetid: cae81c95-83cd-4ab6-8a98-84ef977a2f6d
caps.latest.revision: 24
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 24
---
# 방법: 독립 실행형 프로파일러 설치
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE를 설치하지 않고 실행할 수 있는 명령줄 기반 독립 실행형 프로파일러를 제공합니다.  컴퓨터에 개발 환경이 설치되어 있지 않거나 설치할 수 없는 경우에 이런 상황이 발생합니다.  예를 들어 프로덕션 웹 서버에는 개발 환경을 설치하면 안 됩니다.  
  
> [!NOTE]
>  독립 실행형 프로파일러를 사용하여 ASP.NET 웹 사이트에 대한 성능 데이터를 수집하려면 [VSPerfCmd](../profiling/vsperfcmd.md)보다는 [VSPerfASPNetCmd](../profiling/vsperfaspnetcmd.md) 명령줄 도구를 사용하는 것이 좋습니다.  
  
### 독립 실행형 프로파일러를 설치하려면  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설치 미디어의 \\Standalone Profiler 경로가 포함된 디렉터리에서 독립 실행형 프로파일러 설치 관리자\(vs\_profiler.exe\)를 찾아 실행합니다.  
  
2.  vsintr.exe 및 msdis150.dll의 경로를 시스템 경로에 추가합니다.  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 기본 옵션으로 설치한 경우 vsinstr.exe 및 msdis150.dll은 \\Program Files\\Visual Studio 10\\Team Tools\\Performance Tools에 있습니다.  
  
3.  명령 프롬프트에 **VSInstr**을 입력합니다.  
  
    > [!NOTE]
    >  vsinstr.exe의 사용 정보가 표시되면 모든 것이 제대로 설정된 것입니다.  vsinstr.exe 또는 vsinstr.exe의 종속성 중 하나를 찾을 수 없다는 오류가 표시되면 경로가 2단계에 설명된 대로 설정되었는지 확인합니다.  
  
4.  **\_NT\_SYMBOL\_PATH** 변수를 **symsrv\*symsrv.dll\*c:\\localcache\*http:\/\/msdl.microsoft.com\/download\/symbols**로 선택하여 기호 서버를 설정합니다.  
  
5.  시스템 환경 변수를 사용하여 기호 서버를 설정한 다음 새 명령 프롬프트에서 명령줄 프로파일러 도구를 실행합니다.  이렇게 하면 새 환경 변수가 적용됩니다.  명령 프롬프트 창에서 다음 명령을 입력합니다.  
  
     **start %COMSPEC%**  
  
    > [!NOTE]
    >  기호 서버 패키지를 설정하는 방법에 대한 자세한 내용은 [방법: Windows 기호 정보 참조](../profiling/how-to-reference-windows-symbol-information.md)를 참조하십시오.  
  
6.  [VSPerfReport](../profiling/vsperfreport.md)를 사용하여 기호를 프로파일링 데이터 파일\(.vsp\)로 serialize합니다.  **VSPerfReport \/summary:all \/packsymbols** 스위치를 사용합니다.  데이터 파일에 기호가 삽입되어 있지 않은 경우 \_NT\_SYMBOL\_PATH 환경 변수를 설정했는지 확인합니다.  
  
## 참고 항목  
 [명령줄에서 프로파일링](../profiling/using-the-profiling-tools-from-the-command-line.md)   
 [연습: 샘플링을 사용하여 명령줄 프로파일링](../Topic/Walkthrough:%20Command-Line%20Profiling%20Using%20Sampling.md)   
 [연습: 계측을 사용하여 명령줄 프로파일링](../profiling/walkthrough-command-line-profiling-using-instrumentation.md)   
 [방법: Windows 기호 정보 참조](../profiling/how-to-reference-windows-symbol-information.md)   
 [VSPerfReport](../profiling/vsperfreport.md)