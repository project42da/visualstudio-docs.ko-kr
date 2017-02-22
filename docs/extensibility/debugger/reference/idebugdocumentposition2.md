---
title: "IDebugDocumentPosition2 | Microsoft Docs"
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
  - "IDebugDocumentPosition2"
helpviewer_keywords: 
  - "IDebugDocumentPosition2 인터페이스"
ms.assetid: 0e838ced-12bb-4efc-b811-2b7c034b77b0
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDocumentPosition2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 추상 원본 파일 위치를 나타냅니다.  
  
## 구문  
  
```  
IDebugDocumentPosition2 : IUnknown  
```  
  
## 구현자 참고 사항  
 Visual Studio 일반적으로이 인터페이스를 구현합니다.  자체 소스 코드를 제공 해야 하는 경우 디버그 엔진 \(DE\)도이 인터페이스를 구현 합니다 \(시기는 DE 구현으로 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) 인터페이스\)입니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스에 대 한 인수로 전달 된 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md).  도의 일부로 제공 되는 [BP\_LOCATION](../../../extensibility/debugger/reference/bp-location.md) 공용 구조체 \(구체적으로 [BP\_LOCATION\_CODE\_FILE\_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md) 구조\)는 차례로의 일부입니다는 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 보류 중단점 만들 때 사용 되는 구조를.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugDocumentPosition2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetFileName](../../../extensibility/debugger/reference/idebugdocumentposition2-getfilename.md)|이 문서의 위치를 포함 하는 소스 파일의 파일 이름을 가져옵니다.|  
|[GetDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-getdocument.md)|포함 하는 문서를 가져옵니다.|  
|[IsPositionInDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-ispositionindocument.md)|지정 된 문서에서이 위치 포함 되는지 여부를 결정 합니다.|  
|[GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)|범위를 대 한이 문서의 위치를 가져옵니다.|  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [BP\_LOCATION\_CODE\_FILE\_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md)