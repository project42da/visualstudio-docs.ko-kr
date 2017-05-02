---
title: "액티브 스크립트 디버깅 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "액티브 스크립트 디버깅 개요"
ms.assetid: ce4ec768-d017-4dfa-a7e3-cced3a29e679
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# 액티브 스크립트 디버깅 개요
활성 스크립트 디버깅 인터페이스 언어 중립, 중립 호스트 디버깅을 허용 하 고 다양 한 개발 환경 지원 합니다.  
  
 ![스크립트 호스트 프로세스](../winscript/media/scp56activdbgarchgif.png "Scp56ActivDbgArchgif")  
그림 1  
  
 언어 중립적인 디버깅 환경 프로그래밍 언어 또는 이러한 언어 중 하나에 대 한 특정 지식이 필요 없이 프로그래밍 언어의 조합을 지원할 수 있습니다.  디버깅 환경 또한 언어 간 단계별 실행 및 중단점을 지원합니다.  \(이 개요 Vbscript와 같은 언어의 스크립팅 지원에 주로 초점을 및 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)].\)  
  
 모든 Internet Explorer 또는 사용자 지정 호스트와 같은 액티브 스크립팅 호스트를 자동으로 호스트 중립 디버거를 사용할 수 있습니다.  어떤 디버거 사용자에 게 내용 문서 트리의 구조 및 디버그 문서 구문 색상 표시에서 제시 호스트를 제어 합니다.  이 호스트 문서의 컨텍스트에서 표시할 디버깅된 소스 코드가 있습니다.  예를 들어, Internet Explorer 스크립트 HTML 페이지를 표시할 수 있습니다.  
  
 다음 하위 섹션에는 현재 디버깅 하 고 연결 된 인터페이스에서 각 주요 구성 요소 설명 되어 있습니다.  하지만 더 진행 하기 전에 몇 가지 주요 활성 디버깅 개념 정의 되어야 합니다.  
  
 호스트 응용 프로그램\(host application\)  
 스크립트를 호스팅하는 응용 프로그램 엔진 및 스크립트 집합 개체 \(또는 "개체 모델"\)을 제공 합니다.  
  
 언어 엔진  
 구문 분석, 실행 및 디버깅 특정 언어에 대 한 추상화를 제공 하는 구성 요소입니다.  
  
 IDE 디버거  
 UI 통신 호스트 응용 프로그램 및 언어 엔진을 사용 하 여 디버깅을 제공 하는 응용 프로그램.  
  
 컴퓨터 디버그 관리자  
 응용 프로그램을 디버깅할 수 있는 프로세스의 레지스트리를 유지 관리 하는 구성 요소.  
  
 프로세스 디버그 관리자  
 실행 중인 스레드 및 등 특정 응용 프로그램에 대해 디버깅 가능한 문서 트리를 유지 관리 하는 구성 요소를 추적 합니다.  
  
 문서 컨텍스트  
 문서 컨텍스트 호스트 문서의 소스 코드에서 특정 범위를 나타내는 추상화입니다.  
  
 코드 컨텍스트  
 특정 위치에서 코드를 실행 하는 언어 \("가상 명령 포인터".\) 엔진의 코드 컨텍스트를 나타내는  
  
 식 컨텍스트  
 식 언어 엔진에 의해 계산 될 수 있습니다 특정 컨텍스트 \(예를 들어, 스택 프레임\).  
  
 개체를 검색 합니다.  
 구조적된 언어 독립적인 표현을 개체의 이름, 형식, 값 및 하위 개체의 "감시 창"을 구현 하는 데 적합 한 UI입니다.  
  
 아래 간략하게 각 키 활성 디버깅 구성 요소와 해당, 관련 인터페이스, 인터페이스의 자세한 설명이 표시 됩니다.  
  
## 언어 엔진  
 언어 엔진을 제공합니다.  
  
-   언어 구문 분석 하 고 실행 합니다.  
  
-   디버깅 \(중단점 등\) 지원 합니다.  
  
-   식 계산 합니다.  
  
-   구문 색상 표시 합니다.  
  
-   검색할 개체입니다.  
  
