---
title: "옵션 페이지 만들기 | Microsoft Docs"
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
  - "도구 옵션 페이지[Visual Studio SDK], 만들기"
ms.assetid: 9f4e210c-4b47-4daa-91fa-1c301c4587f9
caps.latest.revision: 62
caps.handback.revision: 62
ms.author: "gregvanl"
manager: "ghogen"
---
# 옵션 페이지 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 연습을 검토 하 고 속성을 설정 하려면 속성 표를 사용 하는 간단한 도구\/옵션 페이지를 만듭니다.  
  
 이러한 속성을 저장 하 고 설정 파일에서 복원 하려면 다음이 단계를 수행 하 고 확인 다음 [설정 범주 만들기](../extensibility/creating-a-settings-category.md)합니다.  
  
 도구 옵션 페이지를 만들 수 있도록 두 개의 클래스를 제공 하는 MPF는 <xref:Microsoft.VisualStudio.Shell.Package> 클래스 및 <xref:Microsoft.VisualStudio.Shell.DialogPage> 클래스입니다. 패키지 클래스 하위 클래스를 지정 하 여 이러한 페이지에 대 한 컨테이너를 제공 하는 VSPackage를 만들어야 합니다. DialogPage 클래스에서 파생 하 여 각 도구 옵션 페이지를 만듭니다.  
  
## 사전 요구 사항  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하세요.  
  
## 도구 옵션 그리드 페이지 만들기  
 이 섹션에서는 간단한 도구 옵션 속성 표를 만듭니다. 이 표를 사용 하 여 표시 하 고 속성의 값을 변경 합니다.  
  
#### VSIX 프로젝트를 만들고 VSPackage를 추가 하려면  
  
1.  모든 Visual Studio 확장 확장 자산을 포함 하는 VSIX 배포 프로젝트를 시작 합니다. 만들기는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 라는 VSIX 프로젝트 `MyToolsOptionsExtension`합니다. VSIX 프로젝트 템플릿을 찾을 수는 **새 프로젝트** 대화 상자의 **Visual C\# \/ 확장성**합니다.  
  
2.  Visual Studio 패키지 항목 템플릿을 추가 하 여 VSPackage를 추가할 `MyToolsOptionsPackage`합니다. 에 **솔루션 탐색기**, 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 \/ 새 항목**합니다. 에 **새 항목 추가 대화 상자**, 로 이동 **Visual C\# 항목 \/ 확장성** 선택한 **Visual Studio 패키지**합니다. 에 **이름** 대화 상자 맨 아래에 필드, 파일 이름을 `MyToolsOptionsPackage.cs`합니다. VSPackage를 만드는 방법에 대 한 자세한 내용은 참조 [VSPackage를 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-vspackage.md)합니다.  
  
#### 도구 옵션 속성 표를 만들려면  
  
1.  코드 편집기에서 MyToolsOptionsPackage 파일을 엽니다.  
  
2.  다음 코드를 추가 문을 사용 합니다.  
  
    ```c#  
    using System.ComponentModel;  
    ```  
  
3.  OptionPageGrid 클래스를 선언 하 고에서 파생 <xref:Microsoft.VisualStudio.Shell.DialogPage>합니다.  
  
    ```c#  
    public class OptionPageGrid : DialogPage  
    {  }  
    ```  
  
4.  적용 한 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> VSPackage 클래스에 옵션 범주 이름과 옵션 페이지의 OptionPageGrid에 대 한 클래스에 할당 합니다. 결과 다음과 같습니다.  
  
    ```c#  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)]  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    [Guid(GuidList.guidMyToolsOptionsPkgString)]  
    [ProvideOptionPage(typeof(OptionPageGrid),  
        "My Category", "My Grid Page", 0, 0, true)]  
    public sealed class MyToolsOptionsPackage : Package  
    ```  
  
5.  추가 `OptionInteger` 속성을는 `OptionPageGrid` 클래스입니다.  
  
    -   적용 한 <xref:System.ComponentModel.CategoryAttribute?displayProperty=fullName> 속성 표 범주 속성에 할당할 수 있습니다.  
  
    -   적용 한 <xref:System.ComponentModel.DisplayNameAttribute?displayProperty=fullName> 속성에 이름을 지정할 수 있습니다.  
  
    -   적용 한 <xref:System.ComponentModel.DescriptionAttribute?displayProperty=fullName> 를 속성에 대 한 설명을 지정 합니다.  
  
    ```c#  
    public class OptionPageGrid : DialogPage  
    {  
        private int optionInt = 256;  
  
        [Category("My Category")]  
        [DisplayName("My Integer Option")]  
        [Description("My integer option")]  
        public int OptionInteger  
        {  
            get { return optionInt; }  
            set { optionInt = value; }  
        }  
    }  
    ```  
  
    > [!NOTE]
    >  기본 구현은 <xref:Microsoft.VisualStudio.Shell.DialogPage> 적절 한 변환기 또는 구조체 또는 배열 속성을 적절 한 변환기로 확장할 수 있는 속성을 지원 합니다. 목록이 변환기에 대 한 참조는 <xref:System.ComponentModel> 네임 스페이스입니다.  
  
