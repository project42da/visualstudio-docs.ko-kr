---
title: "방법: 파일 변경 알림 표시 안 함 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-파일 변경 알림 표시 안 함"
ms.assetid: 891c1eb4-f6d0-4073-8df0-2859dbd417ca
caps.latest.revision: 18
caps.handback.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: 파일 변경 알림 표시 안 함
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

텍스트 버퍼를 나타내는 실제 파일이 변경 될 때 메시지와 함께 대화 상자 표시  **는 다음 항목에 변경 내용을 저장 하 시겠습니까?** 이 이름으로 파일 변경 알림 이라고 합니다.  그러나 많은 변경 사항이 파일을 하는 경우이 대화 상자를 반복 해 서 표시 신속 하 게 성가신 될 수 있습니다.  
  
 다음 절차를 사용 하 여이 대화 상자를 프로그래밍 방식으로 해제할 수 있습니다.  다시이 작업을 수행 하면 파일 즉시 때마다 변경 내용을 저장 하 라는 메시지를 표시 하지 않고 로드할 수 있습니다.  
  
### 파일 변경 알림을 표시 하지 않으려면  
  
1.  호출을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.FindAndLockDocument%2A> 메서드는 텍스트 버퍼 개체를 열린 파일에 연결 된 확인 합니다.  
  
2.  직접는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 받아 무시 합니다 메모리에 파일 변경 사항을 모니터링 하는 개체는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl> 에서 인터페이스는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 개체 \(데이터 문서\) 및 구현 하 고는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl.IgnoreFileChanges%2A> 메서드를 사용는 `fIgnore` 매개 변수를 설정 `true`.  
  
3.  메서드를 호출는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 의 메모리를 업데이트 하기 위한 인터페이스 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 개체를 파일 변경 내용 \(예: 필드 구성 요소에 추가 되 면\).  
  
4.  디스크에 있는 파일의 변경 내용을 보류 중인 편집 내용이 진행 하 게 됩니다 고려 하지 않고 업데이트 합니다.  
  
     구하고 때 이러한 방식으로 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 개체에 대 한 파일 모니터링을 다시 시작 하려면 변경 알림, 텍스트 버퍼 메모리에 모든 보류 중인 편집 및 생성의 변경 내용을 반영 합니다.  디스크의 파일을 최신 사용자에 의해 생성 된 코드를 반영 하 고 이전에 사용자가 편집 하는 코드를 사용자가 변경 내용을 저장 합니다.  
  
5.  호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl.IgnoreFileChanges%2A> 알릴 수 있는 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> 개체에 대 한 파일 변경 알림을 설정 하 여 모니터링을 다시 시작 하는 `fIgnore` 매개 변수를 `false`.  
  
6.  다음 파일을 소스 코드 제어 \(SCC\)의 경우에서와 같이 몇 가지 변경 하는 경우 서식 파일 변경 서비스 파일 변경 알림이 일시적으로 중단 하려면 지시 해야 합니다.  
  
     예를 들어, 파일을 다시 작성 하 고 타임 스탬프를 변경 하는 경우 재작성 및 timestample 작업 각각 별도 파일이 변경 될 때 이벤트 개수에 따라 파일 변경 알림을 일시 중단 합니다.  대신 호출 해야 기본 파일 변경 알림을 사용 하도록 설정 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEx.IgnoreFile%2A> 메서드.  
  
## 예제  
 다음 파일 변경 알림을 표시 하는 방법을 보여 줍니다.  
  
```cpp#  
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
  
## 강력한 프로그래밍  
 다음 사례를 SCC의 경우에서와 같이 파일에 여러 변경 내용이 포함 되어 있는 경우 전체 파일 변경 알림을 파일 변경에 대 한 모니터링을 다시 시작 하려면 문서 데이터를 경고 하기 전에 다시 시작 하는 것이 중요 합니다.