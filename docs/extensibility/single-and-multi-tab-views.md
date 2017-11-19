---
title: "단일 및 다중 탭 보기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], custom - single and multi-tab views
ms.assetid: e3611704-349f-4323-b03c-f2b0a445d781
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6c90f7cec454cc6562e2cd20e2da64cfe86e243f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="single-and-multi-tab-views"></a>단일 및 다중 탭 뷰
편집기는 여러 유형의 보기를 만들 수 있습니다. 한 가지 예는 코드 편집기 창, 양식 디자이너입니다.  
  
 다중 탭 뷰는 여러 탭이 포함 된 보기. 예를 들어, HTML 편집기에 두 개의 탭 아래에: **디자인** 및 **소스**, 각 논리적 보기. 디자인 보기 내용이 표시 됩니다는 웹 페이지를 구성 하는 HTML 렌더링된 된 웹 페이지를 표시 합니다.  
  
## <a name="accessing-physical-views"></a>실제 보기에 액세스  
 실제 뷰 호스트 코드 또는 양식과 같은 버퍼에 있는 데이터의 보기를 나타내는 각 문서 보기 개체입니다. 따라서 각 문서 보기 개체에 물리적 보기 (실제 뷰 문자열로 알려진 것으로 식별 됨) 및 일반적으로 단일 논리 보기.  
  
 그러나 경우에 따라 실제 뷰 두 개 이상의 논리적 보기가 있을 수 있습니다. 몇 가지 예는 함께-뷰가 포함 된 분할 창에 있는 편집기 또는 GUI/디자인 보기 및 코드 숨김을-the-형식 보기는 forms 디자이너입니다.  
  
 모든 사용 가능한 실제 보기에 액세스 하려면 편집기를 사용 하려면 각 유형의 편집기 팩터리를 만들 수 있는 문서 보기 개체에 대 한 고유한 물리적 보기 문자열을 만들어야 합니다. 예를 들어는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 편집기 팩터리 문서 코드 창과 forms 디자이너 창에 대 한 뷰 개체를 만들 수 있습니다.  
  
## <a name="creating-multi-tabbed-views"></a>다중 탭 보기 만들기  
 문서 보기 개체에는 고유한 물리적 보기 문자열을 통해 물리적 보기와 연결 되어야 합니다, 경우에 다른 방법으로 데이터 보기를 사용 하도록 설정 하려면 실제 뷰 내에서 여러 탭을 배치할 수 있습니다. 이 탭이 여러 개 구성에서는 모든 탭은 동일한 물리적 보기 문자열로 연결 되지만 각 탭에는 다른 논리 보기 GUID 제공 됩니다.  
  
 편집기에 대 한 다중 탭 보기를 만들려면 구현는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMultiViewDocumentView> 인터페이스를 연결 하 여 다른 논리 보기 GUID (<xref:Microsoft.VisualStudio.Shell.Interop.LogicalViewID>) 각 탭을 사용 하 여 만들 합니다.  
  
 Visual Studio HTML 편집기는 여러 탭 뷰 편집기의 예시입니다. 있기 **디자인** 및 **소스** 탭 합니다. 다른 논리 보기를 사용 하려면 각 탭에서 연관 된 `LOGICALVIEWID_TextView` 에 대 한는 **디자인** 탭 및 `LOGICALVIEWID_Code` 에 대 한는 **소스** 탭 합니다.  
  
 적절 한 논리 뷰를 지정 하 여 VSPackage 양식을 디자인할 코드를 편집, 디버깅 코드 등의 특정 목적에 해당 하는 보기를 액세스할 수 있습니다. 그러나 창 중 하나는 NULL 문자열에 의해 식별 해야 하 고 기본 논리 뷰 일치 해야 (`LOGVIEWID_Primary`).  
  
 다음 표에서 사용 가능한 논리 뷰 값 및 용도 나열합니다.  
  
|LOGVIEWID GUID|권장된 사용|  
|--------------------|---------------------|  
|`LOGVIEWID_Primary`|편집기 팩터리의 기본/기본 보기입니다.<br /><br /> 모든 편집기 팩터리는이 값을 지원 해야 합니다. 이 보기의 실제 뷰 문자열로 NULL 문자열을 사용 해야 합니다. 논리적 뷰를 하나 이상이 값으로 설정 되어야 합니다.|  
|`LOGVIEWID_Debugging`|보기를 디버깅 합니다. 일반적으로 `LOGVIEWID_Debugging` 동일한 뷰를 매핑됩니다 `LOGVIEWID_Code`합니다.|  
|`LOGVIEWID_Code`|보기를 통해 시작 된 **코드 보기** 명령입니다.|  
|`LOGVIEWID_Designer`|보기를 통해 시작 된 **양식 보기** 명령입니다.|  
|`LOGVIEWID_TextView`|텍스트 편집기 보기입니다. 이 반환 하는 뷰는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>에서 액세스할 수 있는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>합니다.|  
|`LOGVIEWID_UserChooseView`|사용 하는 뷰를 선택 하 라는 메시지입니다.|  
|`LOGVIEWID_ProjectSpecificEditor`|로 전달 된 **프로그램** 대화 상자<br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.OpenItem%2A><br /><br /> 때 사용자가 "(프로젝트 기본 편집기)" 항목을 선택 합니다.|  
  
 논리적 보기 Guid 확장 가능 하지만, VSPackage에 정의 된 논리적 보기 Guid만 사용할 수 있습니다.  
  
 종료, Visual Studio 편집기 팩터리 및 해당 창과 연결 된 문서를 솔루션 다시 열릴 때 문서 창을 다시 열에 사용할 수 있도록 물리적 보기 문자열의 GUID를 유지 합니다. 솔루션을 닫으면 열려 있는 창은 솔루션 (.suo) 파일에서 유지 됩니다. 이러한 값에 해당는 `VSFPROPID_guidEditorType` 및 `VSFPROPID_pszPhysicalView` 전달 된 값의 `propid` 에서 매개 변수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> 메서드.  
  
