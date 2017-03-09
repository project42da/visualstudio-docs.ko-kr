---
title: "자동화를 사용하여 옵션 페이지 만들기 | Microsoft Docs"
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
  - "도구 옵션 페이지[Visual Studio SDK], 만들기"
  - "자동화[Visual Studio SDK], 도구 옵션 페이지 만들기"
ms.assetid: 05ec0337-58fe-4746-8e85-7fb97f285522
caps.latest.revision: 12
caps.handback.revision: 12
manager: "douge"
---
# 자동화를 사용하여 옵션 페이지 만들기
관리 VSPackages 사용할 수 있는 자동화 확장 하는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 추가 하 여 통합된 개발 환경 \(IDE\)  **옵션** 페이지를  **도구** 메뉴.  
  
 A  **도구 옵션** 페이지 근본적으로 사용자 컨트롤이 고 같은 방법으로 사용자 정의 컨트롤에 코드입니다.  일반적으로 중 하나를 사용 하 여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE의 디자이너 개체를 만들고 사용자 정의 컨트롤을 추가 합니다.  
  
> [!NOTE]
>  **도구 옵션** 페이지 대화 상자로 구현 상자를 사용 하는 `DialogProc` windows 메시지를 처리할 수 모덜리스 대화 상자 이어야 하며 호출 하지 않아야 합니다는 `EndDialog` 함수.  
  
 있는 VSPackage 환경으로 제공 하는 자동화 개체를 사용 합니다 사용자 정의 컨트롤 속성을 지원 합니다.  
  
## Interop 어셈블리를 구현 하는 도구 옵션 페이지에 대 한 자동화 지원  
 자동화 모델을 지원 하기 Vspackage를 작성 하 고 자동화 개체를 등록 해야 합니다.  자세한 내용은 [Vspackage에 대 한 자동화를 제공합니다.](../extensibility/internals/providing-automation-for-vspackages.md)를 참조하십시오.  
  
 때 자동화 모델을 사용 하는 코드를 호출 `DTE.Properties` 의 properties 컬렉션에는 지정 된  **도구 옵션** 페이지에서 IDE는 Vspackage의 구현으로 제공 되는 자동화 개체를 사용 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> 컬렉션을 반환 하 고 해당 구성 요소에 액세스할 수 있도록 <xref:EnvDTE.Property> 개체.  
  
 **참고** 에서 반환 하는 자동화 개체 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> \(자동화 개체가 두 개 이상 있는 VSPackage 지원할 수 있는 대로\) 제공 된 GUID에 따라 달라 집니다.  구현 하는 자동화 개체에 대 한 자세한 내용은 참조 하십시오. [옵션 페이지에 대 한 자동화 지원](../extensibility/internals/automation-support-for-options-pages.md).  
  
 A  **도구 옵션** 페이지가 두 식별자가 지정 됩니다.  첫째 식별자 항목을 포함 하는 폴더를 나타내는 문자열입니다의  **옵션** 섹션의  **도구** 메뉴.  둘째 식별자는 특정 폴더의 항목을 나타내는 문자열입니다.  자세한 내용은 [옵션 페이지 사용](../misc/using-options-pages.md)를 참조하십시오.  
  
 자동화 개체를 등록 하려면 두 레지스트리 항목이 필요 합니다.  
  
-   Hkey\_local\_machine\\software\\microsoft\\visualstudio\\에서*\< 버전* \\Packages\\*\<PackageGUID\>*\\Automation  
  
-   Hkey\_local\_machine\\software\\microsoft\\visualstudio\\에서*\<Version\>*\\AutomationProperties  
  
     위치  *\<Version\>* 의 버전이 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] \(8.0\) 및  *\<PackageGUID\>* 자동화 개체를 구현 하 여 VSPackage GUID입니다.  
  
 구성에서 AutomationProperties 레지스트리 항목의 상태에 따라는  **도구 옵션** 페이지 수 있습니다 자동으로 저장 되 고 복원 통해는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설정 메커니즘을 사용자가 선택 하는 경우는  **가져오기\/내보내기 설정** 에  **도구** 메뉴.  절약에 대 한 자세한 내용은  **도구 옵션** 설정 페이지에서 확인 [사용자 지정 옵션 페이지 등록](../misc/registering-custom-options-pages.md).  
  
 응용 프로그램의 자동화 모델에 대 한 지원을 구현 하려면 사용할 수 없으며 한  **도구 옵션** 페이지의 등록 정보 및 설정.  
  
 이러한 여러 가지 이유로 수 있습니다.  
  
