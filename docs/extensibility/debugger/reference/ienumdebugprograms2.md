---
title: "IEnumDebugPrograms2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugPrograms2"
helpviewer_keywords: 
  - "IEnumDebugPrograms2"
ms.assetid: 7fbb8fb7-db64-4546-a364-dc668430c8af
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugPrograms2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 현재 디버그 세션에서 실행 중인 프로그램을 열거 합니다.  
  
## 구문  
  
```  
IEnumDebugPrograms2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) DE에서 디버깅 중인 프로그램의 목록을 제공 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 Visual Studio [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) 이 인터페이스를 가져올 수 있습니다.  [EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md)Visual Studio 사용 되지 않습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IEnumDebugPrograms2`.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md)|지정 된 수의 프로그램에서 열거 시퀀스를 검색합니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugprograms2-skip.md)|지정 된 수의 프로그램에서 열거 시퀀스를 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugprograms2-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugprograms2-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugprograms2-getcount.md)|많은 프로그램에서 열거자를 가져옵니다.|  
  
## 설명  
 Visual Studio이 인터페이스를 사용합니다.  
  
-   채우기는  **모듈** 창 \(호출 하 여 [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) 다음 호출 [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) 각 프로그램에서\).  
  
-   채우기는  **프로세스에 연결** 목록 \(를 호출 하 여 `IDebugProcess2::EnumPrograms` 다음 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 각 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 인터페이스를 얻을 수 있는 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md) 인터페이스\).  
  
-   각 프로그램의 프로세스에서를 디버깅할 수 있습니다 DEs 목록 생성 \(를 사용 하 여 [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md)\).  
  
-   각 프로그램을 편집 하며 계속할 \(ENC\) 업데이트 적용 \(Idebugprocess2::enumprograms를 호출 하 고 호출 하 고 [GetENCUpdate](../../../extensibility/debugger/reference/idebugprogram2-getencupdate.md)\).  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md)   
 [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)