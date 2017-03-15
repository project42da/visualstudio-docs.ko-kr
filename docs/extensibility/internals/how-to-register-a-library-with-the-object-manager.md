---
title: "방법: 개체 관리자와 함께 라이브러리를 등록 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "개체 관리자를 등록 하는 라이브러리"
  - "개체 관리자와 라이브러리를 등록 하는 IVsLibrary2 인터페이스"
  - "개체 관리자와 라이브러리를 등록 하는 IVsSimpleLibrary2 인터페이스"
  - "개체 관리자와 라이브러리를 등록 하는 IVsObjectManager2 인터페이스"
  - "라이브러리, 도구 기호 검색"
ms.assetid: f124dd05-cb0f-44ad-bb2a-7c0b34ef4038
caps.latest.revision: 26
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 26
---
# 방법: 개체 관리자와 함께 라이브러리를 등록 합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기호 검색 도구, 같은  **클래스 뷰**,  **개체 브라우저**,  **호출 브라우저** 및  **기호 찾기 결과**, 또는 외부 구성 요소를 프로젝트에서 기호를 볼 수 있습니다.  네임 스페이스, 클래스, 인터페이스, 메서드 및 기타 언어 요소 기호를 포함 합니다.  라이브러리가 이러한 기호를 추적 하 고 노출 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 도구는 데이터를 채우는 개체 관리자입니다.  
  
 개체 관리자는 라이브러리를 모두 사용할 수를 추적 합니다.  각 라이브러리는 개체 관리자에 기호를 기호 검색 도구를 제공 하기 전에 등록 해야 합니다.  
  
 일반적으로 VSPackage 로드 될 때 라이브러리를 등록 합니다.  그러나이 나중에 필요에 따라 수행할 수 있습니다.  있는 VSPackage 종료 될 때 라이브러리의 등록.  
  
 라이브러리를 등록할 수 있는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterLibrary%2A> 메서드.  경우 관리 코드 라이브러리를 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> 메서드.  
  
 사용 하는 라이브러리의 등록을 취소 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.UnregisterLibrary%2A> 메서드.  
  
 개체 관리자에 대 한 참조를 가져오려면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2>, 전달의 <xref:Microsoft.VisualStudio.Shell.Interop.SVsObjectManager> ID로 서비스를 `GetService` 메서드.  
  
## 등록 및 개체 관리자를 사용 하 여 라이브러리 등록 취소  
  
#### 라이브러리의 개체 관리자에 등록  
  
1.  라이브러리를 만들 수 있습니다.  
  
    ```vb#  
    Private m_CallBrowserLibrary As CallBrowser.Library = Nothing  
    Private m_nLibraryCookie As UInteger = 0  
    ' Create Library.  
    m_CallBrowserLibrary = New CallBrowser.Library()  
    ```  
  
    ```c#  
    private CallBrowser.Library m_CallBrowserLibrary = null;  
    private uint m_nLibraryCookie = 0;  
    // Create Library.  
    m_CallBrowserLibrary = new CallBrowser.Library();  
  
    ```  
  
2.  개체에 대 한 참조를 얻을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2> 를 입력 하 고 호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> 메서드.  
  
    ```vb#  
    Private Sub RegisterLibrary()  
        If m_nLibraryCookie <> 0 Then  
            Throw New Exception("Library already registered with Object Manager")  
        End If  
  
        ' Obtain a reference to IVsObjectManager2 type object.  
        Dim objManager As IVsObjectManager2 = TryCast(GetService(GetType(SVsObjectManager)), IVsObjectManager2)  
        If objManager Is Nothing Then  
            Throw New NullReferenceException("GetService failed for SVsObjectManager")  
        End If  
  
        Try  
            Dim hr As Integer = objManager.RegisterSimpleLibrary(m_CallBrowserLibrary, m_nLibraryCookie)  
            Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(hr)  
        Catch e As Exception  
            ' Code to handle any CLS-compliant exception.  
            Trace.WriteLine(e.Message)  
            Throw  
        End Try  
    End Sub  
    ```  
  
    ```c#  
    private void RegisterLibrary()  
    {  
        if (m_nLibraryCookie != 0)  
            throw new Exception("Library already registered with Object Manager");  
  
        // Obtain a reference to IVsObjectManager2 type object.  
        IVsObjectManager2 objManager =   
                          GetService(typeof(SVsObjectManager)) as IVsObjectManager2;  
        if (objManager == null)  
            throw new NullReferenceException("GetService failed for SVsObjectManager");  
  
        try  
        {  
            int hr =   
                objManager.RegisterSimpleLibrary(m_CallBrowserLibrary,   
                                                 out m_nLibraryCookie);  
                Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure(hr);  
        }  
        catch (Exception e)  
        {  
            // Code to handle any CLS-compliant exception.  
            Trace.WriteLine(e.Message);  
            throw;  
        }  
    }  
  
    ```  
  
#### 개체 관리자를 사용 하는 라이브러리의 등록을 취소 하려면  
  
1.  개체에 대 한 참조를 얻을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2> 를 입력 하 고 호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.UnregisterLibrary%2A> 메서드.  
  
    ```vb#  
    Private Sub UnregisterLibrary()  
        If m_nLibraryCookie <> 0 Then  
            ' Obtain a reference to IVsObjectManager2 type object.  
            Dim objManager As IVsObjectManager2 = TryCast(GetService(GetType(SVsObjectManager)), IVsObjectManager2)  
            If objManager Is Nothing Then  
                Throw New NullReferenceException("GetService failed for SVsObjectManager")  
            End If  
  
            Try  
                objManager.UnregisterLibrary(m_nLibraryCookie)  
            Catch e As Exception  
                ' Code to handle any CLS-compliant exception.  
                Trace.WriteLine(e.Message)  
                Throw  
            Finally  
                m_nLibraryCookie = 0  
            End Try  
        End If  
    End Sub  
    ```  
  
    ```c#  
    private void UnregisterLibrary()  
    {  
        if (m_nLibraryCookie != 0)  
        {  
            // Obtain a reference to IVsObjectManager2 type object.  
            IVsObjectManager2 objManager = GetService(typeof(SVsObjectManager)) as IVsObjectManager2;  
            if (objManager == null)  
                throw new NullReferenceException("GetService failed for SVsObjectManager");  
  
            try  
            {  
                objManager.UnregisterLibrary(m_nLibraryCookie);  
            }  
            catch (Exception e)  
            {  
                // Code to handle any CLS-compliant exception.  
                Trace.WriteLine(e.Message);  
                throw;  
            }  
            finally  
            {  
                m_nLibraryCookie = 0;  
            }  
        }  
    }  
  
    ```  
  
## 참고 항목  
 [레거시 언어 서비스 확장](../../extensibility/internals/legacy-language-service-extensibility.md)   
 [기호 검색 도구를 지원합니다.](../../extensibility/internals/supporting-symbol-browsing-tools.md)   
 [방법: 개체 관리자에는 라이브러리에서 제공 하는 기호 목록을 노출](../../extensibility/internals/how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)