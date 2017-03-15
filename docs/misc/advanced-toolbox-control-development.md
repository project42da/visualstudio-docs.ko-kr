---
title: "고급 도구 상자 컨트롤 개발 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도구 상자[Visual Studio SDK], MPF를 사용하여 항목 추가"
ms.assetid: d22479a8-6d95-400c-a115-f46d10c10d2f
caps.latest.revision: 19
caps.handback.revision: 19
manager: "douge"
---
# 고급 도구 상자 컨트롤 개발
> [!NOTE]
>  사용자 지정 컨트롤을 도구 상자에 추가 하려면 Visual Studio 10 SDK와 함께 제공 되는 도구 상자 컨트롤 템플릿을 사용 하는 것이 좋습니다.  이 항목에서는 이전 버전과 호환성을 위해, 기존 컨트롤을 도구 상자에 추가 및 고급 도구 상자 컨트롤 개발에 대 한 유지 됩니다.  
>   
>  서식 파일을 사용 하 여 도구 상자의 컨트롤 만들기에 대 한 자세한 내용은 참조 하십시오. [방법: Windows Forms를 사용하는 도구 상자 컨트롤 만들기](../misc/how-to-create-a-toolbox-control-that-uses-windows-forms.md) 및 [WPF 도구 상자 컨트롤 만들기](../extensibility/creating-a-wpf-toolbox-control.md).  
  
 관리 패키지 프레임 워크를 기반으로 하는 Vspackage를 확장할 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 컨트롤을 추가 하 여 도구 상자 기능을 개체에서 파생 <xref:System.Drawing.Design.ToolboxItem> 개체입니다.  각 <xref:System.Drawing.Design.ToolboxItem> 에서 파생 된 개체에 의해 구현 됩니다 <xref:System.ComponentModel.Component>.  
  
## 도구 상자 항목 공급자 VSPackage  
 관리 패키지 프레임 워크를 기반으로 하는 VSPackage 자체 도구 상자 컨트롤 공급자를 통해 등록 해야 합니다 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 특성 및 도구 상자와 관련 된 이벤트를 처리 합니다.  
  
#### 도구 상자 항목 공급자로 Vspackage를 구성 하려면  
  
1.  인스턴스를 만들는 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute> 클래스 구현에 적용 된 <xref:Microsoft.VisualStudio.Shell.Package>.  예를 들면 다음과 같습니다.  
  
    ```vb#  
    Namespace Vsip.LoadToolboxMembers   
        <ProvideToolboxItems(14)> _   
        <DefaultRegistryRoot("Software\Microsoft\VisualStudio\8.0")> _   
        <InstalledProductRegistration(False, "#100", "#102", "1.0", IconResourceID := 400)> _   
        <ProvideLoadKey("Standard", "1.0", "Package Name", "Company", 1)> _   
        <ProvideMenuResource(1000, 1)> _   
        <Guid("YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY")> _   
        Public Class LoadToolboxMembers   
            Inherits Package   
        End Class   
    End Namespace  
    ```  
  
    ```c#  
    namespace Vsip.LoadToolboxMembers {  
        [ProvideToolboxItems(14)]  
        [DefaultRegistryRoot("Software\\Microsoft\\VisualStudio\\8.0")]  
        [InstalledProductRegistration(false, "#100", "#102", "1.0", IconResourceID = 400)]  
        [ProvideLoadKey("Standard", "1.0", "Package Name", "Company", 1)]  
        [ProvideMenuResource(1000, 1)]  
        [Guid("YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY")]  
        public class LoadToolboxMembers : Package {  
    ```  
  
    > [!NOTE]
    >  생성자에 대 한 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemsAttribute> 정수 버전 숫자를 인수로 사용 합니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackage 제공 하는 경우 확인 하려면 환경에서는 사용이 버전 번호 <xref:System.Drawing.Design.ToolboxItem> 다시 개체가 있어야 수 로드 하거나 캐시 된 정보를 도구 상자에서 사용할 수 있는지.  있는 Vspackage를 제공 하는 경우 다시 로드를 보장 하는 <xref:System.Drawing.Design.ToolboxItem> 개발 중입니다, 항상 후 수정이 버전 번호를 증가 합니다.  
  
2.  경우는 <xref:System.Drawing.Design.ToolboxItem> 개체를 사용할 수 없는 도구 상자 클립보드 형식은 인스턴스를 제공 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute> 클래스 구현에 적용 되어야 합니다는 <xref:Microsoft.VisualStudio.Shell.Package> 개체에서 지 원하는 각 클립보드 형식에 대 한의 <xref:System.Drawing.Design.ToolboxItem> Vspackage를 제공 하는 개체입니다.  
  
     지원 되는 도구 상자의 클립보드 형식에 대 한 자세한 내용은 [도구 상자 확장](../misc/extending-the-toolbox.md).  
  
    > [!NOTE]
    >  있는 Vspackage이 하나라도 제공 하면 <xref:System.Drawing.Design.ToolboxItem> 비표준 클립보드 형식 가진 개체의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 전제 조건은 표시 된 해당 형식에만 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute> 인스턴스가 있는 Vspackage를 적용 <xref:Microsoft.VisualStudio.Shell.Package> 클래스 구현을 Vspackage가 지원 됩니다.  Vspackage를 기본 클립보드 형식으로 표준이 지원 해야 하는 경우 인스턴스를 적용 해야 합니다 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute> 에 각 기본 형식으로 사용할 수 없는 형식입니다.  
  
