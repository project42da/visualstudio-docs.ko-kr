---
title: "EventSource 이벤트를 표식으로 시각화 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3a10022a-5c37-48b1-a833-dd35902176b6
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# EventSource 이벤트를 표식으로 시각화
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

동시성 시각화 도우미 EventSource 이벤트 표식으로 표시 하 고 표식 표시 되는 방법을 제어할 수 있습니다.  EventSource 표시자를 보려면 ETW 공급자 GUID를 사용하여 등록 된 [고급 설정](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) 대화 상자를 사용합니다.  동시성 시각화 도우미는 기본 규칙과 EventSource 이벤트를 나타내기 위해 [플래그 표식](../profiling/flag-markers.md), [범위 표식](../profiling/span-markers.md), 및 [메시지 표식](../profiling/message-markers.md)를 갖습니다.  EventSource 이벤트는 이벤트에 사용자 지정 필드를 추가 하 여 표시 되는 방식을 사용자 지정할 수 있습니다.  마커에 대한 자세한 내용은 [동시성 시각화 도우미 표식](../profiling/concurrency-visualizer-markers.md)를 참조하십시오.  응용 프로그램 이벤트 소스에 대한 자세한 내용은 <xref:System.Diagnostics.Tracing>를 참조하십시오.  
  
## EventSource 이벤트의 기본 시각화  
 기본적으로 동시성 시각화 도우미 EventSource 이벤트를 나타내기 위해 다음과 같은 규칙을 사용 합니다.  
  
### 표식 종류  
  
1.  이벤트는  [Opcode](http://msdn.microsoft.com/ko-kr/d97953df-669b-4c55-b1a8-925022b339b7) win: 시작 또는 win: 중단 각각 시작과 끝에 걸쳐 중으로 처리 됩니다.  중첩 또는 겹치는 범위를 표시할 수 없습니다.  한 스레드에서 시작 하 고 끝내 다른 이벤트 쌍을 표시할 수 없습니다.  
  
2.  않으면 win: 시작도 아니고 win: 중단 된 Opcode는 이벤트가 플래그 표시자로 처리 됩니다의  [레벨](http://msdn.microsoft.com/ko-kr/dfa4e0a9-4d89-4f50-aef9-1dae0dc11726) \(EVENT\_RECORD 필드입니다.EVENT\_HEADER입니다.EVENT\_DESCRIPTOR\)은 승: 자세한 또는 더 높은 것을 갖습니다.  
  
3.  다른 모든 경우에 이벤트 메시지로 처리 됩니다.  
  
### 중요  
 다음 표에서 이벤트 수준을 마커 중요성에 매핑되는 방식을 정의 합니다.  
  
|ETW 수준|동시성 시각화 도우미의 중요성|  
|------------|----------------------|  
|승: LogAlways|Normal|  
|승리: 중요|Critical|  
|승리: 오류|Critical|  
|승리: 경고|High|  
|win:0x4 \- Informational|Normal|  
|승리: 세부 정보 표시|Low|  
|승리 보다: 자세한 정보 표시|Low|  
  
### 계열 이름.  
 이벤트 작업 이름은 계열 이름에 사용됩니다.  작업이 이벤트에 대해 정의 된 경우 계열 이름이 비어 있습니다.  
  
### 범주  
 수준을 승리가: 중요 한 승리: 오류 다음 범주는 경고 \(\-1\)를 나타냅니다.  그렇지 않으면 범주는 기본 \(0\)입니다.  
  
### Text  
 Printf 형식 서식 있는 텍스트 메시지 이벤트에 대해 정의 설명 표식으로 표시 됩니다.  그렇지 않으면 설명은 이벤트의 이름 및 각 페이로드 필드의 값입니다.  
  
## EventSource 이벤트의 시각화를 사용자 지정합니다.  
 EventSource 이벤트 표시 방법을 이벤트에 적절 한 필드를 추가 하 여 다음 섹션에 설명 된 대로 사용자 지정할 수 있습니다.  
  
### 표식 종류  
 사용 하는  `cvType`  이벤트를 나타내는 데 사용 되는 표식 유형을 제어 하는 바이트 필드입니다.  cvType 에서 사용할 수 있는 값은 다음과 같습니다.  
  
|cvType 값|결과 표시 형식|  
|--------------|--------------|  
|0|메시지|  
|1|Span Start|  
|2|범위 끝|  
|3|플래그|  
|다른 모든 값|메시지|  
  
### 중요  
 사용할 수 있는 `cvImportance` EventSource 이벤트에 대 한 중요도 설정을 제어 하는 바이트 필드입니다.  그러나 이벤트 표시 된 중요도 수준을 사용 하 여 제어 하는 것이 좋습니다.  
  
|cvImportance 값|동시성 시각화 도우미의 중요성|  
|--------------------|----------------------|  
|0|Normal|  
|1|Critical|  
|2|High|  
|3|High|  
|4|Normal|  
|5|Low|  
|다른 모든 값|Low|  
  
### 계열 이름.  
 `cvSeries` 이벤트 필드, 동시성 시각화 도우미에서 EventSource 이벤트 계열 이름을 제어 하는 문자열인 이벤트를 사용합니다.  
  
### 범주  
 `cvCategory` EventSource 이벤트에 동시성 시각화 도우미에서 제공 하는 항목을 제어 하는 바이트 필드를 조정하는 필드를 사용합니다.  
  
### Text  
 `cvTextW` 필드를 제어 EventSource 이벤트에 동시성 시각화 도우미에서 제공 하는 설명 하는 문자열을 사용합니다.  
  
### SpanID  
 CvSpanId 필드는 int를 사용 하 여 이벤트의 쌍을 일치시키는 필드를 사용합니다.  값 범위를 표시 하는 시작\/중지 이벤트의 각 쌍에 대해 고유 해야 합니다.  일반적으로 동시 코드 필요 동기화 기본 형식 사용 하 여와 같은 <xref:System.Threading.Interlocked.Exchange%2A> 키 \(CvSpanID에 사용 되는 값\)이 정확한 지 확인합니다.  
  
> [!NOTE]
>  부분적으로 동일한 스레드에서 중복 하거나 하나의 스레드를 시작 하도록 허용 하려면 허용 범위를 중첩 하는 SpanID 사용 하 고 다른 끝은 지원 되지 않습니다.  
  
## 참고 항목  
 [동시성 시각화 도우미 표식](../profiling/concurrency-visualizer-markers.md)