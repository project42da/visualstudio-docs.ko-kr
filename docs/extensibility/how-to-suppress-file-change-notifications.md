---
title: "방법: 파일 변경 알림 표시 안 함 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - suppress file change notification
ms.assetid: 891c1eb4-f6d0-4073-8df0-2859dbd417ca
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 88f7d2bf3a3351999175425366cf421c3b5ce0b3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-suppress-file-change-notifications"></a>방법: 파일 변경 알림 표시 안 함
메시지와 함께 대화 상자는 표시 텍스트 버퍼를 나타내는 물리적 파일 변경 되었을 때 **다음 항목에 변경 내용을 저장 하 시겠습니까?** 이 파일 변경 알림을 라고 합니다. 하지만 많은 변경 하는 경우 파일을 되도록이 대화 상자를 반복 해 서 다시 표시 될 수 있습니다 신속 하 게 번거로울.  
  
 다음 절차를 사용 하 여이 대화 상자를 프로그래밍 방식으로 억제할 수 있습니다. 이 통해 다시 로드할 수 있습니다 파일을 즉시 될 때마다 변경 내용을 저장 하 라는 메시지 필요 없이 합니다.  
  
### <a name="to-suppress-file-change-notification"></a>파일 변경 알림을 표시 하지 않으려면  
  
1.  호출의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> 텍스트 버퍼 개체가 열려 있는 파일에 연관 된 확인할 수 있습니다.  
  
2.  직접는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 무시 하기 위해 메모리에을 모니터링 하는 파일 변경 내용을 가져와서 개체는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl> 에서 인터페이스는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> (문서 데이터) 개체를 한 다음는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl.IgnoreFileChanges%2A> 메서드는 `fIgnore` 매개 변수 로 설정 `true`합니다.  
  
3.  메서드를 호출할는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 인터페이스 메모리 내 업데이트를 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 파일 변경 (예: 필드 구성 요소에 추가 된 경우) 인 개체입니다.  
  
4.  보류 중인 편집 진행 중에서, 사용자가을 고려 하지 않고 변경 내용으로 디스크에 파일을 업데이트 합니다.  
  
     이러한 방식으로 보내면는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 파일에 대 한 모니터링을 다시 시작 하는 개체 변경 알림, 메모리에서 텍스트 버퍼를 다른 보류 중인 편집 내용이 뿐만 아니라 생성 변경 내용을 반영 합니다. 디스크의 파일을 사용자에 의해 생성 된 최신 코드 반영 되어 있으며 사용자 편집 코드에서 변경 내용을 사용자가 이전에 저장 된 합니다.  
  
5.  호출의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl.IgnoreFileChanges%2A> 알리기 위해 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 파일 변경 알림을 설정 하 여 모니터링을 다시 시작 하는 개체는 `fIgnore` 매개 변수를 `false`합니다.  
  
6.  소스 코드 제어 (SCC)의 경우 처럼 파일에 대 한 몇 가지 변경 하려는 경우 파일 변경 알림을 일시 중단 하도록 전역 파일 변경 서비스에 알려 줘야 합니다.  
  
     예를 들어 파일을 다시 작성 한 다음 타임 스탬프를 변경 하는 경우 다시 작성 및 timestample 작업은 각 계산할 별도 파일 변경 이벤트 파일 변경 알림의 일시 중지 해야 합니다. 대신 호출 해야 하는 기본 파일 변경 알림을 활성화는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEx.IgnoreFile%2A> 메서드.  
  
## <a name="example"></a>예제  
 다음 파일 변경 알림을 표시 하지 않는 방법을 보여 줍니다.  
  
```cpp  
//Misc. helper classes  
  
CSuspendFileChanges::CSuspendFileChanges(  
    /* [in] */ const CString& strMkDocument,   
    /* [in] */ BOOL fSuspendNow /* = TRUE */)   
:  
    m_strMkDocument(strMkDocument),  
    m_fFileChangeSuspended(FALSE)  
{  
    if(fSuspendNow)  
        Suspend();  
}  
CSuspendFileChanges::~CSuspendFileChanges()  
{  
    Resume();  
}  
void CSuspendFileChanges::Suspend()  
{  
    USES_CONVERSION;  
  
    // Prevent suspend from suspending more than once.  
    if(m_fFileChangeSuspended)  
        return;  
  
    IVsRunningDocumentTable* pRDT =   
      _VxModule.GetIVsRunningDocumentTable();  
    ASSERT(pRDT);  
    if (!pRDT)  
        return;  
  
    CComPtr<IUnknown> srpDocData;  
    VSCOOKIE vscookie = VSCOOKIE_NIL;  
    pRDT->FindAndLockDocument(RDT_NoLock, T2COLE(m_strMkDocument),    
      NULL, NULL, &srpDocData, &vscookie);  
    if ( (vscookie == VSCOOKIE_NIL) || !srpDocData)  
        return;  
    CComPtr<IVsFileChangeEx> srpIVsFileChangeEx;  
    HRESULT hr = _VxModule.QueryService(SID_SVsFileChangeEx,   
      IID_IVsFileChangeEx, (void **)&srpIVsFileChangeEx);  
    if (SUCCEEDED(hr) && srpIVsFileChangeEx)  
    {  
        m_fFileChangeSuspended = TRUE;  
        srpIVsFileChangeEx->IgnoreFile(NULL, m_strMkDocument, TRUE);   
        srpDocData->QueryInterface(IID_IVsDocDataFileChangeControl,   
          (void**)&m_srpIVsDocDataFileChangeControl);  
        if(m_srpIVsDocDataFileChangeControl)  
            m_srpIVsDocDataFileChangeControl->IgnoreFileChanges(TRUE);  
    }  
}  
void CSuspendFileChanges::Resume()  
{  
    if(!m_fFileChangeSuspended)  
        return;  
  
    CComPtr<IVsFileChangeEx> srpIVsFileChangeEx;  
    HRESULT hr = _VxModule.QueryService(SID_SVsFileChangeEx,   
      IID_IVsFileChangeEx, (void **)&srpIVsFileChangeEx);  
    if (SUCCEEDED(hr) && srpIVsFileChangeEx)  
  
    srpIVsFileChangeEx->IgnoreFile(NULL, m_strMkDocument, FALSE);   
    if(m_srpIVsDocDataFileChangeControl)  
        m_srpIVsDocDataFileChangeControl->IgnoreFileChanges(FALSE);  
    m_fFileChangeSuspended = FALSE;  
    m_srpIVsDocDataFileChangeControl.Release();  
}  
// Misc. helper classes  
```  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 케이스 SCC의 경우 처럼 파일에 여러 변경 내용을 포함 되는 경우 것이 중요 합니다 전역 파일 변경 알림 경고 문서 데이터 파일 변경에 대 한 모니터링을 다시 시작 하기 전에 다시 시작 합니다.