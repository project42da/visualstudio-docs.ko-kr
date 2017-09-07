---
title: "코드 조각 (레거시) 설치 목록 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- snippets, retrieving list
- code snippets, retrieving list
- GetSnippets method
ms.assetid: 7d142f8b-35b1-44c4-a13e-f89f6460c906
caps.latest.revision: 15
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
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 50d5343d98bba8df79628d9bfdfa838aea9e27d8
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation"></a>연습: 설치 된 코드 조각 (레거시 구현) 목록 가져오기
코드 조각으로 또는 (설치 된 코드 조각 중에서 선택할 수 있음)는 메뉴 명령을 사용 하 여 소스 버퍼에 삽입할 수 있는 코드의 일부는 조각 바로 가기를 IntelliSense 완성 목록에서 선택 합니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionManager.EnumerateExpansions%2A> 메서드는 특정 언어 GUID에 대 한 모든 코드 조각을 가져옵니다. 이러한 조각에 대 한 바로 가기 IntelliSense 완성 목록에 삽입할 수 있습니다.  
  
 참조 [레거시 언어 서비스의 코드 조각에 대 한 지원을](../../extensibility/internals/support-for-code-snippets-in-a-legacy-language-service.md) 코드 조각에는 관리 되는 패키지 프레임 워크 (MPF) 언어 서비스 구현에 대 한 세부 정보에 대 한 합니다.  
  
### <a name="to-retrieve-a-list-of-code-snippets"></a>코드 조각 목록을 검색 하려면  
  
1.  다음 코드에는 지정된 된 언어에 대 한 코드 조각 목록을 가져오는 방법을 보여 줍니다. 결과 배열에 저장 됩니다 <xref:Microsoft.VisualStudio.TextManager.Interop.VsExpansion> 구조입니다. 이 메서드는 정적 사용 <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> 가져올 메서드를는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager> 에서 인터페이스는 <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager> 서비스입니다. 그러나 VSPackage 및 호출에 지정 된 서비스 공급자도 사용할 수는 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A> 메서드.  
  
    ```csharp  
    using System;  
    using System.Collections;  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio.Package;  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.TextManager.Interop;  
  
    [Guid("00000000-0000-0000-0000-000000000000")] //create a new GUID for the language service  
    namespace TestLanguage  
    {  
        class TestLanguageService : LanguageService  
        {  
            private void GetSnippets(Guid languageGuid,  
                                     ref ArrayList expansionsList)  
            {  
                IVsTextManager textManager = (IVsTextManager)Package.GetGlobalService(typeof(SVsTextManager));  
                if (textManager != null)  
                {  
                    IVsTextManager2 textManager2 = (IVsTextManager2)textManager;  
                    if (textManager2 != null)  
                    {  
                        IVsExpansionManager expansionManager = null;  
                        textManager2.GetExpansionManager(out expansionManager);  
                        if (expansionManager != null)  
                        {  
                            // Tell the environment to fetch all of our snippets.  
                            IVsExpansionEnumeration expansionEnumerator = null;  
                            expansionManager.EnumerateExpansions(languageGuid,  
                            0,     // return all info  
                            null,    // return all types  
                            0,     // return all types  
                            1,     // include snippets without types  
                            0,     // do not include duplicates  
                            out expansionEnumerator);  
                            if (expansionEnumerator != null)  
                            {  
                                // Cache our expansions in a VsExpansion array   
                                uint count   = 0;  
                                uint fetched = 0;  
                                VsExpansion expansionInfo = new VsExpansion();  
                                IntPtr[] pExpansionInfo   = new IntPtr[1];  
  
                                // Allocate enough memory for one VSExpansion structure. This memory is filled in by the Next method.  
                                pExpansionInfo[0] = Marshal.AllocCoTaskMem(Marshal.SizeOf(expansionInfo));  
  
                                expansionEnumerator.GetCount(out count);  
                                for (uint i = 0; i < count; i++)  
                                {  
                                    expansionEnumerator.Next(1, pExpansionInfo, out fetched);  
                                    if (fetched > 0)  
                                    {  
                                        // Convert the returned blob of data into a structure that can be read in managed code.  
                                        expansionInfo = (VsExpansion)Marshal.PtrToStructure(pExpansionInfo[0], typeof(VsExpansion));  
  
                                        if (!String.IsNullOrEmpty(expansionInfo.shortcut))  
                                        {  
                                            expansionsList.Add(expansionInfo);  
                                        }  
                                    }  
                                }  
                                Marshal.FreeCoTaskMem(pExpansionInfo[0]);  
                            }  
                        }  
                    }  
                }  
            }  
        }  
    }  
    ```  
  
