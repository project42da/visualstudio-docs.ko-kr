---
title: "사용자 지정 편집기에서 색을 지정 하는 구문 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 사용자 지정-구문 색 지정"
ms.assetid: 74900b9a-baef-432a-8231-4568fb5e19ad
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 사용자 지정 편집기에서 색을 지정 하는 구문
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

코어 편집기를 포함 하 여 Visual Studio 환경 SDK 편집기, 구문 항목을 확인 하 고 지정 된 색이 지정 된 문서 보기를 표시할 언어 서비스 수 있습니다.  
  
## 색 지정 요구 사항  
 모든 편집기 colorizer 언어 서비스를 구현 해야 합니다.  
  
1.  구현 하는 개체 사용 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 텍스트를 조정 하 게 하 고 구현 하는 개체를 관리할 수 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 텍스트 문서 보기를 제공 합니다.  
  
2.  특정 언어 서비스 인터페이스 언어 서비스 식별 GUID를 사용 하 여 VSPackage 서비스 공급자를 쿼리하여 얻을.  
  
3.  호출 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A> 메서드를 구현 하는 개체의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>.  이 메서드는 언어 서비스와 연결을 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> 조정 하 게 하는 것은 텍스트를 관리할 수 있는 Vspackage를 사용 하 여 구현 합니다.  
  
## Colorizer는 언어 서비스의 핵심 편집기 사용  
 언어 서비스는 colorizer와 코어 편집기, 구문 분석 및 언어 서비스를 colorizer로 텍스트 렌더링 인스턴스 때 얻을입니다 사용자의 추가 개입 없이도 자동으로 발생 합니다.  
  
 IDE 투명 하 게 합니다.  
  
-   호출 구문 분석 추가 되거나 구현에 수정할 텍스트를 분석 하 고 필요에 따라 해당 colorizer <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>.  
  
-   이렇게 하면 디스플레이 제공 문서 보기에서 제공 됩니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 구현 업데이트 되어 colorizer로 반환 되는 정보를 사용 하 여 다시 표시 합니다.  
  
## Colorizer 언어 서비스의 핵심 편집기 사용  
 가 해야 명시적으로 검색 및 서비스의 colorizer 적용 하 고 해당 문서 보기를 다시 표시 하지 않은 코어 편집기 인스턴스 언어 서비스를 구문 색 지정 서비스를 사용할 수도 있습니다.  
  
 이 위해서는 핵심 편집기를 필요 합니다.  
  
1.  언어 서비스의 colorizer 개체를 가져온 \(어떤 구현 `T:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer` 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer2>\).  이 호출 하 여 작업 수행 하면 Vspackage를 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> 언어 서비스의 인터페이스에 메서드.  
  
2.  호출 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 메서드는 텍스트의 특정 범위를 조정 하 게 요청 합니다.  
  
     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 메서드 반환 값의 배열, 각 텍스트에서 문자에 대 한 하나에 걸쳐 다른 색으로 표시 하 고 있습니다.  또한 특정 색 항목, 설명, 키워드, 데이터 형식 등의 형식으로 텍스트 범위를 식별합니다.  
  
3.  사용 하 여 반환 되는 색 조정 정보 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 다시 표시 하 고 해당 텍스트를 표시 합니다.  
  
> [!NOTE]
>  Colorizer 언어 서비스를 사용 하는 외에 일반 용도의 Visual Studio 환경 SDK 텍스트 색 지정 메커니즘을 사용 하는 VSPackage 선택할 수 있습니다.  이 메커니즘에 대 한 자세한 내용은 [글꼴 및 색을 사용 하 여](../extensibility/using-fonts-and-colors.md).  
  
## 참고 항목  
 [구문 레거시 언어 서비스에 색 지정](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [구문 색 지정을 구현합니다.](../extensibility/internals/implementing-syntax-coloring.md)   
 [방법: 기본 제공 색 항목을 사용 하 여](../extensibility/internals/how-to-use-built-in-colorable-items.md)   
 [사용자 지정 색 항목](../extensibility/internals/custom-colorable-items.md)