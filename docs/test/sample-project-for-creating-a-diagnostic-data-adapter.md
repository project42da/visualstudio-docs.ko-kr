---
title: Visual Studio에서 진단 데이터 어댑터를 만들기 위한 샘플 프로젝트 | Microsoft Docs
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Diagnostic Data Adapter [Visual Studio ALM]
- samples. Diagnostic Data Adapter [Visual Studio ALM]
- Diagnostic Data Adapter, sample
ms.assetid: 548bdc5e-338f-4be7-a555-e6a2efb1df6b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 0b37512405442b327bb4b9688a39bfc4c99ea594
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="sample-project-for-creating-a-diagnostic-data-adapter"></a>진단 데이터 어댑터를 만들기 위한 샘플 프로젝트

"MyDiagnosticDataAdapter"는 테스트를 실행할 때 테스트 결과에 로그 파일을 연결할 수 있는 간단한 진단 데이터 어댑터입니다.

 진단 데이터 수집기 또는 구성 편집기가 설치된 컴퓨터에 대한 관리자 권한이 있어야 합니다.

## <a name="example-data-adapter"></a>데이터 어댑터의 예

이 샘플에서는 다음 작업을 수행하는 방법을 보여 줍니다.

-   Microsoft Test Manager에서 검색 가능한 클래스를 진단 데이터 어댑터로 만드는 특성을 적용합니다.

-   Microsoft Test Manager에서 검색 가능한 사용자 정의 컨트롤 클래스를 진단 데이터 어댑터에 대한 구성을 변경하는 데 사용할 편집기로 만드는 특성을 적용합니다.

-   기본 구성 데이터에 액세스합니다.

-   특정 진단 데이터 수집 이벤트에 등록합니다.

-   로그 파일을 <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink>로 보내 로그 파일을 연결합니다.

