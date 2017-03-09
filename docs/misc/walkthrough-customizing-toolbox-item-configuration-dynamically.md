---
title: "연습: 도구 상자 항목 구성을 동적으로 사용자 지정 | Microsoft Docs"
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
  - "도구 상자[Visual Studio SDK], 컨트롤(사용자 지정 형식) 추가"
ms.assetid: 761f44b7-c748-4ff5-921f-fc4f71784b0e
caps.latest.revision: 45
caps.handback.revision: 45
manager: "douge"
---
# 연습: 도구 상자 항목 구성을 동적으로 사용자 지정
이 연습에서는 관리되는 VSPackage가 <xref:System.Drawing.Design.ToolboxItem> 개체에 대한 동적 구성 지원을 제공할 수 있는 방법을 보여 줍니다.  
  
> [!NOTE]
>  도구 상자에 사용자 지정 컨트롤을 추가하는 가장 간단한 방법은 Visual Studio SDK에 포함된 도구 상자 컨트롤 템플릿을 사용하는 것입니다. 이 항목은 고급 도구 상자 개발과 관련이 있습니다.  
>   
>  템플릿을 사용하여 도구 상자 컨트롤을 만드는 방법에 대한 자세한 내용은 [방법: Windows Forms를 사용하는 도구 상자 컨트롤 만들기](../misc/how-to-create-a-toolbox-control-that-uses-windows-forms.md) 및 [WPF 도구 상자 컨트롤 만들기](../extensibility/creating-a-wpf-toolbox-control.md)를 참조하세요.  
  
 이 연습에서는 다음 단계를 안내합니다.  
  
1.  <xref:System.ComponentModel.ToolboxItemAttribute> 및 <xref:System.Drawing.ToolboxBitmapAttribute> 클래스를 사용하여 VSPackage 개체에서 모든 **도구 상자** 컨트롤을 추가하고 올바르게 등록합니다.  
  
2.  다음과 같은 두 가지 컨트롤을 만들고 각각에 대한 아이콘을 **도구 상자**에 추가합니다.  
  
    -   연결된 기본 <xref:System.Drawing.Design.ToolboxItem>을 선언하는 컨트롤입니다.  
  
    -   <xref:System.Drawing.Design.ToolboxItem> 클래스에서 파생된 연결된 사용자 지정 **도구 상자** 항목을 선언하는 컨트롤입니다.  
  
3.  다음 작업을 수행하여 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem>의 구현을 작성하고 등록합니다.  
  
    1.  <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> 클래스에서 파생되고 이 구현을 적용할 <xref:System.Drawing.Design.ToolboxItem> 인스턴스를 지정하는 필터 클래스 정의  
  
    2.  VSPackage에 대한 <xref:Microsoft.VisualStudio.Shell.Package> 클래스를 구현하는 클래스에 필터 클래스를 참조하는 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute> 적용  
  
4.  VSPackage에 대한 <xref:Microsoft.VisualStudio.Shell.Package> 클래스를 구현하는 클래스에 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute>를 적용하여 VSPackage를 <xref:System.Drawing.Design.ToolboxItem> 개체의 공급자로 등록합니다.  
  
5.  패키지를 로드할 때 리플렉션을 사용하여 VSPackage가 제공하는 모든 <xref:System.Drawing.Design.ToolboxItem> 개체 목록을 생성합니다.  
  
6.  <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> 및 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> 이벤트에 대한 처리기를 만듭니다. 그러면 VSPackage의 <xref:System.Drawing.Design.ToolboxItem> 개체가 올바르게 로드됩니다.  
  
7.  VSPackage에 대한 명령을 구현하여 **도구 상자**를 강제로 다시 초기화합니다.  
  
## 사전 요구 사항  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)을 참조하세요.  
  
## Visual Studio 패키지 프로젝트 템플릿의 위치  
 Visual Studio 패키지 프로젝트 템플릿은 **새 프로젝트** 대화 상자의 세 가지 서로 다른 위치에 있습니다.  
  
