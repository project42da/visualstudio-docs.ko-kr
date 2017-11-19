---
title: "옵션 및 옵션 페이지 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tools Options pages [Visual Studio SDK], managed package framework support
- managed package framework, Tools Options pages support
- support, Tools Options pages
- Tools Options pages [Visual Studio SDK], layouts
- Tools Options pages [Visual Studio SDK], attributes
ms.assetid: e6c0e636-5ec3-450e-b395-fc4bb9d75918
caps.latest.revision: "34"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 665567430ac9fdfdc301329972a3a4f7b621a241
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="options-and-options-pages"></a>옵션 및 옵션 페이지
클릭 하면 **옵션** 에 **도구** 메뉴가 열립니다는 **옵션** 대화 상자. 이 대화 상자에서 옵션 전체적으로 옵션 페이지 라고 합니다. 탐색 창에서 트리 컨트롤 옵션 범주를 포함 되 고 모든 범주 옵션 페이지를 포함 합니다. 페이지를 선택 하면 해당 옵션이 오른쪽 창에 나타납니다. 이러한 페이지에는 VSPackage의 상태를 결정 하는 옵션의 값을 변경할 수 있습니다.  
  
## <a name="support-for-options-pages"></a>옵션 페이지에 대 한 지원  
 <xref:Microsoft.VisualStudio.Shell.Package> 클래스 옵션 페이지와 옵션 범주를 만들어에 대 한 지원을 제공 합니다. <xref:Microsoft.VisualStudio.Shell.DialogPage> 클래스 옵션 페이지를 구현 합니다.  
  
 기본 구현은 <xref:Microsoft.VisualStudio.Shell.DialogPage> 속성의 일반 눈금의 사용자에 게 공용 속성을 제공 합니다. 자체 사용자 인터페이스 (UI)에 있는 사용자 지정 옵션 페이지를 만들려면 페이지의 다양 한 메서드를 재정의 하 여이 동작을 사용자 지정할 수 있습니다. 자세한 내용은 참조 [옵션 페이지 만들기](../../extensibility/creating-an-options-page.md)합니다.  
  
 <xref:Microsoft.VisualStudio.Shell.DialogPage> 클래스 구현 <xref:Microsoft.VisualStudio.Shell.IProfileManager>, 옵션 페이지에 대 한 및 사용자 설정에 대 한도 지 속성을 제공 합니다. 기본 구현과 <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> 및 <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToStorage%2A> 메서드와 문자열 속성을 변환할 수 있는 경우 레지스트리의 사용자 부분에 속성 변경 내용을 유지 합니다.  
  
