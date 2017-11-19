---
title: IDebugProgramPublisher2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramPublisher2
helpviewer_keywords: IDebugProgramPublisher2 interface
ms.assetid: b1d17f63-7146-4076-a588-034cfc6858b9
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 287864e9e8cba0a32887122dc79f1008e403b667
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogrampublisher2"></a>IDebugProgramPublisher2
이 인터페이스에는 디버그 엔진 (DE) 이나 디버깅에 대 한 프로그램을 등록 하려면 사용자 지정 포트 공급자 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugProgramPublisher2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 Visual Studio는 여러 프로세스에서 디버깅을 위해 볼 수 있도록 설정 하려면 디버깅 중인 프로그램을 등록 하려면이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 COM의 호출 `CoCreateInstance` 작동 `CLSID_ProgramPublisher` 얻으려고이 인터페이스 (예제 참조). DE 또는 사용자 지정 포트 공급자 디버깅 중인 프로그램을 나타내는 프로그램 노드를 등록 하려면이 인터페이스를 사용 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 이 인터페이스는 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md)|프로그램 노드를 사용할 수 있게 DEs 및 세션 디버그 관리자 (SDM).|  
|[UnpublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogramnode.md)|더 이상 사용할 수 있도록 프로그램 노드를 제거 합니다.|  
|[PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md)|에 게는 프로그램 제공 DEs 및은 SDM 합니다.|  
|[UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)|더 이상 사용할 수 있도록 프로그램을 제거 합니다.|  
|[SetDebuggerPresent](../../../extensibility/debugger/reference/idebugprogrampublisher2-setdebuggerpresent.md)|디버거가 있는지를 나타내는 플래그를 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스를 사용 하면 프로그램 및 프로그램 노드에 사용할 수 있는 (즉, "게시") DEs 및 세션 디버그 관리자 (SDM)에서 사용 하도록 합니다. 게시 된 프로그램 및 프로그램 노드에 액세스 하려면 사용 하 여는 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md) 인터페이스입니다. 이것이 Visual Studio 프로그램이 디버깅 되 고 인식할 수 있는 유일한 방법입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="example"></a>예제  
 이 예제 프로그램 게시자를 인스턴스화하고 프로그램 노드를 등록 하는 방법을 보여 줍니다. 이 자습서에서 가져온 것 [프로그램 노드 게시](http://msdn.microsoft.com/en-us/d0100e02-4e2b-4e72-9e90-f7bc11777bae)합니다.  
  
```cpp  
// This is how m_srpProgramPublisher is defined in the class definition:  
// CComPtr<IDebugProgramPublisher2> m_srpProgramPublisher.  
  
void CProgram::Start(IDebugEngine2 * pEngine)  
{  
    m_spEngine = pEngine;  
  
    HRESULT hr = m_srpProgramPublisher.CoCreateInstance(CLSID_ProgramPublisher);  
    if ( FAILED(hr) )  
    {  
        ATLTRACE("Failed to create the program publisher: 0x%x.", hr);  
        return;  
    }  
  
    // Register ourselves with the program publisher. Note that  
    // CProgram implements the IDebgProgramNode2 interface, hence  
    // the static cast on "this".  
    hr = m_srpProgramPublisher->PublishProgramNode(  
        static_cast<IDebugProgramNode2*>(this));  
    if ( FAILED(hr) )  
    {  
        ATLTRACE("Failed to publish the program node: 0x%x.", hr);  
        m_srpProgramPublisher.Release();  
        return;  
    }  
  
    ATLTRACE("Added program node.\n");  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)