---
title: "전달 로거 만들기 | Microsoft Docs"
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
  - "MSBuild, 전달 로거"
  - "MSBuild, 기록"
ms.assetid: 3aebf9c8-b62c-4cb2-b2d6-8cdfcd369a24
caps.latest.revision: 9
caps.handback.revision: 9
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 전달 로거 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

전달 로거를 사용하면 다중 프로세서 시스템에서 프로젝트를 빌드할 때 모니터링할 이벤트를 선택할 수 있으므로 로깅 효율성이 향상됩니다.  전달 로거를 사용하면 원하지 않는 이벤트로 인해 중앙 로거에 과부하가 걸리거나 빌드 시간이 느려지거나 로그가 복잡해지지 않도록 할 수 있습니다.  
  
 전달 로거를 만들려면 <xref:Microsoft.Build.Framework.IForwardingLogger> 인터페이스를 구현한 다음 이 인터페이스의 메서드를 수동으로 구현하거나 <xref:Microsoft.Build.BuildEngine.ConfigurableForwardingLogger> 클래스 및 이 클래스의 미리 구성된 메서드를 사용하면 됩니다.  대부분의 응용 프로그램에서는 두 번째 방법만 사용해도 됩니다.  
  
## 이벤트 등록 및 이벤트에 응답  
 전달 로거는 다중 프로세서 시스템에서 빌드가 수행되는 동안 주 빌드 프로세스에 의해 만들어지는 작업자 프로세스인 보조 빌드 엔진이 빌드 이벤트를 보고할 때 이러한 이벤트에 대한 정보를 수집한 다음  사용자가 지정한 명령을 기반으로 중앙 로거에 전달할 이벤트를 선택합니다.  
  
 모니터링할 이벤트를 처리할 전달 로거를 등록해야 합니다.  이벤트를 등록하려면 로거가 <xref:Microsoft.Build.Utilities.Logger.Initialize%2A> 메서드를 재정의해야 됩니다.  그러면 시스템에 있는 프로세서 수로 설정할 수 있는 선택적 매개 변수인 `nodecount`가 이 메서드에 포함됩니다.  기본적으로 이 값은 1입니다.  
  
 모니터링할 수 있는 이벤트의 예로는 <xref:Microsoft.Build.Framework.IEventSource.TargetStarted>, <xref:Microsoft.Build.Framework.IEventSource.ProjectStarted> 및 <xref:Microsoft.Build.Framework.IEventSource.ProjectFinished>가 있습니다.  
  
 다중 프로세서 환경에서는 이벤트 메시지가 순서대로 수신되지 않을 수 있습니다.  따라서 전달 로거의 이벤트 처리기를 사용하여 이벤트를 처리하고 중앙 로거에 전달하기 위해 리디렉터에 전달할 이벤트를 결정하도록 전달 로거를 프로그래밍해야 합니다.  이렇게 하려면 모든 메시지에 첨부되는 <xref:Microsoft.Build.Framework.BuildEventContext> 클래스를 사용하여 전달할 이벤트를 식별한 다음 이러한 이벤트의 이름을 <xref:Microsoft.Build.BuildEngine.ConfigurableForwardingLogger> 클래스\(또는 이 클래스의 서브클래스\)에 전달하면 됩니다.  이 메서드를 사용할 때는 이벤트를 전달하는 데 다른 특정 코딩이 필요하지 않습니다.  
  
## 전달 로거 지정  
 전달 로거가 어셈블리로 컴파일되면 빌드하는 동안 이 로거를 사용하도록 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에 지시해야 합니다.  이렇게 하려면 MSBuild.exe와 함께 `/FileLogger`, `/FileLoggerParameters` 및 `/DistributedFileLogger` 스위치를 사용합니다.  `/FileLogger` 스위치는 로거가 직접 연결되어 있음을 MSBuild.exe에 알립니다. `/DistributedFileLogger` 스위치는 노드마다 로그 파일이 하나씩 있음을 의미합니다.  전달 로거의 매개 변수를 설정하려면 `/FileLoggerParameters` 스위치를 사용합니다.  이러한 MSBuild.exe 스위치와 기타 MSBuild.exe 스위치에 대한 자세한 내용은 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)를 참조하십시오.  
  
## 다중 프로세서 인식 로거  
 다중 프로세서 시스템에서 빌드하는 경우 각 프로세서의 빌드 메시지가 자동으로 통합 시퀀스로 인터리브되지 않습니다.  대신 모든 메시지에 첨부되는 <xref:Microsoft.Build.Framework.BuildEventContext> 클래스를 사용하여 메시지 그룹화 우선 순위를 설정해야 합니다.  다중 프로세서 빌드에 대한 자세한 내용은 [다중 프로세서 환경에서의 로깅](../msbuild/logging-in-a-multi-processor-environment.md)을 참조하십시오.  
  
## 참고 항목  
 [빌드 로그 가져오기](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [빌드 로거](../msbuild/build-loggers.md)   
 [다중 프로세서 환경에서의 로깅](../msbuild/logging-in-a-multi-processor-environment.md)