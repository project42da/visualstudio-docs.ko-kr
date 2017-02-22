---
title: "IEnumDebugCodeContexts2 | Microsoft Docs"
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
  - "IEnumDebugCodeContexts2"
helpviewer_keywords: 
  - "IEnumDebugCodeContexts2"
ms.assetid: 72915146-215f-4c99-a034-131b2b474e0e
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugCodeContexts2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버그 세션으로 특정 프로그램이 나 문서와 관련 된 코드 컨텍스트가 열거 합니다.  
  
## 구문  
  
```  
IEnumDebugCodeContexts2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 프로그램에서 텍스트를 특정 위치에 대 한 코드 컨텍스트의 목록을 코드 컨텍스트의 컨텍스트 특정 문서에 대 한 목록을 나타내는이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md) 프로그램의 원본 문서에서 특정 텍스트 위치에 대 한 코드 컨텍스트의 목록을 표시 합니다.이 인터페이스를 가져올 수 있습니다.  
  
 호출 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md) 모든 코드 컨텍스트 특정 원본 문서의 목록을 나타내는이 인터페이스를 가져올 수 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IEnumDebugCodeContexts2`.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-next.md)|열거 시퀀스에서 코드 컨텍스트에 지정 된 시간을 검색합니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-skip.md)|코드 컨텍스트 열거 시퀀스에서 지정 된 수를 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-getcount.md)|코드 컨텍스트 수를의 열거자를 가져옵니다.|  
  
## 설명  
 호출 Visual Studio [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md) 코드 컨텍스트 목록을 채우려면 사용자 시점에서 선택할 수 있습니다 다음 문을 설정 하거나 소스 파일의 디스어셈블리를 표시 합니다.  예를 들어, c \+ \+ 스타일 서식 파일의 인스턴스가 여러 개 있으면 여러 코드 컨텍스트에서 발생할 수 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)   
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)