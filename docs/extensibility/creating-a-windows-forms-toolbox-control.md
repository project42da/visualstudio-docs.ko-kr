---
title: Windows Forms 만들기 도구 상자 컨트롤 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- winforms
- toolbox
- windows forms
ms.assetid: 0be6ffc1-8afd-4d02-9a5d-e27dde05fde6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6a7d5bae07d3596902f94417cda20c3d40feed2f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-windows-forms-toolbox-control"></a>Windows Forms 도구 상자 컨트롤 만들기
Visual Studio 확장성 도구 (VS SDK)에 포함 된 Windows Forms 도구 상자 컨트롤 항목 템플릿에 자동으로 추가 하는 컨트롤을 만들 수 있습니다는 **도구 상자** 확장 기능이 설치 됩니다. 이 항목에는 다른 사용자에 게 배포할 수 있는 간단한 카운터 컨트롤을 만드는 템플릿을 사용 하는 방법을 보여 줍니다.  
  
## <a name="prerequisites"></a>필수 조건  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-a-windows-forms-toolbox-control"></a>Windows Forms 도구 상자 컨트롤 만들기  
 Windows Forms 도구 상자 컨트롤 템플릿은 정의 되지 않은 사용자 정의 컨트롤을 만들고 컨트롤을 추가 하는 데 필요한 기능을 모두 제공는 **도구 상자**합니다.  
  
#### <a name="create-an-extension-with-a-windows-forms-toolbox-control"></a>Windows Forms 도구 상자 컨트롤 확장 만들기  
  
1.  라는 VSIX 프로젝트 `MyWinFormsControl`합니다. VSIX 프로젝트 템플릿을 찾을 수 있습니다는 **새 프로젝트** 대화 상자의 **Visual C# / 확장성**합니다.  
  
2.  프로젝트를 열 때 추가 된 **Windows Forms 도구 상자 컨트롤** 라는 항목 템플릿을 `Counter`합니다. 에 **솔루션 탐색기**프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 / 새 항목**합니다. 에 **새 항목 추가** 대화 상자에서로 이동 **Visual C# / 확장성** 선택 **Windows Forms 도구 상자 컨트롤**  
  
3.  이 사용자 정의 컨트롤을 추가 하는 `ProvideToolboxControlAttribute` <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute> 에 컨트롤 배치는 **도구 상자**, 및 **Microsoft.VisualStudio.ToolboxControl** 배포에 대 한 VSIX 매니페스트의 자산 항목이 합니다.  
  
### <a name="building-a-user-interface-for-the-control"></a>컨트롤에 대한 사용자 인터페이스 작성  
 `Counter` 컨트롤을 사용 하려면 두 개의 자식 컨트롤이:는 <xref:System.Windows.Forms.Label> 현재 수를 표시 하 고 <xref:System.Windows.Forms.Button> 개수를 0으로 다시 설정 하 합니다. 호출자에 게는 카운터를 프로그래밍 방식으로 증가 시키므로 다른 자식 컨트롤이 없는 사항은.입니다.  
  
##### <a name="to-build-the-user-interface"></a>사용자 인터페이스를 작성하려면  
  
1.  **솔루션 탐색기**, Counter.cs 디자이너에서 열을 두 번 클릭 합니다.  
  
2.  "여기를 클릭 하십시오!"을 제거 합니다. **단추** Windows Forms 도구 상자 컨트롤 항목 템플릿을 추가 하면 기본적으로 포함 됩니다.  
  
3.  **도구 상자**를 끌어는 `Label` 제어 차례로 `Button` 하위 컨트롤을 디자인 화면입니다.  
  
4.  150 전체 사용자 정의 컨트롤의 크기를 조정, 50, 50 픽셀 및 크기 조정 단추 제어 20 픽셀입니다.  
  
5.  에 **속성** 창 디자인 화면에 컨트롤에 대 한 다음 값을 설정 합니다.  
  
    |Control|속성|값|  
    |-------------|--------------|-----------|  
    |`Label1`|**텍스트**|""|  
    |`Button1`|**이름**|btnReset|  
    |`Button1`|**텍스트**|다시 설정|  
  
