---
title: "MSBuild를 사용하여 빌드 로그 가져오기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSBuild, 로깅"
  - "로깅[MSBuild]"
ms.assetid: 6ba9a754-9cc0-4fed-9fc8-4dcd3926a031
caps.latest.revision: 27
caps.handback.revision: 27
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# MSBuild를 사용하여 빌드 로그 가져오기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Msbuild에서 스위치를 사용 하 여 검토 및 빌드 데이터를 하나 이상의 파일을 저장 하려면 원하는 빌드 데이터의 양을 지정할 수 있습니다.  빌드 데이터를 수집 하 여 사용자 지정로 거를 지정할 수도 있습니다.  이 항목에서는 다루지 않습니다 MSBuild 명령줄 스위치에 대 한 내용은 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md).  
  
> [!NOTE]
>  Visual Studio IDE를 사용 하 여 프로젝트를 빌드하는 경우 빌드 로그를 검토 하 여 해당 빌드를 해결할 수 있습니다.  자세한 내용은 [방법: 빌드 로그 파일 보기, 저장 및 구성](../ide/how-to-view-save-and-configure-build-log-files.md)을 참조하십시오.  
  
## 세부 수준을 설정합니다.  
 Msbuild를 사용 하 여 세부 수준을 지정 하지 않고 프로젝트를 빌드할 때 출력 로그에 다음과 같은 정보를 나타납니다.  
  
-   오류, 경고 및 매우 중요 한으로 분류 된 메시지입니다.  
  
-   일부 상태 이벤트입니다.  
  
-   빌드 요약 합니다.  
  
 사용 하는 **\/verbosity** \(**\/v**\) 전환, 데이터 양을 출력 로그에 표시를 제어할 수 있습니다.  정도의 문제 해결에 대 한 사용 `detailed` \(`d`\) 또는 `diagnostic` \(`diag`\), 가장 많은 정보를 제공 합니다.  
  
 로 설정 하면 빌드 프로세스 속도가 느려질 수 있습니다는 **\/verbosity** 에 `detailed` 및 설정할 때에 느린는 **\/verbosity** 에 `diagnostic`.  
  
```  
msbuild MyProject.proj /t:go /v:diag  
```  
  
## 빌드 로그 파일에 저장  
 사용할 수 있는 **\/fileLogger** \(**fl**\) 빌드 데이터를 파일에 저장 하는 스위치.  다음은 빌드 데이터 라는 파일에 저장 하는 `msbuild.log`.  
  
```  
msbuild MyProject.proj /t:go /fileLogger  
```  
  
 다음 예제에서는 로그 파일 이름이 `MyProjectOutput.log`, 및 로그 출력의 자세한 정도 설정 `diagnostic`.  사용 하 여 이러한 두 설정이 지정 된 **\/filelogparameters** \(`flp`\) 전환.  
  
```  
msbuild MyProject.proj /t:go /fl /flp:logfile=MyProjectOutput.log;verbosity=diagnostic  
```  
  
 자세한 내용은 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)을 참조하십시오.  
  
## 여러 파일에 로그 출력을 저장합니다.  
 다음 예제에서는 전체 로그에 저장 `msbuild1.log`, 방금 오류를 `JustErrors.log`, 및 경고에 방금 `JustWarnings.log`.  이 예제에서는 세 가지 파일 각각에 대해 파일 번호를 사용합니다.  직후 파일 번호 지정은 **\/fl** 및 **\/flp** 스위치 \(예를 들어, `/fl1` 및 `/flp1`\).  
  
 **\/filelogparameters** \(`flp`\) 스위치 2\-3 파일을 각 파일 이름 및 각 파일에 포함할 항목을 지정 합니다.  따라서 1 파일에 대 한 지정 된 이름이 없습니다의 기본 이름은 `msbuild1.log` 사용 됩니다.  
  
```  
msbuild MyProject.proj /t:go /fl1 /fl2 /fl3 /flp2:logfile=JustErrors.log;errorsonly /flp3:logfile=JustWarnings.log;warningsonly  
  
```  
  
 자세한 내용은 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)을 참조하십시오.  
  
## 사용자 지정로 거를 사용 하 여  
 <xref:Microsoft.Build.Framework.ILogger> 인터페이스를 구현하는 관리되는 형식을 작성하여 자신만의 로거를 작성할 수 있습니다.  예를 들어, 빌드 오류에서 전자 메일 보내기, 해당 데이터베이스에 로그온 또는 해당 XML 파일에 기록 하려면 사용자 지정로 거를 사용할 수 있습니다.  자세한 내용은 [빌드 로거](../msbuild/build-loggers.md)을 참조하십시오.  
  
 명령줄에 MSBuild 사용자 지정로 거를 사용 하 여 지정 된 **\/logger** 전환 합니다.  사용할 수도 있습니다는 **\/noconsolelogger** 스위치를 기본 콘솔으로 거를 사용 하지 않도록 설정 합니다.  
  
## 참고 항목  
 <xref:Microsoft.Build.Framework.LoggerVerbosity>   
 [빌드 로거](../msbuild/build-loggers.md)   
 [다중 프로세서 환경에서의 로깅](../msbuild/logging-in-a-multi-processor-environment.md)   
 [전달 로거 만들기](../msbuild/creating-forwarding-loggers.md)   
 [MSBuild 개념](../msbuild/msbuild-concepts.md)