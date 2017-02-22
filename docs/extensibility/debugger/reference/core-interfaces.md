---
title: "코어 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK], 핵심 인터페이스"
ms.assetid: 666b9116-8550-4bdd-bc15-55fc57de87df
caps.latest.revision: 24
caps.handback.revision: 24
ms.author: "gregvanl"
manager: "ghogen"
---
# 코어 인터페이스
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

다음 인터페이스 코어 인터페이스를 사용 하 여 디버거 확장 되는 [!INCLUDE[vsipsdk](../../../extensibility/includes/vsipsdk_md.md)].  
  
## 토론  
 이러한 인터페이스는 주로 디버그 엔진 \(DE\)를 만드는 데 사용 됩니다.  이들은 여기 범주별으로 구성 되어 있습니다.  
  
-   [중단점](#Breakpoints)  
  
-   [컨텍스트](#Contexts)  
  
-   [핵심 서버](#CoreServer)  
  
-   [디버그 엔진](#DebugEngines)  
  
-   [문서](#Documents)  
  
-   [이벤트](#Events)  
  
-   [식](#Expressions)  
  
-   [메모리](#Memory)  
  
-   [모듈](#Modules)  
  
-   [포트](#Ports)  
  
-   [프로세스](#Processes)  
  
-   [프로그램](#Programs)  
  
-   [속성](#Properties)  
  
-   [스택 프레임](#StackFrames)  
  
-   [스레드](#Threads)  
  
-   [형식 시각화 도우미](#TypeVisualizers)  
  
 인터페이스를 구현 하는 엔터티 됩니다.  
  
-   디버그 엔진 \(DE\)  
  
-   포트 공급자 \(PS\)  
  
-   식 계산기 \(EE\)  
  
-   Visual Studio \(VS\)  
  
##  <a name="Breakpoints"></a> 중단점  
 이 인터페이스와 관련 된 구현 및 중단점을 추적 합니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)|DE|메모리 위치에 바인딩된 중단점을 나타냅니다.|  
|[IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)|DE|메모리 위치에 중단점을 바인딩할 때 DE로 전송 합니다.|  
|[IDebugBreakpointChecksumRequest2](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2.md)|VS|문서 중단점 요청에 대 한 체크섬을 나타냅니다.|  
|[IDebugBreakpointErrorEvent2](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)|DE|메모리 위치에 중단점을 실패 하면 DE로 전송 합니다.|  
|[IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)|DE|중단점에 도달 하면 DE로 전송 합니다.|  
|[IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)|VS|중단점에 대 한 요청을 나타냅니다. 보류 중단점 만들 때 사용 합니다.|  
|[IDebugBreakpointRequest3](../../../extensibility/debugger/reference/idebugbreakpointrequest3.md)|VS|중단점에 대 한 요청을 나타냅니다. 보류 중단점 만들 때 사용 합니다.|  
|[IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md)|DE|중단점을 바인딩하는 데 사용 되는 정보를 나타냅니다.|  
|[IDebugBreakpointUnboundEvent2](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md)|DE|DE에서 전송 중단점 메모리 위치에서 바인딩되어 있지 않습니다.|  
|[IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)|DE|잘못 된 중단점이 나타내는 \(반환 된 `IDebugBreakpointErrorEvent2`\).|  
|[IDebugErrorBreakpointResolution2](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2.md)|DE|해상도 잘못 된 중단점에 대 한 정보를 나타냅니다.|  
|[IDebugFunctionPosition2](../../../extensibility/debugger/reference/idebugfunctionposition2.md)|DE|함수에서 중단점 설정 된 위치를 나타냅니다.|  
|[IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)|DE|바인딩된 중단점을 나타냅니다. 바인딩된 중단점을 만들 때 사용 합니다.|  
|[IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)|DE|바인딩된 중단점의 집합에는 열거형을 나타냅니다.|  
|[IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md)|DE|메모리 위치를 바인딩할 수 없습니다 중단점 세트는 열거형을 나타냅니다.|  
  
##  <a name="Contexts"></a> 컨텍스트  
 이러한 인터페이스 컨텍스트 내에서 디버깅 중인 프로그램의 다양 한 종류를 나타냅니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)|DE|코드 명령의 시작 위치를 나타냅니다.|  
|[IDebugCodeContext3](../../../extensibility/debugger/reference/idebugcodecontext3.md)|DE|확장 하 여 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 인터페이스 모듈 및 프로세스 인터페이스를 검색할 수 있도록 합니다.|  
|[IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)|VS, DE|문서에 있는 위치를 나타냅니다.|  
|[IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)|DE|식을 계산 하려면 컨텍스트를 나타냅니다.|  
|[IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)|DE|메모리의 바이트 컬렉션의 시작 위치를 나타냅니다.|  
|[IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)|DE|스택 프레임에서 중단점 또는 예외 컨텍스트를 나타냅니다.|  
|[IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)|DE|스택 프레임에서 중단점 또는 예외 컨텍스트를 나타냅니다.|  
|[IEnumDebugCodeContexts2](../../../extensibility/debugger/reference/ienumdebugcodecontexts2.md)|DE|코드 컨텍스트 집합에는 열거형을 나타냅니다.|  
  
##  <a name="CoreServer"></a> 핵심 서버  
 이러한 인터페이스는 프로그램을 디버깅 하는 컴퓨터를 나타냅니다.  이 의해 구현 된 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 에 디버깅 엔진에 의해 호출 될 수 있지만.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)|VS|액세스 포트 및 포트 공급자 뿐만 아니라 컴퓨터에 대 한 정보를 제공 합니다.|  
|[IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)|VS|나타내는 있는 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) 는 원격 디버깅을 지원 합니다.|  
  
##  <a name="DebugEngines"></a> 디버그 엔진  
 이러한 인터페이스가 디버깅 엔진 및 해당 관련 된 이벤트를 나타냅니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)|DE|사용자 지정 디버그 엔진을 나타냅니다.|  
|[IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)|DE|기호와 Justmycode를 예외의 로딩을 지원 하는 사용자 지정 디버그 엔진을 나타냅니다.|  
|[IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)|DE|DE의 각 새 인스턴스로 전송 디버깅 작업을 처리 하는 것을 나타냅니다.|  
|[IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)|DE|시작 프로그램을 지원 하는 사용자 지정 디버그 엔진을 나타냅니다.|  
|[IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)|DE, PS|처리 하는 여러 디버깅 엔진 프로그램이 노드를 나타냅니다.|  
|[IDebugQueryEngine2](../../../extensibility/debugger/reference/idebugqueryengine2.md)|DE|SDM 스레드, 프로그램 또는 스택 프레임에서 디버그 엔진에 인터페이스를 가져올 수 있는 방법을 제공 합니다.|  
  
##  <a name="Documents"></a> 문서  
 이러한 인터페이스 문서 \(원본 파일\) 및 관련된 요소를 나타냅니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md)|DE|DE에서 열려는 문서를 요청 하는 전송.|  
|[IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)|DE|디스어셈블된 문서에서 스트림을 나타냅니다.|  
|[IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)|VS, DE|이름과 클래스 ID \(CLSID\)를 지정 하는 DE에서 제공 되는 문서를 나타냅니다.|  
|[IDebugDocumentChecksum2](../../../extensibility/debugger/reference/idebugdocumentchecksum2.md)|EE DE|디버그 문서에 대 한 체크섬을 나타냅니다 및 체크섬 구성 요소 간에 전달 하면 됩니다.|  
|[IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)|VS, DE|문서 컨텍스트를, 문 한 코드는 특정 컨텍스트에 해당 문서 내의 위치를 나타냅니다.|  
|[IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)|VS, DE|일반 문서 내의 위치를 나타냅니다.|  
|[IDebugDocumentPositionOffset2](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2.md)|VS|소스 파일에서 위치를 문자 오프셋을 나타냅니다.|  
|[IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)|VS, DE|DE에서 제공 되는 텍스트 문서를 나타냅니다 \(에서 파생 된 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)\), 실제 텍스트를 제공 합니다.|  
|[IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)|DE|DE에서 지정 하려면 메모리에 있는 소스 파일 변경 내용을 전송.|  
  
##  <a name="Events"></a> 이벤트  
 이러한 인터페이스는 DE와 세션 디버그 매니저 \(SDM\) 사이 전송 되는 모든 이벤트를 나타냅니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugActivateDocumentEvent2](../../../extensibility/debugger/reference/idebugactivatedocumentevent2.md)|DE|DE에서 열려는 문서를 요청 하는 전송.|  
|[IDebugBeforeSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2.md)|DE|디버그 엔진 \(DE\)이이 인터페이스 세션 디버그 관리자 \(SDM\) 상태를 설정 하려면 메시지 표시줄 기호 로드 중 보냅니다.|  
|[IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)|DE|프로그램 대로 완료 되 면 DE로 전송 합니다.|  
|[IDebugBreakpointBoundEvent2](../../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)|DE|중단점을 바인딩할 때 DE로 전송 합니다.|  
|[IDebugBreakpointErrorEvent2](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)|DE|중단점에 실패할 때 DE로 전송 합니다.|  
|[IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)|DE|중단점에 도달 하면 DE로 전송 합니다.|  
|[IDebugBreakpointUnboundEvent2](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2.md)|DE|중단점이 바인딩 해제 된 경우 DE로 전송 합니다.|  
|[IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)|DE|특정 위치에서 중지 해야 하는지 여부를 확인 하려면 DE에서를 전송.|  
|[IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)|DE|DE에서 지정 하려면 메모리에 있는 소스 파일 변경 내용을 전송.|  
|[IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)|DE|DE의 각 새 인스턴스로 전송 디버깅 작업을 처리 하는 것을 나타냅니다.|  
|[IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md)|DE|DE에서 디버깅 중인 프로그램에서 첫 번째 명령 실행 준비가 되었습니다 나타내려면 보낸.|  
|[IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)|DE|오류가 발생 한 다른 이벤트 인터페이스에서 사람이 읽을 수 있는 오류 메시지를 제공 하는 데 사용 되는 인터페이스입니다.|  
|[IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)|DE, PS|다른 모든 이벤트에서 인터페이스가 파생 되는 기본 인터페이스입니다.|  
|[IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)|VS|\(특정 이벤트 인터페이스를 구현 하는 개체로 표현\) 이벤트를 받는 SDM에서 구현 되는 인터페이스를 나타냅니다.|  
|[IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)|DE|디버깅 중인 프로그램에서 예외가 발생 했을 때 DE로 전송 합니다.|  
|[IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)|DE|DE에서 비동기 식을 실행이 완료 되 면 전송.|  
|IDebugFindSymbolEvent2||사용 되지 않음.  사용 하지 않습니다.|  
|[IDebugInterceptExceptionCompleteEvent2](../../../extensibility/debugger/reference/idebuginterceptexceptioncompleteevent2.md)|DE|DE에서 차단된 예외 처리가 완료 되 면 전송 합니다.|  
|[IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)|DE|프로그램 로딩이 완료 되 면 DE로 전송 합니다.|  
|[IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)|DE|IDE 표시 하는 DE에서 정보 메시지가 사용자에 게 전송 합니다.|  
|[IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md)|DE|DE 여 모듈이 로드 되거나 언로드될 때 전송 합니다.|  
|[IDebugNoSymbolsEvent2](../../../extensibility/debugger/reference/idebugnosymbolsevent2.md)|DE|신호를 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 디버거에서 기호 시작된 실행 파일을 찾을 수 있는 사용자에 게 경고 하는 사용자 인터페이스입니다.|  
|[IDebugOutputStringEvent2](../../../extensibility/debugger/reference/idebugoutputstringevent2.md)|DE|IDE 표시 하는 DE에서 임의의 문자열을 보낸 합니다.|  
|[IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)|VS, DE|포트에서 포트 이벤트는 수신기에 통신을 보낼.|  
|[IDebugProcessCreateEvent2](../../../extensibility/debugger/reference/idebugprocesscreateevent2.md)|DE, PS|프로세스를 만들 때 DE 나 포트에서 보낸.|  
|[IDebugProcessDestroyEvent2](../../../extensibility/debugger/reference/idebugprocessdestroyevent2.md)|DE, PS|프로세스 소멸 될 때 DE 나 포트에서 보낸.|  
|[IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)|DE, PS|프로그램을 만들 때 DE 나 포트에서 보낸.|  
|[IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)|DE, PS|프로그램이 제거 될 때 DE 나 포트에서 보낸.|  
|[IDebugProgramDestroyEventFlags2](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2.md)|DE|디버그 엔진의 기본 동작을 재정의할 수 있습니다 해당 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 디버그 세션을 종료 하면 UI입니다.|  
|[IDebugProgramNameChangedEvent2](../../../extensibility/debugger/reference/idebugprogramnamechangedevent2.md)|DE|프로그램의 이름을 변경 하는 경우 디버그 엔진 \(DE\)에서 세션 디버그 매니저 \(SDM\) 전송 합니다.|  
|[IDebugPropertyCreateEvent2](../../../extensibility/debugger/reference/idebugpropertycreateevent2.md)|DE|때 새 속성이 DE에 의해 보낸 \(표시 되는 `IDebugProperty2` 인터페이스\) 만들었습니다.|  
|[IDebugPropertyDestroyEvent2](../../../extensibility/debugger/reference/idebugpropertydestroyevent2.md)|DE|속성 제거 될 때 DE로 전송 합니다.|  
|[IDebugReturnValueEvent2](../../../extensibility/debugger/reference/idebugreturnvalueevent2.md)|DE|DE가 부족 하거나 함수에서 반환 값을 올바르게 표시할 수 있도록 한 단계씩 실행 하는 경우 보내지.|  
|[IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)|VS|디버그 엔진 미터법 설정을 읽을 수 있도록 원격으로 합니다.|  
|[IDebugStepCompleteEvent2](../../../extensibility/debugger/reference/idebugstepcompleteevent2.md)|DE|DE에서,을 통해 또는 명령 실행 단계가 완료 되었을 때 전송 합니다.|  
|[IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)|DE|DE에서 성공 또는 모듈에 대해 기호 로드 실패를 나타내는 전송.|  
|[IDebugThreadCreateEvent2](../../../extensibility/debugger/reference/idebugthreadcreateevent2.md)|DE|스레드를 만들 때 DE로 전송 합니다.|  
|[IDebugThreadDestroyEvent2](../../../extensibility/debugger/reference/idebugthreaddestroyevent2.md)|DE|스레드가 소멸 될 때 DE로 전송 합니다.|  
|[IDebugThreadNameChangedEvent2](../../../extensibility/debugger/reference/idebugthreadnamechangedevent2.md)|DE|스레드 이름이 변경 되 면 DE로 전송 합니다.|  
  
##  <a name="Expressions"></a> 식  
 이러한 인터페이스가 특정 컨텍스트에서 평가 될 수 있는 식을 나타냅니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)|DE|평가 되는 식을 나타냅니다.  가져온는 [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md) 인터페이스입니다.|  
|[IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md)|DE|식이 계산 되는 컨텍스트를 나타냅니다.  가져온는 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) 인터페이스입니다.|  
|[IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)|DE|DE에서 비동기 식을 실행이 완료 되 면 전송.|  
  
##  <a name="Memory"></a> 메모리  
 이러한 인터페이스를 메모리에 바이트의 시퀀스를 나타냅니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)|DE|읽기 또는 기록 하는 메모리에 바이트의 시퀀스를 나타냅니다.|  
|[IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)|DE|바이트 시퀀스를 메모리에서 위치를 나타냅니다.|  
  
##  <a name="Modules"></a> 모듈  
 이러한 인터페이스는 실행 파일에 해당 하는 모듈을 나타내는 또는.DLL 파일입니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)|DE|단일 실행 파일 또는 DLL을 나타냅니다.|  
|[IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)|DE|나타내는 있는 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) 는 기호를 지원 합니다.|  
|[IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md)|DE|DE 여 모듈이 로드 되거나 언로드될 때 전송 합니다.|  
|[IDebugSourceServerModule](../../../extensibility/debugger/reference/idebugsourceservermodule.md)|DE|PDB 파일에 포함 된 원본 서버의 정보를 나타냅니다.|  
|[IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)|DE|세트에서 알려진 모듈의 열거형을 나타냅니다는 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md).|  
  
##  <a name="Ports"></a> 포트  
 이러한 인터페이스 포트와 포트 공급자를 나타냅니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)|PS VS|기본 포트를 로컬 컴퓨터를 나타냅니다.|  
|[IDebugFirewallConfigurationCallback2](../../../extensibility/debugger/reference/idebugfirewallconfigurationcallback2.md)|VS|DCOM 요청 하는 데 사용 되는 디버그 엔진 수는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 방화벽 원격 디버깅이 차단 합니다 있는지 확인 하는 사용자 인터페이스입니다.|  
|[IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)|PS VS|포트를 나타냅니다.|  
|[IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)|PS|포트에서 포트 이벤트는 수신기에 통신을 보낼.|  
|[IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)|PS|시작 하 고 프로세스를 종료 하는 포트를 나타냅니다.|  
|[IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)|PS|등록 한 프로그램을 포트의 등록을 취소 하는 데 사용; 현재 디버깅 중인 프로그램을 추적 하는 포트 수 있습니다.|  
|[IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)|PS|포트 선택에 대 한 사용자 지정 된 UI를 나타냅니다.|  
|[IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)|VS|포트를 새 포트를 만든 있거나 있을 것에 대 한 요청을 나타냅니다.|  
|[IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)|PS|협력 업체를의 포트를 나타냅니다.|  
|[IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)|PS|협력 업체에 저장 하는 포트를 나타내는 포트에 대 한 작성 \(저장\)를 디스크 정보입니다.|  
|[IDebugPortSupplierDescription2](../../../extensibility/debugger/reference/idebugportsupplierdescription2.md)|PS|수 있도록는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 안에 텍스트를 표시 하는 UI는  **전송 정보** 섹션에는  **프로세스에 연결** 대화 상자.|  
|[IDebugWindowsComputerPort2](../../../extensibility/debugger/reference/idebugwindowscomputerport2.md)|VS|대상 컴퓨터에 대 한 정보를 쿼리할 수 있습니다.|  
|[IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)|PS VS|열거형을 통해 포트 집합을 나타냅니다.|  
|[IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)|VS|포트 공급자 집합에는 열거형을 나타냅니다.|  
  
##  <a name="Processes"></a> 프로세스  
 이러한 인터페이스 프로세스를 하나 이상의 프로그램을 포함 하는 단일 실행 파일을 나타냅니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)|PS, DE|컴퓨터에서 실행 중인 프로세스를 나타냅니다.|  