### <a name="coding-the-user-control"></a>사용자 정의 컨트롤 코딩  
 `Counter` 컨트롤은 카운터를 증가시키는 메서드, 카운터가 증가될 때마다 발생하는 이벤트, `Reset` 단추 및 현재 카운트, 표시 텍스트 및 `Reset` 단추의 표시/숨김 여부를 저장하는 속성 3개를 노출합니다. `ProvideToolboxControl` 에서 위치를 결정 하는 특성의 **도구 상자** 는 `Counter` 컨트롤이 나타납니다.  
  
##### <a name="to-code-the-user-control"></a>사용자 정의 컨트롤의 코드를 작성 하려면  
  
1.  해당 부하 이벤트 처리기 코드 창에서 열려는 폼을 두 번 클릭 합니다.  
  
2.  이벤트 처리기 메서드 위에 control 클래스에서 다음 예제에 표시 된 대로 텍스트를 저장 하는 문자열과 카운터 값을 저장 하는 정수를 만듭니다.  
  
    ```csharp  
    int currentValue;  
    string displayText;  
    ```  
  
3.  다음 공용 속성 선언을 만듭니다.  
  
    ```csharp  
    public int Value {  
        get { return currentValue; }   
    }  
  
    public string Message {  
        get { return displayText; }  
        set { displayText = value; }  
    }  
  
    public bool ShowReset {  
        get { return btnReset.Visible; }  
        set { btnReset.Visible = value; }  
    }  
  
    ```  
  
     호출자에 게 이러한 속성을 가져오고이 카운터의 표시 텍스트를 설정 하 고 표시 하거나 숨길 수에 액세스할 수는 `Reset` 단추입니다. 호출자에 게 읽기 전용의 현재 값을 가져올 수 `Value` 있지만 속성 값을 직접 설정할 수 없습니다.  
  
4.  다음 코드에 삽입는 `Load` 컨트롤에 대 한 이벤트입니다.  
  
    ```csharp  
    private void Counter_Load(object sender, EventArgs e)  
    {  
        currentValue = 0;  
        label1.Text = Message + Value;  
    }  
  
    ```  
  
     설정의 **레이블** 의 텍스트는 <xref:System.Windows.Forms.UserControl.Load> 이벤트를 사용 하면 해당 값을 적용 하기 전에 로드할 대상 속성입니다. 설정의 **레이블** 빈 생성자에서 텍스트로 인해 **레이블**합니다.  
  
5.  카운터를 증가 시키는 다음 공용 메서드와 만듭니다.  
  
    ```csharp  
    public void Increment()  
    {  
        currentValue++;  
        label1.Text = displayText + Value;  
        Incremented(this, EventArgs.Empty);  
    }  
  
    ```  
  
6.  에 대 한 선언을 추가 `Incremented` 컨트롤 클래스에는 이벤트입니다.  
  
    ```csharp  
    public event EventHandler Incremented;  
    ```  
  
     호출자는 카운터의 값이 변경에 응답 하도록이 이벤트에 처리기를 추가할 수 있습니다.  
  
7.  뷰를 디자인 하 고 두 번 클릭으로 돌아가기는 `Reset` 단추를 생성 하는 `btnReset_Click` 이벤트 처리기에 다음 예제와 같이 입력 합니다.  
  
    ```csharp  
    private void btnReset_Click(object sender, EventArgs e)  
    {  
        currentValue = 0;  
        label1.Text = displayText + Value;  
    }  
  
    ```  
  
8.  클래스 정의 바로 위의는 `ProvideToolboxControl` 특성 선언에서 첫 번째 매개 변수의 값을 변경 하세요 `"MyWinFormsControl.Counter"` 를 `"General"`합니다. **도구 상자**에서 컨트롤을 호스트할 항목 그룹의 이름이 설정됩니다.  
  
     다음 예제에서는 `ProvideToolboxControl` 특성 및 조정된 클래스 정의를 보여 줍니다.  
  
    ```csharp  
    [ProvideToolboxControl("General", false)]  
    public partial class Counter : UserControl  
    ```  
  
### <a name="testing-the-control"></a>컨트롤 테스트  
 테스트 하는 **도구 상자** 제어, 먼저 개발 환경에서 테스트 한 다음 컴파일된 응용 프로그램에서 테스트 합니다.  
  
##### <a name="to-test-the-control"></a>컨트롤을 테스트하려면  
  