6.  프로젝트를 빌드하고 디버깅을 시작합니다.  
  
7.  Visual Studio의 실험적 인스턴스에서는 **도구** 메뉴 클릭 **옵션**합니다.  
  
     왼쪽된 창에 표시 됩니다 **My Category**합니다. \(옵션 범주는 알파벳 순서로 나열을 목록 아래쪽 중간에 대 한 표시 되어야 하므로.\) 열기 **My Category** 클릭 하 고 **그리드 페이지 내**합니다. 옵션 표 오른쪽 창에 표시 됩니다. 속성 범주는 **내 옵션**, 속성 이름이 **내 정수 옵션**합니다. 속성 설명 **내 정수 옵션**, 창의 아래쪽에 나타납니다. 256의 초기 값에서 다른 값을 변경 합니다. 클릭 **확인**, 를 닫은 후 다시 **그리드 페이지 내**합니다. 지속 되 면 새 값을 볼 수 있습니다.  
  
     옵션 페이지에도 Visual Studio의 빠른 실행을 통해 제공 됩니다. 빠른 실행 창에서 IDE의 오른쪽 위 모서리에 입력 **My Category** 나타납니다 **내 범주 –\> 그리드 페이지 내** 드롭다운에 나열 합니다.  
  
## 도구 옵션 사용자 지정 만들기 페이지  
 이 섹션에서는 사용자 지정 UI가 포함 된 도구 옵션 페이지를 만듭니다. 이 페이지를 사용 하 여 표시 하 고 속성의 값을 변경 합니다.  
  
1.  코드 편집기에서 MyToolsOptionsPackage 파일을 엽니다.  
  
2.  다음 코드를 추가 문을 사용 합니다.  
  
    ```vb  
    using System.Windows.Forms;  
    ```  
  
3.  추가 `OptionPageCustom` 클래스 바로 앞의 `OptionPageGrid` 클래스입니다. 새 클래스를 파생 `DialogPage`합니다.  
  
    ```c#  
    public class OptionPageCustom : DialogPage  
    {  
        private string optionValue = "alpha";  
  
        public string OptionString  
        {  
            get { return optionValue; }  
            set { optionValue = value; }  
        }  
    }  
    ```  
  
4.  GUID 특성을 추가 합니다. OptionString 속성을 추가 합니다.  
  
    ```c#  
    [Guid("00000000-0000-0000-0000-000000000000")]  
    public class OptionPageCustom : DialogPage  
    {  
        private string optionValue = "alpha";  
  
        public string OptionString  
        {  
            get { return optionValue; }  
            set { optionValue = value; }  
        }  
    }  
    ```  
  
5.  두 번째 적용 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> VSPackage 클래스에 있습니다. 옵션 범주 및 옵션 페이지 이름에는이 특성 클래스를 할당합니다.  
  
    ```c#  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)]  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    [Guid(GuidList.guidMyToolsOptionsPkgString)]  
    [ProvideOptionPage(typeof(OptionPageGrid),  
        "My Category", "My Grid Page", 0, 0, true)]  
    [ProvideOptionPage(typeof(OptionPageCustom),  
        "My Category", "My Custom Page", 0, 0, true)]  
    public sealed class MyToolsOptionsPackage : Package  
    ```  
  
6.  새 추가 **사용자 정의 컨트롤** MyUserControl 프로젝트에 이름이 있습니다.  
  
7.  추가 **TextBox** 사용자 정의 컨트롤을 제어 합니다.  
  
     에 **속성** 창의 도구 모음을 클릭는 **이벤트** 단추를 두 번 클릭 하 고는 **둡니다** 이벤트입니다. 새 이벤트 처리기는 MyUserControl.cs 코드에 표시 됩니다.  
  