|[IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)|PS, DE|적극적으로 지 원하는 프로세스를 나타내는 디버깅 \(계속 진행 단계를 대체 하는 데, 한 메서드를 실행의 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 인터페이스\)입니다.|  
|[IDebugProcessCreateEvent2](../../../extensibility/debugger/reference/idebugprocesscreateevent2.md)|DE, PS|프로세스를 만들 때 DE 나 포트에서 보낸.|  
|[IDebugProcessDestroyEvent2](../../../extensibility/debugger/reference/idebugprocessdestroyevent2.md)|DE, PS|프로세스 소멸 될 때 DE 나 포트에서 보낸.|  
|[IDebugProcessEx2](../../../extensibility/debugger/reference/idebugprocessex2.md)|PS|연결 되어 있는 세션을 추적 해야 하는 프로세스를 나타냅니다.|  
|[IEnumDebugProcesses2](../../../extensibility/debugger/reference/ienumdebugprocesses2.md)|PS|열거형을 프로세스를 포트 집합을 나타냅니다.|  
  
##  <a name="Programs"></a> 프로그램  
 이러한 인터페이스 프로그램을 실행의 실제 실행 파일 또는 모듈 수와 일치 하지 않는 논리 단위를 나타냅니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)|DE|나타내는 있는 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 동시에 디버깅 중인 다른 프로그램과 동시에 적용 하.|  
