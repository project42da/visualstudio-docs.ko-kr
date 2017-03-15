---
title: "개체 관리자에 제공 된 기호 목록을 노출 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IVsSimpleLibrary2 interface, lists of symbols
- IVsLibrary2 interface, lists of symbols
- symbols, call browser
- lists, symbols for the object manager
- symbols, exposing lists to the object manager
ms.assetid: 19757068-bdaa-4e7e-85d6-f8ce5026a859
caps.latest.revision: 25
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
ms.sourcegitcommit: d5bc147592bfc36247c35f23ac2885055d096af3
ms.openlocfilehash: 82fac3b8400229e97225d1e0c4f394752ff024e9
ms.lasthandoff: 02/22/2017

---
# <a name="how-to-expose-lists-of-symbols-provided-by-the-library-to-the-object-manager"></a>방법: 개체 관리자에는 라이브러리에서 제공 하는 기호 목록을 노출
기호 검색 도구 **클래스 뷰**, **개체 브라우저**, **호출 브라우저** 및 **기호 찾기 결과**에 새 데이터에 대 한 요청을 전달 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 개체 관리자입니다. 개체 관리자는 적절 한 라이브러리를 찾아서 새 기호 목록을 요청 합니다. 라이브러리 요청 된 데이터를 제공 하 여 응답에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 를 통해 개체 관리자는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2>인터페이스.</xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2> [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 의 메서드를 호출 하는 개체 관리자 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2>데이터를 가져오기 위해 인터페이스를 사용 하 여를 채우거 나 기호 검색 도구의 뷰를 업데이트 합니다.</xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2>  
  
 라이브러리는 호출 되는 도구, 노드가 확장 된 또는 보기를 새로 고칠 때 데이터에 대 한 요청을 발생할 수 있습니다. 기호 검색 도구를 처음으로 호출 되 면 개체 관리자는 최상위 목록을 제공 하기 위해 라이브러리를 요청 합니다. 사용자 목록 노드를 확장 하는 경우 라이브러리는 해당 노드 아래에 자식 목록을 제공 합니다. 모든 개체 관리자 조회 관심 있는 항목의 인덱스를 포함합니다. 새 목록을 표시 하려면 개체 관리자는 항목, 이름, 액세스 가능성, 및 기타 속성의 형식 목록에 있는 항목 수를 결정 해야 합니다.  
  
> [!NOTE]
>  다음 관리 되는 코드 예제에는 기호를 구현 하는 과정의 목록을 제공 하는 방법을 보여 줍니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2>인터페이스.</xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2> 개체 관리자는이 인터페이스의 메서드를 호출 하 고를 채우거 나 기호 검색 도구 업데이트 가져온된 데이터를 사용 합니다.  
>   
>  네이티브 코드 기호 공급자 구현에 대 한 사용은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectList2>인터페이스.</xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectList2>  
  
## <a name="providing-lists-of-symbols-to-the-object-manager"></a>기호 목록 개체 관리자에 제공  
  
#### <a name="to-provide-lists-of-symbols-to-the-object-manager"></a>에 제공 하기 위해 기호 목록 개체 관리자  
  
1.  구현 하 여 기호 목록에서 항목의 수를 가져오려면는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetItemCount%2A>메서드.</xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetItemCount%2A> 다음 예제에서는 개체 관리자 목록에서 항목의 수에 대 한 정보를 얻는 방법을 보여 줍니다.  
  
    ```vb#  
    Protected m_Methods As System.Collections.Generic.SortedList(Of String, Method) = New System.Collections.Generic.SortedList(Of String, Method)()  
  
    Public Function GetItemCount(ByRef pCount As UInteger) As Integer  
        pCount = CUInt(m_Methods.Count)  
        Return Microsoft.VisualStudio.VSConstants.S_OK  
    End Function  
    ```  
  
    ```c#  
    protected System.Collections.Generic.SortedList<string, Method> m_Methods = new System.Collections.Generic.SortedList<string, Method>();  
  
    public int GetItemCount(out uint pCount)  
    {  
        pCount = (uint)m_Methods.Count;  
        return Microsoft.VisualStudio.VSConstants.S_OK;  
    }  
  
    ```  
  
2.  구현 하 여 범주 및 특정된 목록 항목의 특성에 대 한 정보를 가져오기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetCategoryField2%2A>메서드.</xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetCategoryField2%2A> 항목 범주에 지정 된 <xref:Microsoft.VisualStudio.Shell.Interop.LIB_CATEGORY>열거형.</xref:Microsoft.VisualStudio.Shell.Interop.LIB_CATEGORY> 다음 예제에서는 개체 관리자는 지정 된 범주에 대 한 항목의 특성을 얻는 방법을 보여 줍니다.  
  
    ```vb#  
    Public Function GetCategoryField2(ByVal index As UInteger, ByVal Category As Integer, ByRef pfCatField As UInteger) As Integer  
        pfCatField = 0  
  
        Select Case CType(Category, LIB_CATEGORY)  
            Case LIB_CATEGORY.LC_MEMBERTYPE  
                pfCatField = CUInt(_LIBCAT_MEMBERTYPE.LCMT_METHOD)  
  
            Case LIB_CATEGORY.LC_MEMBERACCESS  
                Dim method As Method = m_Methods.Values(CInt(Fix(index)))  
  
                If method.IsPublic Then  
                    pfCatField = CUInt(_LIBCAT_MEMBERACCESS.LCMA_PUBLIC)  
                ElseIf method.IsPrivate Then  
                    pfCatField = CUInt(_LIBCAT_MEMBERACCESS.LCMA_PRIVATE)  
                ElseIf method.IsFamily Then  
                    pfCatField = CUInt(_LIBCAT_MEMBERACCESS.LCMA_PROTECTED)  
                ElseIf method.IsFamilyOrAssembly Then  
                    pfCatField = CUInt(_LIBCAT_MEMBERACCESS.LCMA_PROTECTED) Or CUInt(_LIBCAT_MEMBERACCESS.LCMA_PACKAGE)  
                Else  
                    ' Show everything else as internal.  
                    pfCatField = CUInt(_LIBCAT_MEMBERACCESS.LCMA_PACKAGE)  
                End If  
  
            Case LIB_CATEGORY.LC_VISIBILITY  
                pfCatField = CUInt(_LIBCAT_VISIBILITY.LCV_VISIBLE)  
  
            Case LIB_CATEGORY.LC_LISTTYPE  
                pfCatField = CUInt(_LIB_LISTTYPE.LLT_MEMBERS)  
  
            Case Else  
                Return Microsoft.VisualStudio.VSConstants.S_FALSE  
        End Select  
        Return Microsoft.VisualStudio.VSConstants.S_OK  
    End Function  
    ```  
  
    ```c#  
    public int GetCategoryField2(uint index, int Category, out uint pfCatField)  
    {  
        pfCatField = 0;  
  
        switch ((LIB_CATEGORY)Category)  
        {  
            case LIB_CATEGORY.LC_MEMBERTYPE:  
                pfCatField = (uint)_LIBCAT_MEMBERTYPE.LCMT_METHOD;  
                break;  
  
            case LIB_CATEGORY.LC_MEMBERACCESS:  
                {  
                    Method method = m_Methods.Values[(int)index];  
  
                    if (method.IsPublic)  
                    {  
                        pfCatField = (uint)_LIBCAT_MEMBERACCESS.LCMA_PUBLIC;  
                    }  
                    else if (method.IsPrivate)  
                    {  
                        pfCatField = (uint)_LIBCAT_MEMBERACCESS.LCMA_PRIVATE;  
                    }  
                    else if (method.IsFamily)  
                    {  
                        pfCatField = (uint)_LIBCAT_MEMBERACCESS.LCMA_PROTECTED;  
                    }  
                    else if (method.IsFamilyOrAssembly)  
                    {  
                        pfCatField = (uint)_LIBCAT_MEMBERACCESS.LCMA_PROTECTED |  
                                     (uint)_LIBCAT_MEMBERACCESS.LCMA_PACKAGE;  
                    }  
                    else  
                    {  
                        // Show everything else as internal.  
                        pfCatField = (uint)_LIBCAT_MEMBERACCESS.LCMA_PACKAGE;  
                    }  
                }  
                break;  
  
            case LIB_CATEGORY.LC_VISIBILITY:  
                pfCatField = (uint)_LIBCAT_VISIBILITY.LCV_VISIBLE;  
                break;  
  
            case LIB_CATEGORY.LC_LISTTYPE:  
                pfCatField = (uint)_LIB_LISTTYPE.LLT_MEMBERS;  
                break;  
  
            default:  
                return Microsoft.VisualStudio.VSConstants.S_FALSE;  
        }  
        return Microsoft.VisualStudio.VSConstants.S_OK;  
    }  
  
    ```  
  
3.  구현 하 여 지정 된 목록 항목의 텍스트 표현을 가져올는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetTextWithOwnership%2A>메서드.</xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetTextWithOwnership%2A> 다음 예제에서는 지정된 된 항목의 전체 이름을 가져오는 방법을 보여 줍니다.  
  
    ```vb#  
    Public Function GetTextWithOwnership(<System.Runtime.InteropServices.ComAliasNameAttribute("Microsoft.VisualStudio.OLE.Interop.ULONG")> ByVal index As UInteger, <System.Runtime.InteropServices.ComAliasNameAttribute("Microsoft.VisualStudio.Shell.Interop.VSTREETEXTOPTIONS")> ByVal tto As Microsoft.VisualStudio.Shell.Interop.VSTREETEXTOPTIONS, <System.Runtime.InteropServices.ComAliasNameAttribute("Microsoft.VisualStudio.OLE.Interop.WCHAR")> ByRef ppszText As String) As Integer  
        ppszText = m_Methods.Values(CInt(Fix(index))).FullName  
        Return Microsoft.VisualStudio.VSConstants.S_OK  
    End Function  
    ```  
  
    ```c#  
    public int GetTextWithOwnership([System.Runtime.InteropServices.ComAliasNameAttribute("Microsoft.VisualStudio.OLE.Interop.ULONG")] uint index, [System.Runtime.InteropServices.ComAliasNameAttribute("Microsoft.VisualStudio.Shell.Interop.VSTREETEXTOPTIONS")] Microsoft.VisualStudio.Shell.Interop.VSTREETEXTOPTIONS tto, [System.Runtime.InteropServices.ComAliasNameAttribute("Microsoft.VisualStudio.OLE.Interop.WCHAR")] out string ppszText)  
    {  
        ppszText = m_Methods.Values[(int)index].FullName;  
        return Microsoft.VisualStudio.VSConstants.S_OK;  
    }  
  
    ```  
  
4.  구현 하 여 지정 된 목록 항목에 대 한 아이콘 정보를 가져오기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetDisplayData%2A>메서드.</xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetDisplayData%2A> 아이콘 형식 (클래스, 메서드 및 등) 및 내게 필요한 옵션 (사설, 공용 및 등)의 목록 항목을 나타냅니다. 다음 예제에서는 지정 된 항목 특성에 따라 아이콘 정보를 가져오는 방법을 보여 줍니다.  
  
    ```vb#  
    Public Overridable Function GetDisplayData(ByVal index As UInteger, ByVal pData As Microsoft.VisualStudio.Shell.Interop.VSTREEDISPLAYDATA()) As Integer  
        If pData Is Nothing Then  
            Return Microsoft.VisualStudio.VSConstants.E_INVALIDARG  
        End If  
  
        Dim method As Method = m_Methods.Values(CInt(Fix(index)))  
  
        Dim iImage As Integer = 12 * 6 ' See env\inc\OMGlyphs.h.  
  
        Const OM_GLYPH_ACC_PUBLIC As Integer = 0  
        Const OM_GLYPH_ACC_INTERNAL As Integer = 1  
        Const OM_GLYPH_ACC_PROTECTED As Integer = 3  
        Const OM_GLYPH_ACC_PRIVATE As Integer = 4  
  
        If method.IsPublic Then  
            iImage += OM_GLYPH_ACC_PUBLIC  
        ElseIf method.IsPrivate Then  
            iImage += OM_GLYPH_ACC_PRIVATE  
        ElseIf method.IsFamily Then  
            iImage += OM_GLYPH_ACC_PROTECTED  
        ElseIf method.IsFamilyOrAssembly Then  
            iImage += OM_GLYPH_ACC_PROTECTED  
        Else  
            iImage += OM_GLYPH_ACC_INTERNAL  
        End If  
  
        pData(0).Image = CUShort(iImage)  
        pData(0).SelectedImage = CUShort(iImage)  
  
        Return Microsoft.VisualStudio.VSConstants.S_OK  
    End Function  
    ```  
  
    ```c#  
    public virtual int GetDisplayData(uint index, Microsoft.VisualStudio.Shell.Interop.VSTREEDISPLAYDATA[] pData)  
    {  
        if (pData == null)  
        {  
            return Microsoft.VisualStudio.VSConstants.E_INVALIDARG;  
        }  
  
        Method method = m_Methods.Values[(int)index];  
  
        int iImage = 12 * 6;    // See env\inc\OMGlyphs.h.  
  
        const int OM_GLYPH_ACC_PUBLIC = 0;  
        const int OM_GLYPH_ACC_INTERNAL = 1;  
        const int OM_GLYPH_ACC_PROTECTED = 3;  
        const int OM_GLYPH_ACC_PRIVATE = 4;  
  
        if (method.IsPublic)  
        {  
            iImage += OM_GLYPH_ACC_PUBLIC;  
        }  
        else if (method.IsPrivate)  
        {  
            iImage += OM_GLYPH_ACC_PRIVATE;  
        }  
        else if (method.IsFamily)  
        {  
            iImage += OM_GLYPH_ACC_PROTECTED;  
        }  
        else if (method.IsFamilyOrAssembly)  
        {  
            iImage += OM_GLYPH_ACC_PROTECTED;  
        }  
        else  
        {  
            iImage += OM_GLYPH_ACC_INTERNAL;  
        }  
  
        pData[0].Image = (ushort)iImage;  
        pData[0].SelectedImage = (ushort)iImage;  
  
        return Microsoft.VisualStudio.VSConstants.S_OK;  
    }  
  
    ```  
  
5.  구현 하 여 확장 가능한 지정 된 목록 항목 인지 여부에 대 한 정보는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetExpandable3%2A>메서드.</xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetExpandable3%2A> 다음 예제에서는 지정된 된 항목을 확장할 수 있는지 여부에 대 한 정보를 가져오는 방법을 보여 줍니다.  
  
    ```vb#  
    Public Function GetExpandable(ByVal index As UInteger, ByRef pfExpandable As Integer) As Integer  
        pfExpandable = Microsoft.VisualStudio.VSIP.Samples.CallBrowser.Constants.TRUE  
        Return Microsoft.VisualStudio.VSConstants.S_OK  
    End Function  
  
    Public Function GetExpandable3(ByVal index As UInteger, ByVal ListTypeExcluded As UInteger, ByRef pfExpandable As Integer) As Integer  
        Return GetExpandable(index, pfExpandable)  
    End Function  
    ```  
  
    ```c#  
    public int GetExpandable(uint index, out int pfExpandable)  
    {  
        pfExpandable = Microsoft.VisualStudio.VSIP.Samples.CallBrowser.Constants.TRUE;  
        return Microsoft.VisualStudio.VSConstants.S_OK;  
    }  
  
    public int GetExpandable3(uint index, uint ListTypeExcluded, out int pfExpandable)  
    {  
        return GetExpandable(index, out pfExpandable);  
    }  
  
    ```  
  
6.  구현 하 여 기호 지정된 목록 항목의 자식 목록 가져오기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetList2%2A>메서드.</xref:Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2.GetList2%2A> 다음 예제에서는 기호에 대 한 지정된 된 항목의 자식 목록을 가져오는 방법을 보여 줍니다. **호출** 또는 **호출자** 그래프입니다.  
  
    ```vb#  
    ' Call graph list.  
    Public Class CallsList  
        Inherits ResultsList  
        Implements Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2  
        Public Sub New(ByVal library As Library)  
            MyBase.New(library)  
        End Sub  
  
        Public Function GetList2(ByVal index As UInteger, ByVal ListType As UInteger, ByVal flags As UInteger, ByVal pobSrch As Microsoft.VisualStudio.Shell.Interop.VSOBSEARCHCRITERIA2(), ByRef ppList As Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2) As Integer  
            Return MyBase.GetCallsList(index, ppList)  
        End Function  
    End Class  
  
    ' Callers graph list.  
    Public Class CallersList  
        Inherits ResultsList  
        Implements Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2  
        Public Sub New(ByVal library As Library)  
            MyBase.New(library)  
        End Sub  
  
        Public Function GetList2(ByVal index As UInteger, ByVal ListType As UInteger, ByVal flags As UInteger, ByVal pobSrch As Microsoft.VisualStudio.Shell.Interop.VSOBSEARCHCRITERIA2(), ByRef ppList As Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2) As Integer  
            Return MyBase.GetCallersList(index, ppList)  
        End Function  
    End Class  
  
    ' Call graph list.  
    Public Function GetCallsList(ByVal index As UInteger, ByRef ppList As Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2) As Integer  
        ppList = Nothing  
        Dim callsList As ResultsList = New CallsList(m_Library)  
  
        Dim method As Method = m_Methods.Values(CInt(Fix(index)))  
        Dim strMethod As String = method.m_strPrototype  
  
        Dim Calls As System.Collections.Generic.List(Of CallInstance) = m_Library.CallGraph.GetCallGraph(method)  
  
        For i As Integer = 0 To Calls.Count - 1  
            Dim caller As Method = Calls(i).m_Target  
            callsList.AddMethod(caller)  
        Next i  
  
        ppList = CType(callsList, Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2)  
        Return Microsoft.VisualStudio.VSConstants.S_OK  
    End Function  
  
    ' Callers graph list.  
    Public Function GetCallersList(ByVal index As UInteger, ByRef ppList As Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2) As Integer  
        ppList = Nothing  
        Dim callersList As ResultsList = New CallersList(m_Library)  
  
        Dim method As Method = m_Methods.Values(CInt(Fix(index)))  
        Dim strMethod As String = method.m_strPrototype  
  
        Dim Callers As System.Collections.Generic.List(Of CallInstance) = m_Library.CallGraph.GetCallersGraph(method)  
  
        For i As Integer = 0 To Callers.Count - 1  
            Dim caller As Method = Callers(i).m_Source  
            callersList.AddMethod(caller)  
        Next i  
  
        ppList = CType(callersList, Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2)  
        Return Microsoft.VisualStudio.VSConstants.S_OK  
    End Function  
  
    ' Get a child list of symbols for a given list item.  
    Public Function GetList2(ByVal index As UInteger, ByVal ListType As UInteger, ByVal flags As UInteger, ByVal pobSrch As Microsoft.VisualStudio.Shell.Interop.VSOBSEARCHCRITERIA2(), ByRef ppList As Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2) As Integer  
        ppList = Nothing  
  
        Dim method As Method = m_Methods.Values(CInt(Fix(index)))  
        Dim strMethod As String = method.m_strPrototype  
  
        ' Determine if the list belongs to Call or Callers graphs.  
        If CUInt(m_nFlags And CUInt(Microsoft.VisualStudio.Shell.Interop._VSOBSEARCHOPTIONS2.VSOBSO_CALLSFROM)) > 0 Then  
            ' Build the list for the Call graph.  
            Return MyBase.GetCallsList(index, ppList)  
        ElseIf CUInt(m_nFlags And CUInt(Microsoft.VisualStudio.Shell.Interop._VSOBSEARCHOPTIONS2.VSOBSO_CALLSTO)) > 0 Then  
            ' Build the list for the Callers graph.  
            Return MyBase.GetCallersList(index, ppList)  
        End If  
  
        Return Microsoft.VisualStudio.VSConstants.E_FAIL  
    End Function  
    ```  
  
    ```c#  
    // Call graph list.  
    public class CallsList :  
        ResultsList,  
        Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2  
    {  
        public CallsList(Library library) :  
            base(library)  
        {  
        }  
  
        public int GetList2(uint index, uint ListType, uint flags, Microsoft.VisualStudio.Shell.Interop.VSOBSEARCHCRITERIA2[] pobSrch, out Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2 ppList)  
        {  
            return base.GetCallsList(index, out ppList);  
        }  
    }  
  
    // Callers graph list.  
    public class CallersList :  
        ResultsList,  
        Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2  
    {  
        public CallersList(Library library) :  
            base(library)  
        {  
        }  
  
        public int GetList2(uint index, uint ListType, uint flags, Microsoft.VisualStudio.Shell.Interop.VSOBSEARCHCRITERIA2[] pobSrch, out Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2 ppList)  
        {  
            return base.GetCallersList(index, out ppList);  
        }  
    }  
  
    // Call graph list.  
    public int GetCallsList(uint index, out Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2 ppList)  
    {  
        ppList = null;  
        ResultsList callsList = new CallsList(m_Library);  
  
        Method method = m_Methods.Values[(int)index];  
        string strMethod = method.m_strPrototype;  
  
        System.Collections.Generic.List<CallInstance> Calls = m_Library.CallGraph.GetCallGraph(method);  
  
        for (int i = 0; i < Calls.Count; i++)  
        {  
            Method caller = Calls[i].m_Target;  
            callsList.AddMethod(caller);  
        }  
  
        ppList = (Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2)(callsList);  
        return Microsoft.VisualStudio.VSConstants.S_OK;  
    }  
  
    // Callers graph list.  
    public int GetCallersList(uint index, out Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2 ppList)  
    {  
        ppList = null;  
        ResultsList callersList = new CallersList(m_Library);  
  
        Method method = m_Methods.Values[(int)index];  
        string strMethod = method.m_strPrototype;  
  
        System.Collections.Generic.List<CallInstance> Callers = m_Library.CallGraph.GetCallersGraph(method);  
  
        for (int i = 0; i < Callers.Count; i++)  
        {  
            Method caller = Callers[i].m_Source;  
            callersList.AddMethod(caller);  
        }  
  
        ppList = (Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2)(callersList);  
        return Microsoft.VisualStudio.VSConstants.S_OK;  
    }  
  
    // Get a child list of symbols for a given list item.  
    public int GetList2(uint index, uint ListType, uint flags, Microsoft.VisualStudio.Shell.Interop.VSOBSEARCHCRITERIA2[] pobSrch, out Microsoft.VisualStudio.Shell.Interop.IVsSimpleObjectList2 ppList)  
    {  
        ppList = null;  
  
        Method method = m_Methods.Values[(int)index];  
        string strMethod = method.m_strPrototype;  
  
        // Determine if the list belongs to Call or Callers graphs.  
        if ((uint)(m_nFlags & (uint)Microsoft.VisualStudio.Shell.Interop._VSOBSEARCHOPTIONS2.VSOBSO_CALLSFROM) > 0)  
        {  
            // Build the list for the Call graph.  
            return base.GetCallsList(index, out ppList);  
        }  
        else if ((uint)(m_nFlags & (uint)Microsoft.VisualStudio.Shell.Interop._VSOBSEARCHOPTIONS2.VSOBSO_CALLSTO) > 0)  
        {  
            // Build the list for the Callers graph.  
            return base.GetCallersList(index, out ppList);  
        }  
  
        return Microsoft.VisualStudio.VSConstants.E_FAIL;  
    }  
  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [기호 검색 도구를 지원합니다.](../../extensibility/internals/supporting-symbol-browsing-tools.md)   
 [방법: 개체 관리자와 함께 라이브러리를 등록 합니다.](../../extensibility/internals/how-to-register-a-library-with-the-object-manager.md)   
 [방법: 라이브러리에 대 한 기호를 식별 합니다.](../../extensibility/internals/how-to-identify-symbols-in-a-library.md)   
 [레거시 언어 서비스 확장](../../extensibility/internals/legacy-language-service-extensibility.md)
