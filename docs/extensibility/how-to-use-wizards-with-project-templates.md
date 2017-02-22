---
title: "방법: 프로젝트 템플릿에 마법사 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IWizard 인터페이스"
  - "프로젝트 템플릿[Visual Studio], 마법사"
  - "템플릿[Visual Studio], 마법사"
  - "Visual Studio 템플릿, 마법사"
  - "마법사[Visual Studio], 프로젝트 템플릿"
ms.assetid: 47ee26cf-67b7-4ff1-8a9d-ab11a725405c
caps.latest.revision: 23
caps.handback.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: 프로젝트 템플릿에 마법사 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 에서 제공되는 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스를 구현하여 사용자가 템플릿에서 프로젝트를 만들 때 사용자 지정 코드가 실행되도록 할 수 있습니다.  
  
 프로젝트 템플릿 사용자 지정을 사용하여 다음을 수행할 수 있습니다.  
  
-   템플릿을 매개 변수화하기 위해 사용자 입력을 수집하는 사용자 지정 UI를 표시합니다.  
  
-   템플릿에서 사용할 매개 변수 값을 추가합니다.  
  
-   템플릿에 추가 파일을 추가합니다.  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 자동화 개체 모델에서 허용하는 작업을 프로젝트에서 가상으로 수행합니다.  
  
 사용자가 **새 프로젝트** 대화 상자에서 **확인** 을 클릭하는 즉시 시작하여 프로젝트가 만들어지는 동안 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스 메서드는 여러 번 호출됩니다.  인터페이스의 각 메서드는 호출되는 지점을 설명하도록 명명됩니다.  예를 들어, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 에서는 프로젝트를 만들기 시작하면 즉시 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard.RunStarted%2A> 를 호출하므로 사용자 입력을 수집하는 사용자 지정 코드를 작성할 수 있는 좋은 위치가 만들어집니다.  
  
 사용자 지정 마법사에 대해 작성되는 대부분의 코드에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 자동화 개체 모델의 주 개체인 <xref:EnvDTE.DTE> 개체를 사용하여 프로젝트를 사용자 지정합니다.  자동화 개체 모델에 대한 자세한 내용은 [Extending the Visual Studio Environment](../Topic/Extending%20the%20Visual%20Studio%20Environment.md) 및 [Automation and Extensibility Reference](../Topic/Automation%20and%20Extensibility%20Reference.md)를 참조하십시오.  
  
## 사용자 지정 템플릿 마법사 만들기  
 이 항목에서는 프로젝트가 만들어지기 전에 Windows Form을 여는 사용자 지정 마법사를 만드는 방법을 보여 줍니다.  사용자가 이 폼을 사용하여 사용자 지정 매개 변수 값을 추가하면 프로젝트가 만들어지는 동안 소스 코드에 사용자 지정 매개 변수 값이 추가됩니다.  기본 단계와 각각에 대한 자세한 설명은 다음과 같습니다.  
  
#### 사용자 지정 템플릿 마법사를 만들려면  
  
1.  <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스를 구현하는 어셈블리를 만듭니다.  
  
2.  전역 어셈블리 캐시에 어셈블리를 설치합니다.  
  
3.  프로젝트를 만들고 **템플릿 내보내기** 마법사를 사용하여 프로젝트에서 템플릿을 만듭니다.  
  
4.  <xref:Microsoft.VisualStudio.TemplateWizard.IWizard>를 구현하는 어셈블리에 템플릿을 연결하도록 .vstemplate 파일에 `WizardExtension` 요소를 추가하여 템플릿을 수정합니다.  
  
5.  사용자 지정 마법사를 사용하여 새 프로젝트를 만듭니다.  
  
## IWizard 구현  
 이 과정의 첫 단계는 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard>를 구현하는 어셈블리를 만드는 것입니다.  이 어셈블리는 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard.RunStarted%2A> 메서드를 사용하여 사용자가 사용자 지정 매개 변수 값을 추가할 수 있는 Windows Form을 표시합니다. 사용자 지정 매개 변수 값은 나중에 프로젝트를 만드는 동안 사용됩니다.  
  
> [!NOTE]
>  이 예제에서는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 을 사용하여 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard>를 구현합니다. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]을 사용할 수도 있습니다.  
  
#### IWizard를 구현하려면  
  
1.  새 클래스 라이브러리 프로젝트를 만듭니다.  
  
2.  <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스를 구현하는 클래스를 만듭니다.  완전히 구현된 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스의 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 예제는 다음 코드를 참조하십시오.  
  
 이 예제에는 두 개의 코드 파일이 포함되어 있습니다. 하나는 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 인터페이스를 구현하는 `IWizardImplementation` 클래스이고, 다른 하나는 사용자 입력을 위한 Windows Form인 `UserInputForm`입니다.  
  
### IWizardImplementation 클래스  
 `IWizardImplementation` 클래스에는 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard>의 모든 멤버에 대한 메서드 구현이 포함되어 있습니다.  이 예제에서는 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard.RunStarted%2A> 메서드만 작업을 수행합니다.  다른 모든 메서드는 아무 작업도 수행하지 않거나 `true`를 반환합니다.  
  
 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard.RunStarted%2A> 메서드는 네 개의 매개 변수를 사용합니다.  
  
