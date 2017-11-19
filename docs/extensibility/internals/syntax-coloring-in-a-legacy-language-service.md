---
title: "구문 색 레거시 언어 서비스에서 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- syntax coloring
- language services, syntax coloring
ms.assetid: f65ff67e-8c20-497a-bebf-5e2a5b5b012f
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 88af397feba9b06eabd73ec23dcf1204ebe755e6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="syntax-coloring-in-a-legacy-language-service"></a>구문 색에 레거시 언어 서비스
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]언어 요소를 식별 하는 편집기에서 지정 된 색으로 표시할 색 지정 서비스를 사용 합니다.  
  
## <a name="colorizer-model"></a>색 지정 기 모델  
 언어 서비스 구현에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer> 인터페이스는 편집기에서 사용 됩니다. 다음 그림에 나와 있는 것 처럼이 구현은 언어 서비스에서 별도 개체입니다.  
  
 ![SVC 색 지정 기 그래픽](../../extensibility/internals/media/figlgsvccolorizer.gif "FigLgSvcColorizer")  
단순 색 지정 기 모델  
  
> [!NOTE]
>  구문 색 서비스 일반와에서 별개인 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 텍스트의 색을 지정 하기 위한 메커니즘입니다. 일반 대 한 자세한 내용은 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 메커니즘 색 지정를 지 원하는 참조 [를 사용 하 여 글꼴 및 색](../../extensibility/using-fonts-and-colors.md)합니다.  
  
 언어 서비스는 색 지정 기, 외에도 광고 색 사용자 지정 항목을 제공 하 여 편집기에서 사용 되는 색 사용자 지정 항목을 제공할 수 있습니다. 구현 하 여이 수행할 수는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> 인터페이스를 구현 하는 동일한 개체에는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> 인터페이스입니다. 편집기를 호출할 때 사용자 지정 색 항목 수를 반환 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetItemCount%2A> 메서드를 편집기를 호출 하는 경우 개별 사용자 지정 색 항목을 반환은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> 메서드.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> 구현 하는 개체를 반환 하는 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> 인터페이스입니다. 언어 서비스 24 비트 또는 높은 색 값을 지 원하는 경우 구현 해야 합니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiColorItem> 인터페이스와 같은 개체에는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorableItem> 인터페이스입니다.  
  
## <a name="how-a-vspackage-uses-a-language-service-colorizer"></a>VSPackage는 언어 서비스의 색 지정 기를 사용 하는 방법  
  
1.  VSPackage 언어 서비스는 다음을 수행 하기 위해 VSPackage를 실행 해야 하는 적절 한 언어 서비스를 가져와야 합니다.  
  
    1.  구현 하는 개체를 사용 하 여는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 인터페이스를 색으로 표시 될 텍스트를 가져옵니다.  
  
         텍스트는 일반적으로 구현 하는 개체를 사용 하 여 표시 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 인터페이스입니다.  
  
    2.  언어 서비스 GUID에 대 한 VSPackage의 서비스 공급자를 쿼리하여 언어 서비스를 가져옵니다. 언어 서비스 레지스트리 파일 확장명으로 식별 됩니다.  
  
    3.  연결 된 언어 서비스는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 호출 하 여 해당 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> 메서드.  
  
2.  이제 VSPackage 가져올 및 색 지정 기 개체를 다음과 같이 사용할 수 있습니다.  
  
    > [!NOTE]
    >  코어 편집기를 사용 하는 Vspackage는 언어 서비스의 색 지정 기 개체를 명시적으로 가져올 필요가 없습니다. 핵심 편집기의 인스턴스이거나가 적절 한 언어 서비스를 입수 하는 즉시 여기에 표시 된 색 지정 작업을 모두 수행 합니다.  
  
    1.  구현 하는 언어 서비스의 색 지정 기 개체를 가져올는 `T:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer`, 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer2> 호출 하 여 인터페이스는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> 언어 서비스의 메서드입니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> 개체입니다.  
  
    2.  호출의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 메서드를 텍스트의 특정 범위에 대 한 색 지정 기 정보를 가져옵니다.  
  
         <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A>색이 지정 되 고 있는 텍스트 범위에서 각 문자에 대 한 값의 배열을 반환 합니다. 이 값은 코어 편집기에서 유지 관리 하는 기본 색 항목 목록이 나 관리 하는 언어 서비스 자체 사용자 지정 색 항목 목록이 있는 색 항목 목록으로 인덱싱합니다.  
  
    3.  반환 된 색 지정 정보를 사용 하 여는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 선택한 텍스트를 표시 하는 메서드.  
  
> [!NOTE]
>  언어 서비스 색 지정 기를 사용 하는 것 외에도 VSPackage ´ ï ´는 범용 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 텍스트 색 지정 메커니즘입니다. 이 메커니즘에 대 한 자세한 내용은 참조 [를 사용 하 여 글꼴 및 색](../../extensibility/using-fonts-and-colors.md)합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [구문 색 지정 구현](../../extensibility/internals/implementing-syntax-coloring.md)  
 편집기에서 언어 서비스의 구문 색 지정 및 언어 서비스 해야 구문을 지원 하려면 구현 색 지정을 액세스 하는 방법을 설명 합니다.  
  
 [방법: 기본 제공 색 항목 사용](../../extensibility/internals/how-to-use-built-in-colorable-items.md)  
 언어 서비스에서 기본 제공 색 항목을 사용 하는 방법을 보여 줍니다.  
  
 [사용자 지정 색 항목](../../extensibility/internals/custom-colorable-items.md)  
 색 사용자 지정 항목을 구현 하는 방법을 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [글꼴 및 색을 사용 하 여](../../extensibility/using-fonts-and-colors.md)