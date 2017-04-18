---
title: IDebugDocumentTextEvents2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugDocumentTextEvents2
helpviewer_keywords:
- IDebugDocumentTextEvents2 interface
ms.assetid: a10cbb6b-11a8-4056-b42a-2ecebf0e690d
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: 242c15cc456c3a27ba7b7da45a11031b026c02d3
ms.lasthandoff: 04/05/2017

---
# <a name="idebugdocumenttextevents2"></a>IDebugDocumentTextEvents2
이 인터페이스는 Visual Studio 디버그 엔진에서 제공 하는 소스 문서에 변경 내용에 대해 알리기 위해 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugDocumentTextEvents2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE 지원 소스 코드를 변경 하기 위해이 인터페이스를 구현 합니다. 이 인터페이스를 구현 하는 같은 개체에 대해 일반적으로 구현 됩니다는 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]에 대 한 호출을 통해이 인터페이스를 가져옵니다는 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint.Advise%2A>메서드.</xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint.Advise%2A> <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint>인터페이스에 대 한 호출에서 가져온는 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer.EnumConnectionPoints%2A>메서드.</xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer.EnumConnectionPoints%2A> </xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer>인터페이스를 호출 하 여 가져온는 [QueryInterface](/cpp/atl/queryinterface) 에서 메서드는 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) 인터페이스.</xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer>  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugDocumentTextEvents2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[onDestroy](../../../extensibility/debugger/reference/idebugdocumenttextevents2-ondestroy.md)|전체 문서가 제거 된 것을 나타냅니다.|  
|[onInsertText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-oninserttext.md)|문서에 삽입 된 텍스트 디버그 패키지에 알립니다.|  
|[onRemoveText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onremovetext.md)|텍스트 문서에서 제거 된 것 디버그 패키지에 알립니다.|  
|[onReplaceText](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onreplacetext.md)|문서에 텍스트를 교체한 디버그 패키지에 알립니다.|  
|[onUpdateTextAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatetextattributes.md)|텍스트 특성 문서에서 업데이트 되었습니다 디버그 패키지에 알립니다.|  
|[onUpdateDocumentAttributes](../../../extensibility/debugger/reference/idebugdocumenttextevents2-onupdatedocumentattributes.md)|문서 속성의 업데이트 이벤트의 수신기에 알립니다.|  
  
## <a name="remarks"></a>설명  
 자신의 문서를 제공 하는 디버그 엔진 활용 하기 위해 것만 `IDebugDocumentTextEvent2` 인터페이스입니다. 이러한 예는 스크립팅 디버그 엔진 것입니다. 스크립트를 해석 하는 과정에서 새 소스 코드 생성할 수 있습니다 모든 디스크 파일에 제공 되지 않았고는 DE 에게만 알려지므로 호출자입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)   
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)
