---
title: "다중 프로세서 환경에서 로깅 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, multi-processor logging
- MSBuild, logging
ms.assetid: dd4dae65-ed04-4883-b48d-59bcb891c4dc
caps.latest.revision: 9
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: e78d6c35fa294d2f1a39c91af5e278e9e4519d2d
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="logging-in-a-multi-processor-environment"></a>다중 프로세서 환경에서의 로깅
MSBuild에서는 다중 프로세서를 사용할 수 있기 때문에 프로젝트 빌드 시간을 크게 줄일 수 있는 반면 로깅은 복잡해집니다. 단일 프로세서 환경에서로 거가 들어오는 이벤트, 메시지, 경고 및 오류 예측 가능 하 고 순차 방식으로 처리할 수 있습니다. 그러나 다중 프로세서 환경에서는 여러 소스에서 이벤트 동시에 또는 순서 없이 도착할 수 있습니다. MSBuild는에서는 새 다중 프로세서 인식 로거가 제공 및 사용자 지정 "전달로 거."를 만들 수  
  
## <a name="logging-multiple-processor-builds"></a>다중 프로세서 로깅 빌드  
 다중 프로세서 또는 다중 핵심 프로세서에서 하나 이상의 프로젝트를 빌드하면 모든 프로젝트에 대한 MSBuild 빌드 이벤트가 동시에 생성됩니다. 동시에 또는 순서 없이 많은 이벤트 데이터가 거에 도착할 수 있습니다. 이 거에 과부하가 하 고 빌드 시간이 늘어나거나, 잘못 된로 거 출력이 또는 심지어 빌드가 손상된 될 수 있습니다. 이러한 문제를 해결 하기 위해 MSBuild로 거 수 아웃 순서 없는 이벤트를 처리 하 고 상관 관계 이벤트와 해당 소스를 지정 합니다.  
  
 더 많은 사용자 지정 전달으로 거를 만들어 로깅 효율성을 향상 시킬 수 있습니다. 사용자 지정 전달으로 거 필터 역할을 했는지를 빌드하기 전에 모니터링 하려는 이벤트 선택 합니다. 사용자 지정 전달으로 거를 사용 하면 원하지 않는 이벤트 하지로 거에 과부하가, 로그가 복잡해 않거나 느리게 빌드 시간입니다.  
  
### <a name="central-logging-model"></a>중앙 로깅 모델  
 다중 프로세서 빌드에 대 한 MSBuild 사용 하 여 "중앙 로깅 모델"입니다. 중앙 로깅 모델 MSBuild.exe의 인스턴스 역할을 하는 기본 빌드 프로세스 또는 "중앙 노드입니다." MSBuild.exe, 또는 "보조 노드,"의 보조 인스턴스의 중앙 노드에 연결 됩니다. 중앙 노드에 연결 된 모든 ILogger 기반는 거 "중앙로 거" 라고 하며 보조 노드에 연결 된로 거 "보조 로거입니다." 라고 합니다.  
  
 빌드가 발생 하면 보조로 거 중앙로 거 이벤트 트래픽을 라우팅합니다. 여러 개의 보조 노드에서 이벤트 들어오므로 데이터는 중앙 노드에서 동시에 도착 하지만 인터리브. 프로젝트에 이벤트 및 이벤트 대상에 대 한 참조를 해결 하려면 이벤트의 인수 추가 빌드 이벤트 컨텍스트 정보를 포함 합니다.  
  
 유일한 있지만 <xref:Microsoft.Build.Framework.ILogger> 는 또한 구현 하는 것을 권장 중앙로 거에 의해 구현 되어야 하는 데 필요한, <xref:Microsoft.Build.Framework.INodeLogger> 중앙로 거는 빌드에 참여 하는 노드 수를 초기화 하려는 경우. 다음의 오버 로드는 <xref:Microsoft.Build.Framework.ILogger.Initialize%2A> 엔진 로거가 초기화 될 때 메서드가 호출 됩니다.  
  
```csharp
public interface INodeLogger: ILogger  
{  
    public void Initialize(IEventSource eventSource, int nodeCount);  
}  
```  
  
### <a name="distributed-logging-model"></a>분산 로깅 모델  
 중앙 로깅 모델에서 여러 프로젝트 빌드를 때 한 번에 같은 너무 많은 들어오는 메시지 트래픽에 시스템을 강조 하 고 빌드 성능을 낮출 수 하는 중앙 노드에 가득 찰 수 있습니다.  
  
 이 문제를 줄이기 위해 MSBuild에 전달으로 거를 만들 수 있도록 하 여 중앙 로깅 모델을 확장 하는 "분산된 로깅 모델을"을 수 있습니다. 전달으로 거 보조 노드에 연결 된 하 고 해당 노드에서 들어오는 빌드 이벤트를 받습니다. 전달으로 거는 일반로 거와 동일 하 게 이벤트를 필터링 하 고 다음 중앙 노드에 원하는 이벤트만 전달할 수 있습니다. 이 중앙 노드에서 메시지 트래픽이 감소 하 고 따라서 더 나은 성능을 활성화 합니다.  
  
 전달으로 거를 구현 하 여 만들 수 있습니다는 <xref:Microsoft.Build.Framework.IForwardingLogger> 인터페이스에서 파생 된 <xref:Microsoft.Build.Framework.ILogger>합니다. 인터페이스는 다음과 같이 정의 됩니다.  
  
```csharp
public interface IForwardingLogger: INodeLogger  
{  
    public IEventRedirector EventRedirector { get; set; }  
    public int NodeId { get; set; }  
}  
```  
  
 전달으로 거에 대 한 이벤트를 전달 하려면 호출는 <xref:Microsoft.Build.Framework.IEventRedirector.ForwardEvent%2A> 의 메서드는 <xref:Microsoft.Build.Framework.IEventRedirector> 인터페이스입니다. 적절 한 전달 <xref:Microsoft.Build.Framework.BuildEventArgs>, 또는 매개 변수로 파생 개체입니다.  
  
 자세한 내용은 참조 [전달로 거 만들기](../msbuild/creating-forwarding-loggers.md)합니다.  
  
### <a name="attaching-a-distributed-logger"></a>분산된 된로 거를 연결합니다.  
 명령줄 빌드에 분산된 된로 거를 연결 하려면 사용 된 `/distributedlogger` (또는 `/dl` 줄여서) 전환 합니다. 에 대 한 것과 동일로 거 형식 및 클래스의 이름을 지정 하는 형식은 않습니다는 `/logger` 제외 하 고 두 개의 로깅 클래스로 이루어진 분산된로 거 스위치: 전달으로 거 및 중앙로 거 합니다. 다음은 분산된로 거 연결의 예입니다.  
  
```  
msbuild.exe *.proj /distributedlogger:XMLCentralLogger,MyLogger,Version=1.0.2,  
Culture=neutral*XMLForwardingLogger,MyLogger,Version=1.0.2,  
Culture=neutral  
```  
  
 에 두 명의 거 이름을 구분 하는 별표 (*)는 `/dl` 전환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [빌드 로거](../msbuild/build-loggers.md)   
 [전달 로거 만들기](../msbuild/creating-forwarding-loggers.md)
