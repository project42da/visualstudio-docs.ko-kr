---
title: "단일 및 다중 탭 뷰 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 사용자 지정-단일 및 다중 탭 뷰"
ms.assetid: e3611704-349f-4323-b03c-f2b0a445d781
caps.latest.revision: 22
caps.handback.revision: 22
ms.author: "gregvanl"
manager: "ghogen"
---
# 단일 및 다중 탭 뷰
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

편집기는 서로 다른 뷰를 만들 수 있습니다.  예를 들어 코드 편집기 창, 다른 양식 디자이너입니다.  
  
 여러 개 있는 보기에 여러 개의 탭으로 구성 된 보기가입니다.  예를 들어, HTML 편집기 맨 아래에 두 개의 탭이 있습니다:  **디자인** 및  **원본**, 각 논리 보기입니다.  다른 웹 페이지를 구성 하는 HTML을 표시 하는 동안 디자인 뷰에 렌더링 된 웹 페이지를 표시 합니다.  
  
## 물리적 보기에 액세스  
 물리적 보기 각 버퍼에 있는 데이터, 코드 또는 폼 등의 보기를 나타내는 문서 보기 개체를 호스트 합니다.  따라서, 각 문서의 뷰 개체로 실제 뷰 문자열로 알려진 실제 보기, 및 일반적으로 단일 논리적 보기 있습니다.  
  
 경우에 따라, 두 개 이상의 논리 보기 실제 뷰를 가질 수 있습니다.  예를 들면 GUI\/디자인 보기와 코드\-뒤\-\-폼 보기 폼 디자이너 또는 분할 창을 세로로 나란히 보기가 있는 편집기입니다.  
  
 편집기에서 모든 사용 가능한 물리적 보기에 액세스할 수 있도록 문자열 편집기 팩터리를 만들 수 있습니다 문서 보기 개체의 각 유형에 대 한 고유한 물리적 보기를 만들어야 합니다.  예를 들어 있는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 편집기 팩터리 개체 보기의 코드 창과 폼 디자이너 창을 문서를 만들 수 있습니다.  
  
## 여러 개 있는 보기 만들기  
 문서 보기 개체 실제 뷰는 실제 보기 고유 문자열을 통해 연결 되어야 합니다 있지만 보기 데이터를 여러 가지 방식으로 사용할 수 있도록 실제 보기 내에서 여러 개의 탭을 배치할 수 있습니다.  이 여러 개 있는 구성에서 모든 탭 같은 물리적 보기 문자열과 관련 된 있지만 각 탭 다른 논리 보기 GUID 지정 됩니다.  
  
 여러 개 있는 보기를 만들려면 편집기를 구현에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMultiViewDocumentView> 인터페이스와 다른 논리 보기 GUID 다음 연결 \(<xref:Microsoft.VisualStudio.Shell.Interop.LogicalViewID>\) 만드는 각 탭이.  
  
 Visual Studio HTML 편집기 편집기를 multi\-tab 보기의 예입니다.  이  **디자인** 및  **원본** 탭.  이 기능을 사용 하려면 다른 논리 보기 탭과 관련이 `LOGICALVIEWID_TextView` 에  **디자인** 탭 및 `LOGICALVIEWID_Code` 에  **원본** 탭.  
  
 적절 한 논리 뷰를 지정 하 여 양식 디자인, 코드 편집 또는 코드 디버깅 등 특정 목적에 해당 하는 보기는 VSPackage 액세스할 수 있습니다.  그러나 창 중 하나가 합니다 식별할 수 NULL 문자열 및이 기본 논리 보기에 해당 합니다 \(`LOGVIEWID_Primary`\).  
  
 다음 값 사용 가능한 논리 보기 및 사용 하는 표입니다.  
  
|LOGVIEWID GUID|권장된 용도|  
|--------------------|------------|  
|`LOGVIEWID_Primary`|기본\/기본 뷰 편집기 팩터리입니다.<br /><br /> 모든 편집기 팩터리는이 값을 지원 해야 합니다.  이 보기의 실제 뷰 문자열로 NULL 문자열을 사용 해야 합니다.  하나 이상의 논리적 보기를이 값으로 설정 되어야 합니다.|  
|`LOGVIEWID_Debugging`|보기를 디버깅 합니다.  일반적으로, `LOGVIEWID_Debugging` 맵 이름으로 동일한 보기를 `LOGVIEWID_Code`.|  
|`LOGVIEWID_Code`|보기 시작 하는  **코드 보기** 명령입니다.|  
|`LOGVIEWID_Designer`|보기를 시작 하는  **양식 보기** 명령을.|  
|`LOGVIEWID_TextView`|텍스트 편집기 뷰입니다.  이 반환 하는 보기입니다. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>에서 액세스할 수 있는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>.|  
|`LOGVIEWID_UserChooseView`|볼을 사용 하려면 선택 하 라는.|  
|`LOGVIEWID_ProjectSpecificEditor`|전달 하는  **와** 대화 상자에<br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject.OpenItem%2A><br /><br /> 때 사용자가 "\(프로젝트 기본 편집기\)" 항목을 선택 합니다.|  
  
 확장 가능한 논리 보기의 Guid는 하지만 하면 Vspackage에 정의 된 논리적 보기 Guid만 사용할 수 있습니다.  
  
 종료에, Visual Studio 편집기 팩터리 및 솔루션이 열립니다 됩니다 때 문서 windows를 사용할 수 있도록 문서 창에 연결 된 실제 보기 문자열 GUID 유지 합니다.  솔루션을 닫을 때 열려 있는 창에는 솔루션 \(.suo\) 파일에 저장 됩니다.  이러한 값에 해당 하는 `VSFPROPID_guidEditorType` 및 `VSFPROPID_pszPhysicalView` 전달 된 값은 `propid` 매개 변수에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> 메서드.  
  
## 예제  
 이 코드 조각을 보여 줍니다 방법에 <xref:Microsoft.VisualStudio.Shell.Interop.LogicalViewID.TextView> 개체를 구현 하는 보기에 액세스 하는 데 사용 됩니다 `IVsCodeWindow`.  이 경우에 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShellOpenDocument> 서비스를 호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenDocumentViaProject%2A> 을 요청 `LOGVIEWID_TextView`, 창 프레임에 대 한 포인터를 가져옵니다.  호출 하 여 문서의 뷰 개체에 대 한 포인터를 얻을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> 값을 지정 하 고 `VSFPROPID_DocView`.  문서 보기 개체를 `QueryInterface` 에 대 한 호출 됩니다 `IVsCodeWindow`.  이란이 경우 텍스트 편집기 반환 되 고 따라서 반환 된 문서 보기 개체에는 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> 메서드 코드 창입니다.  
  
```cpp#  
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
  
## 참고 항목  
 [여러 문서 보기를 지원합니다.](../extensibility/supporting-multiple-document-views.md)   
 [방법: 뷰 문서 데이터를 연결 합니다.](../extensibility/how-to-attach-views-to-document-data.md)   
 [사용자 지정 편집기 및 디자이너 만들기](../extensibility/creating-custom-editors-and-designers.md)