-   스택 열거형 및 구문 분석 합니다.  
  
 아래 스크립트 엔진이 디버깅을 위해 지원 해야 하는 인터페이스, 식 계산 및 찾아보기 개체입니다.  이러한 인터페이스는 호스트 응용 프로그램에서 해당 문서 컨텍스트와 엔진의 코드 컨텍스트 매핑 디버거에서 식 계산을 수행 하는 사용자 인터페이스, 열거형, 스택 및 개체 찾아보기에 사용 됩니다.  
  
 [IActiveScriptDebug 인터페이스](../winscript/reference/iactivescriptdebug-interface.md)  
 구문 색상 표시 및 코드 컨텍스트 열거형을 제공합니다.  
  
 [IActiveScriptErrorDebug 인터페이스](../winscript/reference/iactivescripterrordebug-interface.md)  
 반환 컨텍스트 및 스택 프레임에 대 한 오류를 문서화합니다.  
  
 [IActiveScriptSiteDebug 인터페이스](../winscript/reference/iactivescriptsitedebug-interface.md)  
 디버거를 스크립트 엔진에서 제공 된 링크를 호스트 합니다.  
  
 [IDebugCodeContext 인터페이스](../winscript/reference/idebugcodecontext-interface.md)  
 가상 제공 스레드 "명령 포인터".  
  
 [IEnumDebugCodeContexts 인터페이스](../winscript/reference/ienumdebugcodecontexts-interface.md)  
 문서 컨텍스트를 해당 하는 코드 컨텍스트를 열거 합니다.  
  
 [IDebugStackFrame 인터페이스](../winscript/reference/idebugstackframe-interface.md)  
 스레드 스택의 논리 스택 프레임을 나타냅니다.  
  
 [IDebugExpressionContext 인터페이스](../winscript/reference/idebugexpressioncontext-interface.md)  
 컨텍스트를 식이 계산 될 수 있습니다.  
  
 [IDebugStackFrameSniffer 인터페이스](../winscript/reference/idebugstackframesniffer-interface.md)  
 논리 스택 프레임을 열거 하는 방법을 제공 합니다.  
  
 [IDebugExpression 인터페이스](../winscript/reference/idebugexpression-interface.md)  
 비동기적으로 계산된 하는 식을 나타냅니다.  
  
 [IDebugSyncOperation 인터페이스](../winscript/reference/idebugsyncoperation-interface.md)  
 특정 차단 된 스레드를 중첩 하는 동안 수행 해야 하는 작업을 추상화 하는 스크립트 엔진을 수 있습니다.  
  
 [IDebugAsyncOperation 인터페이스](../winscript/reference/idebugasyncoperation-interface.md)  
 동기 디버그 작업을 비동기 액세스를 제공합니다.  
  
 [IDebugAsyncOperationCallBack 인터페이스](../winscript/reference/idebugasyncoperationcallback-interface.md)  
 진행에 관련 된 상태 이벤트를 제공 된 `IDebugAsyncOperation` 인터페이스 평가 합니다.  
  
 [IEnumDebugExpressionContexts 인터페이스](../winscript/reference/ienumdebugexpressioncontexts-interface.md)  
 컬렉션의 열거 `IDebugExpressionContexts` 개체입니다.  
  
 [IProvideExpressionContexts 인터페이스](../winscript/reference/iprovideexpressioncontexts-interface.md)  
 특정 구성 요소에서 알려진 식 컨텍스트를 열거 하는 방법을 제공 합니다.  
  
 [IDebugFormatter 인터페이스](../winscript/reference/idebugformatter-interface.md)  
 언어 또는 IDE VARIANT 값 또는 VARTYPE 형식과 문자열 간의 변환을 사용자 지정할 수 있습니다.  
  
 [IDebugStackFrameSnifferEx 인터페이스](../winscript/reference/idebugstackframesnifferex-interface.md)  
 PDM에 대 한 논리적 스택 프레임을 열거합니다.  
  
## 호스트  
 호스트:  
  
-   언어 엔진을 호스팅합니다.  
  
-   \(집합 스크립팅 될 개체의\) 개체 모델을 제공 합니다.  
  
-   트리를 디버깅할 수 있습니다 문서 및 해당 내용을 정의 합니다.  
  
-   가상 응용 프로그램에 스크립트를 구성합니다.  
  
 두 가지 종류의 호스트:  
  
-   단순 호스트 기본 Active 스크립팅 인터페이스만을 지원합니다.  문서 구조 나 조직에 따른 통제 되지. 이 언어 엔진을 제공 하는 스크립트에 전적으로 결정 됩니다.  
  
-   스마트 호스트 문서 트리, 문서 내용 및 구문 색을 정의할 수 있도록 큰 인터페이스 집합을 지원 합니다.  스마트 호스트를 사용할 수 있는 호스트에 대해 훨씬 쉽게 하는 다음 하위 절에서 설명 된 도우미 인터페이스의 집합이입니다.  
  
