---
title: "옵션 및 옵션 페이지 | Microsoft Docs"
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
  - "도구 옵션 페이지 [Visual Studio SDK] 관리 되는 패키지 프레임 워크 지원"
  - "관리 되는 패키지 프레임 워크, 도구 옵션 페이지 지원"
  - "지원, 도구 옵션 페이지"
  - "도구 옵션 페이지 [Visual Studio SDK] 레이아웃"
  - "도구 옵션 페이지 [Visual Studio SDK] 특성"
ms.assetid: e6c0e636-5ec3-450e-b395-fc4bb9d75918
caps.latest.revision: 34
caps.handback.revision: 34
ms.author: "gregvanl"
manager: "ghogen"
---
# 옵션 및 옵션 페이지
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

클릭 하면 **옵션** 에 **도구** 메뉴가 열립니다는 **옵션** 대화 상자입니다. 이 대화 상자의 옵션에에서는 전체적으로 옵션 페이지 라고 합니다. 탐색 창에서 트리 컨트롤 옵션 범주를 포함 하며 모든 범주 옵션 페이지입니다. 페이지를 선택 하면 오른쪽 창에 해당 옵션이 표시 됩니다. 이러한 페이지에는 VSPackage의 상태를 결정 하는 옵션의 값을 변경할 수 있습니다.  
  
## 옵션 페이지에 대 한 지원  
 <xref:Microsoft.VisualStudio.Shell.Package> 옵션 페이지와 옵션 범주를 만들기 위한 지원을 제공 합니다.<xref:Microsoft.VisualStudio.Shell.DialogPage> 클래스 옵션 페이지를 구현 합니다.  
  
 기본 구현은 <xref:Microsoft.VisualStudio.Shell.DialogPage> 사용자 속성의 일반 눈금에 공용 속성을 제공 합니다. 자체 사용자 인터페이스 \(UI\)에 있는 사용자 지정 옵션 페이지를 만들려면 페이지의 다양 한 메서드를 재정의 하 여이 동작을 사용자 지정할 수 있습니다. 자세한 내용은 [옵션 페이지 만들기](../../extensibility/creating-an-options-page.md)을 참조하세요.  
  
 <xref:Microsoft.VisualStudio.Shell.DialogPage> 클래스 구현 <xref:Microsoft.VisualStudio.Shell.IProfileManager>, 옵션 페이지 및 사용자 설정에 대 한도 지 속성을 제공 합니다. 기본 구현에서 <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> 및 <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToStorage%2A> 메서드 속성 문자열에서 변환할 수 있는 경우 레지스트리 사용자 섹션에 속성 변경 내용을 유지 합니다.  
  
