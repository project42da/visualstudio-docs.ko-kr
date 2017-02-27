---
title: "IDebugActivateDocumentEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugActivateDocumentEvent2"
helpviewer_keywords: 
  - "IDebugActivateDocumentEvent2 인터페이스"
ms.assetid: 6f37edd7-a48c-4b41-b160-dff9be63a284
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugActivateDocumentEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\) 로드 되는 문서를 요청 하려면이 인터페이스를 사용 합니다.  
  
## 구문  
  
```  
IDebugActivateDocumentEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 소스 파일을 열 수 있어야 하는 경우는 DE이이 인터페이스를 구현 합니다.  이 인터페이스는 작업 또는 스크립트 인터프리터에 포함 된 디버그 엔진에만 구현 됩니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다 \(SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스\)입니다.  
  
## 호출자에 대 한 참고 사항  
 DE를 만들고 소스 파일을 열 경우이 이벤트 개체를 보냅니다.  이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 콜백 함수 디버깅 중인 프로그램에 연결 하는 경우 SDM가 제공 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugActivateDocumentEvent2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetDocument](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocument.md)|활성화 하 여 문서를 가져옵니다.|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugactivatedocumentevent2-getdocumentcontext.md)|문서 내에서 위치에 설명 하는 문서 컨텍스트를 가져옵니다.|  
  
## 설명  
 이 인터페이스를 사용 하는 일반적인 시나리오 스크립트 코드는 HTML 페이지를 구문 분석 오류가 발생 하는 경우 문서 구문 분석 오류와 함께 표시 될 수 있도록 스크립트 DE이이 인터페이스 SDM을 보내는 것입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)