### 스마트 호스트 도우미 인터페이스  
 `IDebugDocumentHelper` 메서드는 호스트는 전체 복잡성 \(및 전원\)의 전체 호스트 인터페이스를 처리 하지 않고 스마트 호스팅의 이점을 얻을 수 있는 아주 간단 하 게 인터페이스 집합을 제공 합니다.  
  
 물론 이러한 인터페이스를 사용 하는 호스트 필요는 없습니다.  그러나 이러한 인터페이스를 사용 하 여 구현 또는 여러 복잡 한 인터페이스를 사용 하 여 피할 수 있습니다.  
  
 [IDebugDocumentHelper 인터페이스](../winscript/reference/idebugdocumenthelper-interface.md)  
 PDM으로 구현 하 고 스마트 호스트에 대 한 필요한 많은 인터페이스에 대 한 구현을 제공 합니다.  
  
 [IDebugDocumentHost 인터페이스](../winscript/reference/idebugdocumenthost-interface.md)  
 구문 색, 디버거를 호스트 관련 기능을 노출 하는 호스트 구현 \(선택 사항\).  
  
 자세한 내용은 [스마트 호스트 도우미 인터페이스 구현](../winscript/implementing-smart-host-helper-interfaces.md)을 참조하십시오.  
  
### 전체 스마트 호스트 인터페이스  
 아래는 전체 스마트 호스트를 구현 하거나 도우미 인터페이스 사용 하는 경우 사용 하는 인터페이스를 설정 합니다.  
  
 호스트에서 구현한 인터페이스:  
  
 [IDebugDocumentInfo 인터페이스](../winscript/reference/idebugdocumentinfo-interface.md)  
 인스턴스화할 수 있고 문서에 정보를 제공 합니다.  
  
 [IDebugDocumentProvider 인터페이스](../winscript/reference/idebugdocumentprovider-interface.md)  
 문서는 필요할 때 인스턴스화는 수단을 제공 합니다.  
  
 [IDebugDocument 인터페이스](../winscript/reference/idebugdocument-interface.md)  
 디버그의 모든 문서에 대 한 기본 인터페이스입니다.  
  
 [IDebugDocumentText 인터페이스](../winscript/reference/idebugdocumenttext-interface.md)  
 텍스트 전용 버전의 디버그 문서 액세스를 제공합니다.  
  
 [IDebugDocumentTextAuthor 인터페이스](../winscript/reference/idebugdocumenttextauthor-interface.md)  
 디버그 문서의 텍스트 전용 버전을 편집할 수 있습니다.  
  
 [IDebugDocumentContext 인터페이스](../winscript/reference/idebugdocumentcontext-interface.md)  
 디버깅 중인 문서 중 일부는 추상 표현을 제공 합니다.  
  
 호스트를 대신 하 여 PDM으로 구현 된 인터페이스:  
  
 [IDebugApplicationNode 인터페이스](../winscript/reference/idebugapplicationnode-interface.md)  
 기능을 확장은 `IDebugDocumentProvider` 프로젝트 트리 내에서 컨텍스트를 제공 하는 인터페이스입니다.  
  
## IDE 디버거  
 IDE는 디버깅 하는 언어 독립적인 UI입니다.  이 제공합니다.  
  
-   문서 뷰어\/편집기입니다.  
  
-   중단점 관리  
  
-   식 평가 및 조사식 창입니다.  
  
-   프레임 탐색 스택.  
  
-   객체\/클래스 검색 합니다.  
  
-   가상 응용 프로그램 구조를 탐색 합니다.  
  
 디버거를 통해 구현 하는 인터페이스.  
  
 [IApplicationDebugger 인터페이스](../winscript/reference/iapplicationdebugger-interface.md)  
 IDE 디버거 세션에서 노출 하는 기본 인터페이스입니다.  
  
 [IApplicationDebuggerUI 인터페이스](../winscript/reference/iapplicationdebuggerui-interface.md)  
 외부 구성 요소에서 디버거 사용자 인터페이스 \(UI\)를 보다 효율적으로 제어할 수 있습니다.  
  
 [IDebugExpressionCallBack 인터페이스](../winscript/reference/idebugexpressioncallback-interface.md)  
 상태 이벤트에 대 한 제공 `IDebugExpression` 평가 진행 합니다.  
  
 [IDebugDocumentTextEvents 인터페이스](../winscript/reference/idebugdocumenttextevents-interface.md)  
 연결 된 텍스트 문서에 변경 사항을 나타내는 이벤트를 제공 합니다.  
  
 [IDebugApplicationNodeEvents 인터페이스](../winscript/reference/idebugapplicationnodeevents-interface.md)  
 이벤트 인터페이스에 대 한 제공 된 `IDebugApplicationNode` 인터페이스.  
  