1.  F5 키를 누릅니다.  
  
     프로젝트가 빌드되고 컨트롤이 설치 된 Visual Studio의 두 번째 실험적 인스턴스를 엽니다.  
  
2.  Visual Studio의 실험적 인스턴스를 만듭니다는 **Windows Forms 응용 프로그램** 프로젝트.  
  
3.  **솔루션 탐색기**, Form1.cs를 아직 열지 않은 경우 디자이너에서 열을 두 번 클릭 합니다.  
  
4.  에 **도구 상자**, `Counter` 컨트롤에 표시 되어야 합니다는 **일반** 섹션.  
  
5.  끌어서는 `Counter` 양식에 컨트롤을 선택 합니다. `Value`, `Message`, 및 `ShowReset` 속성에 표시 됩니다는 **속성** 창에서 상속 된 속성과 함께 <xref:System.Windows.Forms.UserControl>합니다.  
  
6.  `Message` 속성을 `Count:`으로 설정합니다.  
  
7.  끌어서는 <xref:System.Windows.Forms.Button> 을 폼으로 제어 하 고 다음 단추를의 이름 및 텍스트 속성을 설정 `Test`합니다.  
  
8.  코드 보기에서 Form1.cs를 열고 클릭 처리기를 만들려면 단추 두 번 클릭 합니다.  
  
9. Click 처리기에 호출 `counter1.Increment()`합니다.  
  
10. 생성자 함수를 호출한 후에 `InitializeComponent`, 형식 `counter1``.``Incremented +=` 한 탭 키를 두 번 누릅니다.  
  
     Visual Studio에 대 한 폼 수준 처리기가 생성 된 `counter1.Incremented` 이벤트입니다.  
  
11. 강조 표시는 `Throw` 유형 이벤트 처리기에서 문을 `mbox`, 한 다음 사서함 코드 조각에서 생성 되는 메시지 상자를 두 번 탭 키를 누릅니다.  
  
12. 다음 줄에 다음 추가 `if` / `else` 블록의 표시 유형을 설정 하는 `Reset` 단추입니다.  
  
    ```csharp  
    if (counter1.Value < 5) counter1.ShowReset = false;  
    else counter1.ShowReset = true;  
    ```  
  
13. F5 키를 누릅니다.  
  
     양식이 열립니다. `Counter` 컨트롤 다음 텍스트를 표시 합니다.  
  
     **Count: 0**  
  
14. **테스트**를 클릭합니다.  
  
     카운터가 증가 하 고 Visual Studio에는 메시지 상자를 표시 합니다.  
  
15. 메시지 상자를 닫습니다.  
  
     **재설정** 단추가 사라집니다.  
  
16. 클릭 **테스트** 카운터에 도달할 때까지 **5** 때마다 상자는 메시지를 닫은 합니다.  
  
     **재설정** 단추를 다시 표시 합니다.  
  
17. **다시 설정**을 클릭합니다.  
  
     이 카운터를 다시 설정 **0**합니다.  
  
## <a name="next-steps"></a>다음 단계  
 **도구 상자** 컨트롤을 작성할 때 Visual Studio는 프로젝트의 \bin\debug\ 폴더에 *ProjectName*.vsix라는 파일을 만듭니다. 네트워크 또는 웹 사이트에.vsix 파일을 업로드하여 컨트롤을 배포할 수 있습니다. 컨트롤이 설치 되어 Visual Studio에 추가 사용자가.vsix 파일을 열면 **도구 상자** 사용자의 컴퓨터에 있습니다. 또는.vsix 파일을 업로드할 수 있습니다는 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847) 사용자에서 이동 하 여 찾을 수 있도록 웹 사이트는 **도구 / 확장명 및 업데이트** 대화 상자.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio의 다른 부분을 확장합니다.](../extensibility/extending-other-parts-of-visual-studio.md)   
 [WPF 도구 상자 컨트롤 만들기](../extensibility/creating-a-wpf-toolbox-control.md)   
 [Visual Studio의 다른 부분을 확장합니다.](../extensibility/extending-other-parts-of-visual-studio.md)   
 [Windows Forms 컨트롤 개발 기본 사항](/dotnet/framework/winforms/controls/windows-forms-control-development-basics)