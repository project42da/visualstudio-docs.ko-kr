---
title: "연습: 도구 상자 항목 자동 로드  | Microsoft Docs"
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
  - "도구 상자[Visual Studio SDK], 리플렉션을 사용하여 컨트롤 추가"
  - "리플렉션, 도구 상자"
ms.assetid: b03c0d62-3be0-475f-b1d9-725dee993ad6
caps.latest.revision: 56
caps.handback.revision: 56
manager: "douge"
---
# 연습: 도구 상자 항목 자동 로드 
이 연습에서는 관리되는 VSPackage가 리플렉션을 사용하여 자체 어셈블리에서 제공된 모든 <xref:System.Drawing.Design.ToolboxItem> 항목을 자동으로 로드하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  도구 상자에 사용자 지정 컨트롤을 추가하려면 자동 로드 지원이 포함된 Visual Studio SDK와 함께 제공되는 도구 상자 컨트롤 템플릿을 사용하는 것이 좋습니다. 이 항목은 이전 버전과의 호환성, 도구 상자에 기존 컨트롤 추가 및 고급 도구 상자 개발을 위한 것입니다.  
>   
>  템플릿을 사용하여 도구 상자 컨트롤을 만드는 방법에 대한 자세한 내용은 [방법: Windows Forms를 사용하는 도구 상자 컨트롤 만들기](../misc/how-to-create-a-toolbox-control-that-uses-windows-forms.md) 및 [WPF 도구 상자 컨트롤 만들기](../extensibility/creating-a-wpf-toolbox-control.md)를 참조하세요.  
  
 이 연습에서는 다음 단계를 안내합니다.  
  
1.  <xref:System.ComponentModel.ToolboxItemAttribute>, <xref:System.Drawing.ToolboxBitmapAttribute> 및 <xref:System.ComponentModel.DisplayNameAttribute>를 사용하여 VSPackage 개체에서 모든 **도구 상자** 컨트롤을 추가하고 올바르게 등록합니다.  
  
2.  다음과 같은 두 가지 컨트롤을 만들고 각각에 대한 아이콘을 **도구 상자**에 추가합니다.  
  
    -   기본 <xref:System.Drawing.Design.ToolboxItem> 클래스를 사용하여 한 컨트롤을 추가합니다.  
  
    -   <xref:System.Drawing.Design.ToolboxItem> 클래스에서 파생된 사용자 지정 클래스를 사용하여 다른 컨트롤을 추가합니다.  
  
3.  <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute> 클래스가 있는 <xref:System.Drawing.Design.ToolboxItem> 개체를 제공하는 VSPackage 패키지를 등록합니다.  
  
4.  로드될 때 리플렉션을 사용하여 VSPackage가 제공하는 모든 <xref:System.Drawing.Design.ToolboxItem> 개체 목록을 생성합니다.  
  
5.  <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> 및 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> 이벤트에 대한 처리기를 만듭니다. 그러면 VSPackage의 <xref:System.Drawing.Design.ToolboxItem> 개체가 반드시 올바르게 로드됩니다.  
  
6.  VSPackage에 대한 명령을 구현하여 **도구 상자**를 강제로 다시 초기화합니다.  
  
## 사전 요구 사항  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 [Visual Studio 개요 확장](../Topic/Extending%20Visual%20Studio%20Overview.md)을 참조하세요.  
  
## Visual Studio 패키지 프로젝트 템플릿의 위치  
 Visual Studio 패키지 프로젝트 템플릿은 **새 프로젝트** 대화 상자의 세 가지 서로 다른 위치에 있습니다.  
  
1.  Visual Basic 확장성에 위치한 템플릿 프로젝트의 기본 언어는 Visual Basic입니다.  
  
2.  C\# 확장성에 위치한 템플릿 프로젝트의 기본 언어는 C\#입니다.  
  
3.  다른 프로젝트 형식 확장성에 위치한 템플릿 프로젝트의 기본 언어는 C\+\+입니다.  
  
## 관리되는 VSPackage 만들기  
  
#### LoadToolboxMembers VSPackage를 만들려면  
  
1.  `LoadToolboxMembers`라는 VSPackage를 만듭니다. 자세한 내용은 [연습: Visual Studio 패키지 템플릿을 사용하여 메뉴 명령 만들기](../Topic/Walkthrough:%20Creating%20a%20Menu%20Command%20By%20Using%20the%20Visual%20Studio%20Package%20Template.md)을 참조하세요.  
  
