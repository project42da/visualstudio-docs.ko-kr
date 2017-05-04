---
title: "IActiveScript | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScript 인터페이스"
ms.assetid: d8acee11-7f0d-4999-b97a-66774af16f71
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScript
스크립팅 엔진을 초기화 하는 데 필요한 메서드를 제공 합니다.  스크립팅 엔진 구현 해야는 `IActiveScript` 인터페이스.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IActiveScript::SetScriptSite](../../winscript/reference/iactivescript-setscriptsite.md)|스크립팅 엔진의 알립니다의 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 호스트에서 제공 하는 사이트.|  
|[IActiveScript::GetScriptSite](../../winscript/reference/iactivescript-getscriptsite.md)|Windows 스크립트 엔진에 관련 된 사이트 개체를 검색 합니다.|  
|[IActiveScript::SetScriptState](../../winscript/reference/iactivescript-setscriptstate.md)|스크립팅 엔진이 지정 된 상태에 배치 됩니다.|  
|[IActiveScript::GetScriptState](../../winscript/reference/iactivescript-getscriptstate.md)|스크립팅 엔진의 현재 상태를 검색합니다.|  
|[IActiveScript::Close](../../winscript/reference/iactivescript-close.md)|스크립팅 엔진에서 현재 로드 된 스크립트를 중단 하 고 해당 상태가 손실가 닫힌된 상태에 따라서 입력 하는 다른 개체에 인터페이스 포인터를 해제 하면 됩니다.|  
|[IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md)|루트 수준 항목의 이름을 스크립트 엔진의 네임 스페이스를 추가합니다.|  
|[IActiveScript::AddTypeLib](../../winscript/reference/iactivescript-addtypelib.md)|형식 라이브러리의 네임 스페이스를 스크립트에 추가합니다.|  
|[IActiveScript::GetScriptDispatch](../../winscript/reference/iactivescript-getscriptdispatch.md)|검색은 `IDispatch` 인터페이스에 대 한 스크립트를 실행 합니다.|  
|[IActiveScript::GetCurrentScriptThreadID](../../winscript/reference/iactivescript-getcurrentscriptthreadid.md)|현재 실행 중인 스레드는 스크립팅 엔진 정의 식별자를 검색합니다.|  
|[IActiveScript::GetScriptThreadID](../../winscript/reference/iactivescript-getscriptthreadid.md)|지정 된 Microsoft Win32 스레드와 연관 된 스레드는 스크립팅 엔진 정의 식별자를 검색 합니다.|  
|[IActiveScript::GetScriptThreadState](../../winscript/reference/iactivescript-getscriptthreadstate.md)|스크립트 스레드의 현재 상태를 검색합니다.|  
|[IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)|실행 중인 스레드가 스크립트의 실행을 중단합니다.|  
|[IActiveScript::Clone](../../winscript/reference/iactivescript-clone.md)|현재 스레드에서 없는 사이트는 로드 된 스크립팅 엔진에 반환 현재 스크립팅 엔진 \(현재 실행 상태\), 빼기를 복제 합니다.|  
  
## 참고 항목  
 [Windows 스크립트 인터페이스 참조](../../winscript/reference/windows-script-interfaces-reference.md)