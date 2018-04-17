---
title: '방법: 개체 관리자는 라이브러리를 등록 합니다. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- libraries, registering with object manager
- IVsLibrary2 interface, registering library with object manager
- IVsSimpleLibrary2 interface, registering library with object manager
- IVsObjectManager2 interface, registering library with object manager
- libraries, symbol-browsing tools
ms.assetid: f124dd05-cb0f-44ad-bb2a-7c0b34ef4038
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 30bf2775c358b107fe299f0d60bc00a2030465e4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-register-a-library-with-the-object-manager"></a>방법: 개체 관리자는 라이브러리를 등록 합니다.
와 같은 도구 기호 검색 **클래스 뷰**, **개체 브라우저**, **호출 브라우저** 및 **기호 찾기 결과**를 볼 수 있도록 외부 구성 요소 또는 프로젝트의 기호입니다. 기호는 네임 스페이스, 클래스, 인터페이스, 메서드 및 다른 언어 요소를 포함 합니다. 라이브러리 이러한 기호를 추적 하 고 노출 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용 하 여 데이터를 사용 하 여 도구를 채울 개체 관리자입니다.  
  
 사용 가능한 모든 라이브러리 개체 관리자는 추적입니다. 각 라이브러리 개체 관리자 기호 검색 도구에 대 한 기호를 제공 하기 전에 등록 해야 합니다.  
  
 일반적으로 VSPackage를 로드 하는 경우 라이브러리를 등록 합니다. 그러나 필요에 따라 나중에 그를 수행할 수 있습니다. VSPackage가 종료 될 때 해당 라이브러리를 등록 취소 하십시오.  
  
 라이브러리를 등록 하려면는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterLibrary%2A> 메서드. 관리 코드 라이브러리의 경우에 사용 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> 메서드.  
  
 라이브러리의 등록을 취소 하려면 사용 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.UnregisterLibrary%2A> 메서드.  
  
 개체 관리자에 대 한 참조를 가져오려면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2>, 전달 된 <xref:Microsoft.VisualStudio.Shell.Interop.SVsObjectManager> 서비스 ID를 `GetService` 메서드.  
  
## <a name="registering-and-unregistering-a-library-with-the-object-manager"></a>등록 및 라이브러리 개체 관리자를 등록 취소  
  
#### <a name="to-register-a-library-with-the-object-manager"></a>개체 관리자와 라이브러리를 등록 하려면  
  
1.  라이브러리를 만듭니다.  
  
    ```vb  
    Private m_CallBrowserLibrary As CallBrowser.Library = Nothing  
    Private m_nLibraryCookie As UInteger = 0  
    ' Create Library.  
    m_CallBrowserLibrary = New CallBrowser.Library()  
    ```  
  
    ```csharp  
    private CallBrowser.Library m_CallBrowserLibrary = null;  
    private uint m_nLibraryCookie = 0;  
    // Create Library.  
    m_CallBrowserLibrary = new CallBrowser.Library();  
  
    ```  
  
2.  개체에 대 한 참조는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2> 입력 하 고 호출에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.RegisterSimpleLibrary%2A> 메서드.  
  
    ```vb  
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
  
    ```csharp  
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
  
#### <a name="to-unregister-a-library-with-the-object-manager"></a>개체 관리자와 라이브러리 등록을 취소 하려면  
  
1.  개체에 대 한 참조는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2> 입력 하 고 호출에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager2.UnregisterLibrary%2A> 메서드.  
  
    ```vb  
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
  
    ```csharp  
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
  
## <a name="see-also"></a>참고 항목  
 [레거시 언어 서비스 확장성](../../extensibility/internals/legacy-language-service-extensibility.md)   
 [기호 검색 도구를 지원합니다.](../../extensibility/internals/supporting-symbol-browsing-tools.md)   
 [방법: 라이브러리에서 제공하는 기호 목록을 개체 관리자에 노출](../../extensibility/internals/how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager.md)