3.  있는 VSPackage 동적 구성을 제공 하는 경우 <xref:System.Drawing.Design.ToolboxItem>,이 있어야 합니다.  
  
    1.  인스턴스를 적용 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute> 사용 하 여 생성은 <xref:System.Type> 패키지를 사용 하 여 구현 하는 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> 인터페이스입니다.  
  
    2.  에 `public` Vspackage의 독립적인 클래스 <xref:Microsoft.VisualStudio.Shell.Package>, Vspackage를 구현 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> 인터페이스입니다.  
  
         인스턴스는 <xref:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute> 클래스 구현에 적용 합니다 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem>, 인수로 선택 조건 \(필터\)을 포함 하는 문자열을 사용 하는 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute> 인스턴스 생성자.  
  
 알림 방법에 대 한의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 있는 VSPackage 도구 상자를 제공 하는 환경 제어, 참조 하십시오 [도구 상자 지원 기능 등록](../misc/registering-toolbox-support-features.md).  
  
 하나를 어떻게 구현할 수 있는지 보여 주는 예를 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> 지원를 참조 하십시오 [연습: 도구 상자 항목 구성을 동적으로 사용자 지정](../misc/walkthrough-customizing-toolbox-item-configuration-dynamically.md).  
  
1.  Vspackages를 제공 하는 <xref:System.Drawing.Design.ToolboxItem> 처리 해야 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> 및 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> 이벤트입니다.  
  
    1.  에 대 한 처리기를 구현 하는 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> 및 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> 이벤트:  
  
        ```vb#  
        Private Sub OnToolboxUpgraded(ByVal sender As Object, ByVal e As EventArgs)   
            OnToolboxInitialized(send, e)   
        End Sub   
        Private Sub OnToolboxInitialized(ByVal sender As Object, ByVal e As EventArgs)   
            'Make sure all toolbox items are added.   
        End Sub  
        ```  
  
        ```c#  
        private void OnToolboxUpgraded(object sender, EventArgs e) {  
            OnToolboxInitialized(send,e);  
        }  
        private void OnToolboxInitialized(object sender, EventArgs e) {  
            //Make sure all toolbox items are added.  
        }  
        ```  
  
    2.  등록은 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> 및 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> 이벤트입니다.  
  
         이것은 일반적으로 수행 되는 <xref:Microsoft.VisualStudio.Shell.Package> 구현의 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> 메서드:  
  
        ```vb#  
        Protected Overloads Overrides Sub Initialize()   
            AddHandler ToolboxInitialized, AddressOf OnToolboxInitialized   
            AddHandler ToolboxUpgraded, AddressOf OnToolboxUpgraded   
        End Sub  
        ```  
  
        ```c#  
        protected override void Initialize() {  
            ToolboxInitialized += new EventHandler(OnToolboxInitialized);  
            ToolboxUpgraded += new EventHandler(OnToolboxUpgraded);  
        }  
        ```  
  
     예에 대 한 처리기를 구현 하는 방법에 대 한 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxInitialized> 및 <xref:Microsoft.VisualStudio.Shell.Package.ToolboxUpgraded> 이벤트를 참조 하십시오. [연습: 도구 상자 항목 자동 로드 ](../misc/walkthrough-autoloading-toolbox-items.md).  
  
## 도구 상자 컨트롤 만들기  
 도구 상자 컨트롤의 기본 구현에서 파생 되어야 합니다 <xref:System.ComponentModel.Component> , 기본 또는 파생 된 구현에서 캡슐화는 <xref:System.Drawing.Design.ToolboxItem> 개체입니다.  
  
 제공 하는 가장 쉬운 방법은 한 <xref:System.ComponentModel.Component>\-도구 상자 컨트롤이 파생된 되는 구현입니다에서 파생 된 개체를 확장 하 여 <xref:System.Windows.Forms.Control>, 특히는 <xref:System.Windows.Forms.UserControl> 클래스입니다.  
  
#### 도구 상자 컨트롤을 만들려면  
  
1.  사용  **솔루션 탐색기**의  **새 항목 추가** 을 구현 하는 도구 상자 개체를 만드는 명령 <xref:System.Windows.Forms.UserControl>.  
  
    ```vb#  
    Public Partial Class ToolboxControl1   
        Inherits UserControl   
        Public Sub New()   
            InitializeComponent()   
        End Sub   
        Private Sub button1_Click(ByVal sender As Object, ByVal e As EventArgs)   
            MsgBox("Hello world from" & Me.ToString())   
        End Sub   
  
        Private Sub ToolboxItem1_Load(ByVal sender As Object, ByVal e As EventArgs)   
  
        End Sub   
    End Class  
    ```  
  
    ```c#  
    public partial class ToolboxControl1 : UserControl {  
            public ToolboxControl1() {  
                InitializeComponent();  
            }  
  
            private void button1_Click(object sender, EventArgs e) {  
                MessageBox.Show("Hello world from" + this.ToString());  
            }  
  
            private void ToolboxItem1_Load(object sender, EventArgs e) {  
  
            }  
        }  
    ```  
  
     도구 상자 컨트롤 및 Windows Forms 컨트롤 제작에 대 한 자세한 내용은 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../Topic/Developing%20Custom%20Windows%20Forms%20Controls%20with%20the%20.NET%20Framework.md) 또는 [연습: 도구 상자 항목 자동 로드 ](../misc/walkthrough-autoloading-toolbox-items.md).  
  
