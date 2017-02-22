---
title: "포함 된 언어 | Microsoft Docs"
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
  - "편집기 [Visual Studio SDK] 레거시-포함 된 언어"
ms.assetid: b75bbb51-8e42-41b1-bece-09ab0b1f03cc
caps.latest.revision: 18
caps.handback.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
---
# 포함 된 언어
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

*언어에 포함 된* 는 다른 언어에 포함 된 언어입니다.  예를 들어, HTML에서 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 페이지가 포함 될 수 있습니다 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 또는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 스크립트입니다.  이중 언어 아키텍처는.aspx 파일 편집기에서 HTML과 스크립팅 언어에 대 한 IntelliSense, 색 처리 및 기타 편집 기능을 제공 하는 데 필요한입니다.  
  
## 구현  
 인터페이스에 포함 된 언어에 대 한 구현 하는 데 가장 중요 한 것은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> 인터페이스입니다.  내의 기본 언어를 호스팅할 수 있습니다 모든 언어에서이 인터페이스를 구현 합니다.  언어 서비스 colorizer, 텍스트 보기 필터 및 기본 언어 서비스 ID에 액세스할 수 있습니다.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory> 만들 수는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> 인터페이스입니다.  다음 단계에 포함 된 언어를 구현 하는 방법을 보여 줍니다.  
  
1.  사용 `QueryService()` 언어의 인터페이스 ID 및 서비스 ID를 가져올 수 있는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory>.  
  
2.  호출 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory.GetLanguage%2A> 메서드를 만들 수는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> 인터페이스입니다.  전달 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 인터페이스 항목 ID \(는 하나 이상의 <xref:Microsoft.VisualStudio.VSConstants.VSITEMID_NIL>, <xref:Microsoft.VisualStudio.VSConstants.VSITEMID_ROOT>, 또는 <xref:Microsoft.VisualStudio.VSConstants.VSITEMID_SELECTION>\) 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> 인터페이스.  
  
3.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> 텍스트 버퍼 코디네이터 개체는 인터페이스를 기본 파일에서 위치 버퍼는 보조 언어에 대응 하는 데 필요한 기본적인 서비스를 제공 합니다.  
  
     예를 들어, 단일.aspx 파일에는 ASP, HTML 및 포함 된 모든 코드가 주 파일이 포함 되어 있습니다.  그러나 보조 버퍼 방금 보조 버퍼 확인 하십시오 올바른 코드 파일에 클래스 정의 함께 포함 된 코드를 포함 합니다.  버퍼 코디네이터 하나 이상의 버퍼에서 편집 하 여 다른 조정 작업을 처리 합니다.  
  
4.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetSpanMappings%2A> 기본 언어인 메서드를 보조 버퍼에서 해당 텍스트를 텍스트 버퍼 내에서 매핑된 버퍼 코디네이터에 지시 합니다.  
  
     언어의 배열에 전달의 <xref:Microsoft.VisualStudio.TextManager.Interop.NewSpanMapping> 현재 기본 및 보조 범위는 포함 하는 구조입니다.  
  
5.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapPrimaryToSecondarySpan%2A> 메서드 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapSecondaryToPrimarySpan%2A> 메서드에서 차 보조 버퍼 및 그 반대로의 매핑이 제공.