```csharp
// My Data Collector Class
using Microsoft.VisualStudio.TestTools.Common;
using Microsoft.VisualStudio.TestTools.Execution;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Xml;
using System;

namespace MyCompany.MyDiagnosticDataAdapters
{
    // Provide a URI and friendly name for your diagnostic data adapter
    [DataCollectorTypeUri("datacollector://MyCompany/MyDataCollector/1.0")]
    [DataCollectorFriendlyName("Collect Log Files sample", false)]
    // Designate your chosen configuration editor
    [DataCollectorConfigurationEditor(
        "configurationeditor://MyCompany/MyDataConfigEditor/1.0")]
    public class MyDataCollector : DataCollector
    {
        private DataCollectionEvents dataEvents;
        private DataCollectionLogger dataLogger;
        private DataCollectionSink dataSink;
        private XmlElement configurationSettings;

        // Required method called by the testing framework
        public override void Initialize(
            XmlElement configurationElement,
            DataCollectionEvents events,
            DataCollectionSink sink,
            DataCollectionLogger logger,
            DataCollectionEnvironmentContext environmentContext)
        {
            dataEvents = events; // The test events
            dataLogger = logger; // The error and warning log
            dataSink = sink;     // Saves collected data
            // Configuration from the test settings
            configurationSettings = configurationElement;

            // Register common events for the data collector
            // Not all of the events are used in this class
            dataEvents.SessionStart +=
                new EventHandler<SessionStartEventArgs>(OnSessionStart);
            dataEvents.SessionEnd +=
                new EventHandler<SessionEndEventArgs>(OnSessionEnd);
            dataEvents.TestCaseStart +=
                new EventHandler<TestCaseStartEventArgs>(OnTestCaseStart);
            dataEvents.TestCaseEnd +=
                new EventHandler<TestCaseEndEventArgs>(OnTestCaseEnd);
            dataEvents.DataRequest +=
                new EventHandler<DataRequestEventArgs>(OnDataRequest);
        }

        protected override void Dispose(bool disposing)
        {
            if (disposing)
            {
                dataEvents.SessionStart -=
                    new EventHandler<SessionStartEventArgs>(OnSessionStart);
                dataEvents.SessionEnd -=
                    new EventHandler<SessionEndEventArgs>(OnSessionEnd);
                dataEvents.TestCaseStart -=
                    new EventHandler<TestCaseStartEventArgs>(OnTestCaseStart);
                dataEvents.TestCaseEnd -=
                    new EventHandler<TestCaseEndEventArgs>(OnTestCaseEnd);
                dataEvents.DataRequest -=
                    new EventHandler<DataRequestEventArgs>(OnDataRequest);
            }
        }

        #region Event Handlers
        public void OnSessionStart(object sender, SessionStartEventArgs e)
        {
            // TODO: Provide implementation
        }

        public void OnSessionEnd(object sender, SessionEndEventArgs e)
        {
            // TODO: Provide implementation
        }

        public void OnTestCaseStart(object sender, TestCaseEventArgs e)
        {
            // TODO: Provide implementation
        }

        public void OnTestCaseEnd(object sender, TestCaseEndEventArgs e)
        {
            // Get any files to be collected that are
            // configured in your test settings
            List<string> files = getFilesToCollect();

            // For each of the files, send the file to the data sink
            // which will attach it to the test results or to a bug
            foreach (string file in files)
            {
                dataSink.SendFileAsync(e.Context, file, false);
            }
        }

        public void OnDataRequest(object sender, DataRequestEventArgs e)
        {
            // TODO: Provide implementation
            // Most likely this occurs because a bug is being filed
        }
        #endregion

        // A private method to collect the configured file names
        private List<string> getFilesToCollect()
        {
            // Seetup namespace manager with our namespace
            XmlNamespaceManager nsmgr =
                new XmlNamespaceManager(
                    configurationSettings.OwnerDocument.NameTable);
            nsmgr.AddNamespace("ns",
                "http://MyCompany/schemas/MyDataCollector/1.0");

            // Find all of the "File" elements under our configuration
            XmlNodeList files =
                configurationSettings.SelectNodes(
                    "//ns:MyDataCollector/ns:File");

            // Build the list of files to collect from the
            // "FullPath" attributes of the "File" nodes.
            List<string> result = new List<string>();
            foreach (XmlNode fileNode in files)
            {
                XmlAttribute pathAttribute =
                    fileNode.Attributes["FullPath"];
                if (pathAttribute != null &&
                    !String.IsNullOrEmpty(pathAttribute.Value))
                {
                    result.Add(pathAttribute.Value);
                }
            }

            return result;
        }
    }
}
```

## <a name="example-configuration-editor"></a>구성 편집기의 예

다음은 진단 데이터 어댑터에 대한 샘플 구성 편집기입니다. 프로젝트에 사용자 정의 컨트롤을 추가하고 "Name of Log File:"이라는 레이블의 매우 간단한 폼과 "FileTextBox"라는 텍스트 상자를 만듭니다.