2.  \(선택 사항\) 응용 프로그램에서 파생 된 사용자 지정 개체를 사용할 수 있습니다에서 <xref:System.Drawing.Design.ToolboxItem> 개체를 도구 상자의 컨트롤을 제공 하는  **도구 상자**.  
  
    > [!NOTE]
    >  파생 된 클래스는 <xref:System.Drawing.Design.ToolboxItem> 개체의 인스턴스를 갖고 있어야 합니다는 <xref:System.SerializableAttribute> 적용 됩니다.  
  
     사용자 지정 구현을 파생 <xref:System.Drawing.Design.ToolboxItem> 방법을 세부적으로 제어를 제공 하 여 응용 프로그램을 확장할 수 있습니다 <xref:System.Drawing.Design.ToolboxItem> 입니다 데이터 직렬화, 비표준 클립보드 형식 및 최종 사용자의 상호 작용을 허용 하는 기능에 대 한 지원 향상 디자이너 메타 데이터를 처리 합니다.  
  
     하는 사용자 기능 선택 대화 상자에 메시지가 나타납니다.  
  
    ```vb#  
    <ToolboxItemAttribute(GetType(CustomControl))> _   
    <Serializable()> _   
    Class CustomControl   
        Inherits ToolboxItem   
  
        Public Sub New(ByVal type As Type)   
            MyBase.New(GetType(CustomControl))   
        End Sub   
        Public Sub New(ByVal type As Type, ByVal icon As Bitmap)   
            MyBase.New(GetType(SCustomControl))   
            Me.DisplayName = "CustomContorl"   
            Me.Bitmap = icon   
        End Sub   
  
        Private Sub New(ByVal info As SerializationInfo, ByVal context As StreamingContext)   
            Deserialize(info, context)   
        End Sub   
        Protected Overloads Overrides Function CreateComponentsCore(ByVal host As IDesignerHost) As IComponent()   
            Dim dialog As New CustomControlDialog(host)   
            Dim dialogResult__1 As DialogResult = dialog.ShowDialog()   
            If dialogResult__1 = DialogResult.OK Then   
                Dim component As IComponent = DirectCast(dialog.CustomInstance, IComponent)   
                Dim container As IContainer = host.Container   
                container.Add(component)   
                Return New IComponent() {component}   
            Else   
                Return New IComponent() {}   
            End If   
        End Function   
    End Class  
    ```  
  
    ```c#  
    [ToolboxItemAttribute(typeof(CustomControl))]  
    [Serializable]  
    class CustomControl : ToolboxItem {  
  
        public CustomControl(Type type) : base(typeof(CustomControl)) {}  
            public CustomControl(Type type, Bitmap icon) : base(typeof(SCustomControl)) {  
            this.DisplayName = "CustomContorl";  
            this.Bitmap = icon;  
        }  
  
        private CustomControl(SerializationInfo info, StreamingContext context) {  
            Deserialize(info, context);  
        }  
        protected override IComponent[] CreateComponentsCore(IDesignerHost host) {  
            CustomControlDialog dialog = new CustomControlDialog(host);  
            DialogResult dialogResult = dialog.ShowDialog();  
            if (dialogResult == DialogResult.OK) {  
                IComponent component = (IComponent)dialog.CustomInstance;  
                IContainer container = host.Container;  
                container.Add(component);  
                return new IComponent[] { component };  
            }  
            else {  
                return new IComponent[] {};  
            }  
        }  
    }  
    ```  
  
> [!NOTE]
>  파생 된 클래스에 대 한 수도 있습니다의 <xref:System.Drawing.Design.ToolboxItem> 내부 컨트롤의 자체 독립적인된 구현을 제공 하는 개체입니다.  클래스는 다음 만들고 모든 내부 구성 요소를 제공 하는 데 담당 합니다.  
  
## 명시적 도구 상자 항목 추가  
 도구 상자에 추가할 컨트롤의 인스턴스를 포함 합니다 <xref:System.Drawing.Design.ToolboxItem> 에서 파생 된 개체의 <xref:System.Drawing.Design.ToolboxItem> 에 추가할 수는  **도구 상자** 를 사용 하는 <xref:System.Drawing.Design.IToolboxService> 인터페이스.  
  
#### 캡슐화 하 고 도구 상자 컨트롤을 추가 하려면  
  
