---
title: "구문 색 지정을 구현합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "구문 색 지정, 구현"
  - "텍스트의 색을 지정 하는 편집기 [Visual Studio SDK]"
  - "텍스트를 편집기에서 색 지정"
ms.assetid: 96e762ca-efd0-41e7-8958-fda4897c8c7a
caps.latest.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 20
---
# 구문 색 지정을 구현합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

구문 색 지정을 제공 하는 언어 서비스 파서 텍스트 줄의 색 항목을 배열로 변환 하 고 이러한 색 항목에 해당 하는 토큰 형식을 반환 합니다. 파서는 색 항목 목록에 속해 있는 토큰 유형을 반환 해야 합니다.[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 적절 한 토큰 유형이 colorizer 개체에 의해 할당 된 속성에 따라 코드 창에서 각 색 항목을 표시 합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 파서 인터페이스를 지정 하지 않는 속도가 파서 구현 완전히 달려 있습니다. 그러나 Visual Studio 언어 패키지 프로젝트에서 기본 파서 구현이 제공 됩니다. 관리 되는 패키지 프레임 워크 \(MPF\)는 관리 코드에 대 한 텍스트의 색을 지정 하는 것에 대 한 완벽 한 지원이 제공 합니다.  
  
 레거시 언어 서비스는 VSPackage의 일부로 구현 되는 하지만 MEF 확장을 사용 하는 언어 서비스 기능을 구현 하는 새로운 방법입니다. 구문 색 지정을 구현 하는 새로운 방법에 대 한 자세한 내용을 참조 하십시오 [연습: 텍스트를 강조 표시](../../extensibility/walkthrough-highlighting-text.md)합니다.  
  
> [!NOTE]
>  새 편집기 API를 최대한 빨리 사용을 시작 하는 것이 좋습니다. 이 언어 서비스의 성능을 향상 하 고 새로운 편집기 기능을 이용할 수 있도록 합니다.  
  
## 텍스트 색을 지정 하는 편집기에서 다음 단계  
  
1.  편집기의 색 지정 기를 호출 하 여 가져옵니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A> 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> 개체입니다.  
  
2.  편집기를 호출 하 여는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.GetStateMaintenanceFlag%2A> 각 줄의 색 지정 기 외부 유지 관리의 상태는 색 지정 기에 필요한 지 여부를 결정할 수 있습니다.  
  
3.  편집기를 호출 하는 colorizer 상태를는 colorizer 외부 유지가 필요한 경우는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.GetStartState%2A> 메서드는 첫 번째 줄의 상태를 가져옵니다.  
  
4.  편집기를 호출 하면 버퍼의 각 줄에 대 한는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 메서드를 다음 단계를 수행 합니다.  
  
    1.  텍스트 줄의 텍스트를 토큰으로 변환할 수 스캐너에 전달 됩니다. 각 토큰에는 토큰 텍스트와 토큰 형식을 지정합니다.  
  
    2.  토큰 유형이 색 항목 목록에 대 한 인덱스 변환 됩니다.  
  
    3.  토큰 정보는 줄의 문자에 해당 하는 배열의 각 요소를 배열에 채우는 데 사용 됩니다. 배열에 저장 된 값에는 색 항목 목록에는 인덱스입니다.  
  
    4.  줄의 끝에서 상태는 각 줄에 대해 반환 됩니다.  
  
5.  편집기는 colorizer 상태를 유지가 필요한 경우 해당 줄에 대 한 상태를 캐시 합니다.  
  
6.  반환 되는 정보를 사용 하 여 텍스트의 줄을 렌더링 하는 편집기는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 메서드. 이 경우 다음 단계를 수행해야 합니다.  
  
    1.  각 문자는 줄에 대 한 색 항목 인덱스를 가져옵니다.  
  
    2.  기본 색 항목을 사용 하는 경우 편집기의 색 항목 목록에 액세스 합니다.  
  
    3.  그렇지 않은 경우 언어 서비스를 호출 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem%2A> 메서드 색 항목에 얻으려고 합니다.  
  
    4.  화면에 텍스트를 렌더링 하는 색 항목의 정보를 사용 합니다.  
  
## 관리 되는 패키지 프레임 워크 색 지정 기  
 관리 되는 패키지 프레임 워크 \(MPF\)는 colorizer를 구현 하는 데 필요한 모든 클래스를 제공 합니다. 언어 서비스 클래스에서 상속 해야는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스 하 고 필요한 메서드를 구현 합니다. 구현 하 여 스캐너 및 파서를 제공 해야는 <xref:Microsoft.VisualStudio.Package.IScanner> 에서 해당 인터페이스의 인스턴스를 반환 하 고 인터페이스를 <xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner%2A> 메서드 \(에서 구현 해야 하는 방법 중 하나는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스\). 자세한 내용은 [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)을 참조하세요.  
  
## 참고 항목  
 [방법: 기본 제공 색 항목을 사용 하 여](../../extensibility/internals/how-to-use-built-in-colorable-items.md)   
 [사용자 지정 색 항목](../../extensibility/internals/custom-colorable-items.md)   
 [언어 서비스 개발](../../extensibility/internals/developing-a-legacy-language-service.md)   
 [레거시 언어 서비스의 구문 색 지정](../../extensibility/internals/syntax-colorizing-in-a-legacy-language-service.md)