## <a name="options-page-registry-path"></a>옵션 페이지 레지스트리 경로  
 기본적으로 레지스트리 경로 옵션 페이지에서 관리 하는 속성의 결정에 결합 하 여 <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A>, DialogPage, word 및 옵션 페이지 클래스의 형식 이름입니다. 예를 들어 옵션 페이지 클래스는 다음과 같이 정의할 수 있습니다.  
  
 [!code-csharp[VSSDKSupportForOptionsPages#1](../../extensibility/internals/codesnippet/CSharp/options-and-options-pages_1.cs)]
 [!code-vb[VSSDKSupportForOptionsPages#1](../../extensibility/internals/codesnippet/VisualBasic/options-and-options-pages_1.vb)]  
  
 경우는 <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A> HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0Exp, 속성 이름 / 값 쌍은 HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0Exp\DialogPage\의 하위 키가 Company.OptionsPage.OptionsPageGeneral 합니다.  
  
 옵션 페이지 자체의 레지스트리 경로 결합 하 여 결정 됩니다 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>, 단어, ToolsOptionsPages, 및 옵션 페이지 범주 및 이름입니다. 예를 들어, 사용자 지정 옵션 페이지의 내 옵션 페이지, 범주 및 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A> HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp, 옵션 페이지에 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ 레지스트리 키가 VisualStudio\8.0Exp\ToolsOptionsPages\My 옵션 Pages\Custom 합니다.  
  
## <a name="toolsoptions-page-attributes-and-layout"></a>도구/옵션 페이지 특성 및 레이아웃  
 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 특성 결정 사용자 지정 옵션 페이지의 탐색 트리에서 범주로 그룹화 된 **옵션** 대화 상자. <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 특성 인터페이스를 제공 하는 VSPackage 옵션 페이지에 연결 합니다. 다음과 같은 코드 조각을 생각해 봅시다.  
  
 [!code-csharp[VSSDKSupportForOptionsPages#2](../../extensibility/internals/codesnippet/CSharp/options-and-options-pages_2.cs)]
 [!code-vb[VSSDKSupportForOptionsPages#2](../../extensibility/internals/codesnippet/VisualBasic/options-and-options-pages_2.vb)]  
  
 이 선언 MyPackage OptionsPageGeneral 및 OptionsPageCustom 두 옵션 페이지를 제공 합니다. 에 **옵션** 대화 상자에서는 두 옵션 페이지에 표시는 **옵션 페이지의 내** 범주도 **일반** 및 **사용자 지정**각각.  
  
## <a name="option-attributes-and-layout"></a>옵션 특성 및 레이아웃  
 이 페이지에 제공 하는 사용자 인터페이스 (UI)에 사용자 지정 옵션 페이지의 옵션의 모양을 결정 합니다. 레이아웃, 레이블 지정 및 설명의 일반 옵션 페이지의 옵션은 다음 특성으로 결정 됩니다.  
  
-   <xref:System.ComponentModel.CategoryAttribute>옵션의 범주를 결정합니다.  
  
-   <xref:System.ComponentModel.DisplayNameAttribute>옵션의 표시 이름을 결정합니다.  
  
-   <xref:System.ComponentModel.DescriptionAttribute>옵션의 설명에 따라 결정 됩니다.  
  
    > [!NOTE]
    >  해당 특성, SRCategory, LocDisplayName, SRDescription, 지역화에 대 한 문자열 리소스를 사용 하 여 및에 정의 된는 [관리 되는 프로젝트 샘플](http://go.microsoft.com/fwlink/?LinkId=122774)합니다.  
  
 다음과 같은 코드 조각을 생각해 봅시다.  
  
 [!code-csharp[VSSDKSupportForOptionsPages#3](../../extensibility/internals/codesnippet/CSharp/options-and-options-pages_3.cs)]
 [!code-vb[VSSDKSupportForOptionsPages#3](../../extensibility/internals/codesnippet/VisualBasic/options-and-options-pages_3.vb)]  
  
 OptionInteger 옵션이 옵션 페이지에 표시 되는 **정수 옵션** 에 **내 옵션** 범주입니다. 옵션을 선택 하는 경우 설명을 **내 정수 옵션**, 설명 상자에 나타납니다.  
  
## <a name="accessing-options-pages-from-another-vspackage"></a>다른 VSPackage에서 옵션 페이지에 액세스  
 자동화 모델을 사용 하 여 다른 VSPackage에서 호스트 하 고 옵션 페이지를 관리 하는 VSPackage는 프로그래밍 방식으로 액세스할 수 있습니다. 예를 들어 다음 코드에서 VSPackage 옵션 페이지를 호스팅하는 것으로 등록 됩니다.  
  
 [!code-csharp[VSSDKSupportForOptionsPages#4](../../extensibility/internals/codesnippet/CSharp/options-and-options-pages_4.cs)]
 [!code-vb[VSSDKSupportForOptionsPages#4](../../extensibility/internals/codesnippet/VisualBasic/options-and-options-pages_4.vb)]  
  
 다음 코드 조각은 MyOptionPage에서 OptionInteger의 값을 가져옵니다.  
  
 [!code-csharp[VSSDKSupportForOptionsPages#5](../../extensibility/internals/codesnippet/CSharp/options-and-options-pages_5.cs)]
 [!code-vb[VSSDKSupportForOptionsPages#5](../../extensibility/internals/codesnippet/VisualBasic/options-and-options-pages_5.vb)]  
  
 경우는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 특성 옵션 페이지 등록, AutomationProperties 키 경우 아래에서 등록 하는 페이지는 `SupportsAutomation` 특성의 인수는 `true`합니다. 자동화 연결된 VSPackage 및 자동화를 찾으려면이 레지스트리 항목을 검사 하 여 다음 페이지를 통해 호스팅된 옵션,이 경우 그리드 페이지 내 속성에 액세스 합니다.  
  
 자동화 속성의 레지스트리 경로 결합 하 여 결정 됩니다 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>, 단어, AutomationProperties, 및 옵션 페이지 범주 및 이름입니다. 예를 들어, 옵션 페이지의 내 그리드 페이지 이름을 내 범주 범주 및 <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp를 보내어 자동화 속성이 레지스트리 키를 HKEY_LOCAL_MACHINE\SOFTWARE\ Microsoft\VisualStudio\8.0Exp\AutomationProperties\My Category\My 그리드 페이지입니다.  
  
> [!NOTE]
>  정식 이름 내 Category.My 그리드 페이지에는이 키의 이름 하위 키의 값입니다.