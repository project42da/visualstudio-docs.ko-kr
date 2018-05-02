---
title: Visual Studio에서 진단 데이터 어댑터에 대한 사용자 지정 데이터 편집기 만들기
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter, creating custom editor
ms.assetid: 24970227-d1ea-4f6d-9839-e911478848ba
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 6141defb2248cf79888b0ed94824a827bd36815f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter"></a>방법: 진단 데이터 어댑터 데이터용 사용자 지정 편집기 만들기

진단 데이터 어댑터를 만드는 경우 테스트 설정에 대한 사용자 지정 진단 데이터 어댑터가 선택될 때 최종 사용자가 특정 데이터를 구성할 수 있도록 설정할 수 있습니다. 예를 들어, 추출할 레지스트리 키, 시뮬레이트할 네트워크 부하 수준 또는 연결할 임시 파일이나 작업 파일을 찾을 디렉터리를 지정하는 구성 데이터를 선택할 수 있습니다.

구성 파일을 사용하여 진단 데이터 어댑터의 초기 값을 설정해야 합니다. 사용자가 구성 데이터를 수정할 수 있도록 해주는 사용자 지정 편집기를 제공할 수 있습니다.

편집기를 직접 만들려면 <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor>를 구현하는 사용자 정의 컨트롤을 만듭니다.

진단 데이터 어댑터는 <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>를 사용하여 진단 데이터 구성 설정을 편집하는 데 사용할 편집기 클래스를 지정할 수 있습니다.

또한 사용할 기본 구성 데이터를 지정합니다.  샘플 기본 구성에 대한 [진단 데이터 어댑터 생성을 위한 샘플 프로젝트](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)를 참조하세요.

사용자 지정 진단 데이터 어댑터를 사용할 때 테스트 설정에 대한 데이터를 업데이트하는 사용자 지정 편집기를 만들려면 다음 절차를 수행합니다.

> [!NOTE]
> 사용자 지정 편집기를 만들려면 먼저 클래스에 <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>가 적용된 진단 데이터 어댑터를 만들어야 합니다. 해당 특성의 선택적 <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute.HelpUri*> 속성을 사용하여 편집기의 도움말 콘텐츠 소스를 지정할 수 있습니다. 진단 데이터 어댑터를 만드는 방법에 대한 자세한 내용은 [방법: 진단 데이터 어댑터 만들기](../test/how-to-create-a-diagnostic-data-adapter.md)를 참조하세요.

사용자 지정 구성 편집기를 비롯한 전체 예제 진단 데이터 어댑터 프로젝트는 [진단 데이터 어댑터를 만들기 위한 샘플 프로젝트](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)를 참조하세요.

## <a name="to-create-a-custom-editor-for-your-diagnostic-data-adapter"></a>진단 데이터 어댑터용 사용자 지정 편집기를 만들려면

1.  프로젝트에서 진단 데이터 어댑터용 사용자 정의 컨트롤을 만듭니다.

    1.  진단 데이터 어댑터 클래스가 포함되어 있는 코드 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음, **사용자 정의 컨트롤**을 가리킵니다.

    2.  이 예제에서는 **Data File Name:** 이라는 텍스트가 있는 레이블과 **FileTextBox**라는 텍스트 상자를 양식에 추가하여 사용자가 필요한 데이터를 입력할 수 있도록 합니다.

    > [!NOTE]
    > 현재 Windows Forms 사용자 정의 컨트롤만 지원됩니다.

2.  다음 줄을 선언 섹션에 추가합니다.

    ```csharp
    using System.Xml;
    using Microsoft.VisualStudio.TestTools.Common;
    using Microsoft.VisualStudio.TestTools.Execution;
    ```

3.  이 사용자 지정 컨트롤을 사용자 지정 편집기로 만듭니다.

    1.  코드 프로젝트에서 사용자 정의 컨트롤을 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 가리킵니다.

    2.  다음과 같이 클래스에서 편집기 인터페이스 <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor>를 구현하도록 설정합니다.

    ```csharp
    public partial class MyDataConfigEditor :
         UserControl, IDataCollectorConfigurationEditor
    ```

    1.  코드에서 <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor>를 마우스 오른쪽 단추로 클릭하고 **인터페이스 구현** 명령을 선택합니다. 이 인터페이스에 대해 구현해야 할 메서드가 클래스에 추가됩니다.

    2.  편집기에서 사용자 정의 컨트롤을 진단 데이터 어댑터 편집기로 식별하도록 해당 사용자 정의 컨트롤에 <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>를 추가하고 **회사**, **제품** 및 **버전**을 진단 데이터 어댑터에 대한 적합한 정보로 바꿉니다.

        ```csharp
        [DataCollectorConfigurationEditorTypeUri(
            "configurationeditor://MyCompany/MyConfigEditor/1.0")]
        ```

4.  다음과 같이 두 개의 private 변수를 추가합니다.

    ```csharp
    private DataCollectorSettings collectorSettings;
    private IServiceProvider ServiceProvider { get; set; }
    ```

5.  진단 데이터 어댑터용 편집기를 초기화할 코드를 추가합니다. 설정 변수에 있는 데이터를 사용하여 사용자 정의 컨트롤의 필드에 기본값을 추가할 수 있습니다. 이는 어댑터에 대한 XML 구성 파일의 `<DefaultConfiguration>` 요소에 있는 데이터입니다.

    ```csharp
    public void Initialize(
        IServiceProvider svcProvider,
        DataCollectorSettings settings)
    {
        ServiceProvider = svcProvider;
        collectorSettings = settings;

        // Display the default file name as listed in the settings file.
        this.SuspendLayout();
        this.FileTextBox.Text = getText(collectorSettings.Configuration);
        this.ResumeLayout();
    }
    ```