1.  캡슐화는 <xref:System.ComponentModel.Component> 구현에서의 인스턴스는 <xref:System.Drawing.Design.ToolboxItem> 개체 나는 <xref:System.Drawing.Design.ToolboxItem>\-개체에서 해당 개체를 호출 하 여 파생 된 <xref:System.Drawing.Design.ToolboxItem.Initialize%2A> 메서드를 구현 하는 구성 요소의 <xref:System.Type?displayProperty=fullName>:  
  
    ```vb#  
    Dim customItem As New ToolboxItem()   
    If customItem IsNot Nothing Then   
        customItem.Initialize(userControl)   
    End If  
    ```  
  
    ```c#  
    ToolboxItem customItem = new ToolboxItem() ;  
    if (customItem != null) {  
        customItem.Initialize(userControl);  
    }  
    ```  
  
     위에 개체의 예입니다 `userControl` 에서 파생 된 <xref:System.Windows.Forms.UserControl> \(인스턴스를의 `ToolboxControl1` 개체 위에 표시 된\) 새 생성에 사용 되 고 <xref:System.Drawing.Design.ToolboxItem>.  
  
    > [!NOTE]
    >  기본 구현에서 <xref:System.Drawing.Design.ToolboxItem> 생성자 기록은 <xref:System.Type?displayProperty=fullName> 인수 \(<xref:System.Drawing.Design.ToolboxItem.%23ctor%28System.Type%29> 생성자 호출의 <xref:System.Drawing.Design.ToolboxItem> 개체의 <xref:System.Drawing.Design.ToolboxItem.Initialize%2A> 메서드.  
  
2.  도구 상자 서비스를 사용 \(<xref:System.Drawing.Design.IToolboxService>\) 추가 하는 <xref:System.Drawing.Design.ToolboxItem> 를 기본 컨트롤 구현에서 생성 된 개체입니다.  
  
     아래 예제에서는 도구 상자 서비스에 액세스할 수 있습니다 가져온 속성 중 일부는 <xref:System.Drawing.Design.ToolboxItem> 인스턴스 `customItem` 설정 된 다음 `customItem` 추가 됩니다 있는  **도구 상자**:  
  
    ```vb#  
    Dim toolboxService As IToolboxService = TryCast(GetService(GetType(IToolboxService)), IToolboxService)  
    customItem.Bitmap = New System.Drawing.Bitmap(ToolBoxControl1, "Control1.bmp")  
    customItem.DisplayName = "Custom Item"   
    toolboxService.AddToolboxItem(item, "Custom Tab")  
    ```  
  
    ```c#  
    IToolboxService toolboxService = GetService(typeof(IToolboxService)) as IToolboxService;  
    customItem.Bitmap = new System.Drawing.Bitmap(ToolboxControl1,"Control1.bmp");  
    customItem.DisplayName= "Custom Item";  
    toolboxService.AddToolboxItem(item, "Custom Tab");  
    ```  
  
## 리플렉션을 사용 하 여 도구 상자의 컨트롤 추가  
 도구 상자 컨트롤을 구현 하는 클래스에 특성을 적용할 수 있습니다는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 환경 나는 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 기반 리플렉션을 사용 하 여 자동으로 감지 하 고 제대로 컨트롤을 추가 하려면 응용 프로그램의  **도구 상자**.  
  
#### 도구 상자의 컨트롤을 리플렉션 및 특성 적용  
  
1.  도구 상자 컨트롤의 인스턴스를 구현 하는 데 사용 되는 모든 객체를 식별 <xref:System.ComponentModel.ToolboxItemAttribute>.  
  
     형식 인스턴스의 <xref:System.ComponentModel.ToolboxItemAttribute> 개체에 합니다 결정 하는 경우와 방법을 <xref:System.Drawing.Design.ToolboxItem> 에서 생성 됩니다.  
  
    1.  인스턴스를 적용 <xref:System.ComponentModel.ToolboxItemAttribute> 로 생성 된는 `BOOLEAN` 값이 `false` 개체에 해당 개체가 사용할 수 없는 리플렉션을 통해 도구 상자에 있습니다.  
  
         이 같은 개체를 격리 하는 것이 유용할 수 있습니다는 <xref:System.Windows.Forms.UserControl> 에서  **도구 상자** 개발 중입니다.  
  
    2.  인스턴스를 적용 <xref:System.ComponentModel.ToolboxItemAttribute> 를 생성는 `BOOLEAN` 값이 `true` 개체를 해당 개체는 리플렉션을 통해 도구 상자에 활성화 되 고 개체에 기본 사용 하 여 도구 상자에 추가 해야 <xref:System.Drawing.Design.ToolboxItem> 개체입니다.  
  
    3.  인스턴스를 적용 <xref:System.ComponentModel.ToolboxItemAttribute> 를 생성은 <xref:System.Type> 에서 파생 된 사용자 지정 개체의 <xref:System.Drawing.Design.ToolboxItem> 개체를 사용할 수 있습니다의  **도구 상자** 리플렉션을 통해 개체에서 파생 된이 사용자 지정 개체를 사용 하 여 도구 상자에 추가 해야 하 고 <xref:System.Drawing.Design.ToolboxItem>.  
  
2.  지정 \(하는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 환경의 리플렉션 메커니즘\) 비트맵 도구 상자 컨트롤에 표시 하는 데 사용 하는  **도구 상자** 인스턴스를 추가 하 여 <xref:System.Drawing.ToolboxBitmapAttribute> 컨트롤을 도구 상자에 구현.  
  
3.  필요한 경우 인스턴스를 적용 <xref:System.ComponentModel.ToolboxItemFilterAttribute> 에 <xref:System.Drawing.Design.ToolboxItem> 리플렉션을 사용 하 여 정적으로 일치 하는 특성을 가진 개체를 표시 하는 개체입니다.  
  
     아래 예제에서는 인스턴스를 도구 상자 컨트롤의 구현 된 <xref:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute> 적용할 수 있기 때문에 사용할 수 있는 해당 컨트롤의  **도구 상자** 인 경우에 현재 작업 문서는 <xref:System.Windows.Forms.UserControl> 디자이너  
  
    ```vb#  
    <ToolboxItemFilter(System.Windows.Forms.UserControl, ToolboxItemFilterType.Require)> _   
    <SerializableAttribute()> _   
    <GuidAttribute("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX")> _   
    Friend Class CustomToolboxItem   
        Inherits ToolboxItem   
    End Class  
    ```  
  
    ```c#  
    [ToolboxItemFilter(System.Windows.Forms.UserControl,ToolboxItemFilterType.Require)]  
    [SerializableAttribute()]  //ToolboxItem implementations much has this attribute.  
    [GuidAttribute("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX")]  
    internal class CustomToolboxItem : ToolboxItem   
    ```  
  
 자동 로드를 리플렉션 사용에 대 한 세 가지 기본 기술이 <xref:System.Drawing.Design.ToolboxItem>.  
  
### ToolService 기능을 사용 하 여 검색 도구 상자 컨트롤  
 <xref:System.Drawing.Design.ToolboxService> VSPackages 정적으로 제공 <xref:System.Drawing.Design.ToolboxService.GetToolboxItems%2A> 메서드는 리플렉션을 사용 하 여 도구 상자 항목, 지원 되는 모든 형식에 대 한 어셈블리를 검사 하 고 해당 형식에 대 한 항목을 반환 합니다.  반환 될 도구 상자 항목을 해야 합니다.  
  
-   public이어야 합니다.  
  
-   구현에서 <xref:System.ComponentModel.IComponent> 클래스입니다.  
  
-   abstract가 아니어야 합니다.  
  
-   가 <xref:System.ComponentModel.ToolboxItemAttribute> 에.  
  
-   없는 한 <xref:System.ComponentModel.ToolboxItemAttribute> 설정 `false` 에  
  
-   제네릭 매개 변수가 포함되어 있지 않아야 합니다.  
  
##### 이 목록을 얻으려면  
  
1.  인스턴스를 만들 <xref:System.Reflection.Assembly> 참조 하는 어셈블리를 검색 하 여 <xref:System.Drawing.Design.ToolboxItem> 개체입니다.  
  
    > [!NOTE]
    >  인스턴스를 가져오기 위해 <xref:System.Reflection.Assembly> 는 현재 어셈블리에 대 한 정적 메서드를 사용 합니다. <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>.  
  
2.  호출 <xref:System.Drawing.Design.ToolboxService.GetToolboxItems%2A>, 반환 된 <xref:System.Collections.ICollection> 적절 한 개체의 목록이 포함 된 개체입니다.  
  
    > [!NOTE]
    >  개체에 반환 되는 경우 <xref:System.Collections.ICollection> 의 올바른 인스턴스가 <xref:System.Drawing.ToolboxBitmapAttribute> 할당을 구현 하는 <xref:System.Drawing.Design.ToolboxService.GetToolboxItems%2A> 됩니다 방법을 설정의 <xref:System.Drawing.Design.ToolboxItem> 개체의 <xref:System.Drawing.Design.ToolboxItem.Bitmap%2A> 속성.  
  
3.  사용 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 액세스할 수 <xref:System.Drawing.Design.IToolboxService>, 사용 하 고 해당 <xref:System.Drawing.Design.IToolboxService.AddToolboxItem%2A> 에서 반환 된 항목을 추가 하는 방법을 <xref:System.Collections.ICollection> 개체를 도구 상자에 있습니다.  
  
     아래 코드는 실행 중인 응용 프로그램에 쿼리 및 모든 목록을 가져옵니다 해당 <xref:System.Drawing.Design.ToolboxItem> 개체 및 로드 합니다.  코드 실행 중에 이것을 보여 주는 예제를 보려면 해당 `Initialization` 메서드에서 [연습: 도구 상자 항목 구성을 동적으로 사용자 지정](../misc/walkthrough-customizing-toolbox-item-configuration-dynamically.md).  
  
    ```vb#  
    Protected ToolboxItemList As ICollection = Nothing  
    ToolboxItemList = ToolboxService.GetToolboxItems(Assembly.GetExecutingAssembly(), "")  
    If ToolboxItemList Is Nothing Then   
        Throw New ApplicationException("Unable to generate a toolbox Items listing for " & [GetType]().FullName)   
    End If   
    Dim toolboxService As IToolboxService = TryCast(GetService(GetType(IToolboxService)), IToolboxService)   
    For Each itemFromList As ToolboxItem In ToolboxItemList   
        toolboxService.AddToolboxItem(itemFromList, CategoryTab)   
    Next  
    ```  
  
    ```c#  
    protected ICollection ToolboxItemList = null;  
    ToolboxItemList = ToolboxService.GetToolboxItems(Assembly.GetExecutingAssembly(), "");  
    if (ToolboxItemList == null){  
        throw new ApplicationException("Unable to generate a toolbox Items listing for "  
    + GetType().FullName);  
    }  
    IToolboxService toolboxService = GetService(typeof(IToolboxService)) as IToolboxService;  
    foreach (ToolboxItem itemFromList in ToolboxItemList){  
        toolboxService.AddToolboxItem(itemFromList, CategoryTab);  
    }  
    ```  
  
### 자동 로드 도구 상자 컨트롤에 포함 된 텍스트 리소스를 사용 하 여  
 텍스트 리소스 도구 상자 컨트롤이 올바른 형식의 목록을 포함 하는 어셈블리에서 사용할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A> 올바르게 포맷 하는 경우 도구 상자 컨트롤을 자동으로 로드할 수 있습니다.  
  
 로드 하는 개체의 목록이 포함 된 텍스트 리소스 Vspackage를 액세스할 수 있는 어셈블리에서 사용할 수 있어야 합니다.  
  
##### 추가 하 고 텍스트 리소스를 어셈블리에 사용할 수 있도록  
  
1.  **솔루션 탐색기**, 마우스 오른쪽 단추로 클릭 한 프로젝트입니다.  
  
2.  가리키는  **추가**를 누른 다음  **새 항목**.  
  
3.  에  **새 항목 추가** 선택 대화 상자에서  **텍스트 파일** 이름을 지정 하 고 있습니다.  
  
4.  **솔루션 탐색기**, 새로 만든된 텍스트 파일을 마우스 오른쪽 단추로 클릭 하 고 설정에서  **빌드 작업** 속성을 포함 리소스.  
  
     항목에는  **도구 상자** 로드 되는 컨트롤의 구현 클래스 이름 포함 하는 어셈블리의 이름을 포함 해야 합니다.  
  
     도구 상자에서 형식에 대 한 정보를 항목에 포함 된 텍스트 리소스 제어에 대 한 참조를 <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A> 페이지 참조.  
  
5.  도구 상자 컨트롤 개체를 호스팅하는 어셈블리를 포함 하는 파일에 대 한 검색 경로 설정 합니다.  
  
     <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A>HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\ 레지스트리 항목에 지정 된 유일한 디렉터리 검색*\<version\>*\\AssemblyFolders, 어디  *\<version\>* Visual Studio \(예를 들어, 8.0\)의 릴리스는 버전 번호입니다.  
  
    > [!NOTE]
    >  루트 경로를 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\*\<Version\>* Visual Studio 셸 초기화 되 면 대체 루트 또는 사용으로 재정의 될 수 있습니다 <xref:Microsoft.VisualStudio.Shell.DefaultRegistryRootAttribute>.  자세한 내용은 [명령줄 스위치](../extensibility/command-line-switches-visual-studio-sdk.md)을 참조하십시오.  
  
     AssemblyFolder 레지스트리 항목을 올바른 형식에 대 한 자세한 내용은 <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A> 페이지 참조.  
  
6.  인스턴스를 가져오는 <xref:System.IO.TextReader.Synchronized%2A> 텍스트가 포함 된 리소스에 액세스 하 고 지역화를 지 원하는 경우 범주 이름에 대 한 인스턴스를 필요 <xref:System.Resources.ResourceManager>, 및 이러한 정보를 사용 하 여 호출 하는 <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A> 메서드.  
  
    ```vb#  
    Dim rm As New ResourceManager("TbxCategories", Assembly.GetExecutingAssembly())  
    Dim toolboxStream As Stream = TbxItemProvider.[GetType]().Assembly.GetManifestResourceStream("ToolboxItems.txt")  
    If toolboxStream IsNot Nothing Then   
        Using reader As TextReader = New StreamReader(toolboxStream)   
            ParseToolboxResource(reader, rm)   
        End Using   
    End If  
    ```  
  
    ```c#  
    ResourceManager rm = new ResourceManager("TbxCategories", Assembly.GetExecutingAssembly());  
    Stream toolboxStream = TbxItemProvider.GetType().Assembly.GetManifestResourceStream("ToolboxItems.txt");  
    if (toolboxStream != null) {  
        using (TextReader reader = new StreamReader(toolboxStream)) {  
        ParseToolboxResource(reader, rm);  
    }  
    }  
    ```  
  
     위 목록에 포함 된 텍스트 리소스를 클래스가 들어 있는 어셈블리에 포함 된 예에서 `TbxItemProvider` 에 전달 된 <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A> 와 함께 `TbxCategories` 리소스는 문자열입니다.  
  
     모든 도구 상자 컨트롤에 대 한 AssemblyFolders 레지스트리 항목에서 지정 된 디렉터리에서 어셈블리를 포함 하는 파일에서 리소스를 나열 하 고 로드 메서드를 검색 합니다.  
  
    > [!NOTE]
    >  컨트롤 도구 상자를 찾을 경우 <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A> 의 올바른 인스턴스가 <xref:System.Drawing.ToolboxBitmapAttribute> 의 구현에 할당 된 <xref:Microsoft.VisualStudio.Shell.Package.ParseToolboxResource%2A> 도구 상자 컨트롤을 표시 하는 데 사용 되는 비트맵을 설정 합니다.  
  
### 명시적으로 반사 자동 로드 도구 상자의 컨트롤을 사용 하 여  
 어셈블리를 명시적으로 쿼리에 대 한 자세한 내용은 필요한 경우는  **도구 상자** 작업을 위임 하는 것이 아니라 컨트롤 포함을 <xref:System.Drawing.Design.ToolboxService.GetToolboxItems%2A>에서이 할 수 있습니다.  
  
##### 반사 도구 상자 컨트롤 자동 로드를 명시적으로 사용 하  
  
1.  인스턴스를 만들 <xref:System.Reflection.Assembly>, 참조를 검색 하 여 각 어셈블리에 <xref:System.Drawing.Design.ToolboxItem> 개체입니다.  
  
    > [!NOTE]
    >  인스턴스를 가져오기 위해 <xref:System.Reflection.Assembly> 는 현재 어셈블리에 대 한 정적 메서드를 사용 합니다. <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>.  
  
2.  각 어셈블리에 대 한 검색을 위해 사용 하는 <xref:System.Reflection.Assembly> 개체의 <xref:System.Reflection.Assembly.GetTypes%2A> 각 목록을 구하는 방법 <xref:System.Type?displayProperty=fullName> 어셈블리에 있습니다.  
  
3.  확인 형식을 추상이 아닌 한 지원는 <xref:System.ComponentModel.IComponent> 인터페이스 \(도구 상자 컨트롤을 인스턴스화하는 데 사용 하는 모든 구현에 <xref:System.Drawing.Design.ToolboxItem> 개체는이 인터페이스를 구현 해야 합니다\).  
  
4.  특성을 가져올 <xref:System.Type> 및이 정보를 사용 하 여 있는 VSPackage 개체를 로드 하 고 싶은지를 결정 합니다.  
  
    > [!NOTE]
    >  주 서버에서 만들 수는 있지만 한 <xref:System.Drawing.Design.ToolboxItem> 에서 개체는 <xref:System.ComponentModel.IComponent> 인터페이스 구현 하지 않고 인스턴스를 <xref:System.ComponentModel.ToolboxItemAttribute> 설정할 없습니다 `false` 적용, 우리가 이렇게 하지 않는 것이 좋습니다.  
  
5.  사용 <xref:System.Type.GetConstructor%2A> 생성자에 대해 얻을 수 있는 <xref:System.Drawing.Design.ToolboxItem> 도구 상자 컨트롤 해야 하는 개체입니다.  
  
6.  구성의 <xref:System.Drawing.Design.ToolboxItem> 를 추가 하 고 개체의  **도구 상자**.  
  
 리플렉션 얻을 수 및 자동 로드 도구 상자 컨트롤을 명시적으로 사용을 보여 주는 예제를 보려면를 참조 하십시오은 `CreateItemList` 에서 설명한 [연습: 도구 상자 항목 자동 로드 ](../misc/walkthrough-autoloading-toolbox-items.md).  
  
## 추가 도구 상자 컨트롤 구성  
 언제, 어떻게 도구 상자 컨트롤을 표시 하 여 추가로 제어할 Vspackage를 행사할 수 있습니다의  **도구 상자**의 구현을 통해 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem>, 및를 사용 하 여 <xref:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute>, 및 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute>.  
  
 적용 <xref:System.ComponentModel.ToolboxItemFilterAttribute> 클래스의 인스턴스 제공 정적 컨트롤 위로 언제, 어떻게는  **도구 상자** 컨트롤 사용할 수 있습니다.  
  
#### 동적 구성 지원에 대 한 도구 상자 컨트롤을 만들려면  
  
1.  구현 하는 클래스를 생성은 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> 인터페이스는 Vspackage의 일환으로 합니다.  
  
    > [!NOTE]
    >  <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> 같은 클래스에 있는 VSPackage 구현을 제공 하는 인터페이스를 구현 해야 합니다지 않습니다 <xref:Microsoft.VisualStudio.Shell.Package>.  
  
2.  구현에 연결 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> 인스턴스를 적용 하 여 특정 어셈블리의 개체를 <xref:Microsoft.VisualStudio.Shell.ProvideAssemblyFilterAttribute> 합니다.  
  
     다음 예제에서는 동적 구성 내에서 도구 상자의 컨트롤 개체가 어셈블리에 대 한 제공의 `Vsip.*` 네임 스페이스 및 특정 요구 <xref:System.Drawing.Design.ToolboxItem> 개체 에서만 볼 수 <xref:System.Windows.Forms.UserControl>\-기반 디자이너 및 기타 표시 안 함을 <xref:System.Windows.Forms.UserControl>\-디자이너 따라.  
  
    ```vb#  
    <ProvideAssemblyFilterAttribute("Vsip.*, Version=*, Culture=*, PublicKeyToken=*")> _   
    <GuidAttribute("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX")> _   
    Public NotInheritable Class ToolboxConfig   
        Implements IConfigureToolboxItem   
        Public Sub New()   
        End Sub  
  
        ''' <summary>   
        ''' Adds extra configuration information to this toolbox item.   
        ''' </summary>   
        Public Sub ConfigureToolboxItem(ByVal item As ToolboxItem)   
            If item Is Nothing Then   
                Exit Sub   
            End If   
  
            'hide from .NET Compact Framework on the device designer.   
            Dim newFilter As ToolboxItemFilterAttribute = Nothing   
            If item.TypeName = GetType(ToolboxControl1).ToString() Then   
                newFilter = New ToolboxItemFilterAttribute("System.Windows.Forms.UserControl", ToolboxItemFilterType.Require)   
            ElseIf item.TypeName = GetType(ToolboxControl2).ToString() Then   
  
                newFilter = New ToolboxItemFilterAttribute("System.Windows.Forms.UserControl", ToolboxItemFilterType.Prevent)   
            End If   
            If newFilter IsNot Nothing Then   
                Dim array As New ArrayList()   
                array.Add(newFilter)   
                item.Filter = DirectCast(array.ToArray(GetType(ToolboxItemFilterAttribute)), ToolboxItemFilterAttribute())   
            End If   
        End Sub   
    End Class  
    ```  
  
    ```c#  
    [ProvideAssemblyFilterAttribute("Vsip.*, Version=*, Culture=*, PublicKeyToken=*")]  
        [GuidAttribute("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX")]  
        public sealed class ToolboxConfig : IConfigureToolboxItem {  
            public ToolboxConfig() {  
            }  
  
            /// <summary>  
            ///     Adds extra configuration information to this toolbox item.  
            /// </summary>  
            public void ConfigureToolboxItem(ToolboxItem item) {  
                if (item == null)  
                    return;  
  
                //hide from .NET Compact Framework  on the device designer.  
                ToolboxItemFilterAttribute newFilter = null;  
                if (item.TypeName == typeof(ToolboxControl1).ToString()) {  
                    newFilter = new ToolboxItemFilterAttribute("System.Windows.Forms.UserControl",  
                                                          ToolboxItemFilterType.Require);  
                }   
                else if (item.TypeName == typeof(ToolboxControl2).ToString()) {  
  
                    newFilter = new ToolboxItemFilterAttribute("System.Windows.Forms.UserControl",  
                                                          ToolboxItemFilterType.Prevent);  
                }  
                if (newFilter != null) {  
                    ArrayList array = new ArrayList();  
                    array.Add(newFilter);  
                    item.Filter = (ToolboxItemFilterAttribute[])  
                            array.ToArray(typeof(ToolboxItemFilterAttribute));  
                }  
            }  
        }  
    }  
    ```  
  
3.  특정 구현을 제공 하는 있는 VSPackage 등록 <xref:Microsoft.VisualStudio.Shell.IConfigureToolboxItem> 인스턴스를 적용 하 여 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxItemConfigurationAttribute> 있는 VSPackage 구현과 <xref:Microsoft.VisualStudio.Shell.Package>.  
  
     아래 예에 게 알려는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 패키지를 구현 하 여 환경 `Vsip.ItemConfiguration.ItemConfiguration` 클래스를 제공 합니다. `Vsip.ItemConfiguration.ToolboxConfiguration` 동적 지원 하기 위해 <xref:System.Drawing.Design.ToolboxItem>.  
  
    ```vb#  
    <ProvideToolboxItemsAttribute(3)> _   
    <DefaultRegistryRoot("Software\Microsoft\VisualStudio\8.0")> _   
    <InstalledProductRegistration(False, "#100", "#102", "1.0", IconResourceID := 400)> _   
    <ProvideLoadKey("Standard", "1.0", "Package Name", "Company", 1)> _   
    <ProvideMenuResource(1000, 1)> _   
    <ProvideToolboxItemConfigurationAttribute(GetType(ToolboxConfig))> _   
    <GuidAttribute("YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY")> _   
    Public Class ItemConfiguration   
        Inherits Package   
    End Class  
    ```  
  
    ```c#  
    [ProvideToolboxItemsAttribute(3)]  
    [DefaultRegistryRoot("Software\\Microsoft\\VisualStudio\\8.0")]  
    [InstalledProductRegistration(false, "#100", "#102", "1.0", IconResourceID = 400)]  
    [ProvideLoadKey("Standard", "1.0", "Package Name", "Company", 1)]  
    [ProvideMenuResource(1000, 1)]  
    [ProvideToolboxItemConfigurationAttribute(typeof(ToolboxConfig))]  
  
    [GuidAttribute("YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY")]  
    public class ItemConfiguration : Package  
    ```  
  
## 사용자 지정 드래그 앤 드롭 지원  
 에 추가 되 고 이외에  **도구 상자** 자체를 <xref:System.Drawing.Design.ToolboxItem> 개체 및 해당 구현을 사용할 수 있습니다에서 끌어서 놓기 지원을 확장 하는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE.  이 임의의 클립보드 형식에 노출 될 수 있습니다 있는  **도구 상자** 및 편집기에서.  
  
 Vspackages에 관리 패키지 프레임 워크를 기반으로 해야 합니다 등록 사용자 정의 제공 하는  **도구 상자** 인스턴스를 적용 하면 항목을 클립보드 형식은 <xref:Microsoft.VisualStudio.Shell.ProvideToolboxFormatAttribute> 클래스가 구현 하는 <xref:Microsoft.VisualStudio.Shell.Package>.  
  
 으로 등록에 대 한 자세한 내용은  **도구 상자** 공급자를 참조 하십시오 [도구 상자 지원 기능 등록](../misc/registering-toolbox-support-features.md).  
  
#### 도구 상자의 컨트롤을 사용자 지정 클립보드 서식 및 끌어서 놓기 지원을 제공  
  
1.  구현을 만들은 <xref:System.Drawing.Design.ToolboxItemCreatorCallback> 대리자입니다.  
  
     이 구현에서 반환 해야는 <xref:System.Drawing.Design.ToolboxItem> 표준 클립보드 형식을 지 원하는 개체입니다.  
  
     구현 예를 대 한는 <xref:System.Drawing.Design.ToolboxItemCreatorCallback> 위임, 볼의 <xref:System.Drawing.Design.ToolboxItem> 및 <xref:System.Drawing.Design.ToolboxItemCreatorCallback> 페이지를 참조 합니다.  
  
2.  이 구현 하 게는 <xref:System.Drawing.Design.ToolboxItemCreatorCallback> 대리자를 사용할 수 있는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]**도구 상자** 는 사용할 수 없는 도구 상자 호출에 대 한 <xref:System.Drawing.Design.IToolboxService.AddCreator%2A>.  
  
    ```vb#  
    <GuidAttribute("7D91995B-A799-485e-BFC7-C52545DFB5DD")> _   
    <ProvideToolboxFormatAttribute("MyFormat")> _   
    Public Class ItemConfiguration   
        Inherits MSVSIP.Package   
        Public Overloads Overrides Sub Initialize()   
            '"Adding this class as a ToolboxItemCreator");   
            Dim toolbox As IToolboxService = DirectCast(host.GetService(GetType(IToolboxService)), IToolboxService)   
            If toolbox IsNot Nothing Then   
                toolboxCreator = New ToolboxItemCreatorCallback(Me.OnCreateToolboxItem)   
                toolbox.AddCreator(toolboxCreator, "MyFormat", host)   
            End If   
        End Sub   
    End Class  
    ```  
  
    ```c#  
    [GuidAttribute("7D91995B-A799-485e-BFC7-C52545DFB5DD")]  
    [ProvideToolboxFormatAttribute("MyFormat")]  
    public class ItemConfiguration : MSVSIP.Package  
    {  
        public override void Initialize() {   
            /*  
            *  
            */  
            //"Adding this class as a ToolboxItemCreator");  
            IToolboxService toolbox = (IToolboxService)host.GetService(typeof(IToolboxService));  
            if (toolbox != null) {  
                toolboxCreator = new ToolboxItemCreatorCallback(this.OnCreateToolboxItem);  
                toolbox.AddCreator(toolboxCreator, "MyFormat", host);  
            }  
            private ToolboxItem OnCreateToolboxItem(object serializedData, string format) {  
               /*  
                *  
                */  
            }  
        }  
    }  
    ```  
  