|[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)|DE, PS|실행의 논리 단위를 나타냅니다.|  
|[IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)|DE, PS|프로그램을 만들 때 DE 나 포트에서 보낸.|  
|[IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)|DE, PS|프로그램이 제거 될 때 DE 나 포트에서 보낸.|  
|[IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)|DE, PS|나타내는 있는 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 를 처리할 수 있습니다 여러 디버깅 엔진에서.|  
|[IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)|PS|나타내는 있는 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 는 연결 되어 있는 세션을 추적할 수 있어야 합니다.|  
|[IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)|DE, PS|나타내는 있는 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 에서 실행 되는 프로세스에 대 한 정보를 반환할 수 있습니다.|  
|[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)|DE, PS|디버깅할 수 있는 프로그램을 나타냅니다.|  
|[IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)|DE, PS|프로그램 노드가 연결 된 프로그램에 연결 하려고 수 있습니다.|  
|[IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)|DE|SDM DE는 DE에서 제어 하는 프로그램에 대 한 쿼리 하는 방법을 제공 합니다.|  
|[IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)|VS|프로그램을 디버깅 하 고 표시 하는 SDM을 등록 하 여 Des가 사용 됩니다.|  
|[IDebugProviderProgramNode2](../../../extensibility/debugger/reference/idebugproviderprogramnode2.md)|DE, PS|나타내는 있는 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 는 수 마샬링할 인터페이스 스레드 또는 프로세스 경계를 넘어.|  
|[IEnumDebugPrograms2](../../../extensibility/debugger/reference/ienumdebugprograms2.md)|DE, PS|프로그램의 일련의 열거형을 나타냅니다.|  
  
