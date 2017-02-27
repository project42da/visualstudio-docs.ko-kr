---
title: "IDebugDocumentContext2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugDocumentContext2"
helpviewer_keywords: 
  - "IDebugDocumentContext2"
ms.assetid: 2a446c71-8100-4c09-a1cc-fd446bd74030
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugDocumentContext2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 소스 파일이 문서의 위치를 나타냅니다.  
  
## 구문  
  
```  
IDebugDocumentContext2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 소스 코드 수준 디버깅에 대 한 지원의 일부로 서이 인터페이스를 구현합니다.  소스 코드 위치 외에이 인터페이스 컨텍스트를 비교 하 고 소스 코드 문서에서 탐색 하는 방법을 제공 합니다.  
  
## 호출자에 대 한 참고 사항  
 가장 일반적으로 방법에는 여러 가지 인터페이스는 [GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md) 및 [GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md) 인터페이스,이 인터페이스를 반환 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugDocumentContext2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetDocument](../../../extensibility/debugger/reference/idebugdocumentcontext2-getdocument.md)|이 문서의 컨텍스트에 포함 된 문서를 가져옵니다.|  
|[GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)|이 문서의 컨텍스트에 포함 된 문서를 표시할 수 있는 이름을 가져옵니다.|  
|[EnumCodeContexts](../../../extensibility/debugger/reference/idebugdocumentcontext2-enumcodecontexts.md)|이 문서 컨텍스트와 관련 된 모든 코드 컨텍스트 목록을 검색 합니다.|  
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugdocumentcontext2-getlanguageinfo.md)|이 문서 컨텍스트와 연관 된 언어를 가져옵니다.|  
|[GetStatementRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)|문서에는 파일 정보 보호 범위를 가져옵니다.|  
|[GetSourceRange](../../../extensibility/debugger/reference/idebugdocumentcontext2-getsourcerange.md)|파일 원본 범위를는 문서를 가져옵니다.|  
|[비교](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)|문서 컨텍스트를 지정 된 배열에이 문서 컨텍스트를 비교합니다.|  
|[검색](../../../extensibility/debugger/reference/idebugdocumentcontext2-seek.md)|문서의 컨텍스트에서 지정 된 문 또는 줄 수 만큼 이동합니다.|  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getdocumentcontext.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocumentcontext.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)   
 [GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)