### 단원 내용  
 [방법: 도구 상자 끌어서 놓기 기능 지원](../misc/how-to-support-toolbox-drag-and-drop-functionality.md)  
 문서 보기에서 끌어서 놓기 지원을 구현 하는 방법에 설명 합니다.  
  
 [방법: Interop 어셈블리를 사용하여 사용자 지정 도구 상자 항목 제공](../misc/how-to-provide-custom-toolbox-items-by-using-interop-assemblies.md)  
 새 ActiveX 컨트롤 및 새 항목 추가 설명의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]**도구**.   이러한 새 항목은 표준 클립보드 형식 또는 Vspackage가 지원 되는 사용자 지정 형식을 가질 수 있습니다.  
  
 [도구 상자 지원 기능 등록](../misc/registering-toolbox-support-features.md)  
 있는 VSPackage 도구 상자 공급자로 등록 하는 방법에 설명 합니다.  지원 이나 다른 도구 상자 기능을 사용 하는 방법에 대 한도 설명 합니다.  
  
## 참고 항목  
 [도구 상자 확장](../misc/extending-the-toolbox.md)   
 [도구 상자 연습](../misc/toolbox-walkthroughs.md)   
 [도구 상자 지원 기능 등록](../misc/registering-toolbox-support-features.md)   
 [방법: Interop 어셈블리를 사용하여 사용자 지정 도구 상자 항목 제공](../misc/how-to-provide-custom-toolbox-items-by-using-interop-assemblies.md)   
 [도구 상자 관리](../misc/managing-the-toolbox.md)   
 [How to: Control the Toolbox](../Topic/How%20to:%20Control%20the%20Toolbox.md)