##  <a name="Properties"></a> 속성  
 이러한 인터페이스 속성을, 식 계산의 결과 일반적으로 특정 컨텍스트와 연관 된 값을 나타냅니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugCustomViewer](../../../extensibility/debugger/reference/idebugcustomviewer.md)|EE|나타내는 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 의 값을 사용자 지정 방식으로 표시할 수 있습니다.|  
|[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)|DE|값을을 스택 프레임, 문서 또는 식 계산의 결과 나타냅니다.|  
|[IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)|DE|나타내는 있는 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 는 임의의 문자열을 지원 합니다.|  
|[IDebugPropertyCreateEvent2](../../../extensibility/debugger/reference/idebugpropertycreateevent2.md)|DE|때 새 속성이 DE에 의해 보낸 \(표시 되는 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 인터페이스\) 만들었습니다.|  
|[IDebugPropertyDestroyEvent2](../../../extensibility/debugger/reference/idebugpropertydestroyevent2.md)|DE|속성 제거 될 때 DE로 전송 합니다.|  
|[IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)|DE|특정 스택 프레임 밖에 존재 하는 속성에 대 한 참조를 나타냅니다.|  
|[IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)|DE|집합에는 열거형을 나타냅니다 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 변수, 레지스터, 매개 변수 및 식에 설명 하는 구조입니다.|  
|[IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)|DE|집합에는 열거형을 나타냅니다 [DEBUG\_REFERENCE\_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) 구조체입니다.|  
  