8.  추가 `OptionsPage` 필드는 `Initialize` 업데이트 옵션을 설정 하는 이벤트 처리기는 입력란의 내용에 값 및 컨트롤 클래스에 메서드:  
  
    ```c#  
    public partial class MyUserControl : UserControl  
    {  
        public MyUserControl()  
        {  
            InitializeComponent();  
        }  
  
        internal OptionPageCustom optionsPage;  
  
        public void Initialize()  
        {  
            textBox1.Text = optionsPage.OptionString;  
        }  
  
        private void textBox1_Leave(object sender, EventArgs e)  
        {  
            optionsPage.OptionString = textBox1.Text;  
        }  
    }  
    ```  
  
     `optionsPage` 필드 부모에 대 한 참조가 `OptionPageCustom` 인스턴스.`Initialize` 메서드 표시 `OptionString` 에 **TextBox**합니다. 이벤트 처리기의 현재 값이 기록는 **TextBox** 에 `OptionString` 리프 초점을 맞출 때는 **TextBox**합니다.  
  
9. 패키지 코드 파일에 대 한 재정의 추가 `OptionPageCustom.Window` 만들기, 초기화 및 인스턴스를 반환 하려면 OptionPageCustom 클래스에 속성을 `MyUserControl`합니다. 클래스는 이제 다음과 같이 표시 됩니다.  
  
    ```c#  
    [Guid("00000000-0000-0000-0000-000000000000")]  
    public class OptionPageCustom : DialogPage  
    {  
        private string optionValue = "alpha";  
  
        public string OptionString  
        {  
            get { return optionValue; }  
            set { optionValue = value; }  
        }  
  
        protected override IWin32Window Window  
        {  
            get  
            {  
                MyUserControl page = new MyUserControl();  
                page.optionsPage = this;  
                page.Initialize();  
                return page;  
            }  
        }  
    }  
    ```  
  
10. 프로젝트를 빌드하고 실행합니다.  
  
11. 실험적 인스턴스에서 클릭 **도구 \/ 옵션**합니다.  
  
12. 찾을 **내 범주** 차례로 **내 사용자 지정 페이지**합니다.  
  
13. 값을 변경 **OptionString**합니다. 클릭 **확인**, 를 닫은 후 다시 **내 사용자 지정 페이지**합니다. 새 값이 유지 되는지 확인할 수 있습니다.  
  
## 옵션에 액세스  
 이 섹션에서는 관련 된 도구 옵션 페이지를 호스팅하는 VSPackage에서 옵션의 값을 가져옵니다. 동일한 기법 public 속성의 값을 가져오는 데 사용할 수 있습니다.  
  
1.  패키지 코드 파일에서 라는 공용 속성 추가 **OptionInteger** 에 **MyToolsOptionsPackage** 클래스입니다.  
  
    ```  
    public int OptionInteger  
    {  
        get  
        {  
            OptionPageGrid page = (OptionPageGrid)GetDialogPage(typeof(OptionPageGrid));  
            return page.OptionInteger;  
        }  
    }  
  
    ```  
  
     이 코드는 호출 <xref:Microsoft.VisualStudio.Shell.Package.GetDialogPage%2A> 를 만들거나 검색 한 `OptionPageGrid` 인스턴스.`OptionPageGrid` 호출 <xref:Microsoft.VisualStudio.Shell.DialogPage.LoadSettingsFromStorage%2A> 해당 옵션은 공용 속성을 로드 합니다.  
  
2.  이제 사용자 지정 명령 항목 템플릿을 추가 **MyToolsOptionsCommand** 값을 표시 합니다. 에 **새 항목 추가** 대화 상자에서 이동 **Visual C\# \/ 확장성** 선택한 **사용자 지정 명령**합니다. 에 **이름** 창의 맨 아래에 필드, 명령 파일 이름을 **MyToolsOptionsCommand.cs**합니다.  
  
3.  MyToolsOptionsCommand 파일에서 명령의의 본문을 바꿉니다 `ShowMessageBox` 메서드를 다음으로:  
  
    ```c#  
    private void ShowMessageBox(object sender, EventArgs e)  
    {  
        MyToolsOptionsPackage myToolsOptionsPackage = this.package as MyToolsOptionsPackage;  
        System.Windows.Forms.MessageBox.Show(string.Format(CultureInfo.CurrentCulture, "OptionInteger: {0}", myToolsOptionsPackage.OptionInteger));  
    }  
  
    ```  
  
4.  프로젝트를 빌드하고 디버깅을 시작합니다.  
  
5.  실험적 인스턴스에서는 **도구** 메뉴를 클릭 하 여 **MyToolsOptionsCommand 호출**합니다.  
  
     현재 값을 표시 하는 메시지 상자 `OptionInteger`합니다.  
  
## 참고 항목  
 [옵션 및 옵션 페이지](../extensibility/internals/options-and-options-pages.md)