### <a name="to-call-the-getsnippets-method"></a>GetSnippets 메서드를 호출 하려면  
  
1.  다음 메서드를 호출 하는 방법을 보여 줍니다는 `GetSnippets` 메서드 구문 분석 작업의 완료 합니다. <xref:Microsoft.VisualStudio.Package.LanguageService.OnParseComplete%2A> 메서드가 구문 분석 작업 이유와 함께 시작 된 이후에 호출 <xref:Microsoft.VisualStudio.Package.ParseReason>합니다.  
  
> [!NOTE]
>  `expansionsList` 성능상의 이유로 캐시 listis 배열입니다. 언어 서비스를 중지 하 고 다시 로드 될 때까지 목록에 조각 변경 내용이 반영 되지 않습니다 (중지 및 다시 시작 하 여 예를 들어 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]).  
  
```csharp  
class TestLanguageService : LanguageService  
{  
    private ArrayList expansionsList;  
  
    public override void OnParseComplete(ParseRequest req)  
    {  
        if (this.expansionsList == null)  
        {  
            this.expansionsList = new ArrayList();  
            GetSnippets(this.GetLanguageServiceGuid(),  
                ref this.expansionsList);  
        }  
    }  
}  
```  
  
### <a name="to-use-the-snippet-information"></a>코드 조각 정보를 사용 하려면  
  
1.  다음 코드에서는에서 반환 된 코드 조각 정보를 사용 하 여 `GetSnippets` 메서드. `AddSnippets` 파서 코드 조각의 목록을 채우는 데 사용 되는 구문 분석 어떤 이유로 든에 대 한 응답에서 메서드를 호출 합니다. 이 수행할 전체 구문 분석을 처음으로 이루어졌습니다.  
  
     `AddDeclaration` 메서드는 나중에 완성 목록에 표시 되는 선언의 목록을 작성 합니다.  
  
     `TestDeclaration` 클래스 형식의 선언을 비롯 하 여 완성 목록에 표시 될 수 있는 모든 정보가 포함 되어 있습니다.  
  
    ```csharp  
    class TestAuthoringScope : AuthoringScope  
    {  
        public void AddDeclarations(TestDeclaration declaration)  
        {  
            if (m_declarations == null)  
                m_declarations = new List<TestDeclaration>();  
            m_declarations.Add(declaration);  
         }  
    }  
    class TestDeclaration   
    {  
        private string m_name;  
        private string m_description;  
        private string m_type;  
  
        public TestDeclaration(string name, string desc, string type)  
        {  
            m_name = name;  
            m_description = desc;  
            m_type = type;  
        }  
  
    class TestLanguageService : LanguageService  
    {  
        internal void AddSnippets(ref TestAuthoringScope scope)  
        {  
            if (this.expansionsList != null && this.expansionsList.Count > 0)  
            {  
                int count = this.expansionsList.Count;  
                for (int i = 0; i < count; i++)  
                {  
                    VsExpansion expansionInfo = (VsExpansion)this.expansionsList[i];  
                    scope.AddDeclaration(new TestDeclaration(expansionInfo.title,  
                         expansionInfo.description,  
                         "snippet"));  
                }  
            }  
        }  
    }  
  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [레거시 언어 서비스의 코드 조각 지원](../../extensibility/internals/support-for-code-snippets-in-a-legacy-language-service.md)
