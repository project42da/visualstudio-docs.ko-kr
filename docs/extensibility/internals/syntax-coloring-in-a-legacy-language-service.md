---
title: "구문 레거시 언어 서비스에 색 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "구문 색 지정"
  - "언어 서비스 구문 색 지정"
ms.assetid: f65ff67e-8c20-497a-bebf-5e2a5b5b012f
caps.latest.revision: 22
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 22
---
# 구문 레거시 언어 서비스에 색 지정
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]색 지정 서비스를 사용 하 여 언어의 요소를 식별 하 여 편집기에서 지정 된 색상을 표시 합니다.  
  
## Colorizer 모델  
 언어 서비스 구현에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> 다음 편집기에서 사용 되는 인터페이스입니다.  이 구현 언어 서비스에서 별도 개체는 다음 그림에 표시 된 대로입니다.  
  
 ![SVC 색 지정기 그래픽](~/docs/extensibility/internals/media/figlgsvccolorizer.gif "FigLgSvcColorizer")  
간단한 colorizer 모델  
  
> [!NOTE]
>  구문 서비스의 일반 분리 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 텍스트 색을 조정 하는 메커니즘입니다.  일반에 대 한 자세한 내용은 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 색 조정, 지원 메커니즘을 참조 하십시오. [글꼴 및 색을 사용 하 여](../../extensibility/using-fonts-and-colors.md).  
  
 뿐만 아니라 colorizer, 편집기에서 사용자 지정 색 항목을 제공 하는 광고에서 사용 되는 사용자 지정 색 항목 언어 서비스를 제공할 수 있습니다.  구현 하 여이 작업을 수행할 수 있습니다의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> 인터페이스를 구현 하는 동일한 개체에는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> 인터페이스입니다.  편집기를 호출 하는 경우 사용자 지정 색 항목 수 반환의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetItemCount%2A> 메서드 및 해당 반환를 개별 사용자 지정 색 항목 편집기를 호출 하는 경우는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> 메서드.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> 메서드를 구현 하는 개체를 반환 합니다. 해당 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> 인터페이스입니다.  24 비트 또는 높은 색상 값을 지 원하는 언어 서비스 구현 해야는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem> 인터페이스와 같은 개체에는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> 인터페이스입니다.  
  
## 있는 VSPackage 언어 서비스 Colorizer 사용 하는 방법  
  
1.  있는 VSPackage 언어 서비스 VSPackage 다음 작업을 수행 해야 하는 적합 한 언어 서비스를 가져와야 합니다.  
  
    1.  구현 하는 개체를 사용 하 여 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 텍스트를 조정 하 게 하는 인터페이스입니다.  
  
         구현 하는 개체를 사용 하 여 텍스트 표시 됩니다 일반적으로 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 인터페이스입니다.  
  
    2.  언어 서비스를 VSPackage GUID는 언어 서비스의 서비스 공급자를 쿼리하여 가져옵니다.  언어 서비스에서 레지스트리 파일 확장명으로 식별 됩니다.  
  
    3.  언어 서비스와 연결을 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 를 호출 하 여 해당 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> 메서드.  
  
2.  지금 있는 VSPackage 있습니다 구하고 colorizer 개체를 다음과 같이 사용.  
  
    > [!NOTE]
    >  코어 편집기 사용 VSPackages 언어 서비스 colorizer 개체를 명시적으로 얻이 필요가 없습니다.  적절 한 언어 서비스 코어 편집기의 인스턴스를 얻는 즉시 여기에 표시 된 색 처리 작업을 모두 수행 합니다.  
  
    1.  구현 하는 언어 서비스 colorizer 개체를 가져온는 `T:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer`, 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer2> 를 호출 하 여 인터페이스를는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> 메서드는 언어 서비스를 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> 개체입니다.  
  
    2.  호출 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 텍스트의 특정 범위에 대 한 colorizer 정보를 얻으려면 방법입니다.  
  
         <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A>값을 각각 다른 색으로 표시 되는 텍스트 범위에 문자 배열로 반환 합니다.  코어 편집기에 의해 유지 관리 되는 기본 색 항목 목록 또는 언어 서비스에서 유지 관리 되는 사용자 지정 색 항목 목록 색 항목 목록 인덱스 값을입니다.  
  
    3.  반환할 색 조정 정보를 사용 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 메서드는 선택한 텍스트를 표시 합니다.  
  
> [!NOTE]
>  언어 서비스 colorizer 이외에 있는 Vspackage도는 일반적인 용도의 사용 하 여 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 텍스트 색 메커니즘이 있습니다.  이 메커니즘에 대 한 자세한 내용은 참조 하십시오. [글꼴 및 색을 사용 하 여](../../extensibility/using-fonts-and-colors.md).  
  
## 단원 내용  
 [구문 색 지정을 구현합니다.](../../extensibility/internals/implementing-syntax-coloring.md)  
 편집기는 언어 서비스의 구문 색상 표시 및 언어 서비스 색 구문을 지원 하기 위해 구현 해야에 액세스 하는 방법에 대해 설명 합니다.  
  
 [방법: 기본 제공 색 항목을 사용 하 여](../../extensibility/internals/how-to-use-built-in-colorable-items.md)  
 기본 제공 색 항목 언어 서비스에서 사용 하는 방법을 보여 줍니다.  
  
 [사용자 지정 색 항목](../../extensibility/internals/custom-colorable-items.md)  
 사용자 지정 색 항목을 구현 하는 방법에 대해 설명 합니다.  
  
## 참고 항목  
 [글꼴 및 색을 사용 하 여](../../extensibility/using-fonts-and-colors.md)