### 컴퓨터 디버그 관리자  
 컴퓨터 디버그 관리자 유지 관리 및 활성 가상 응용 프로그램 목록을 열거 하 여 후크 지점 간의 가상 응용 프로그램 및 디버거를 제공 합니다.  
  
 [IDebugSessionProvider 인터페이스](../winscript/reference/idebugsessionprovider-interface.md)  
 실행 중인 응용 프로그램에 대 한 디버그 세션을 설정합니다.  
  
 [IMachineDebugManager 인터페이스](../winscript/reference/imachinedebugmanager-interface.md)  
 컴퓨터 디버그 관리자에는 기본 인터페이스입니다.  
  
 [IMachineDebugManagerCookie 인터페이스](../winscript/reference/imachinedebugmanagercookie-interface.md)  
 유사한 있는 `IMachineDebugManager` 인터페이스를 있지만 인터페이스 지 원하는 디버그 쿠키.  
  
 [IMachineDebugManagerEvents 인터페이스](../winscript/reference/imachinedebugmanagerevents-interface.md)  
 신호 변경 실행 하는 컴퓨터 디버그 관리자에 의해 관리 되는 응용 프로그램 목록입니다.  
  
 [IEnumRemoteDebugApplications 인터페이스](../winscript/reference/ienumremotedebugapplications-interface.md)  
 컴퓨터에서 실행 중인 응용 프로그램을 열거합니다.  
  
### 프로세스 디버그 관리자  
 PDM은 다음을 수행합니다.  
  
-   여러 언어 엔진의 디버깅을 동기화 합니다.  
  
-   디버깅 가능한 문서 트리를 유지 관리합니다.  
  
-   스택 프레임을 병합 합니다.  
  
-   중단점 및 단계별 언어 엔진 간에 조정 합니다.  
  
-   스레드를 추적합니다.  
  
-   비동기 처리에 대 한 디버거 스레드를 유지합니다.  
  
-   컴퓨터 디버그 관리자 및 IDE 디버거가 통신합니다.  
  
 다음은 프로세스 디버그 관리자가 제공 하는 인터페이스입니다.  
  
 [IProcessDebugManager 인터페이스](../winscript/reference/iprocessdebugmanager-interface.md)  
 프로세스 디버그 관리자에 대 한 기본 인터페이스입니다.  이 인터페이스를 만드는 하 고, 추가 또는 프로세스에서 가상 응용 프로그램을 제거 합니다.  
  
 [IRemoteDebugApplication 인터페이스](../winscript/reference/iremotedebugapplication-interface.md)  
 실행 중인 응용 프로그램을 나타냅니다.  
  
 [IDebugApplication 인터페이스](../winscript/reference/idebugapplication-interface.md)  
 원격화 할 수 있는 이외의 디버깅 방법을 사용할 언어 엔진 및 호스트에서 노출합니다.  
  
 [IRemoteDebugApplicationThread 인터페이스](../winscript/reference/iremotedebugapplicationthread-interface.md)  
 특정 응용 프로그램 내의 실행 스레드를 나타냅니다.  
  
 [IDebugApplicationThread 인터페이스](../winscript/reference/idebugapplicationthread-interface.md)  
 언어 엔진 및 호스트 스레드 동기화를 제공 하 고 디버그 상태, 스레드 관련 정보를 관리할 수 있습니다.  
  
 [IEnumRemoteDebugApplicationThreads 인터페이스](../winscript/reference/ienumremotedebugapplicationthreads-interface.md)  
 응용 프로그램에서 실행 중인 스레드를 열거합니다.  
  
 [IDebugThreadCall 인터페이스](../winscript/reference/idebugthreadcall-interface.md)  
 마샬링된 호출을 디스패치합니다.  
  
 [IDebugApplicationNode 인터페이스](../winscript/reference/idebugapplicationnode-interface.md)  
 위치를 문서 계층 구조에서를 유지합니다.  
  
 [IEnumDebugApplicationNodes 인터페이스](../winscript/reference/ienumdebugapplicationnodes-interface.md)  
 응용 프로그램과 연결 된 노드의 자식 노드를 열거 합니다.  
  
 [IEnumDebugStackFrames 인터페이스](../winscript/reference/ienumdebugstackframes-interface.md)  
 엔진에서 병합을 스레드에 해당 하는 스택 프레임을 열거 합니다.  
  
 [IDebugCookie 인터페이스](../winscript/reference/idebugcookie-interface.md)  
 디버그 쿠키를에서 스크립트 디버거를 설정할 수 있습니다.  
  
 [IDebugHelper 인터페이스](../winscript/reference/idebughelper-interface.md)  
 스크립트 엔진에 대 한 간단한 연결 점과 개체 브라우저에 대 한 팩터리 역할을 합니다.  
  
 [ISimpleConnectionPoint 인터페이스](../winscript/reference/isimpleconnectionpoint-interface.md)  
 간단 하 게 설명 하 고 스크립트 엔진에 대 한 특정 연결 지점에서 발생 하는 이벤트를 열거 하기 위한 제공 합니다.  
  
## 참고 항목  
 [액티브 스크립트 디버거 인터페이스](../winscript/reference/active-script-debugger-interfaces.md)