2.  메뉴 명령을 추가합니다.  
  
     명령의 이름을 Visual Basic에는 `Initialize LoadToolboxMembers VB`로 지정하고 Visual C\#에는 `Initialize LoadToolboxMembers CS`로 지정합니다.  
  
 둘 이상의 언어에 대해 이 연습을 수행하는 경우 생성된 어셈블리의 차이를 명확히 구분하기 위해 프로젝트를 업데이트해야 합니다.  
  
#### Visual Basic과 Visual C\# VSPackage의 차이를 명확히 구분하려면  
  
1.  [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우:  
  
    -   **솔루션 탐색기**에서 프로젝트 속성을 열고 **응용 프로그램** 탭을 선택합니다.  
  
         어셈블리 이름을 `LoadToolboxMembersVB`로 변경하고 기본 네임스페이스를 `Company.LoadToolboxMembersVB`로 변경합니다.  
  
2.  [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]의 경우:  
  
    1.  **솔루션 탐색기**에서 프로젝트 속성을 열고 **응용 프로그램** 탭을 선택합니다.  
  
         어셈블리 이름을 `LoadToolboxMembersCS`로 변경하고 기본 네임스페이스를 `Company.LoadToolboxMembersCS`로 변경합니다.  
  
    2.  코드 편집기에서 LoadToolboxMembersPackage 클래스를 엽니다.  
  
         리팩터링 도구를 사용하여 기존 네임스페이스의 이름을 바꾸려면 기존 네임스페이스 이름인 `LoadToolboxMembers`를 마우스 오른쪽 단추로 클릭하고 **리팩터링**을 가리킨 다음 **이름 바꾸기**를 클릭합니다. 이름을 `LoadToolboxMembersCS`로 바꿉니다.  
  
3.  모든 변경 내용을 저장합니다.  
  
#### 지원하는 참조를 추가하려면  
  
1.  LoadToolboxMembers 프로젝트에서 다음과 같이 <xref:System.Drawing.Design?displayProperty=fullName> .NET Framework 구성 요소에 참조를 추가합니다.  
  
    1.  **솔루션 탐색기**에서 LoadToolboxMembers 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **추가**, **참조**를 차례로 클릭합니다.  
  
    2.  **참조** 대화 상자의 **.NET** 탭에서 **System.Drawing.Design**을 두 번 클릭합니다.  
  
2.  Visual Basic의 경우 다음 네임스페이스를 프로젝트의 가져온 네임스페이스 목록에 추가합니다.  
  
    -   Company.LoadToolboxMembersVB  
  
    -   시스템  
  
    -   System.ComponentModel  
  
    -   System.Drawing  
  
    -   System.Windows.Forms  
  
#### 생성된 코드를 테스트하려면  
  
1.  Visual Studio의 실험 하이브에서 VSPackage를 컴파일하고 시작합니다.  
  
2.  **도구** 메뉴에서 **LoadToolboxMembers VB 초기화** 또는 **LoadToolboxMembers CS 초기화**를 클릭합니다.  
  
     그러면 패키지의 메뉴 항목 처리기가 호출되었다고 나타내는 텍스트가 있는 메시지 상자가 열립니다.  
  
3.  실험 버전의 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]를 닫습니다.  
  
## 도구 상자 컨트롤 만들기  
 이 섹션에서는 연결된 기본 **도구 상자** 항목을 선언하는 사용자 지정 컨트롤 `Control1`을 만들고 등록합니다. Windows Form 컨트롤 및 <xref:System.Drawing.Design.ToolboxItem> 클래스를 제작하는 방법에 대한 자세한 내용은 [디자인할 때 Windows Forms 컨트롤 개발](../Topic/Developing%20Windows%20Forms%20Controls%20at%20Design%20Time.md)을 참조하세요.  
  
#### 기본 ToolboxItem과 함께 사용할 Toolbox 컨트롤을 만들려면  
  