```csharp
using Microsoft.VisualStudio.TestTools.Common;
using Microsoft.VisualStudio.TestTools.Execution;
using System.Collections.Generic;
using System.ComponentModel;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;
using System.Xml;
using System;

namespace MyCompany.DiagnosticDataAdapters.ConfigurationEditors
{
    [DataCollectorConfigurationEditorTypeUri(
        "configurationeditor://MyCompany/MyConfigEditor/1.0")]
    public partial class MyDataConfigEditor :
        UserControl, IDataCollectorConfigurationEditor
    {
        private DataCollectorSettings collectorSettings;

        // Create a private property for the service provider
        private IServiceProvider ServiceProvider { get; set; }

        // Constructor
        public MyConfigurationEditor()
        {
            InitializeComponent();
        }

        // Required method called by the testing framework
        public void Initialize(
            IServiceProvider svcProvider,
            DataCollectorSettings settings)
        {
            ServiceProvider = svcProvider;
            collectorSettings = settings;

            // Display the file name as listed in the settings file.
            // If the configuration has not been updated before, this
            // data will be provided by the default configuration
            // section from <nameofcollector>.dll.config:
            // <DefaultConfiguration>
            //   <MyCollectorName
            //       xmlns="http://MyCompany/schemas/ProductName/Version");
            //     <File FullPath="C:\temp\logfile1.txt" />
            //   </MyCollectorName>
            // </DefaultConfiguration>
            this.SuspendLayout();
            this.FileTextBox.Text = GetText(collectorSettings.Configuration);
            this.ResumeLayout();
        }

        // Can be used to verify data before saving it
        public bool VerifyData()
        {
            // Not currently verifying data
            return true;
        }

        // Reset to default value from XML configuration
        // using a custom method
        public void ResetToAgentDefaults()
        {
            this.FileTextBox.Text =
                getText(collectorSettings.DefaultConfiguration);
        }

        // Saves data changed in the editor to the test configuration
        // settings. Does not change the default value.
        public DataCollectorSettings SaveData()
        {
            collectorSettings.Configuration.InnerXml =
                String.Format(
                    @"<MyCollectorName
      xmlns=""http://MyCompany/schemas/MyDataCollector/1.0"">
  <File FullPath=""{0}"" />
</MyCollectorName>",
                    FileTextBox.Text);
            return collectorSettings;
        }

        // Reads the configuration settings
        private string getText(XmlElement element)
        {
            // Setup namespace manager with our namespace
            XmlNamespaceManager nsmgr =
                new XmlNamespaceManager(
                    element.OwnerDocument.NameTable);

            // Find all the "File" elements under our configuration
            XmlNodeList files = element.SelectNodes("//ns:MyDataCollector/ns:File", nsmgr);

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
    }
}
```

## <a name="example-configuration-file"></a>구성 파일의 예

다음은 진단 데이터 수집기 구성 편집기에 대한 샘플 구성 파일입니다.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <section
      name="DataCollectorConfiguration"
      type="Microsoft.VisualStudio.QualityTools.Execution.DataCollectorConfigurationSection,
        Microsoft.visualStudio.QualityTools.ExecutionCommon,
        Version=4.0.0.0, Culture=neutral,
        PublicKeyToken=b03f5f7f11d50a3a" />
  </configSections>
  <DataCollectorConfiguration
      xmlns="http://microsoft.com/schemas/VisualStudio/TeamTest/11">
    <DataCollector
        typeUri="datacollector://MyCompany/MyDataCollector/1.0">
      <DefaultConfiguration>
        <!-- Your default config settings-->
        <File FullPath="c:\temp\logfile1.txt" />
      </DefaultConfiguration>
    </DataCollector>
  </DataCollectorConfiguration>
</configuration>

