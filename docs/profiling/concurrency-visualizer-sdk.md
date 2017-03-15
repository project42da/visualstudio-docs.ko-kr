---
title: "동시성 시각화 도우미 SDK | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.cv.sdk.about"
ms.assetid: 4b22cdf9-59b1-4c88-a6d8-1644a4a11e08
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# 동시성 시각화 도우미 SDK
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

자세한 내용은 동시성 시각화 도우미에 표시할 동시성 시각화 도우미 SDK를 사용 하 여 소스 코드를 계측할 수 있습니다.  코드에서 단계와 이벤트를 사용하여 추가 데이터를 연결할 수 있습니다.  이러한 추가 시각화 이라고 *마커*라고 알려져 있습니다.  기초 연습을 참조 하십시오. [는 동시성 시각화 도우미 SDK 소개](http://go.microsoft.com/fwlink/?LinkId=235405).  
  
## 속성  
 플래그, 범위, 및 두 개의 속성을가지고 각 메시지: 범주 및 중요도입니다.  에  [고급 설정](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) 대화 상자가 표시 되는 표식의 집합을 필터링 하려면이 속성을 사용할 수 있습니다.  또한 이러한 속성 마커의 시각적 표현을 영향을 줍니다.  예를 들어, 플래그의 크기는 중요도 나타내는 데 사용 됩니다.  또한 색 범주를 나타내는 데 사용 됩니다.  
  
## 기본 사용법  
 동시성 시각화 도우미에서 노출 마커를 생성 하는 데 사용할 수 있는 기본 공급자.  동시성 시각화 도우미와 함께 이미 등록 된 공급자 및 UI에 마커를 다른 작업을 수행할 필요가 없습니다.  
  
### Visual Basic 및 C\# 언어  
 C\#, Visual basic 및 다른 관리 코드를 호출 하 여 기본 공급자를 사용하세요 <xref:Microsoft.ConcurrencyVisualizer.Instrumentation.Markers>.  마커를 생성 하기 위한 네 가지 기능 노출: <xref:Microsoft.ConcurrencyVisualizer.Instrumentation.Markers.WriteFlag%2A>, <xref:Microsoft.ConcurrencyVisualizer.Instrumentation.Markers.EnterSpan%2A>, <xref:Microsoft.ConcurrencyVisualizer.Instrumentation.Markers.WriteMessage%2A>, 및 <xref:Microsoft.ConcurrencyVisualizer.Instrumentation.Markers.WriteAlert%2A>.  원하는 속성에 대해 기본값을 사용 하는지 여부에 따라 이러한 함수에 대 한 여러 개의 오버 로드가 있습니다.  가장 간단한 오버 로드는 문자열 매개 변수만 이벤트에 대 한 설명을 지정 하는.  동시성 시각화 보고서에 설명이 표시 됩니다.  
  
##### SDK 지원 C\# 또는 Visual Basic 프로젝트에 추가 하려면  
  
1.  선택 메뉴 모음에서 **분석**, **동시성 시각화 도우미**, **프로젝트에 추가 SDK**선택합니다.  
  
2.  SDK에 액세스 한 다음 선택 하려는 프로젝트를 선택 하면 **선택한 프로젝트에 추가 SDK** 단추를 선택합니다.  
  
3.  Imports 또는 using 문을 코드에 추가 합니다.  
  
    ```c#  
    using Microsoft.ConcurrencyVisualizer.Instrumentation;  
    ```  
  
    ```vb  
    Imports Microsoft.ConcurrencyVisualizer.Instrumentation  
    ```  
  
### C\+\+  
 C \+ \+에서 작성한 [marker\_series 클래스](../profiling/marker-series-class.md) 개체를 사용하여 함수를 호출하고 사용하니다.   `marker_series`  마커를 생성 하기 위한 세 가지 함수를 제공 하는 클래스는 [marker\_series::write\_flag 메서드](../profiling/marker-series-write-flag-method.md), [marker\_series::write\_message 메서드](../profiling/marker-series-write-message-method.md), 및 [marker\_series::write\_alert 메서드](../profiling/marker-series-write-alert-method.md).  
  
##### C 또는 c \+ \+ 프로젝트에 SDK 지원을 추가 하려면  
  
1.  선택 메뉴 모음에서 **분석**, **동시성 시각화 도우미**, **프로젝트에 추가 SDK**선택합니다.  
  
2.  SDK에 액세스 한 다음 선택 하려는 프로젝트를 선택 하면 **선택한 프로젝트에 추가 SDK** 단추를 선택합니다.  
  
3.  C \+ \+ 포함  `cvmarkersobj.h` .  C \+ \+ 포함  `cvmarkers.h` .  
  
4.  사용 하 여 추가 문을 코드에 있습니다.  
  
    ```  
    using namespace Concurrency::diagnostic;  
    ```  
  
5.  새 `marker_series` 개체를 만들고 `span` 개체를 여기에서 전달합니다.  
  
    ```cpp  
  
    marker_series mySeries;  
    span s(mySeries, _T("Span description"));  
  
    ```  
  
## 사용자 지정 사용  
 동시성 시각화 도우미 SDK 고급 시나리오에 대 한 제어를 제공합니다.  고급 시나리오를 사용 하 여 관련 된 두 가지 주요 개념: 공급자 마커 및 마커 시리즈.  표시기 공급자는 ETW 공급자 \(각각 다른 GUID를가지고\)입니다.  마커 일련은 직렬 채널을 한 공급자에 의해 생성 되는 이벤트입니다.  표시기 공급자에 의해 생성 되는 이벤트를 구성 하 여 사용할 수 있습니다.  
  
#### C\# 또는 Visual Basic 프로젝트에 새 표시기 공급자를 사용 하려면  
  
1.  <xref:Microsoft.ConcurrencyVisualizer.Instrumentation.MarkerWriter> 개체를 만듭니다.  생성자는 GUID를 사용 합니다.  
  
2.  동시성 시각화 도우미를 열려면 공급자를 등록 하려면 [고급 설정](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) 대화 상자를 엽니다.  선택은 **마커** 탭을 누른 다음 선택의 **새 공급자를 추가** 단추를 추가합니다.  [고급 설정](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) 대화 상자에 공급자와 공급자에 대 한 설명을 만드는데 사용된 GUID를 입력합니다.  
  
#### C\+\+ 또는 C 프로젝트에 새 표시기 공급자를 사용 하려면  
  
1.  사용 하는 `CvInitProvider` PCV\_PROVIDER를 초기화할 함수입니다.  생성자는 GUID \* 및 PCV\_PROVIDER \*를 사용 합니다.  
  
2.  열 공급자를 등록 하는 [고급 설정](../profiling/advanced-settings-dialog-box-concurrency-visualizer.md) 대화 상자를 엽니다.  선택은 **마커** 탭을 누른 다음 선택의 **새 공급자를 추가** 단추를 추가합니다.  이 대화 상자에 공급자와 공급자에 대 한 설명을 만드는데 사용된 GUID를 입력합니다.  
  
#### C\# 또는 Visual Basic 프로젝트에 새 표시기를 사용 하려면  
  
1.  새를 사용 하 여 <xref:Microsoft.ConcurrencyVisualizer.Instrumentation.MarkerSeries>를 먼저 사용하여 만드는 <xref:Microsoft.ConcurrencyVisualizer.Instrumentation.MarkerWriter> 개체를 새 시리즈에서 직접 마커 이벤트를 생성 합니다.  
  
    ```c#  
    MarkerSeries series1 = myMarkerWriter.CreateMarkerSeries(″Series 1″);  
    series1.WriteFlag(″My flag″);  
    ```  
  
    ```vb  
    Dim series1 As New myMarkerWriter.CreateMarkerSeries(″Series 1″)  
    series1.WriteFlag(″My flag″)  
    ```  
  
#### C \+ \+ 프로젝트에서 마커 시리즈를 사용하여  
  
1.  `marker_series` 개체를 만듭니다.  이 새로운 시리즈에서 이벤트를 생성할 수 있습니다.  
  
    ```scr  
    marker_series series;  
    series.write_flag(_T("Hello world!"));  
    ```  
  
#### C 프로젝트에서 마커 시리즈를 사용하여  
  
1.  PCV\_MARKERSERIES를 만들기 위해 `CvCreateMarkerSeries` 기능을 사용하세요.  
  
    ```cpp  
    PCV_MARKERSERIES series;  
    CvCreatemarkerSeries(myProvider, _T("My Series"), &series);  
    CvWriteFlag(series, _T("Writing a flag"));  
    ```  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[C\+\+ 라이브러리 참조](../profiling/cpp-library-reference.md)|C\+\+용 동시성 시각화 도우미 API를 설명합니다.|  
|[C 라이브러리 참조](../profiling/c-library-reference.md)|C용 동시성 시각화 도우미 API를 설명합니다.|  
|<xref:Microsoft.ConcurrencyVisualizer.Instrumentation>|동시성 시각화 도우미 API는 관리 코드에 대해 설명합니다.|  
|[동시성 시각화 도우미](../profiling/concurrency-visualizer.md)|동시성 방법으로 생성되고 스레드 실행 데이터를 포함하는 프로파일링 데이터 파일의 뷰 및 보고서에 대한 참조 정보입니다.|