1.  **솔루션 탐색기**에서 다음과 같이 <xref:System.Windows.Forms.UserControl> 개체를 LoadToolboxMembers 프로젝트에 추가합니다.  
  
    1.  **솔루션 탐색기**에서 **LoadToolboxMembers** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **사용자 지정 컨트롤**을 클릭합니다.  
  
    2.  **새 항목 추가** 대화 상자에서 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 `Control1.vb`로 또는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]의 경우 `Control1.cs`로 이름을 변경합니다.  
  
         프로젝트에 새 항목을 추가하는 방법에 대한 자세한 내용은 [NIB: 방법: 새 프로젝트 항목 추가](http://msdn.microsoft.com/ko-kr/63d3e16b-de6e-4bb5-a0e3-ecec762201ce)를 참조하세요.  
  
     새 컨트롤이 디자인 뷰에서 열립니다.  
  
2.  **도구 상자**에서 **단추** 컨트롤\(**공용 컨트롤** 범주에 있음\)을 디자이너로 끕니다.  
  
3.  방금 만든 단추를 두 번 클릭합니다. 이렇게 하면 단추의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기가 생성됩니다. 다음 코드를 사용하여 이벤트 처리기를 업데이트합니다.  
  
     [!code-cs[LoadToolboxMembers#01](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_1.cs)]
     [!code-vb[LoadToolboxMembers#01](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_1.vb)]  
  
4.  `InitializeComponent` 메서드를 호출한 후 컨트롤의 생성자를 수정하여 단추 텍스트를 설정합니다.  
  
     [!code-cs[LoadToolboxMembers#02](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_2.cs)]
     [!code-vb[LoadToolboxMembers#02](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_2.vb)]  
  
5.  VSPackage가 제공된 <xref:System.Drawing.Design.ToolboxItem> 클래스를 쿼리할 수 있도록 특성을 파일에 추가합니다.  
  
     [!code-cs[LoadToolboxMembers#03](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_3.cs)]
     [!code-vb[LoadToolboxMembers#03](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_3.vb)]  
  
6.  파일을 저장합니다.  
  
 다음 프로시저에서는 두 번째 사용자 지정 컨트롤\(`Control2`\)과 연결된 사용자 지정 **도구 상자** 항목\(<xref:System.Drawing.Design.ToolboxItem> 클래스에서 파생된 `Control2_ToolboxItem`\)을 만들고 등록합니다.  
  
#### 사용자 지정 ToolboxItem에서 파생된 클래스를 사용하기 위한 도구 상자 컨트롤을 만들려면  
  
1.  `Control2`라는 두 번째 사용자 지정 컨트롤을 만듭니다. 폼을 두 번 클릭하여 코드 파일을 가져옵니다.  
  
2.  `System.Drawing.Design` 및 `System.Globalization`을 클래스에서 사용하는 네임스페이스에 추가합니다.  
  
     [!code-cs[LoadToolboxMembers#04](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_4.cs)]
     [!code-vb[LoadToolboxMembers#04](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_4.vb)]  
  
3.  단추 및 단추 클릭 이벤트 처리기를 추가하고 첫 번째 컨트롤을 업데이트한 것과 같이 컨트롤의 생성자를 업데이트합니다.  
  
4.  <xref:System.ComponentModel.DisplayNameAttribute>, <xref:System.ComponentModel.DescriptionAttribute>, <xref:System.ComponentModel.ToolboxItemAttribute> 및 <xref:System.Drawing.ToolboxBitmapAttribute> 특성을 파일에 추가합니다.  
  
     이러한 특성을 사용하면 VSPackage에서 <xref:System.Drawing.Design.ToolboxItem> 클래스에 대해 쿼리할 수 있습니다.  
  
     사용자 지정 <xref:System.Drawing.Design.ToolboxItem> 개체를 작성하는 방법에 대한 자세한 내용 및 예제는 <xref:System.Drawing.Design.ToolboxItem> 참조 페이지의 토론을 참조하세요.  
  
     이전 변경 내용과 함께 두 번째 컨트롤 클래스가 다음 코드와 유사해야 합니다.`Control2_ToolboxMenu` 기호는 다음 단계 이후까지 정의되지 않습니다.  
  
     [!code-cs[LoadToolboxMembers#05](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_5.cs)]
     [!code-vb[LoadToolboxMembers#05](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_5.vb)]  
  
5.  `Control2_ToolboxItem`이라는 클래스를 만듭니다. 이 <xref:System.Drawing.Design.ToolboxItem>이 두 번째 컨트롤에 대해 생성되고 **도구 상자**에 추가됩니다. 클래스에 `SerializableAttribute`가 적용되어 있어야 합니다.  
  
     [!code-cs[LoadToolboxMembers#06](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_6.cs)]
     [!code-vb[LoadToolboxMembers#06](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_6.vb)]  
  
6.  파일을 저장합니다.  
  
## 비트맵 아이콘 포함  
 이전에 사용된 <xref:System.Drawing.ToolboxBitmapAttribute>의 두 인스턴스의 의미는 프로젝트가 다음 아이콘을 사용하여 두 컨트롤을 나타낸다는 것입니다.  
  
-   `Control1.bmp`, 첫 번째 컨트롤이 있는 네임스페이스에 있습니다.  
  
-   `Control2.bmp`, 두 번째 컨트롤이 있는 네임스페이스에 있습니다.  
  
#### ToolboxItem에 대해 비트맵 아이콘을 포함하려면  
  
1.  다음과 같이 두 개의 새 비트맵을 프로젝트에 추가합니다.  
  
    1.  `LoadToolboxMembers` 프로젝트를 마우스 오른쪽 단추로 클릭합니다.  
  
    2.  **추가**를 가리킨 다음 **새 항목**을 클릭합니다.  
  
    3.  **새 항목 추가** 대화 상자에서 **비트맵 파일**을 선택하고 파일 이름을 `Control1.bmp`로 지정합니다.  
  
    4.  두 번째 비트맵에 대해 이 단계를 반복하고 이름을 `Control2.bmp`로 지정합니다.  
  
         그러면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 비트맵 편집기에서 각 비트맵이 열립니다.  
  
2.  다음과 같이 각 아이콘의 크기를 16x16으로 설정합니다.  
  
    1.  각 비트맵에 대해 **보기** 메뉴에서 **속성 창**을 클릭합니다.  
  
    2.  **속성** 창에서 **높이**와 **너비**를 16으로 설정합니다.  
  
3.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 비트맵 편집기를 사용하여 각 아이콘에 대한 이미지를 만듭니다.  
  
4.  **솔루션 탐색기**에서 각 비트맵 파일을 클릭한 다음 **속성** 창에서 **빌드 작업** 속성을 **포함 리소스**로 설정합니다.  
  
5.  열려 있는 모든 파일을 저장합니다.  
  
## VSPackage 구현 수정  
 다음 작업을 수행하려면 VSPackage의 기본 구현을 수정해야 합니다.  
  
-   **도구 상자** 항목 공급자가 될 수 있도록 지원을 등록합니다.  
  
-   VSPackage가 지원하는 <xref:System.Drawing.Design.ToolboxItem> 개체 목록을 가져옵니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> 및 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> 이벤트가 처리될 때 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] **도구 상자**에서 <xref:System.Drawing.Design.ToolboxItem> 개체를 로드합니다.  
  
 다음 프로시저에서는 패키지 구현을 수정하는 방법을 보여 줍니다.  
  
#### VSPackage에 대한 도구 상자 항목 공급자가 되도록 패키지 구현을 수정하려면  
  
1.  코드 편집기에서 LoadToolboxMembersPackage.cs 또는 LoadToolboxMembersPackage.vb 파일을 엽니다.  
  
2.  다음과 같이 솔루션에서 <xref:Microsoft.VisualStudio.Shell.Package> 클래스의 구현인 `LoadToolboxMembersPackage` 클래스의 선언을 수정합니다.  
  
    1.  다음 네임스페이스 지시문을 `LoadToolboxMembersPackage` 클래스 파일에 추가합니다.  
  
         [!code-cs[LoadToolboxMembers#07](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_7.cs)]
         [!code-vb[LoadToolboxMembers#07](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_7.vb)]  
  
    2.  <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute>의 인스턴스를 추가하여 VSPackage를 <xref:System.Drawing.Design.ToolboxItem> 클래스로 등록합니다.  
  
        > [!NOTE]
        >  <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute>의 유일한 인수는 VSPackage에서 제공한 <xref:System.Drawing.Design.ToolboxItem> 버전입니다. 이전에 캐시된 <xref:System.Drawing.Design.ToolboxItem> 클래스 버전이 있는 경우에도 이 값을 변경하면 IDE에서 강제로 VSPackage를 로드합니다.  
  
    3.  다음 두 가지 새 `private` 필드를 `LoadToolboxMembersPackage` 클래스에 추가합니다.  
  
         이름이 `ToolboxItemList`인 <xref:System.Collections.ArrayList> 멤버이며 `LoadToolboxMembersPackage` 클래스에서 관리되는 <xref:System.Drawing.Design.ToolboxItem> 개체 목록을 유지합니다.  
  
         **도구 상자** 범주 또는 탭에 있는 이름이 `CategoryTab`인 <xref:System.String>이며 `LoadToolboxMembersPackage` 클래스에서 관리되는 <xref:System.Drawing.Design.ToolboxItem> 개체를 유지하는 데 사용합니다.  
  
     이 수정 작업의 결과는 다음 코드와 유사합니다.  
  
     [!code-cs[LoadToolboxMembers#08](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_8.cs)]
     [!code-vb[LoadToolboxMembers#08](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_8.vb)]  
  
3.  다음 작업을 수행하기 위해 패키지 멤버 영역을 확장하여 `Initialize` 메서드를 수정합니다.  
  
    -   [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]의 경우 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> 및 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> 이벤트에 알림을 신청합니다.  
  
    -   `CreateItemList` 메서드를 호출하여 <xref:System.Collections.ArrayList> 개체 `ToolboxItemList`를 채웁니다.`ToolboxItemList`에는 `LoadToolboxMembersPackage`에서 관리되는 모든 도구 상자 항목의 목록이 있습니다.  
  
     [!code-cs[LoadToolboxMembers#09](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_9.cs)]
     [!code-vb[LoadToolboxMembers#09](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_9.vb)]  
  
4.  다음과 같이 두 메서드\(`CreateItemList` 및 `CreateToolboxItem`\)를 추가하고 메타데이터를 사용하여 `LoadToolboxMembers` 어셈블리에서 사용 가능한 <xref:System.Drawing.Design.ToolboxItem> 개체의 인스턴스를 구성합니다.  
  
     [!code-cs[LoadToolboxMembers#10](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_10.cs)]
     [!code-vb[LoadToolboxMembers#10](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_10.vb)]  
  
5.  `OnRefreshToolbox` 메서드를 구현하여 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> 및 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> 이벤트를 처리합니다.  
  
     `OnRefreshToolbox` 메서드는 `LoadToolboxMembersPackage` 클래스의 `ToolboxItemList` 멤버에 있는 <xref:System.Drawing.Design.ToolboxItem> 개체 목록을 사용합니다. 또한 다음과 같은 작업을 수행합니다.  
  
    -   `CategoryTab` 변수에서 정의된 도구 상자 범주에 이미 있는 모든 <xref:System.Drawing.Design.ToolboxItem> 개체를 제거합니다.  
  
    -   `ToolboxItemList`에 나열된 모든 <xref:System.Drawing.Design.ToolboxItem> 개체의 새 인스턴스를 VSProject에 대한 범주 탭에 추가합니다.  
  
    -   **도구 상자** 활성 탭을 VSProject에 대한 범주 탭으로 설정합니다.  
  
     [!code-cs[LoadToolboxMembers#11](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_11.cs)]
     [!code-vb[LoadToolboxMembers#11](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_11.vb)]  
  
    > [!NOTE]
    >  연습으로 VSPackage 또는 항목 버전을 테스트하기 위한 메커니즘을 개발하고 VSPackage 버전이 변경되거나 <xref:System.Drawing.Design.ToolboxItem> 버전이 변경된 경우 업데이트만 할 수 있습니다.  
  
## 도구 상자 초기화  
  
#### 도구 상자를 초기화하는 명령을 구현하려면  
  
-   다음과 같이 메뉴 항목 명령 처리기 메서드인 `MenuItemCallBack`을 변경합니다.  
  
    1.  `MenuItemCallBack`의 기존 구현을 다음 코드로 바꿉니다.  
  
         [!code-cs[LoadToolboxMembers#12](../misc/codesnippet/CSharp/walkthrough-autoloading-toolbox-items_12.cs)]
         [!code-vb[LoadToolboxMembers#12](../misc/codesnippet/VisualBasic/walkthrough-autoloading-toolbox-items_12.vb)]  
  
## 솔루션 빌드 및 실행  
 실험 하이브에서 실행되는 Visual Studio의 인스턴스를 사용하여 이 연습의 제품을 사용해 볼 수 있습니다.  
  
#### 이 연습을 사용해 보려면  
  
1.  Visual Studio의 **빌드** 메뉴에서 **솔루션 다시 빌드**를 클릭합니다.  
  
2.  F5 키를 눌러 실험 레지스트리 하이브에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 두 번째 인스턴스를 시작합니다.  
  
     실험 하이브를 사용하는 방법에 대한 자세한 내용은 [실험적 인스턴스](../extensibility/the-experimental-instance.md)를 참조하세요.  
  
3.  **도구** 메뉴를 클릭합니다.  
  
     **LoadToolboxMembers VB 초기화** 또는 **LoadToolboxMembers CS 초기화**라는 명령이 숫자 1을 가진 아이콘과 함께 메뉴의 위에 표시되어야 합니다.  
  
4.  새 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 또는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] Windows Forms 응용 프로그램을 만듭니다.  
  
     <xref:System.Windows.Forms.Form> 기반 디자이너가 표시되어야 합니다.  
  
5.  **도구 상자**의 **LoadToolboxMembers Walkthrough VB** 또는 **LoadToolboxMembers Walkthrough CS** 범주의 새 컨트롤 중 하나 또는 둘 다를 디자이너의 폼으로 끕니다.  
  
    > [!NOTE]
    >  **도구 상자**가 표시되지 않으면 **보기** 메뉴에서 **도구 상자**를 클릭합니다. VSPackage에 대한 범주 탭이 **도구 상자**에 표시되지 않는 경우 **도구** 메뉴에서 **LoadToolboxMembers VB 초기화** 또는 **LoadToolboxMembers CS 초기화**를 클릭하여 **도구 상자**를 다시 초기화합니다.  
  
6.  **빌드** 메뉴에서 **솔루션 다시 빌드**를 클릭하여 Windows 응용 프로그램을 빌드합니다.  
  
7.  **디버그** 메뉴에서 **시작** 또는 **디버깅 시작**을 클릭하여 응용 프로그램을 실행합니다.  
  
8.  응용 프로그램이 실행될 때 응용 프로그램에 추가한 컨트롤 중 하나를 클릭합니다.  
  
     메시지 상자가 나타나면서 `"Hello world from Company.LoadToolboxMembers.Control1"` 또는  `"Hello world from Company.LoadToolboxMembers.Control2"`을 표시합니다.  
  
## 구현 분석  
  
### 도구 상자 컨트롤 만들기  
 `Control1` 및 `Control2`에 할당된 특성은 사용 가능한 **도구 상자** 컨트롤에 대해 `Assembly`를 쿼리할 때 `CreateItemList` 메서드에서 사용합니다.  
  
-   <xref:System.ComponentModel.ToolboxItemAttribute>는 다음 두 가지 기능을 수행합니다.  
  
    -   <xref:System.ComponentModel.ToolboxItemAttribute>를 `Control1` 및 `Control2`에 할당하는 것은 각 컨트롤이 도구 상자 컨트롤이라는 것을 나타냅니다.  
  
    -   <xref:System.ComponentModel.ToolboxItemAttribute> 생성자에 대한 인수는 컨트롤이 **도구 상자**에 추가될 때 기본값 <xref:System.Drawing.Design.ToolboxItem>이 사용되는지 아니면 <xref:System.Drawing.Design.ToolboxItem>에서 파생된 사용자 지정 클래스가 사용되는지 여부를 나타냅니다.  
  
         `Control1`에 할당된 <xref:System.ComponentModel.ToolboxItemAttribute>의 인스턴스는 `true`의 인수를 사용하여 만들어지며 이는 **도구 상자**에 추가될 때 기본 <xref:System.Drawing.Design.ToolboxItem> 클래스를 사용한다는 것을 나타냅니다.  
  
         `Control2`에 할당된 <xref:System.ComponentModel.ToolboxItemAttribute>의 인스턴스는 <xref:System.Drawing.Design.ToolboxItem>, `Control2_ToolboxItem`에서 파생된 클래스의 <xref:System.Type>을 사용하여 만들어집니다.  
  
-   <xref:System.Drawing.ToolboxBitmapAttribute> 클래스는 환경에 따라 사용되는 비트맵을 지정하여 컨트롤을 식별합니다.  
  
     해당 **빌드 작업** 속성을 **포함 리소스**로 설정하여 어셈블리에서 비트맵을 포함하면 어셈블리의 네임스페이스에 비트맵을 넣습니다. 따라서 `Control1.bmp`은 `Company.LoadToolboxMembers.Control1.bmp`로 참조될 수 있습니다.  
  
     <xref:System.Drawing.ToolboxBitmapAttribute>는 이 전체 경로를 인수로 사용하는 생성자를 지원합니다. 예를 들어 <xref:System.Drawing.ToolboxBitmapAttribute> 클래스가 `[ToolboxBitmap("Company.LoadToolboxMembers.Control1.bmp")]`을 사용하여 `Control1`에 적용될 수 있습니다.  
  
     유연하게 사용할 수 있도록 이 연습에서는 <xref:System.Type> 클래스가 <xref:System.Drawing.ToolboxBitmapAttribute> 생성자에 대한 첫 번째 인수인 생성자를 사용합니다. 비트맵 파일을 식별하는 데 사용하는 네임스페이스는 <xref:System.Type>에서 가져와서 비트맵의 기본 이름 앞에 삽입됩니다.  
  
     <xref:Microsoft.VisualStudio.Shell.Package>, `LoadToolboxMembers`를 구현하는 <xref:System.Type> 개체가 `Company.LoadToolboxMembers` 네임스페이스에 있기 때문에 `[ToolboxBitmap(typeof(Control1), "Control1.bmp")]`은 `[ToolboxBitmap("Company.LoadToolboxMembers.Control1.bmp")]`와 같습니다.  
  
-   <xref:System.ComponentModel.DisplayNameAttribute>는 **도구 상자**의 컨트롤 이름을 지정합니다.  
  
### 도구 상자 제어 공급자 등록  
 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute> 클래스를 <xref:Microsoft.VisualStudio.Shell.Package>를 구현하는 클래스에 적용하면 결과 VSPackage의 레지스트리 설정에 영향을 미칩니다.<xref:System.Drawing.Design.ToolboxItem> 공급자에 대한 레지스트리 설정에 대한 자세한 내용은 [도구 상자 지원 기능 등록](../misc/registering-toolbox-support-features.md)를 참조하세요.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 환경은 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute> 생성자에 대한 버전 인수를 사용하여 항목을 **도구 상자**에 제공하는 VSPackage의 캐싱을 관리합니다. VSPackage가 **도구 상자** 항목을 제공하기 위해 로드된 후 등록된 버전의 공급자가 변경될 때까지 캐시된 버전의 VSPackage를 사용합니다. 따라서 빌드 후 이 연습의 제품을 수정하려면 `AddToolboxItem`에 적용된 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute> 생성자의 버전 인수를 변경해야 합니다. 예를 들어 `[ProvideToolboxItems(1)]`은 `[ProvideToolboxItems(2)]`로 변경해야 합니다. 버전을 변경하지 않으면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 환경에서는 수정된 내용이 로드되지 않습니다.  
  
 이 연습에서는 VSPackage가 기본 클립보드 형식을 지원하는 **도구 상자** 컨트롤만 제공하도록 구성됩니다. 기본 클립보드 형식 목록은 [도구 상자 확장](../misc/extending-the-toolbox.md)를 참조하세요. 다른 클립보드 형식을 지원하려거나 기본 형식을 지원하지 않기로 결정한 경우 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute> 특성을 `LoadToolboxMembersPackage` 클래스에 적용합니다.**도구 상자** 컨트롤 공급자 등록에 대한 자세한 내용은 [고급 도구 상자 컨트롤 개발](../misc/advanced-toolbox-control-development.md)를 참조하세요.  
  
### 도구 상자에 컨트롤 추가  
 `CreateItemList`의 기능은 <xref:System.Drawing.Design.ToolboxService.System%23Drawing%23Design%23IToolboxService%23GetToolboxItems%2A>에서 사용 가능한 사항을 에뮬레이트합니다.  
  
 `CreateItemList` 메서드는 <xref:System.ComponentModel.IComponent> 인터페이스를 구현하는 비추상 <xref:System.Type> 개체만 검사합니다.  
  
## 다음 단계  
 `CreateItemList` 대신 <xref:System.Drawing.Design.ToolboxService.System%23Drawing%23Design%23IToolboxService%23GetToolboxItems%2A>을 사용하면 이 연습의 제품을 더 강력하게 만듭니다.  
  
 또한 <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A>를 사용하여 컨트롤을 `LoadToolboxMembers` 어셈블리에 포함된 텍스트 목록을 기반으로 한 **도구 상자**로 로드하도록 `CreateItemList`를 수정할 수도 있습니다.  
  
## 참고 항목  
 [도구 상자 확장](../misc/extending-the-toolbox.md)   
 [도구 상자 지원 기능 등록](../misc/registering-toolbox-support-features.md)   
 [고급 도구 상자 컨트롤 개발](../misc/advanced-toolbox-control-development.md)   
 [도구 상자 연습](../misc/toolbox-walkthroughs.md)