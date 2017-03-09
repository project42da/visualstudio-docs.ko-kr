---
title: "Interop 어셈블리를 사용하여 옵션 페이지 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도구 옵션 페이지[Visual Studio SDK], Interop 어셈블리를 사용하여 만들기"
  - "interop 어셈블리, 도구 옵션 페이지 만들기"
ms.assetid: 7a03f2f5-a53e-4a46-877f-5b10dd82dbc3
caps.latest.revision: 30
caps.handback.revision: 30
manager: "douge"
---
# Interop 어셈블리를 사용하여 옵션 페이지 만들기
관리되는 VSPackage는 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)]의 COM 기반 interop 어셈블리를 사용하여 **도구** 메뉴에 **옵션** 페이지를 추가하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE\(통합 개발 환경\)를 확장합니다.  
  
 **도구 옵션** 페이지는 기본적으로 사용자 컨트롤이며 다른 사용자 컨트롤과 동일한 방식으로 코딩됩니다. 일반적으로 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE의 디자이너 중 하나를 사용하여 개체를 만들고 사용자 컨트롤을 추가합니다.  
  
> [!NOTE]
>  DialogProc를 사용하여 창 메시지를 처리하는 대화 상자로 구현된 **도구 옵션** 페이지는 모덜리스 대화 상자여야 하며 EndDialog 함수를 호출하지 않아야 합니다.  
  
 사용자 컨트롤이 표시하는 속성을 지원하기 위해 VSPackage가 환경에 제공하는 자동화 개체를 사용해야 합니다.  
  
 **도구 옵션** 페이지를 구현하는 VSPackage는 해당 속성의 프로그래밍 방식 제어를 직접 지원하거나 IDE의 자동화 모델을 통해 지원할 수 있습니다. 자동화를 사용하는 **도구 옵션** 페이지의 지원에 대한 자세한 내용은 [자동화를 사용하여 옵션 페이지 만들기](../misc/creating-options-pages-by-using-automation.md)를 참조하세요.  
  
## IDE에서 도구 옵션 페이지 사용  
 VSPackage는 사용자 컨트롤을 구현하는 것 이외에도 IDE에서 이 컨트롤을 사용할 수 있게 해야 합니다.  
  
 이렇게 하려면 전달된 GUID를 기반으로 하여 <xref:Microsoft.VisualStudio.Shell.Interop.VSPROPSHEETPAGE> 구조체를 반환하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> 메서드를 구현하면 됩니다.  
  
 IDE에서는 <xref:Microsoft.VisualStudio.Shell.Interop.VSPROPSHEETPAGE> 구조체를 사용하여 **속성** 페이지의 특성을 설정합니다.  
  
 해당 `dwFlags` 멤버에 포함된 설정에 따라 다른 <xref:Microsoft.VisualStudio.Shell.Interop.VSPROPSHEETPAGE> 멤버의 정확한 해석이 결정됩니다. 구조체는 일반적으로 다음을 제공합니다.  
  
-   아이콘 또는 문자열 리소스를 로드할 인스턴스에 대한 핸들  
  
-   페이지의 대화 상자 템플릿에 대한 리소스 ID  
  
-   페이지의 DialogProc에 대한 포인터  
  
## 도구 옵션 페이지 등록  
 레지스트리 위치 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\*\<Version\>*\\ToolsOptionsPages\(여기서 *\<Version\>*은 8.0과 같은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 버전\)에 항목을 만들어 **도구 옵션** 페이지를 등록할 수 있습니다.  
  
 페이지를 등록하려면 레지스트리를 수동으로 편집하거나 레지스트리 스크립트\(.rgs 파일\)를 사용할 수 있습니다. 자세한 내용은 [Creating Registrar Scripts](/visual-cpp/atl/creating-registrar-scripts)을 참조하세요.  
  
## 참고 항목  
 [Extending the Visual Studio Environment](../Topic/Extending%20the%20Visual%20Studio%20Environment.md)   
 [Creating Registrar Scripts](/visual-cpp/atl/creating-registrar-scripts)   
 [옵션 페이지에 대 한 자동화 지원](../extensibility/internals/automation-support-for-options-pages.md)   
 [옵션 페이지 사용](../misc/using-options-pages.md)   
 [옵션 페이지 만들기](../extensibility/internals/creating-options-pages.md)   
 [자동화를 사용하여 옵션 페이지 만들기](../misc/creating-options-pages-by-using-automation.md)