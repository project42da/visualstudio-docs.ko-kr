---
title: "방법: 기본 글꼴 및 색 구성표에 액세스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "글꼴, 기본 제공 액세스"
  - "글꼴 및 색 컨트롤 [Visual Studio SDK] 범주"
  - "색, 기본 제공 스키마에 액세스"
ms.assetid: 6905845e-e88e-4805-adcf-21da39108ec7
caps.latest.revision: 23
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 23
---
# 방법: 기본 글꼴 및 색 구성표에 액세스
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 통합된 개발 환경 \(IDE\)에 연결 된 편집기 창의 글꼴 및 색 구성표가 있습니다. 이 체계를 통해 액세스할 수는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 인터페이스입니다.  
  
 VSPackage 기본 글꼴 및 색 구성표를 사용 하려면 다음을 해야 합니다.  
  
-   기본 글꼴 및 색 서비스와 함께 사용 하는 범주를 정의 합니다.  
  
-   기본 글꼴 및 색 서버와 범주를 등록 합니다.  
  
-   특정 창 표시 기본 제공 항목 및 범주를 사용 하 여 사용 하는 IDE에 게 알리기는 `T:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer` 및 `T:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer` 인터페이스입니다.  
  
 IDE 창에 대 한 핸들로 결과 범주를 사용합니다. 에 범주 이름이 표시 됩니다는 **설정 표시:** 드롭다운 목록 상자에는 **글꼴 및 색** 속성 페이지.  
  
### 기본 제공 글꼴 및 색을 사용 하 여 범주를 정의 하려면  
  
1.  임의의 GUID를 만듭니다.  
  
     이 GUID는 범주를 고유 하 게 식별 하는 데 사용 됩니다**.** 이 범주에는 IDE의 기본 글꼴 및 색 사양을 다시 사용합니다.  
  
    > [!NOTE]
    >  사용 하 여 글꼴 및 색 데이터를 검색 하는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> 또는 다른 인터페이스를 Vspackage이이 GUID를 사용할 기본 제공 정보를 참조 합니다.  
  
2.  IDE에서 표시 하는 경우 필요에 따라 지역화 될 수 있도록 항목의 이름은 VSPackage의 리소스 \(.rc\) 파일 내 문자열 테이블에 추가 되어야 합니다.  
  
     자세한 내용은 [Adding or Deleting a String](/visual-cpp/windows/adding-or-deleting-a-string)을 참조하십시오.  
  
### 기본 제공 글꼴 및 색을 사용 하 여 범주를 등록 하려면  
  
1.  특수 한 유형의 범주 레지스트리 항목의 다음 위치에서 구성 됩니다.  
  
     \[HKLM\\SOFTWARE\\Microsoft \\Visual Studio\\*\< Visual Studio 버전 \>*\\FontAndColors\\*\< 범주 \>*\]  
  
     *\< 범주 \>* 범주의 지역화 되지 않은 이름입니다.  
  
2.  4 개의 값이 있는 스톡 글꼴 및 색 구성표를 사용 하 여 레지스트리를 채웁니다.  
  
    |이름|형식|데이터|설명|  
    |--------|--------|---------|--------|  
    |범주|REG\_SZ|GUID|스톡 글꼴 및 색 구성표를 포함 하는 범주를 식별 하는 임의의 GUID입니다.|  
    |Package|REG\_SZ|GUID|{F5E7E71D\-1401\-11D1\-883B\-0000F87579D2}<br /><br /> 이 GUID는 기본 글꼴 및 색 구성을 사용 하는 모든 Vspackage에서 사용 됩니다.|  
    |NameID|REG\_DWORD|ID|VSPackage에서 지역화 가능한 범주 이름의 리소스 ID입니다.|  
    |ToolWindowPackage|REG\_SZ|GUID|구현 하는 VSPackage의 GUID는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 인터페이스입니다.|  
  
3.  
  
### 시스템 제공 글꼴 및 색 사용을 시작 하려면  
  
1.  인스턴스를 만들고는 `T:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer` 창의 구현과 초기화의 일부로 인터페이스입니다.  
  
2.  호출에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer.GetPropertyCategory%2A> 의 인스턴스를 가져올 메서드는 `T:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer` 인터페이스에 해당 하는 현재 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 인스턴스.  
  
3.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> 두 번입니다.  
  
    -   사용 하 여 한 번 호출 `VSEDITPROPID_ViewGeneral_ColorCategory`인수로 합니다.  
  
    -   사용 하 여 한 번 호출 `VSEDITPROPID_ViewGeneral_FontCategory` 인수로 합니다.  
  
     설정 하 고 창의 속성으로는 기본 글꼴 및 색 서비스를 제공 합니다.  
  
## 예제  
 다음 예제에서는 기본 제공 글꼴 및 색 사용을 시작합니다.  
  
```  
CComVariant vt;  
CComQIPtr<IVsTextEditorPropertyCategoryContainer> spPropCatContainer(m_spView);  
if (spPropCatContainer != NULL){  
    CComPtr<IVsTextEditorPropertyContainer> spPropContainer;  
    if (SUCCEEDED(spPropCatContainer->GetPropertyCategory(GUID_EditPropCategory_View_MasterSettings,   
                                                          &spPropContainer))){  
        CComVariant vt;CComVariant VariantGUID(bstrGuidText);  
        spPropContainer->SetProperty(VSEDITPROPID_ViewGeneral_FontCategory, VariantGUID);  
        spPropContainer->SetProperty(VSEDITPROPID_ViewGeneral_ColorCategory, VariantGUID);  
    }  
}  
```  
  
## 참고 항목  
 [글꼴 및 색을 사용 하 여](../extensibility/using-fonts-and-colors.md)   
 [글꼴 및 텍스트 색 지정에 대 한 색 정보 가져오기](../extensibility/getting-font-and-color-information-for-text-colorization.md)   
 [저장 된 글꼴 및 색상 설정에 액세스](../extensibility/accessing-stored-font-and-color-settings.md)   
 [글꼴 및 색상 개요](../extensibility/font-and-color-overview.md)