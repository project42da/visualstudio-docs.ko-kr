---
title: "IDebugApplication 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugApplication 인터페이스"
ms.assetid: 5dfa941b-4cd9-46fa-a230-3f41df9ea205
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugApplication 인터페이스
원격으로 디버깅 방법을 사용할 언어 엔진 및 호스트에서 노출합니다.  
  
 `IRemoteDebugApplication`에서 상속되는 메서드 외에 `IDebugApplication` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugApplication::SetName](../../winscript/reference/idebugapplication-setname.md)|응용 프로그램 이름을 설정합니다.|  
|[IDebugApplication::StepOutComplete](../../winscript/reference/idebugapplication-stepoutcomplete.md)|프로세스 디버그 관리자 단일 단계 모드에서는 언어 엔진 약 호출자로 반환 됨을 알립니다.|  
|[IDebugApplication::DebugOutput](../../winscript/reference/idebugapplication-debugoutput.md)|주어진된 문자열 IDE 디버거를 통해 표시 됩니다.|  
|[IDebugApplication::StartDebugSession](../../winscript/reference/idebugapplication-startdebugsession.md)|기본 IDE 디버거를 시작 하 고 하나 이미 연결 되어 있는 경우이 응용 프로그램에 디버그 세션에 연결 합니다.|  
|[IDebugApplication::HandleBreakPoint](../../winscript/reference/idebugapplication-handlebreakpoint.md)|현재 스레드를 차단 하 고 IDE 디버거에서 중단점에 대 한 알림을 보냅니다.|  
|[IDebugApplication::Close](../../winscript/reference/idebugapplication-close.md)|이 응용 프로그램에 대 한 모든 참조를 해제 하 고 비활성 상태가 됩니다.|  
|[IDebugApplication::GetBreakFlags](../../winscript/reference/idebugapplication-getbreakflags.md)|응용 프로그램에 대 한 현재 중단 플래그를 반환합니다.|  
|[IDebugApplication::GetCurrentThread](../../winscript/reference/idebugapplication-getcurrentthread.md)|현재 실행 중인 스레드에 스레드를 반환 합니다.|  
|[IDebugApplication::CreateAsyncDebugOperation](../../winscript/reference/idebugapplication-createasyncdebugoperation.md)|주어진된 동기 디버그 작업 비동기 액세스를 제공합니다.|  
|[IDebugApplication::AddStackFrameSniffer](../../winscript/reference/idebugapplication-addstackframesniffer.md)|이 응용 프로그램에 스택 프레임 표시기 공급자를 추가합니다.|  
|[IDebugApplication::RemoveStackFrameSniffer](../../winscript/reference/idebugapplication-removestackframesniffer.md)|이 응용 프로그램에서 스택 프레임 표시기 공급자를 제거합니다.|  
|[IDebugApplication::QueryCurrentThreadIsDebuggerThread](../../winscript/reference/idebugapplication-querycurrentthreadisdebuggerthread.md)|디버거에서 스레드의 현재 실행 중인 스레드가 있는지 확인 합니다.|  
|[IDebugApplication::SynchronousCallInDebuggerThread](../../winscript/reference/idebugapplication-synchronouscallindebuggerthread.md)|호출자가 코드에 디버거 스레드가 실행 하는 메커니즘을 제공 합니다.|  
|[IDebugApplication::CreateApplicationNode](../../winscript/reference/idebugapplication-createapplicationnode.md)|문서를 특정 공급자와 관련 된 새 응용 프로그램 노드를 만듭니다.|  
|[IDebugApplication::FireDebuggerEvent](../../winscript/reference/idebugapplication-firedebuggerevent.md)|일반 이벤트는 디버거를 발생 시키는 `IApplicationDebugger` 인터페이스.|  
|[IDebugApplication::HandleRuntimeError](../../winscript/reference/idebugapplication-handleruntimeerror.md)|현재 스레드를 차단 하 고 IDE 디버거를 오류에 대 한 알림을 보냅니다.|  
|[IDebugApplication::FCanJitDebug](../../winscript/reference/idebugapplication-fcanjitdebug.md)|Just in time \(JIT\) 디버거 등록 되어 있는지 확인 합니다.|  
|[IDebugApplication::FIsAutoJitDebugEnabled](../../winscript/reference/idebugapplication-fisautojitdebugenabled.md)|JIT 디버거 자동 디버그 단순 호스트에 등록 된 경우 결정 합니다.|  
|[IDebugApplication::AddGlobalExpressionContextProvider](../../winscript/reference/idebugapplication-addglobalexpressioncontextprovider.md)|이 응용 프로그램에 전역 식 컨텍스트 공급자를 추가합니다.|  
|[IDebugApplication::RemoveGlobalExpressionContextProvider](../../winscript/reference/idebugapplication-removeglobalexpressioncontextprovider.md)|이 응용 프로그램에서 전역 식 컨텍스트 공급자를 제거합니다.|