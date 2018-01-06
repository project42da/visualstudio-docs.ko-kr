---
title: "구문 색 사용자 지정 편집기에서 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], custom - syntax coloring
ms.assetid: 74900b9a-baef-432a-8231-4568fb5e19ad
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8c40538b34c23e88b2c680db170b9d46b7b40f62
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="syntax-coloring-in-custom-editors"></a>사용자 지정 편집기에서 색을 지정 하는 구문
코어 편집기를 포함 하 여 visual Studio 환경 SDK 편집기 특정 구문 항목을 식별 하는 지정 된 문서 보기에 대 한 지정 된 색으로 표시할 언어 서비스를 사용 합니다.  
  
## <a name="colorization-requirements"></a>색 지정 요구 사항  
 언어 서비스의 색 지정 기를 구현 하는 모든 편집기 수행 해야 합니다.  
  
1.  구현 하는 개체를 사용 하 여 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 텍스트 색이 지정 하 고 구현 하는 개체를 관리 하려면 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 텍스트의 문서 뷰를 제공 합니다.  
  
2.  언어 서비스의 식별 GUID를 사용 하 여 VSPackage의 서비스 공급자를 쿼리하여 특정 언어 서비스에 대 한 인터페이스를 가져옵니다.  
  
3.  호출 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> 구현 하는 개체의 메서드 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>합니다. 이 메서드를 사용 하 여 언어 서비스 연결의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 를 색이 지정 된 텍스트를 관리 하는 VSPackage 사용 하 여 구현 합니다.  
  
## <a name="core-editor-usage-of-a-language-services-colorizer"></a>언어 서비스의 색 지정 기의 코어 편집기 사용  
 코어 편집기, 구문 분석 및 언어 서비스의 색 지정 기 별로 텍스트의 렌더링의 인스턴스에서 언어 서비스는 색 지정 기를 가져온 경우는 사용자의 추가 작업을 수행할 필요 없이 자동으로 수행 됩니다.  
  
 IDE 투명 하 게 합니다.  
  
-   호출 하는 색 지정 기 필요에 따라 구문 분석 하 여이 추가 되거나의 구현에서 수정 하는 대로 텍스트를 분석 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>합니다.  
  
-   제공 하는 문서 보기에서 제공 표시 되도록는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 구현 업데이트 되 고는 색 지정 기에서 반환 된 정보를 사용 하 여 다시 표시 합니다.  
  
## <a name="non-core-editor-usage-of-a-language-services-colorizer"></a>언어 서비스의 색 지정 기의 비핵심 편집기 사용  
 비 코어 편집기 인스턴스 언어 서비스의 구문 색 지정 서비스를 사용할 수도 있지만 명시적으로 검색 하 고 서비스의 색 지정 기를 적용 하 고 되어야 직접 자신의 문서 보기를 다시 그립니다.  
  
 이 작업을 수행 하는 중요 하지 않은 편집기를로 필요 합니다.  
  
1.  언어 서비스의 색 지정 기 개체를 가져옵니다 (구현 하는 `T:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer` 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer2>). VSPackage이 작업을 호출 하 여 수행 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> 언어 서비스의 인터페이스에서 메서드.  
  
2.  호출 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 메서드를 특정 텍스트 범위에 색이 지정 될 요청 합니다.  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 색이 지정 되 고 걸쳐 텍스트에 각 문자에 대해 하나, 메서드는 값의 배열을 반환 합니다. 또한 텍스트 범위를 특정 유형의 주석, 키워드 또는 데이터 형식이 같은 색 항목을 식별합니다.  
  
3.  반환 된 색 지정 정보를 사용 하 여 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 다시 그려야 하 여 해당 텍스트를 표시 합니다.  
  
> [!NOTE]
>  언어 서비스의 색 지정 기를 사용 하는 것 외에도 VSPackage는 범용 Visual Studio 환경 SDK 텍스트 색 지정 메커니즘을 사용 하도록 선택할 수 있습니다. 이 메커니즘에 대 한 자세한 내용은 참조 하십시오. [를 사용 하 여 글꼴 및 색](../extensibility/using-fonts-and-colors.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [구문 색에 레거시 언어 서비스](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [구문 색 지정을 구현합니다.](../extensibility/internals/implementing-syntax-coloring.md)   
 [방법: 기본 제공 색 항목 사용](../extensibility/internals/how-to-use-built-in-colorable-items.md)   
 [사용자 지정 색 항목](../extensibility/internals/custom-colorable-items.md)