-   루트 <xref:EnvDTE._DTE> 개체로 캐스팅될 수 있는 <xref:System.Object> 매개 변수. 이 매개 변수를 사용하여 프로젝트를 사용자 지정할 수 있습니다.  
  
-   템플릿의 미리 정의된 모든 매개 변수 컬렉션을 포함하는 <xref:System.Collections.Generic.Dictionary%602> 매개 변수.  템플릿 매개 변수에 대한 자세한 내용은 [템플릿 매개 변수](../ide/template-parameters.md)를 참조하십시오.  
  
-   사용될 템플릿 종류에 대한 정보를 포함하는 <xref:Microsoft.VisualStudio.TemplateWizard.WizardRunKind> 매개 변수  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에 의해 마법사로 전달되는 일련의 매개 변수를 포함하는 <xref:System.Object> 배열  
  
 이 예제에서는 사용자 입력 폼의 매개 변수 값을 <xref:System.Collections.Generic.Dictionary%602> 매개 변수에 추가합니다.  프로젝트에서 `$custommessage$` 매개 변수의 모든 인스턴스는 사용자가 입력하는 텍스트로 바뀝니다.  프로젝트에 다음 조립을 추가해야 합니다.  
  
1.  EnvDTE.dll  
  
2.  Microsoft.VisualStudio.TemplateWizardInterface.dll  
  
3.  System.Windows.Forms.dll  
  
> [!IMPORTANT]
>  이 예제에 사용 된 UserInputForm는 다음 섹션에서 정의됩니다.  
  
```c#  
using System;  
using System.Collections.Generic;  
using Microsoft.VisualStudio.TemplateWizard;  
using System.Windows.Forms;  
using EnvDTE;  
  
namespace CustomWizard  
{  
    public class IWizardImplementation:IWizard  
    {  
        private UserInputForm inputForm;  
        private string customMessage;  
  
        // This method is called before opening any item that   
        // has the OpenInEditor attribute.  
        public void BeforeOpeningFile(ProjectItem projectItem)  
        {  
        }  
  
        public void ProjectFinishedGenerating(Project project)  
        {  
        }  
  
        // This method is only called for item templates,  
        // not for project templates.  
        public void ProjectItemFinishedGenerating(ProjectItem   
            projectItem)  
        {  
        }  
  
        // This method is called after the project is created.  
        public void RunFinished()  
        {  
        }  
  
        public void RunStarted(object automationObject,  
            Dictionary<string, string> replacementsDictionary,  
            WizardRunKind runKind, object[] customParams)  
        {  
            try  
            {  
                // Display a form to the user. The form collects   
                // input for the custom message.  
                inputForm = new UserInputForm();  
                inputForm.ShowDialog();  
  
                customMessage = inputForm.get_CustomMessage();  
  
                // Add custom parameters.  
                replacementsDictionary.Add("$custommessage$",   
                    customMessage);  
            }  
            catch (Exception ex)  
            {  
                MessageBox.Show(ex.ToString());  
            }  
        }  
  
        // This method is only called for item templates,  
        // not for project templates.  
        public bool ShouldAddProjectItem(string filePath)  
        {  
            return true;  
        }          
    }  
}  
```  
  
### 사용자 입력 폼  
 사용자 입력 폼은 사용자 지정 매개 변수를 입력할 수 있는 단순한 폼을 제공합니다.  이 폼에는 `textBox1` 이라는 텍스트 상자와 `button1`이라는 단추가 포함되어 있습니다.  단추를 클릭하면 텍스트 상자의 텍스트가 `customMessage` 매개 변수에 저장됩니다.  
  
##### 솔루션에 Windows Form을 추가하려면  
  
1.  마법사 구성 요소가 포함된 파일에 다음 코드를 추가합니다.  
  
```c#  
public partial class UserInputForm : Form  
{  
    private string customMessage;  
    private TextBox textBox1;  
  
    public UserInputForm()  
    {   
        textBox1 = new TextBox();  
        this.Controls.Add(textBox1);  
    }  
  
    public string get_CustomMessage()  
    {  
        return customMessage;  
    }  
  
    private void textBox1_TextChanged(object sender, EventArgs e)  
    {  
        customMessage = textBox1.Text;  
        this.Dispose();  
    }  
}  
```  
  
## 전역 어셈블리 캐시에 어셈블리 설치  
 이 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> 를 구현하는 어셈블리는 강력한 이름으로 서명되어야 하며 전역 어셈블리 캐시에 설치되어야 합니다.  
  
#### 전역 어셈블리 캐시에 어셈블리를 설치하려면  
  
1.  강력한 이름으로 어셈블리에 서명합니다.  자세한 내용은 [방법: 강력한 이름으로 어셈블리 서명](../Topic/How%20to:%20Sign%20an%20Assembly%20with%20a%20Strong%20Name.md) 또는 [How to: Sign an Assembly \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/f468a7d3-234c-4353-924d-8e0ae5896564)를 참조하십시오.  
  
