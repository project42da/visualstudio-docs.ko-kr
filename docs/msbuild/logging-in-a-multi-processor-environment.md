---
title: "다중 프로세서 환경에서의 로깅 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSBuild, 기록"
  - "MSBuild, 다중 프로세서 로깅"
ms.assetid: dd4dae65-ed04-4883-b48d-59bcb891c4dc
caps.latest.revision: 9
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 9
---
# 다중 프로세서 환경에서의 로깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

MSBuild에서는 다중 프로세서를 사용할 수 있기 때문에 프로젝트 빌드 시간을 크게 줄일 수 있는 반면 로깅은 복잡해집니다.  단일 프로세서 환경에서는 로거가 들어오는 이벤트, 메시지, 경고 및 오류를 예측 가능한 순차적인 방법으로 처리할 수 있습니다.  그러나 다중 프로세서 환경에서는 여러 소스의 이벤트가 동시에 또는 순서 없이 도착할 수 있습니다.  MSBuild에서는 새 다중 프로세서 인식 로거가 제공되며, 사용자 지정 "전달 로거"를 만들 수 있습니다.  
  
## 다중 프로세서 빌드 로깅  
 다중 프로세서 또는 다중 핵심 프로세서에서 하나 이상의 프로젝트를 빌드하면 모든 프로젝트에 대한 MSBuild 빌드 이벤트가 동시에 생성됩니다.  따라서 많은 이벤트 데이터가 로거에 동시에 또는 순서 없이 도착할 수 있습니다.  이는 로거를 과부하시키고 빌드 시간을 증가시키며, 잘못된 로거 출력 혹은 빌드의 손상을 일으킬 수 있습니다.  이러한 문제를 해결하기 위해 MSBuild 로거를 사용하면 순서 없는 이벤트를 처리하고 이벤트와 해당 소스를 서로 연결할 수 있습니다.  
  
 사용자 지정 전달 로거를 만들면 로깅 효율성을 훨씬 더 향상시킬 수 있습니다.  사용자 지정 전달 로거는 빌드하기 전에 모니터링할 이벤트를 선택할 수 있는 필터 역할을 합니다.  사용자 지정 전달 로거를 사용하면 원하지 않는 이벤트에 의해 로거에 과부하가 걸리거나 로그가 복잡해지거나 빌드 시간이 느려지지 않습니다.  
  
### 중앙 로깅 모델  
 MSBuild에서는 다중 프로세서 빌드를 위해 "중앙 로깅 모델"을 사용합니다. 중앙 로깅 모델에서 MSBuild.exe의 인스턴스는 기본 빌드 프로세스 또는 "중앙 노드" 역할을 합니다. MSBuild.exe의 보조 인스턴스 또는 "보조 노드"는 중앙 노드에 연결됩니다.  중앙 노드에 연결된 모든 ILogger 기반 로거는 "중앙 로거"라고 하고 보조 노드에 연결된 로거는 "보조 로거"라고 합니다.  
  
 빌드가 발생하면 보조 로거는 해당 이벤트 트래픽을 중앙 로거에 라우트합니다.  이벤트가 여러 개의 보조 노드에서 발생하기 때문에 데이터는 중앙 노드에 동시에 인터리브된 상태로 도착합니다.  이벤트\-프로젝트 및 이벤트\-대상 참조를 확인하기 위해 이벤트 인수에는 추가 빌드 이벤트 컨텍스트 정보가 포함되어 있습니다.  
  
 중앙 로거에서 <xref:Microsoft.Build.Framework.ILogger>만 구현하면 되지만 빌드에 참여하는 노드 수만큼 중앙 로거를 초기화하려면 <xref:Microsoft.Build.Framework.INodeLogger>도 구현하는 것이 좋습니다.  <xref:Microsoft.Build.Framework.ILogger.Initialize%2A> 메서드의 다음 오버로드는 엔진에 의해 로거가 초기화될 때 호출됩니다.  
  
```  
public interface INodeLogger: ILogger  
{  
    public void Initialize(IEventSource eventSource, int nodeCount);  
}  
```  
  
### 분산 로깅 모델  
 중앙 로깅 모델에서 한 번에 많은 프로젝트를 빌드할 때처럼 들어오는 메시지 트래픽이 너무 많으면 중앙 로거에 과부하가 걸릴 수 있습니다. 그러면 시스템에 과부하가 걸리고 빌드 성능이 저하됩니다.  
  
 이 문제를 줄이기 위해 MSBuild에서 전달 로거를 만들 수 있도록 하여 중앙 로깅 모델을 확장하는 "분산 로깅 모델"을 사용할 수도 있습니다.  전달 로거는 보조 노드에 연결되고 노드에서 들어오는 빌드 이벤트를 받습니다.  전달 로거는 이벤트를 필터링하여 중앙 노드에 원하는 이벤트만 전달할 수 있다는 점을 제외하고 일반 로거와 같습니다.  전달 로거를 사용하면 중앙 노드의 메시지 트래픽을 줄이고 성능을 향상시킬 수 있습니다.  
  
 <xref:Microsoft.Build.Framework.ILogger>에서 파생된 <xref:Microsoft.Build.Framework.IForwardingLogger> 인터페이스를 구현하여 전달 로거를 만들 수 있습니다.  이 인터페이스는 다음과 같이 정의됩니다.  
  
```  
public interface IForwardingLogger: INodeLogger  
{  
    public IEventRedirector EventRedirector { get; set; }  
    public int NodeId { get; set; }  
}  
```  
  
 전달 로거에 이벤트를 전달하려면 <xref:Microsoft.Build.Framework.IEventRedirector> 인터페이스의 <xref:Microsoft.Build.Framework.IEventRedirector.ForwardEvent%2A> 메서드를 호출합니다.  적절한 <xref:Microsoft.Build.Framework.BuildEventArgs> 또는 파생 개체를 매개 변수로 전달합니다.  
  
 자세한 내용은 [전달 로거 만들기](../msbuild/creating-forwarding-loggers.md)을 참조하십시오.  
  
### 분산 로거 연결  
 명령줄 빌드에서 분산 로거를 연결하려면 `/distributedlogger`\(또는 줄여서 `/dl`\) 스위치를 사용합니다.  로거 형식 및 클래스의 이름을 지정하는 형식은 분산 로거가 두 개의 로깅 클래스, 전달 로거와 중앙 로거로 구성된다는 점을 제외하고 `/logger` 스위치와 같습니다.  다음 예제에서는 분산 로거를 연결하는 방법을 보여 줍니다.  
  
```  
msbuild.exe *.proj /distributedlogger:XMLCentralLogger,MyLogger,Version=1.0.2,  
Culture=neutral*XMLForwardingLogger,MyLogger,Version=1.0.2,  
Culture=neutral  
```  
  
 별표\(\*\)는 `/dl` 스위치에 있는 두 개의 로거 이름을 구분합니다.  
  
## 참고 항목  
 [빌드 로거](../msbuild/build-loggers.md)   
 [전달 로거 만들기](../msbuild/creating-forwarding-loggers.md)