---
title: '방법: 기본 제공 글꼴 및 색 구성표에 액세스 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- fonts, accessing built-in
- font and color control [Visual Studio SDK], categories
- colors, accessing built-in schemes
ms.assetid: 6905845e-e88e-4805-adcf-21da39108ec7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5f72640369152b03ef86383fda1162b1cfbacba8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-access-the-built-in-fonts-and-color-scheme"></a>방법: 기본 제공 글꼴 및 색 구성표에 액세스
Visual Studio 통합된 개발 환경 (IDE)에 편집기 창에 연결 되는 글꼴 및 색 구성표가 있습니다. 이 체계를 통해 액세스할 수 있습니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 인터페이스입니다.

 기본 제공 글꼴 및 색 구성표를 사용 하려면 VSPackage 해야 합니다.

-   기본 글꼴 및 색 서비스와 함께 사용 하는 범주를 정의 합니다.

-   기본 글꼴 및 색 서버와 범주를 등록 합니다.

-   특정 창 기본 표시 항목 및 범주를 사용 하 여 사용 하도록 IDE에 알립니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer> 인터페이스입니다.

 IDE 창에 대 한 핸들으로 결과 범주를 사용합니다. 범주 이름이 표시 됩니다는 **설정 표시:** 드롭다운 목록 상자에는 **글꼴 및 색** 속성 페이지.

### <a name="to-define-a-category-using-built-in-fonts-and-colors"></a>기본 제공 글꼴 및 색을 사용 하 여 범주를 정의 하려면

1.  임의 GUID를 만듭니다.

     이 GUID는 범주를 고유 하 게 식별 하는 데 사용 되**합니다.** 이 범주에는 IDE의 기본 글꼴 및 색 사양 다시 사용합니다.

    > [!NOTE]
    >  사용 하 여 글꼴 및 색 데이터를 검색할 때는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> 다른 인터페이스의 경우 Vspackage를 사용 하 여이 GUID 기본 제공 정보를 참조 합니다.

2.  IDE에서 표시 하는 경우 필요에 따라 지역화할 수 있도록 항목의 이름은 VSPackage의 리소스 (.rc) 파일 내의 문자열 테이블에 추가 되어야 합니다.

     자세한 내용은 참조 [추가 또는 삭제 문자열로](/cpp/windows/adding-or-deleting-a-string)합니다.

### <a name="to-register-a-category-using-built-in-fonts-and-colors"></a>기본 제공 글꼴 및 색을 사용 하 여 범주를 등록 하려면

1.  특수 한 유형의 범주 레지스트리 항목의 다음 위치에서 구성 됩니다.

     [HKLM\SOFTWARE\Microsoft \Visual Studio\\*\<Visual Studio version>*\FontAndColors\\*\<Category>*]

     *\<범주 >* 범주의 지역화 되지 않은 이름입니다.

2.  4 개의 값이 포함 된 스톡 글꼴 및 색 구성표를 사용 하도록 레지스트리를를 채웁니다.

    |이름|형식|데이터|설명|
    |----------|----------|----------|-----------------|
    |범주|REG_SZ|GUID|스톡 글꼴 및 색 구성표를 포함 하는 범주를 식별 하는 임의의 GUID입니다.|
    |패키지|REG_SZ|GUID|{F5E7E71D-1401-11D1-883B-0000F87579D2}<br /><br /> 이 GUID는 기본 글꼴 및 색 구성을 사용 하는 모든 Vspackage에서 사용 됩니다.|
    |NameID|REG_DWORD|ID|VSPackage에서 지역화 가능한 범주 이름의 리소스 ID입니다.|
    |ToolWindowPackage|REG_SZ|GUID|구현 하는 VSPackage의 GUID는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 인터페이스입니다.|

### <a name="to-initiate-the-use-of-system-provided-fonts-and-colors"></a>시스템 제공 글꼴 및 색의 사용을 시작 하려면

1.  인스턴스를 만들고는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer> 창의 구현과 초기화의 일부로 인터페이스입니다.

2.  호출 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer.GetPropertyCategory%2A> 의 인스턴스를 가져오는 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer> 현재 해당 인터페이스 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 인스턴스.

3.  호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A> 두 번입니다.

    -   한 번 호출 `VSEDITPROPID_ViewGeneral_ColorCategory`인수로 합니다.

    -   한 번 호출 `VSEDITPROPID_ViewGeneral_FontCategory` 인수로 합니다.

     설정 하 고 기본 글꼴 및 색 서비스 창의 속성으로 노출 합니다.

## <a name="example"></a>예제
 다음 예제에서는 기본 제공 글꼴 및 색의 사용을 시작합니다.

```cpp
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

## <a name="see-also"></a>참고 항목

- [글꼴 및 색을 사용 하 여](../extensibility/using-fonts-and-colors.md)
- [글꼴 및 텍스트 색 지정에 대 한 색상 정보 가져오기](../extensibility/getting-font-and-color-information-for-text-colorization.md)
- [저장 된 글꼴 및 색 설정에 액세스](../extensibility/accessing-stored-font-and-color-settings.md)
- [글꼴 및 색 개요](../extensibility/font-and-color-overview.md)