1.  Visual Basic 확장성에 위치한 템플릿 프로젝트의 기본 언어는 Visual Basic입니다.  
  
2.  C\# 확장성에 위치한 템플릿 프로젝트의 기본 언어는 C\#입니다.  
  
3.  다른 프로젝트 형식 확장성에 위치한 템플릿 프로젝트의 기본 언어는 C\+\+입니다.  
  
## 관리되는 VSPackage 만들기  
 관리되는 VSPackage를 만들려면 다음 절차를 완료합니다.  
  
#### 도구 상자 항목을 제공하는 관리되는 VSPackage를 만들려면  
  
1.  `ItemConfiguration`이라는 VSPackage를 만듭니다. 자세한 내용은 [연습: Visual Studio 패키지 템플릿을 사용하여 메뉴 명령 만들기](../Topic/Walkthrough:%20Creating%20a%20Menu%20Command%20By%20Using%20the%20Visual%20Studio%20Package%20Template.md)을 참조하세요.  
  
2.  **Visual Studio 패키지** 템플릿에서 메뉴 명령을 추가합니다.  
  
     명령의 이름을 Visual Basic에는 `Initialize ItemConfigurationVB`로 지정하고 Visual C\#에는 `Initialize ItemConfigurationCS`로 지정합니다.  
  
