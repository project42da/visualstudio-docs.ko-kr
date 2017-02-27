---
title: "IEnumDebugModules2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugModules2"
helpviewer_keywords: 
  - "IEnumDebugModules2"
ms.assetid: 4fe28074-a960-41ad-b74d-b57f04c0c0ad
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IEnumDebugModules2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 모듈의 목록을 열거합니다.  
  
## 구문  
  
```  
IEnumDebugModules2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 프로그램을 로드 한 모듈의 목록을 표시 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 Visual Studio [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) 이 인터페이스를 가져올 수 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IEnumDebugModules2`.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md)|지정한 수 만큼 열거 시퀀스에서 모듈을 검색합니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugmodules2-skip.md)|지정한 수 만큼 열거 시퀀스에서 모듈을 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugmodules2-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugmodules2-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugmodules2-getcount.md)|모듈의 수를 가져옵니다.|  
  
## 설명  
 Visual Studio이 인터페이스를 사용 하 여 기본적으로 업데이트는  **모듈** 창입니다.  
  
 Visual Studio 디버깅 하기 위해 프로그램 논리 따라서 모듈 경계 교차 수 있습니다 코드 지침입니다 단일 모듈 목록 필요 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 인터페이스입니다.  일반적으로 목록에서 첫 번째 모듈 관련된 프로그램에 대 한 초기 진입점이 포함 됩니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md)