## 옵션 페이지 레지스트리 경로  
 기본적으로 레지스트리 경로 옵션 페이지에서 관리 하는 속성의 조합 하 여 결정 <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A>, DialogPage, word 및 옵션 페이지 클래스의 형식 이름입니다. 예를 들어 옵션 페이지 클래스는 다음과 같이 정의 됩니다.  
  
 [!CODE [VSSDKSupportForOptionsPages#1](../CodeSnippet/VS_Snippets_VSSDK/vssdksupportforoptionspages#1)]  
  
 하는 경우는 <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A> HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\8.0Exp, 속성 이름 및 값 쌍은 HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\8.0Exp\\DialogPage\\Company.OptionsPage.OptionsPageGeneral의 하위 키가 있습니다.  
  
 옵션 페이지 자체의 레지스트리 경로 결합 하 여 결정 됩니다 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>, 단어, ToolsOptionsPages, 그리고 옵션 페이지 범주 및 이름입니다. 예를 들어 사용자 지정 옵션 페이지에는 범주 내 옵션 페이지 및 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A> 옵션 페이지에는 레지스트리 키에 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\8.0Exp\\ToolsOptionsPages\\My 옵션 Pages\\Custom HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\8.0Exp, 됩니다.  
  
## 도구\/옵션 페이지 특성 및 레이아웃  
 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 특성 결정 사용자 지정 옵션 페이지의 탐색 트리에서 범주로 그룹화는 **옵션** 대화 상자입니다.<xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 특성 인터페이스를 제공 하는 VSPackage 옵션 페이지에 연결 합니다. 다음과 같은 코드 조각을 생각해 봅시다.  
  
 [!CODE [VSSDKSupportForOptionsPages#2](../CodeSnippet/VS_Snippets_VSSDK/vssdksupportforoptionspages#2)]  
  
 이 선언 MyPackage OptionsPageGeneral 및 OptionsPageCustom 두 옵션 페이지를 제공 합니다. 에 **옵션** 대화 상자에 표시 된 두 옵션 페이지의 **내 옵션 페이지** 범주에 속하는 **일반** 및 **사용자 지정**, 각각.  
  
## 옵션 특성 및 레이아웃  
 사용자 지정 옵션 페이지의 옵션의 모양을 결정 하는 페이지를 제공 하는 사용자 인터페이스 \(UI\). 레이아웃, 레이블 지정, 및에 대 한 일반 옵션 페이지의 옵션을 설명은 다음 특성으로 결정 됩니다.  
  
-   <xref:System.ComponentModel.CategoryAttribute> 옵션의 범주를 결정합니다.  
  
-   <xref:System.ComponentModel.DisplayNameAttribute> 옵션의 표시 이름을 결정합니다.  
  
-   <xref:System.ComponentModel.DescriptionAttribute> 옵션의 설명에 따라 결정 됩니다.  
  
    > [!NOTE]
    >  문자열 리소스를 사용 하 여 지역화를 위한 및에 정의 된 해당 하는 특성, SRCategory, LocDisplayName, 및 SRDescription는 [관리 되는 프로젝트 샘플](http://go.microsoft.com/fwlink/?LinkId=122774)합니다.  
  
 다음과 같은 코드 조각을 생각해 봅시다.  
  
 [!CODE [VSSDKSupportForOptionsPages#3](../CodeSnippet/VS_Snippets_VSSDK/vssdksupportforoptionspages#3)]  
  
 OptionInteger 옵션이 옵션 페이지에 표시 되는 **정수 옵션** 에 **내 옵션** 범주입니다. 옵션을 선택 하는 경우 설명을 **내 정수 옵션**, 설명 상자에 나타납니다.  
  
## 다른 VSPackage에서 옵션 페이지에 액세스  
 자동화 모델을 사용 하 여 다른 VSPackage에서 호스팅하고 옵션 페이지를 관리 하는 VSPackage는 프로그래밍 방식으로 액세스할 수 있습니다. 예를 들어 다음 코드에서 VSPackage 옵션 페이지를 호스팅하는 것으로 등록 됩니다.  
  
 [!CODE [VSSDKSupportForOptionsPages#4](../CodeSnippet/VS_Snippets_VSSDK/vssdksupportforoptionspages#4)]  
  
 다음 코드에서는 MyOptionPage에서 OptionInteger의 값을 가져옵니다.  
  
 [!CODE [VSSDKSupportForOptionsPages#5](../CodeSnippet/VS_Snippets_VSSDK/vssdksupportforoptionspages#5)]  
  
 때는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 옵션 페이지를 등록 하는 특성, AutomationProperties 키 경우 아래에서 등록 하는 페이지는 `SupportsAutomation` 특성의 인수는 `true`합니다. 자동화 연결된 VSPackage 및 자동화를 찾으려면이 레지스트리 항목을 검사 한 다음 호스팅된 옵션 페이지를 통해이 경우 그리드 페이지 내 속성에 액세스 합니다.  
  
 자동화 속성의 레지스트리 경로 결합 하 여 결정 됩니다 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>, 단어, AutomationProperties, 그리고 옵션 페이지 범주 및 이름입니다. 예를 들어 옵션 페이지에서 My Category 범주를 내 그리드 페이지 이름 및 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>, HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\8.0Exp, 다음 자동화 속성에는 레지스트리 키가 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\8.0Exp\\AutomationProperties\\My Category\\My 그리드 페이지입니다.  
  
> [!NOTE]
>  정식 이름 Category.My 그리드 페이지 내에이 키의 이름 하위 키의 값입니다.