3.  [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 다음 네임스페이스를 생성된 프로젝트의 가져온 네임스페이스 목록에 추가합니다.  
  
    -   Company.ItemConfiguration  
  
    -   시스템  
  
    -   System.ComponentModel  
  
    -   System.Drawing  
  
    -   System.Windows.Forms  
  
4.  <xref:System.Drawing.Design?displayProperty=fullName> .NET Framework 구성 요소에 대한 참조를 추가합니다.  
  
 둘 이상의 언어에 대해 이 연습을 수행하는 경우 생성된 어셈블리의 차이를 명확히 구분하기 위해 프로젝트를 업데이트해야 합니다.  
  
#### Visual Basic과 Visual C\# VSPackage의 차이를 명확히 구분하려면  
  
1.  [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우:  
  
    1.  프로젝트 속성을 열고 **응용 프로그램** 탭을 선택합니다.  
  
         어셈블리 이름을 `ItemConfigurationVB`로 변경하고 기본 네임스페이스를 `Company.ItemConfigurationVB`로 변경합니다.  
  
    2.  **참조** 탭을 선택합니다.  
  
         가져온 네임스페이스 목록을 업데이트합니다.  
  
         Company.ItemConfiguration을 제거합니다.  
  
         Company.ItemConfigurationVB를 추가합니다.  
  
2.  [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]의 경우:  
  
    1.  프로젝트 속성을 열고 **응용 프로그램** 탭을 선택합니다.  
  
         어셈블리 이름을 `ItemConfigurationCS`로 변경하고 기본 네임스페이스를 `Company.ItemConfigurationCS`로 변경합니다.  
  
    2.  코드 편집기에서 ItemConfigurationPackage 클래스를 엽니다.  
  
         리팩터링 도구를 사용하여 기존 네임스페이스의 이름을 바꾸려면 기존 네임스페이스 이름인 `ItemConfiguration`를 마우스 오른쪽 단추로 클릭하고 **리팩터링**을 가리킨 다음 **이름 바꾸기**를 클릭합니다. 이름을 `ItemConfigurationCS`로 바꿉니다.  
  
3.  모든 변경 내용을 저장합니다.  
  
#### 생성된 코드를 테스트하려면  
  
1.  Visual Studio의 실험 하이브에서 VSPackage를 컴파일하고 시작합니다.  
  
2.  **도구** 메뉴에서 **항목 구성 VB 초기화** 또는 **항목 구성 CS 초기화**를 클릭합니다.  
  
     그러면 패키지의 메뉴 항목 처리기가 호출되었다고 나타내는 텍스트가 있는 메시지 상자가 열립니다.  
  
3.  실험 버전의 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]를 닫습니다.  
  
## 도구 상자 컨트롤 만들기  
 이 섹션에서는 연결된 기본 **도구 상자** 항목을 선언하는 사용자 지정 컨트롤 `Control1`을 만들고 등록합니다. 또한 두 번째 사용자 지정 컨트롤\(`Control2`\)과 연결된 사용자 지정 **도구 상자** 항목\(<xref:System.Drawing.Design.ToolboxItem> 클래스에서 파생된 `Control2_ToolboxItem`\)을 만들고 등록합니다. Windows Forms 컨트롤 및 <xref:System.Drawing.Design.ToolboxItem> 클래스를 제작하는 방법에 대한 자세한 내용은 [디자인할 때 Windows Forms 컨트롤 개발](../Topic/Developing%20Windows%20Forms%20Controls%20at%20Design%20Time.md)을 참조하세요.  
  
#### 기본 및 사용자 지정 도구 상자 항목을 만들려면  
  
1.  [연습: 도구 상자 항목 자동 로드 ](../misc/walkthrough-autoloading-toolbox-items.md)의 지침에 따라 다음과 같이 기본 **도구 상자** 항목 및 사용자 지정 **도구 상자** 항목을 만듭니다.  
  
    1.  "기본 ToolboxItem과 함께 사용할 **도구 상자** 컨트롤을 만들려면" 절차를 완료합니다. 이 프로젝트를 참조하는 <xref:System.ComponentModel.DescriptionAttribute>를 업데이트합니다.  
  
         `Control1` 클래스에 대한 결과 코드는 다음 코드와 유사합니다.  
  
         [!code-cs[DynamicToolboxMembers#01](../misc/codesnippet/CSharp/walkthrough-customizing-toolbox-item-configuration-dynamically_1.cs)]
         [!code-vb[DynamicToolboxMembers#01](../misc/codesnippet/VisualBasic/walkthrough-customizing-toolbox-item-configuration-dynamically_1.vb)]  
  
    2.  "사용자 지정 ToolboxItem에서 파생된 클래스를 사용하기 위한 **도구 상자** 컨트롤을 만들려면" 절차를 완료합니다. 이 프로젝트를 참조하는 <xref:System.ComponentModel.DescriptionAttribute>를 업데이트합니다.  
  
         `Control2` 및 `Control2_ToolboxItem` 클래스에 대한 결과 코드는 다음 코드와 유사합니다.  
  
         [!code-vb[DynamicToolboxMembers#02](../misc/codesnippet/VisualBasic/walkthrough-customizing-toolbox-item-configuration-dynamically_2.vb)]
         [!code-cs[DynamicToolboxMembers#02](../misc/codesnippet/CSharp/walkthrough-customizing-toolbox-item-configuration-dynamically_2.cs)]  
  
2.  파일을 저장합니다.  
  
## 비트맵 아이콘 포함  
 각 컨트롤에 적용되는 <xref:System.Drawing.ToolboxBitmapAttribute> 특성은 해당 컨트롤과 연결할 아이콘을 지정합니다. 두 컨트롤에 대한 비트맵을 만들고 다음과 같이 이름을 지정합니다.  
  
-   `Control1` 클래스에 대한 `Control1.bmp`  
  
-   `Control2` 클래스에 대한 `Control2.bmp`  
  
#### 도구 상자 항목에 대한 비트맵 아이콘을 포함하려면  
  
1.  다음과 같이 새 비트맵을 프로젝트에 추가합니다.  
  
    1.  **솔루션 탐색기**에서 VSPackage 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **새 항목**을 클릭합니다.  
  
    2.  **새 항목 추가** 대화 상자에서 **비트맵 파일**을 선택하고 비트맵의 이름을 입력합니다.  
  
2.  비트맵 편집기를 사용하여 다음과 같이 16x16 아이콘을 만듭니다.  
  
    1.  **보기** 메뉴에서 **속성 창**을 클릭합니다.  
  
    2.  **속성** 창에서 **높이**와 **너비**를 16으로 설정합니다.  
  
    3.  편집기를 사용하여 아이콘 이미지를 만듭니다.  
  
3.  **솔루션 탐색기**에서 비트맵 항목을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  
  
4.  **빌드 작업** 속성을 **포함 리소스**로 설정합니다.  
  
5.  열려 있는 모든 파일을 저장합니다.  
  
## 동적 도구 상자 구성 공급자 추가  
 이 섹션에서는 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> 인터페이스를 구현하는 클래스를 만들고 등록합니다. 이 클래스는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE\(통합 개발 환경\)에서 인스턴스화되고 **도구 상자** 컨트롤을 구성하는 데 사용됩니다.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 환경에서 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem>의 구현 인스턴스를 인스턴스화하기 때문에 VSPackage에 대한 <xref:Microsoft.VisualStudio.Shell.Package>를 구현하는 클래스에는 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> 인터페이스를 구현하지 마세요.  
  
#### 도구 상자 컨트롤 구성 개체를 만들고 등록하려면  
  
1.  **솔루션 탐색기**에서 ItemConfiguration 프로젝트에 클래스를 추가하고 이름을 `ToolboxConfig`로 지정합니다.  
  
2.  파일에 다음 네임스페이스 문을 추가합니다.  
  
     [!code-cs[DynamicToolboxMembers#03](../misc/codesnippet/CSharp/walkthrough-customizing-toolbox-item-configuration-dynamically_3.cs)]
     [!code-vb[DynamicToolboxMembers#03](../misc/codesnippet/VisualBasic/walkthrough-customizing-toolbox-item-configuration-dynamically_3.vb)]  
  
3.  `ToolboxConfig` 클래스가 `public`이고 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> 인터페이스를 구현하는지 확인합니다.  
  
4.  <xref:System.Runtime.InteropServices.GuidAttribute> 및 <xref:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute>를 `ToolboxConfig` 클래스`.`에 적용합니다.  
  
    -   [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 `"ItemConfigurationVB, Version=*, Culture=*, PublicKeyToken=*"`의 어셈블리 이름을 사용합니다.  
  
    -   [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]의 경우 `"ItemConfigurationCS, Version=*, Culture=*, PublicKeyToken=*"`의 어셈블리 이름을 사용합니다.  
  
     이렇게 하면 `ToolboxConfig` 클래스가 현재 VSPackage를 포함하는 어셈블리에서 제공하는 <xref:System.Drawing.Design.ToolboxItem> 개체에만 적용되도록 제한됩니다.  
  
     [!code-cs[DynamicToolboxMembers#04](../misc/codesnippet/CSharp/walkthrough-customizing-toolbox-item-configuration-dynamically_4.cs)]
     [!code-vb[DynamicToolboxMembers#04](../misc/codesnippet/VisualBasic/walkthrough-customizing-toolbox-item-configuration-dynamically_4.vb)]  
  
     **도구** 메뉴에서 **GUID 만들기**를 클릭하여 GUID를 생성할 수 있습니다.**대괄호 포함 형식**을 선택하고 **복사**를 클릭한 다음 코드에 GUID를 붙여넣습니다.`GUID` 키워드를 `Guid`로 변경합니다.  
  
5.  메서드가 두 <xref:System.Drawing.Design.ToolboxItem> 클래스인 `Control1` 및 `Control2`에만 적용되도록 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> 인터페이스의 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem.ConfigureToolboxItem%2A> 메서드를 구현합니다.  
  
     <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem.ConfigureToolboxItem%2A> 구현은 다음과 같도록 <xref:System.ComponentModel.ToolboxItemFilterAttribute> 인스턴스를 두 개의 <xref:System.Drawing.Design.ToolboxItem> 개체에 적용합니다.  
  
    -   `Control1`에 의해 구현된 <xref:System.Drawing.Design.ToolboxItem>만 <xref:System.Windows.Forms.UserControl> 개체를 처리하는 디자이너용 **도구 상자**에 제공됩니다.  
  
    -   `Control2`에 의해 구현된 <xref:System.Drawing.Design.ToolboxItem>은 <xref:System.Windows.Forms.UserControl> 개체를 처리하는 디자이너용 **도구 상자**에 제공되지 않습니다.  
  
     [!code-cs[DynamicToolboxMembers#05](../misc/codesnippet/CSharp/walkthrough-customizing-toolbox-item-configuration-dynamically_5.cs)]
     [!code-vb[DynamicToolboxMembers#05](../misc/codesnippet/VisualBasic/walkthrough-customizing-toolbox-item-configuration-dynamically_5.vb)]  
  
## VSPackage 구현 수정  
 다음 작업을 수행하려면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 패키지 템플릿에서 제공하는 VSPackage의 기본 구현을 수정해야 합니다.  
  
-   **도구 상자** 항목 공급자로 등록합니다.  
  
-   VSPackage에 대한 동적 **도구 상자** 컨트롤 구성을 제공하는 클래스를 등록합니다.  
  
-   <xref:System.Drawing.Design.ToolboxService>를 사용하여 VSPackage 어셈블리에서 제공하는 <xref:System.Drawing.Design.ToolboxItem> 개체를 모두 로드합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> 및 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> 이벤트를 처리합니다.  
  
#### VSPackage에서 도구 상자 항목 공급자에 대한 패키지 구현을 수정하려면  
  
1.  코드 편집기에서 ItemConfigurationPackage 클래스를 엽니다.  
  
2.  솔루션에서 <xref:Microsoft.VisualStudio.Shell.Package> 클래스의 구현인 `ItemConfigurationPackage` 클래스의 선언을 수정합니다.  
  
    1.  파일에 다음 네임스페이스 문을 추가합니다.  
  
         [!code-vb[DynamicToolboxMembers#06](../misc/codesnippet/VisualBasic/walkthrough-customizing-toolbox-item-configuration-dynamically_6.vb)]
         [!code-cs[DynamicToolboxMembers#06](../misc/codesnippet/CSharp/walkthrough-customizing-toolbox-item-configuration-dynamically_6.cs)]  
  
    2.  **도구 상자** 항목을 제공하도록 VSPackage를 등록하려면 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute>를 패키지에 적용합니다.**도구 상자** 컨트롤 동적 구성을 제공하도록 `ToolboxConfig` 클래스를 등록하려면 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute>를 패키지에 적용합니다.  
  
         [!code-vb[DynamicToolboxMembers#07](../misc/codesnippet/VisualBasic/walkthrough-customizing-toolbox-item-configuration-dynamically_7.vb)]
         [!code-cs[DynamicToolboxMembers#07](../misc/codesnippet/CSharp/walkthrough-customizing-toolbox-item-configuration-dynamically_7.cs)]  
  
        > [!NOTE]
        >  <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute>의 유일한 인수는 VSPackage에서 제공한 <xref:System.Drawing.Design.ToolboxItem> 버전입니다. 이전에 캐시된 <xref:System.Drawing.Design.ToolboxItem> 버전이 있는 경우에도 이 값을 변경하면 IDE에서 강제로 VSPackage를 로드합니다.  
  
    3.  `ItemConfiguration` 클래스에 두 개의 새 `private` 필드를 다음과 같이 만듭니다.  
  
         이름이 `ToolboxItemList`인 <xref:System.Collections.ArrayList> 멤버이며 `ItemConfiguration` 클래스에서 관리되는 <xref:System.Drawing.Design.ToolboxItem> 개체 목록을 유지합니다.  
  
         이름이 `CategoryTab`인 <xref:System.String>이며 `ItemConfiguration` 클래스에서 관리되는 <xref:System.Drawing.Design.ToolboxItem> 개체를 유지하는 데 사용되는 **도구 상자** 탭을 포함합니다.  
  
         [!code-vb[DynamicToolboxMembers#08](../misc/codesnippet/VisualBasic/walkthrough-customizing-toolbox-item-configuration-dynamically_8.vb)]
         [!code-cs[DynamicToolboxMembers#08](../misc/codesnippet/CSharp/walkthrough-customizing-toolbox-item-configuration-dynamically_8.cs)]  
  
     이 수정 작업의 결과는 다음 코드와 유사합니다.  
  
     [!code-vb[DynamicToolboxMembers#09](../misc/codesnippet/VisualBasic/walkthrough-customizing-toolbox-item-configuration-dynamically_9.vb)]
     [!code-cs[DynamicToolboxMembers#09](../misc/codesnippet/CSharp/walkthrough-customizing-toolbox-item-configuration-dynamically_9.cs)]  
  
3.  <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> 및 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> 이벤트를 처리할 `OnRefreshToolbox` 메서드를 정의합니다.  
  
     `OnRefreshToolbox` 메서드는 `ToolboxItemList` 필드에 포함된 <xref:System.Drawing.Design.ToolboxItem> 개체 목록을 사용하며 다음 작업을 수행합니다.  
  
    -   `CategoryTab` 필드에 정의된 **도구 상자** 탭에서 <xref:System.Drawing.Design.ToolboxItem> 개체를 모두 제거합니다.  
  
    -   `ToolboxItemList` 필드에 나열된 모든 <xref:System.Drawing.Design.ToolboxItem> 개체의 새 인스턴스를 **도구 상자** 탭에 추가합니다.  
  
    -   **도구 상자** 탭을 활성 탭으로 설정합니다.  
  
     [!code-vb[DynamicToolboxMembers#10](../misc/codesnippet/VisualBasic/walkthrough-customizing-toolbox-item-configuration-dynamically_10.vb)]
     [!code-cs[DynamicToolboxMembers#10](../misc/codesnippet/CSharp/walkthrough-customizing-toolbox-item-configuration-dynamically_10.cs)]  
  
4.  [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]에 대한 생성자에서 `OnRefreshToolbox` 메서드를 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> 및 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> 이벤트에 대한 이벤트 처리기로 등록합니다.  
  
     [!code-cs[DynamicToolboxMembers#11](../misc/codesnippet/CSharp/walkthrough-customizing-toolbox-item-configuration-dynamically_11.cs)]  
  
5.  <xref:System.Drawing.Design.ToolboxService?displayProperty=fullName> 클래스의 <xref:System.Drawing.Design.ToolboxService.GetToolboxItems%2A> 메서드를 호출하여 `ToolboxItemList` 필드를 채우도록 `ItemConfigurationPackage`의 `Initialize` 메서드를 수정합니다.**도구 상자** 서비스는 현재 실행 중인 어셈블리에 정의된 **도구 상자** 항목 클래스를 모두 가져옵니다.`ToolboxItemList` 필드는 **도구 상자** 이벤트 처리기에서 **도구 상자** 항목을 로드하는 데 사용됩니다.  
  
     `Initialize` 메서드의 끝에 다음 코드를 추가합니다.  
  
     [!code-vb[DynamicToolboxMembers#12](../misc/codesnippet/VisualBasic/walkthrough-customizing-toolbox-item-configuration-dynamically_12.vb)]
     [!code-cs[DynamicToolboxMembers#12](../misc/codesnippet/CSharp/walkthrough-customizing-toolbox-item-configuration-dynamically_12.cs)]  
  
    > [!NOTE]
    >  연습으로 VSPackage 또는 항목 버전을 테스트하기 위한 메커니즘을 개발하고 VSPackage 버전이 변경되거나 <xref:System.Drawing.Design.ToolboxItem> 버전이 변경된 경우 업데이트만 할 수 있습니다.  
  
## 도구 상자 초기화  
  
#### 도구 상자를 초기화하는 명령을 구현하려면  
  
-   `ItemConfigurationPackage` 클래스에서 메뉴 항목의 명령 처리기인 `MenuItemCallBack` 메서드를 변경합니다.  
  
     다음 코드를 사용하여 `MenuItemCallBack` 메서드의 기존 구현을 바꿉니다.  
  
     [!code-vb[DynamicToolboxMembers#13](../misc/codesnippet/VisualBasic/walkthrough-customizing-toolbox-item-configuration-dynamically_13.vb)]
     [!code-cs[DynamicToolboxMembers#13](../misc/codesnippet/CSharp/walkthrough-customizing-toolbox-item-configuration-dynamically_13.cs)]  
  
## 솔루션 빌드 및 실행  
 실험 하이브에서 실행되는 Visual Studio의 인스턴스를 사용하여 이 연습의 제품을 사용해 볼 수 있습니다.  
  
#### 이 연습을 사용해 보려면  
  
1.  Visual Studio의 **빌드** 메뉴에서 **솔루션 다시 빌드**를 클릭합니다.  
  
2.  F5 키를 눌러 실험 레지스트리 하이브에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 두 번째 인스턴스를 시작합니다.  
  
     실험 하이브를 사용하는 방법에 대한 자세한 내용은 [실험적 인스턴스](../extensibility/the-experimental-instance.md)를 참조하세요.  
  
3.  **도구** 메뉴를 클릭합니다.  
  
     **ItemConfiguration VB 초기화** 또는 **ItemConfiguration CS 초기화**라는 명령이 숫자 1을 가진 아이콘과 함께 메뉴의 맨 위에 나타납니다.  
  
4.  새 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 또는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] Windows Forms 응용 프로그램을 만듭니다.  
  
     <xref:System.Windows.Forms.Form> 기반 디자이너가 나타납니다.  
  
5.  프로젝트에 사용자 정의 컨트롤을 추가합니다.  
  
     사용자 정의 컨트롤 디자이너가 나타납니다.  
  
6.  **도구 상자**를 연 상태로 고정하고 두 디자인 뷰 간을 전환합니다.  
  
     포커스가 있는 디자이너에 따라 표시되는 **도구 상자** 항목과 숨겨지는 항목이 달라집니다.  
  
7.  첫 번째 **도구 상자** 항목을 사용자 정의 컨트롤로 끌어 `Control1` 인스턴스를 사용자 정의 컨트롤에 추가합니다.  
  
8.  두 번째 **도구 상자** 항목을 폼으로 끌어 `Control2` 인스턴스를 폼에 추가합니다.  
  
9. Windows 응용 프로그램을 빌드합니다.  
  
     이제 **도구 상자**에서 응용 프로그램에 대한 사용자 정의 컨트롤을 사용할 수 있습니다.  
  
10. 응용 프로그램의 사용자 정의 컨트롤을 폼에 추가하고 응용 프로그램을 다시 빌드하여 실행합니다.  
  
     응용 프로그램이 실행되면 폼에서 각 컨트롤을 클릭하여 연결된 메시지 상자를 가져옵니다.  
  
## 구현 분석  
 <xref:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute> 클래스 생성자에 `assemblyFilter` 매개 변수가 있으므로 `ToolboxConfg` 클래스의 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem.ConfigureToolboxItem%2A> 메서드는 이 연습에서 생성된 어셈블리의 <xref:System.Drawing.Design.ToolboxItem> 개체에만 적용됩니다.  
  
 따라서 **도구 상자**에서 **ItemConfiguration 연습** 범주가 활성화될 때마다 `ToolboxConfg` 클래스의 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem.ConfigureToolboxItem%2A> 메서드가 호출되며, `Control1` 및 `Control2`에서 구현된 <xref:System.Drawing.Design.ToolboxItem> 개체에 <xref:System.ComponentModel.ToolboxItemFilterAttribute> 인스턴스가 적용됩니다.  
  
## 참고 항목  
 [도구 상자 확장](../misc/extending-the-toolbox.md)   
 [도구 상자 지원 기능 등록](../misc/registering-toolbox-support-features.md)   
 [고급 도구 상자 컨트롤 개발](../misc/advanced-toolbox-control-development.md)   
 [도구 상자 연습](../misc/toolbox-walkthroughs.md)