6.  다음과 같이 편집기에서 컨트롤의 데이터를 진단 데이터 어댑터 API에서 필요로 하는 XML 형식으로 다시 저장하는 코드를 추가합니다.

    ```csharp
    public DataCollectorSettings SaveData()
    {
        collectorSettings.Configuration.InnerXml =
            String.Format(
    @"<MyCollectorName
        xmlns=""http://MyCompany/schemas/MyDiagnosticDataCollector/1.0"">
      <File FullPath=""{0}"" />
    </MyCollectorName>",
        FileTextBox.Text);
        return collectorSettings;
    }
    ```

7.  `VerifyData` 메서드에서 데이터가 올바른지 확인하는 코드를 추가하는 것이 중요합니다. 또는 이 메서드에서 `true`를 반환하도록 지정할 수 있습니다.

    ```csharp
    public bool VerifyData()
    {
        // Not currently verifying data
        return true;
    }
    ```

8.  (선택 사항) 전용 `ResetToAgentDefaults()` 메서드를 사용하는 `getText()` 메서드에서 데이터를 XML 구성 파일에 제공된 초기 설정으로 다시 설정하는 코드를 추가할 수 있습니다.

    ```csharp
    // Reset to default value from XML configuration
    // using a custom getText() method
    public void ResetToAgentDefaults()
    {
        this.FileTextBox.Text = getText(collectorSettings.DefaultConfiguration);
    }

    // Local method to read the configuration settings
    private string getText(XmlElement element)
    {
        // Setup namespace manager with our namespace
        XmlNamespaceManager nsmgr =
            new XmlNamespaceManager(
                element.OwnerDocument.NameTable);

        // Find all the "File" elements under our configuration
        XmlNodeList files = element.SelectNodes("//ns:MyCollectorName/ns:File", nsmgr);

        string result = String.Empty;
        if (files.Count > 0)
        {
            XmlAttribute pathAttribute = files[0].Attributes["FullPath"];
            if (pathAttribute != null &&
                !String.IsNullOrEmpty(pathAttribute.Value))
            {
                result = pathAttribute.Value;
            }
        }

        return result;
    }
    ```

9. 솔루션을 빌드합니다. 진단 데이터 어댑터 어셈블리 및 XML 구성 파일(`<diagnostic data adapter name>.dll.config`)을 사용자 설치 디렉터리를 기준으로 *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies\DataCollectors*에 해당하는 위치에 복사합니다.

    > [!NOTE]
    > 구성 편집기는 진단 데이터 어댑터와는 다른 프로젝트 및 어셈블리에 있을 수도 있지만, 동일한 어셈블리에 있을 수도 있습니다.

10. 테스트에서 진단 데이터 어댑터를 사용하려면 기존 테스트 설정 목록에서 선택하거나 Microsoft Test Manager 또는 Visual Studio에서 새 항목을 만든 후 진단 데이터 어댑터를 선택해야 합니다.

     어댑터는 클래스에 할당된 이름으로 테스트 설정의 **데이터 및 진단** 탭에 표시됩니다.

11. 테스트 설정에 대해 진단 데이터 어댑터를 구성하려면 어댑터 이름 옆에서 **구성**을 선택합니다.

     이제 사용자 지정 편집기가 표시됩니다.

12. 필요한 경우 사용자 지정 편집기에서 필드를 편집한 다음, **저장**을 선택합니다.

13. Microsoft Test Manager에서 테스트를 실행할 경우 테스트를 실행하기 전에 테스트 계획에 이러한 테스트 설정을 할당하거나, **옵션과 함께 실행** 명령을 사용하여 테스트 설정을 할당하고 테스트 설정을 재정의할 수 있습니다. 테스트 설정에 대한 자세한 내용은 [테스트 설정을 사용하여 진단 정보 수집](../test/collect-diagnostic-information-using-test-settings.md)을 참조하세요.

14. 진단 데이터 어댑터가 있는 새 구성 편집기를 사용하기 전에 먼저 편집기를 사용할 각 진단 데이터 어댑터 클래스에 <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>를 적용하고, 클라이언트 컴퓨터에서 다시 컴파일하고 다시 설치해야 합니다. 진단 데이터 어댑터와 구성 편집기를 설치하는 방법에 대한 자세한 내용은 [방법: 사용자 지정 진단 데이터 어댑터 설치](../test/how-to-install-a-custom-diagnostic-data-adapter.md)를 참조하세요.

15. 진단 데이터 어댑터가 선택된 테스트 설정을 사용하여 테스트를 실행합니다.

     편집기에서 지정한 데이터 파일이 테스트 결과에 연결됩니다.

 테스트를 실행할 때 환경을 사용하도록 테스트 설정을 구성하는 방법에 대한 자세한 내용은 [테스트하는 동안 진단 데이터 수집(VSTS)](/vsts/manual-test/collect-diagnostic-data) 또는 [수동 테스트에서 진단 데이터 수집(VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)을 참조하세요.

## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>
- [진단 데이터 어댑터를 만들어 사용자 지정 데이터를 수집하거나 테스트 컴퓨터에 영향 주기](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)
- [테스트 설정을 사용하여 진단 정보 수집](../test/collect-diagnostic-information-using-test-settings.md)
- [진단 데이터 어댑터를 만들기 위한 샘플 프로젝트](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)