-   설정을 처리 하는  **도구 옵션** 페이지는 비교적 자동화 속성 모델 지 원하는 것 보다 구조가 복잡 합니다.  
  
-   다른 응용 프로그램에서 프로그래밍 방식으로 관리 되지 않도록 필요가 그  **도구 옵션** 페이지입니다.  
  
-   특수 액세스 제어 나 보안 기능이 필요합니다.  
  
 이러한 경우 Vspackages를 구현할 수 있습니다  **도구 옵션** 페이지를 적절 한 방법으로 지원 합니다.  그러나, 해야합니다.  
  
-   설정 처리  **도구 옵션** 속성 페이지입니다.  
  
-   지 속성을 관리  **도구 옵션** 통해 상태 페이지는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설정 합니다.  
  
-   원하면 다른 응용 프로그램이 사용 하는 API를 제공의  **도구 옵션** 페이지입니다.  
  
 속성을의  **글꼴 및 색** 대화 상자 예 수는  **도구 옵션** 자동화 모델을 통해 수정할 수 없는 페이지입니다.  대신 별도 API를 기반으로 제공 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> 를 프로그래밍 방식으로 조작할 수 있도록 하는 인터페이스는  **글꼴 및 색도구 옵션** 페이지.  제어에 대 한 자세한 내용은  **글꼴 및 색도구 옵션** 페이지에서 참고 하십시오 [글꼴 및 색을 사용 하 여](../extensibility/using-fonts-and-colors.md).  
  
## 패키지 관리 프레임 워크 내에서 도구 옵션 페이지에 대 한 자동화 지원  
 설정의 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute.SupportsAutomation%2A> 의 속성의 구현 등록 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 인스턴스를 나타내기 위해에서는 패키지 관리 하는 기본 프레임 워크를 구현 하는  **도구 옵션** 페이지가 자동화를 지 원하는.  
  
 **도구 옵션** 에서 파생 페이지 <xref:Microsoft.VisualStudio.Shell.DialogPage> 재정의할 수 있는 기본 자동화 개체와 함께 제공 됩니다.  
  
 경우는  **도구 옵션** 페이지 구현 자동화를 지원 하지 않습니다, 자체 API 프로그래밍 방식 액세스를 허용 하는 구현을 제공 해야의  **도구 옵션** 페이지입니다.  
  
> [!NOTE]
>  IDE의  **글꼴 및 색** 페이지의 예입니다의  **도구 옵션** 자동화 기능을 지원 하지 않지만 액세스를 제공 하는 페이지의  **도구 옵션** 페이지 자체 API 통해.  자세한 내용은 [글꼴 및 색을 사용 하 여](../extensibility/using-fonts-and-colors.md)를 참조하십시오.  
  
## 참고 항목  
 [Extending the Visual Studio Environment](../Topic/Extending%20the%20Visual%20Studio%20Environment.md)   
 [Interop 어셈블리를 사용하여 옵션 페이지 만들기](../misc/creating-options-pages-by-using-interop-assemblies.md)   
 [옵션 페이지 만들기](../extensibility/internals/creating-options-pages.md)   
 [How to: Create Custom Options Pages](../Topic/How%20to:%20Create%20Custom%20Options%20Pages.md)   
 [Creating Registrar Scripts](/visual-cpp/atl/creating-registrar-scripts)   
 [옵션 페이지에 대 한 자동화 지원](../extensibility/internals/automation-support-for-options-pages.md)   
 [옵션 페이지 사용](../misc/using-options-pages.md)