## <a name="example"></a>예제  
 이 코드 조각에서는 방법을 <xref:Microsoft.VisualStudio.Shell.Interop.LogicalViewID.TextView> 개체를 구현 하는 보기에 액세스 하는 데 사용 됩니다 `IVsCodeWindow`합니다. 이 경우에 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShellOpenDocument> 서비스를 사용 하 여를 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenDocumentViaProject%2A> 및 요청 `LOGVIEWID_TextView`, 창 프레임에 대 한 포인터를 가져오는 합니다. 문서 보기 개체에 대 한 포인터를 호출 하 여 가져온 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> 값을 지정 하 고 `VSFPROPID_DocView`합니다. 문서 보기 개체에서 `QueryInterface` 에 대해 호출 `IVsCodeWindow`합니다. 예상 텍스트 편집기가 반환 되 고, 문서 보기 개체에 반환 되므로 경우에는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> 메서드 코드 창입니다.  
  
```cpp  
HRESULT CFindTool::GotoFileLocation(const WCHAR * szFile, long iLine, long iStart, long iLen)  
{  
  HRESULT hr;  
  if (NULL == szFile || !*szFile)  
    return E_INVALIDARG;  
  
  if (iLine == -1L)  
    return S_FALSE;  
  
  VSITEMID                  itemid;  
  VARIANT                   var;  
  RECT                      rc;  
  IVsUIShellOpenDocument *  pOpenDoc    = NULL;  
  IVsCodeWindow *           pCodeWin    = NULL;  
  IVsTextView *             pTextView   = NULL;  
  IVsUIHierarchy *          pHierarchy  = NULL;  
  IVsWindowFrame *          pFrame      = NULL;  
  IUnknown *                pUnk        = NULL;  
  IVsHighlight *            pHighlight  = NULL;  
  
  IfFailGo(CGlobalServiceProvider::HrQueryService(SID_SVsUIShellOpenDocument, IID_IVsUIShellOpenDocument, (void **)&pOpenDoc));  
  IfFailGo(pOpenDoc->OpenDocumentViaProject(szFile, LOGVIEWID_TextView, NULL, &pHierarchy, &itemid, &pFrame));  
  pFrame->Show();  
  VariantInit(&var);  
  IfFailGo(pFrame->GetProperty(VSFPROPID_DocView, &var));  
  if (VT_UNKNOWN != var.vt) { hr = E_FAIL; goto Error; }  
  pUnk = V_UNKNOWN(&var);  
  if (NULL != pUnk)  
  {  
    IfFailGo(pUnk->QueryInterface(IID_IVsCodeWindow, (void **)&pCodeWin));  
    if (SUCCEEDED(hr = pCodeWin->GetLastActiveView(&pTextView)) ||  
        SUCCEEDED(hr = pCodeWin->GetPrimaryView(&pTextView)) )  
    {  
      pTextView->SetSelection(iLine, iStart, iLine, iStart + iLen);  
      // uncover selection  
      IfFailGo(pTextView->QueryInterface(IID_IVsHighlight, (void**)&pHighlight));  
      IfFailGo(SUCCEEDED(pHighlight->GetHighlightRect(&rc)));  
      UncoverSelectionRect(&rc);  
    }  
  }  
  
Error:  
  CLEARINTERFACE(pHighlight);  
  CLEARINTERFACE(pTextView);  
  CLEARINTERFACE(pCodeWin);  
  CLEARINTERFACE(pUnk);  
  CLEARINTERFACE(pFrame);  
  CLEARINTERFACE(pOpenDoc);  
  CLEARINTERFACE(pHierarchy);  
  RedrawWindow(m_hwndResults, NULL, NULL, RDW_ERASE|RDW_FRAME|RDW_INVALIDATE|RDW_ALLCHILDREN);  
  return hr;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [여러 문서 보기를 지원합니다.](../extensibility/supporting-multiple-document-views.md)   
 [방법: 뷰 문서 데이터를 연결 합니다.](../extensibility/how-to-attach-views-to-document-data.md)   
 [사용자 지정 편집기 및 디자이너 만들기](../extensibility/creating-custom-editors-and-designers.md)