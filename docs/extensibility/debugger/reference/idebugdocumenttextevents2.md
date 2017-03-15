---
title: "IDebugDocumentTextEvents2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugDocumentTextEvents2"
helpviewer_keywords: 
  - "IDebugDocumentTextEvents2 인터페이스"
ms.assetid: a10cbb6b-11a8-4056-b42a-2ecebf0e690d
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# IDebugDocumentTextEvents2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버그 엔진에서 제공 하는 원본 문서의 변경 내용에 대 한 Visual Studio 알리는 데 사용 됩니다.  
  
## 구문  
  
```  
IDebugDocumentTextEvents2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE의 지원 소스 코드를 변경 하기 위해이 인터페이스를 구현 합니다.  이 인터페이스를 구현 하는 동일한 개체에서 일반적으로 구현 되는 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]이 인터페이스에 대 한 호출을 통해 얻습니다는 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint.Advise%2A> 메서드가 있습니다.  <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> 인터페이스에서 얻은를 호출 하 여 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer.EnumConnectionPoints%2A> 메서드.  <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> 인터페이스를 호출 하 여 얻은 [QueryInterface](/visual-cpp/atl/queryinterface) 방법에는 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) 인터페이스.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugDocumentTextEvents2`.  
  
|메서드|설명|  
|---------|--------|  
|[onDestroy](../../../extensibility/debugger/reference/idebugdocumenttextevents2-ondestroy.md)|문서 전체가 소멸 되었음을 나타냅니다.|  
|[onInsertText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-oninserttext.md)|텍스트를 문서에 삽입 한 디버그 패키지를 알립니다.|  
|[onRemoveText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onremovetext.md)|디버그 패키지 텍스트를 문서에서 제거 되었음을 알립니다.|  
|[onReplaceText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onreplacetext.md)|텍스트 문서에서 대체 되었습니다 디버그 패키지를 알립니다.|  
|[onUpdateTextAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatetextattributes.md)|문서에서 텍스트 특성 업데이트 된 디버그 패키지를 알립니다.|  
|[onUpdateDocumentAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatedocumentattributes.md)|문서 속성 업데이트 된 이벤트 수신기에 알립니다.|  
  
## 설명  
 에 자신의 문서를 제공 하는 디버깅 엔진을 활용 하는 `IDebugDocumentTextEvent2` 인터페이스입니다.  이러한 예는 디버그 스크립트를 수 있습니다.  스크립트를 해석 하 고 있는 소스 코드를 새 디스크의 모든 파일에 존재 하지 않습니다 하는 DE만 하 라고 생성할 수 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)   
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)