2.  전역 어셈블리 캐시에 강력한 이름의 어셈블리를 설치합니다.  자세한 내용은 [방법: 전역 어셈블리 캐시에 어셈블리 설치](../Topic/How%20to:%20Install%20an%20Assembly%20into%20the%20Global%20Assembly%20Cache.md)을 참조하십시오.  
  
## 템플릿으로 사용할 프로젝트 만들기  
 이 예제에서 템플릿으로 사용되는 프로젝트는 사용자 지정 마법사의 사용자 입력 폼에서 지정한 메시지를 표시하는 콘솔 응용 프로그램입니다.  
  
#### 예제 프로젝트를 만들려면  
  
1.  새 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 콘솔 응용 프로그램을 만듭니다.  
  
2.  응용 프로그램의 `Main` 메서드에 다음 코드 줄을 추가합니다.  
  
    ```  
    Console.WriteLine("$custommessage$");  
    ```  
  
     `$custommessage$` 매개 변수는 프로젝트가 템플릿에서 만들어질 때 사용자 입력 폼에 입력된 텍스트로 바뀝니다.  
  
3.  **파일** 메뉴에서 **템플릿 내보내기**를 클릭합니다.  
  
4.  **템플릿 내보내기** 마법사에서 **프로젝트 템플릿**을 클릭하고 해당 프로젝트를 선택한 후 **다음**을 클릭합니다.  
  
5.  **템플릿 내보내기** 마법사에서 템플릿에 대한 설명 정보를 입력하고 **자동으로 템플릿을 Visual Studio로 가져오기** 확인란을 선택한 다음 **마침**을 클릭합니다.  
  
     템플릿은 **새 프로젝트** 대화 상자에 나타나지만 사용자 지정 마법사를 사용하지 않습니다.  
  
 다음 예제에서는 템플릿으로 내보내기 전의 전체 코드 파일을 보여 줍니다.  
  
```c#  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
namespace TemplateProject  
{  
    class WriteMessage  
    {  
        static void Main(string[] args)  
        {  
            Console.WriteLine("$custommessage$");  
        }  
    }  
}  
```  
  
## 템플릿 수정  
 이제 템플릿이 만들어지고 **새 프로젝트** 대화 상자에 나타나므로 이전 단계에서 만든 어셈블리를 사용하도록 템플릿을 수정해야 합니다.  
  
#### 사용자 지정 마법사를 템플릿에 추가하려면  
  
1.  템플릿을 포함하는 .zip 파일을 찾습니다.  
  
    1.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
    2.  **프로젝트 및 솔루션**을 클릭합니다.  
  
    3.  **Visual Studio 사용자 프로젝트 템플릿 위치** 텍스트 상자를 읽습니다.  
  
     기본적으로 이 위치는 My Documents\\Visual Studio *Version*\\Templates\\ProjectTemplates입니다.  
  
2.  .zip 파일의 압축을 풉니다.  
  
3.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 .vstemplate 파일을 엽니다.  
  
4.  `TemplateContent` 요소 뒤에 사용자 지정 마법사 어셈블리의 강력한 이름을 갖는 [WizardExtension 요소\(Visual Studio 템플릿\)](../extensibility/wizardextension-element-visual-studio-templates.md) 요소를 추가합니다.  어셈블리의 강력한 이름을 찾는 방법에 대한 자세한 내용은 [방법: 전역 어셈블리 캐시의 내용 보기](../Topic/How%20to:%20View%20the%20Contents%20of%20the%20Global%20Assembly%20Cache.md)및 [방법: 강력한 이름의 어셈블리 참조](../Topic/How%20to:%20Reference%20a%20Strong-Named%20Assembly.md)를 참조하십시오.  
  
     다음 예제에서는 `WizardExtension` 요소를 보여 줍니다.  
  
    ```  
    <WizardExtension>  
        <Assembly>CustomWizard, Version=1.0.0.0, Culture=Neutral, PublicKeyToken=fa3902f409bb6a3b</Assembly>  
        <FullClassName>CustomWizard.IWizardImplementation</FullClassName>  
    </WizardExtension>  
    ```  
  
## 사용자 지정 마법사 사용  
 이제는 템플릿에서 프로젝트를 만들고 사용자 지정 마법사를 사용할 수 있습니다.  
  
#### 사용자 지정 마법사를 사용하려면  
  
1.  **파일** 메뉴에서 **새 프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자에서 템플릿을 찾고 이름을 입력한 다음 **확인**을 클릭합니다.  
  
     마법사 사용자 입력 폼이 열립니다.  
  
3.  사용자 지정 매개 변수의 값을 입력하고 단추를 클릭합니다.  
  
     마법사 사용자 입력 폼이 닫히고 템플릿에서 프로젝트가 만들어집니다.  
  
4.  **솔루션 탐색기**에서 소스 코드 파일을 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 선택합니다.  
  
     이 `$custommessage$` 는 마법사 사용자 입력 폼에 입력된 텍스트로 바뀝니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard>   
 [템플릿 사용자 지정](../ide/customizing-project-and-item-templates.md)   
 [WizardExtension 요소\(Visual Studio 템플릿\)](../extensibility/wizardextension-element-visual-studio-templates.md)