##  <a name="StackFrames"></a> 스택 프레임  
 이러한 인터페이스 컨텍스트 스택 프레임을 나타내는에서 중단점 또는 예외를 발생 했습니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)|DE|컨텍스트를 나타내는에서 중단점 또는 예외를 발생 했습니다.|  
|[IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)|DE|나타내는 있는 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) 를 처리할 수 있는 예외를 가로챌.|  
|[IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)|DE|열거형을 통해 집합을 나타내는 [CODE\_PATH](../../../extensibility/debugger/reference/code-path.md) 함수를 지정 하는 구조에서 특정 스택 프레임을 도달 하는 데 사용 되는 시퀀스를 호출 합니다.|  
|[IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)|DE|집합에는 열거형을 나타냅니다 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 스택 프레임에 설명 하는 구조입니다.|  
  
##  <a name="Threads"></a> 스레드  
 이러한 인터페이스 스레드 및 해당 관련 된 이벤트를 나타냅니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)|DE|실행 스레드를를 나타냅니다.|  
|[IDebugThreadCreateEvent2](../../../extensibility/debugger/reference/idebugthreadcreateevent2.md)|DE|스레드를 만들 때 DE로 전송 합니다.|  
|[IDebugThreadDestroyEvent2](../../../extensibility/debugger/reference/idebugthreaddestroyevent2.md)|DE|스레드가 소멸 될 때 DE로 전송 합니다.|  
|[IDebugThreadNameChangedEvent2](../../../extensibility/debugger/reference/idebugthreadnamechangedevent2.md)|DE|스레드 이름이 변경 되 면 DE로 전송 합니다.|  
|[IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)|DE|열거를 스레드 집합을 나타냅니다.|  
  
##  <a name="TypeVisualizers"></a> 형식 시각화 도우미  
 이러한 인터페이스에 대 한 시각화 유형을 지원합니다.  이러한 인터페이스는 식 계산기가 일반적으로 구현 됩니다.  
  
|Interface|관계형 데이터베이스|설명|  
|---------------|----------------|--------|  
|[IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)|EE|형식을 시각화 도우미를 표시 하려면 바이트 배열을 나타냅니다.|  
|[IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)|EE|형식을 시각화 도우미에 전달 해야 하는 데이터에 액세스 하기 위한 메서드를 제공 합니다.|  
|[IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md)|EE|액세스를 제공 하는 속성을 나타내는 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) 구현 합니다.|  
  
## 참고 항목  
 [API 참조](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)   
 [사용자 지정 디버그 엔진 만들기](../../../extensibility/debugger/creating-a-custom-debug-engine.md)