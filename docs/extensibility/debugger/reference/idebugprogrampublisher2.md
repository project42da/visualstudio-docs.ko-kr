---
title: "IDebugProgramPublisher2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramPublisher2"
helpviewer_keywords: 
  - "IDebugProgramPublisher2 인터페이스"
ms.assetid: b1d17f63-7146-4076-a588-034cfc6858b9
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugProgramPublisher2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버그 엔진 \(DE\) 또는 사용자 지정 포트 공급자 디버깅 프로그램을 등록할 수 있습니다.  
  
## 구문  
  
```  
IDebugProgramPublisher2 : IUnknown  
```  
  
## 구현자 참고 사항  
 Visual Studio 보이게 여러 프로세스에서 디버깅 하려면 디버깅할 프로그램을 등록 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 COM의 호출 `CoCreateInstance` 기능 `CLSID_ProgramPublisher` 가져오도록이 인터페이스 \(예 참조\).  DE 또는 사용자 지정 포트 공급자 디버깅 중인 프로그램을 나타내는 노드를 프로그램에 등록 하려면이 인터페이스를 사용 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 방법이이 인터페이스를 구현합니다.  
  
|메서드|설명|  
|---------|--------|  
|[PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md)|프로그램 노드에서 사용할 수 있는 DEs 및 세션에 디버그 매니저를 \(SDM\) 있습니다.|  
|[UnpublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogramnode.md)|더 이상 사용할 수 있도록 프로그램 노드를 제거 합니다.|  
|[PublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogram.md)|Des와 SDM을에 사용할 수 있는 프로그램이 있습니다.|  
|[UnpublishProgram](../../../extensibility/debugger/reference/idebugprogrampublisher2-unpublishprogram.md)|더 이상 사용할 수 있도록 하는 프로그램을 제거 합니다.|  
|[SetDebuggerPresent](../../../extensibility/debugger/reference/idebugprogrampublisher2-setdebuggerpresent.md)|디버거 표시 되어 있는지 나타내는 플래그를 설정 합니다.|  
  
## 설명  
 프로그램 및 프로그램 노드의이 인터페이스를 사용할 수 있습니다 \(즉, "를 사용 하 여 DEs 및 세션 디버그 매니저 \(SDM\)에 대 한 게시"\).  게시 된 프로그램 및 프로그램 노드에 액세스할 수 있는 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md) 인터페이스입니다.  이 Visual Studio 프로그램이 디버깅 되 고 있는지 알아볼 수 있는 유일한 방법입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 예제  
 프로그램 게시자를 인스턴스화하고 프로그램이 노드를 등록 하는 방법을 보여 주는이 예제입니다.  이 자습서를 가져옵니다 [Publishing the Program Node](http://msdn.microsoft.com/ko-kr/d0100e02-4e2b-4e72-9e90-f7bc11777bae).  
  
```cpp#  
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
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)