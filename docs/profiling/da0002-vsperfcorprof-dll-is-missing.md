---
title: "DA0002: VSPerfCorProf.dll이 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.DA0002"
  - "vs.performance.2"
  - "vs.performance.rules.DAVsPerfCorProfMissing"
  - "vs.performance.rules.DA0002"
ms.assetid: 76e614b3-ad7e-4b92-b7be-88dc1329be1d
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# DA0002: VSPerfCorProf.dll이 없습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0002|  
|범주|프로파일링 도구 사용|  
|프로파일링 방법|VSPerfCmd 및 VSPerfASPNETCmd 명령줄 도구를 사용한 프로파일링|  
|메시지|VSPerfCLREnv.cmd를 사용하여 환경 변수를 제대로 설정하지 않고 파일을 수집한 것 같습니다.  관리되는 이진에 대한 기호가 확인되지 않을 수 있습니다.|  
|규칙 유형|정보|  
  
## 원인  
 프로파일러에서 프로파일링 실행 중 VSPerfCorProf.dll을 찾지 못했습니다.  이 경고는 프로파일러 데이터 수집용 명령줄 도구를 사용할 때 VSPerfCLREnv.cmd 도구를 사용하여 필요한 환경 변수를 초기화하지 않은 경우에 발생합니다.  프로파일링 도구를 시작할 때 다른 프로파일러가 실행 중인 경우에도 경고가 표시될 수 있습니다.  
  
## 규칙 설명  
 프로파일링 실행 전에 프로파일러에서 .NET Framework 이진 파일의 기호를 확인할 수 있도록 특정 환경 변수를 설정해야 합니다.  이 경고는 프로파일링 데이터가 수집되기 전에 VSPerfCLREnv.cmd 도구가 실행되지 않았음을 나타냅니다.  따라서 관리되는 이진 파일의 기호를 확인할 수 없습니다.  명령줄에서 프로파일링 도구 사용에 대한 자세한 내용은 [명령줄에서 프로파일링](../profiling/using-the-profiling-tools-from-the-command-line.md)을 참조하십시오.  
  
## 위반 문제를 해결하는 방법  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구에서 명령줄 도구를 사용하여 관리되는 응용 프로그램을 프로파일링하는 경우 데이터 수집을 시작하기 전에 [VSPerfCLREnv](../profiling/vsperfclrenv.md) 명령줄 도구를 실행합니다.