```

## <a name="compiling-the-code"></a>코드 컴파일

### <a name="to-create-the-code-project-for-this-diagnostic-adapter"></a>이 진단 데이터 어댑터에 대한 코드 프로젝트를 만들려면

1.  "MyDataCollector"라는 새 클래스 라이브러리 프로젝트를 만듭니다.

2.  **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭한 다음, **속성**을 선택합니다. 추가할 폴더를 선택하려면 **참조 경로**를 선택한 후 줄임표(**...**)를 선택합니다.

     **참조 경로 선택** 대화 상자가 표시됩니다.

3.  사용자 설치 디렉터리를 기준으로 *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies* 경로를 선택합니다. **확인**을 선택합니다.

4.  참조 경로에 폴더를 추가하려면 **폴더 추가**를 선택합니다.

     참조 경로 목록에 폴더가 표시됩니다.

5.  **모두 저장** 아이콘을 선택하여 참조 경로를 저장합니다.

6.  어셈블리 **Microsoft.VisualStudio.QualityTools.ExecutionCommon**을 추가합니다.

    1.  **솔루션 탐색기**에서 **참조**를 마우스 오른쪽 단추로 클릭한 다음, **참조 추가**를 선택합니다.

    2.  **찾아보기**를 선택하고 **Microsoft.VisualStudio.QualityTools.ExecutionCommon.dll**을 찾습니다.

         이 어셈블리는 *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies*에 있습니다.

    3.  **확인**을 선택합니다.

7.  어셈블리 **Microsoft.VisualStudio.QualityTools.Common**을 추가합니다.

    1.  솔루션 탐색기에서 **참조**를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택합니다.

    2.  **찾아보기**를 선택하고 **Microsoft.VisualStudio.QualityTools.Common.dll**을 찾습니다.

         이 어셈블리는 *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies*에 있습니다.

    3.  **확인**을 선택합니다.

8.  이 문서의 앞부분에 나열된 진단 데이터 어댑터 클래스를 클래스 라이브러리에 대한 클래스로 복사합니다. 이 클래스를 저장합니다.

9. 프로젝트에 사용자 정의 컨트롤을 추가하려면 솔루션 탐색기에서 MyDataCollector 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음, **사용자 정의 컨트롤**을 선택합니다. **추가**를 선택합니다.

10. 도구 상자를 사용하여 사용자 정의 컨트롤에 레이블을 추가하고 텍스트 속성을 **파일 이름:**으로 변경합니다.

11. 도구 상자를 사용하여 사용자 정의 컨트롤에 텍스트 상자를 추가하고 이름을 **textBoxFileName**으로 변경합니다.

12. **솔루션 탐색기**에서 사용자 정의 컨트롤을 마우스 오른쪽 단추로 클릭한 다음, **코드 보기**를 선택합니다. 이 사용자 정의 컨트롤 클래스를 이 문서의 앞부분에 나열된 사용자 정의 컨트롤 클래스로 바꿉니다. 이 클래스를 저장합니다.

    > [!NOTE]
    > 기본적으로 사용자 정의 컨트롤은 UserControl1이라고 합니다. 이 사용자 정의 컨트롤 클래스 코드가 이 예제에서 추가한 사용자 정의 컨트롤의 이름을 사용하는지 확인합니다.

13. 구성 파일을 만들려면 **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음, **새 항목**을 선택합니다. **응용 프로그램 구성 파일**을 선택한 다음, **추가**를 선택합니다. 이렇게 하면 **App.config**라는 파일이 솔루션에 추가됩니다.

14. 앞에 제공된 샘플에 나와 있는 XML을 XML 파일로 복사합니다. 파일을 저장합니다.

15. 솔루션을 빌드한 다음, 빌드한 어셈블리와 `App.config` 파일을 *%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies\DataCollectors* 디렉터리에 복사합니다.

16. 이 사용자 지정 진단 데이터 어댑터를 사용하는 테스트 설정을 만듭니다. 존재하는 파일을 수집하도록 테스트 설정을 구성합니다.

     Microsoft Test Manager에서 테스트를 실행할 경우 테스트를 실행하기 전에 테스트 계획에 이러한 테스트 설정을 할당하거나 옵션과 함께 실행 명령을 사용하여 테스트 설정을 할당하고 테스트 설정을 재정의할 수 있습니다. 테스트 설정에 대한 자세한 내용은 [테스트 설정을 사용하여 진단 정보 수집](../test/collect-diagnostic-information-using-test-settings.md)을 참조하세요.

17. 진단 데이터 어댑터가 선택된 테스트 설정을 사용하여 테스트를 실행합니다.

     테스트가 실행될 때 지정한 데이터 파일이 테스트 결과에 연결됩니다.

## <a name="see-also"></a>참고 항목

- [방법: 진단 데이터 어댑터 만들기](../test/how-to-create-a-diagnostic-data-adapter.md)
- [방법: 진단 데이터 어댑터 데이터용 사용자 지정 편집기 만들기](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)
- [방법: 사용자 지정 진단 데이터 어댑터 설치](../test/how-to-install-a-custom-diagnostic-data-adapter.md)
- [진단 데이터 어댑터를 만들어 사용자 지정 데이터를 수집하거나 테스트 컴퓨터에 영향 주기](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)