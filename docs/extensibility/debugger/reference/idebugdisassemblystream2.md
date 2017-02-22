---
title: "IDebugDisassemblyStream2 | Microsoft Docs"
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
  - "IDebugDisassemblyStream2"
helpviewer_keywords: 
  - "IDebugDisassemblyStream2 인터페이스"
ms.assetid: b03cab0c-3f0b-4cc6-88dc-acb3b48c567a
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDisassemblyStream2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 명령 스트림을 나타냅니다.  
  
## 구문  
  
```  
IDebugDisassemblyStream2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 프로그램의 코드를 디스어셈블리를 지원 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 하 여 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md) 메서드는이 인터페이스를 반환 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugDisassemblyStream2`.  
  
|메서드|설명|  
|---------|--------|  
|[읽기](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)|디스어셈블리 스트림 내의 현재 위치에서 시작 하는 지침을 읽습니다.|  
|[검색](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)|디스어셈블리 스트림에 지정된 된 명령에 지정 된 위치를 기준으로 수 읽기 포인터를 이동합니다.|  
|[GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)|특정 코드 컨텍스트에 대해 코드 위치 식별자를 반환합니다.|  
|[GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)|지정 된 코드 위치 식별자에 해당 하는 코드 컨텍스트 개체를 반환 합니다.|  
|[GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md)|코드의 현재 위치를 나타내는 코드 위치 식별자를 반환 합니다.|  
|[GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md)|이 분해 스트림과 연결 된 원본 문서를 가져옵니다.|  
|[GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)|이 분해 stream의 범위를 가져옵니다.|  
|[GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md)|이 분해 스트림의 크기를 가져옵니다.|  
  
## 설명  
 전체 주소 공간 또는 방금 함수나 모듈은 공간 내에서 나타내는 디스어셈블리 스트림을 만들 수 있습니다.  각 명령으로 표시 되는 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) 구조를 호출 하 여 반환 되는 [읽기](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) 메서드.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)