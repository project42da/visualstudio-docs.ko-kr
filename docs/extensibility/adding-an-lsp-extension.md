---
title: "서버 프로토콜 언어 확장 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/14/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52f12785-1c51-4c2c-8228-c8e10316cd83
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ea93ddee9c47f80322db2403aeecc0fb7dddb209
ms.sourcegitcommit: c0a2385a16cc4f47d2e1ff23d35c4da40f5605e0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="adding-a-language-server-protocol-extension"></a>서버 프로토콜 언어 확장 추가

언어 서버 프로토콜 (LSP)는 서비스 기능을 다양 한 코드 편집기를 제공 하는 데 사용 되는 JSON RPC v2.0의 형태로 일반적인 프로토콜입니다. 프로토콜을 사용 개발자 LSP를 지 원하는 다양 한 코드 편집기에 모든 등에 대 한 참조를 찾을, IntelliSense, 오류를 진단 같은 서비스 기능 언어를 제공 하기 위해 단일 언어 서버를 작성할 수 있습니다. 일반적으로 하나가 Visual Studio에서 언어 서비스를 추가할 수 있습니다 TextMate 문법 파일을 사용 하 여 같은 구문 강조 표시 하거나 Visual Studio 확장성 Api의 전체 집합을 사용 하 여 사용자 지정 언어 서비스를 작성 하 여 기본 기능을 제공 하기를 다양 한 데이터를 제공 합니다. 이제 지원 LSP 수 있는 세 번째 옵션을 제공 합니다.

![Visual Studio에서 서버 프로토콜 서비스 언어](media/lsp-service-in-VS.png)

## <a name="language-server-protocol"></a>언어 서버 프로토콜

프로토콜 자체에 대 한 자세한 내용은 설명서를 참조 하십시오. [여기](https://github.com/Microsoft/language-server-protocol)합니다. 언어 서버 프로토콜의 구현 visual Studio의 미리 보기에 있으며 지원을 실험적으로 간주 됩니다. 미리 보기 릴리스에서 확장의 형태로 표현 ([언어 서버 프로토콜 클라이언트 미리 보기](https://marketplace.visualstudio.com/items?itemName=vsext.LanguageServerClientPreview)), **이 확장 수만 설치에 미리 보기 채널의 Visual Studio**합니다. 이후 버전의 Visual Studio 언어 서버 프로토콜, 미리 보기 플래그는 삭제 될 때에 기본 제공을 포함 됩니다. **프로덕션 환경에 대 한 미리 보기를 사용 하지 마십시오.**

샘플 언어 서버 또는 Visual Studio 코드를 기존 언어 서버를 통합 하는 방법을 참조 설명서를 만드는 방법에 대 한 자세한 내용은 [여기](https://code.visualstudio.com/docs/extensions/example-language-server)합니다.

![언어 서버 프로토콜 구현](media/lsp-implementation.png)

이 문서에서는 언어 LSP 기반 서버를 사용 하는 Visual Studio 확장을 만드는 방법을 설명 합니다. LSP 기반 언어 서버를 미리 만들어 둔 Visual Studio로 통합 하 려 하 가정 합니다.

Visual Studio 내에서 지원에 대 한 언어 서버가 (Visual Studio)는 다음과 같은 메커니즘을 통해 클라이언트와 통신할 수 있습니다.

* 표준 입력/출력 스트림
* 명명 된 파이프
* 소켓

Visual Studio에서 지원을 확인 하 고 LSP의 목적은 Visual Studio 제품의 일부분이 아닌 온보드 언어 서비스를입니다. Visual Studio에서 기존 언어 서비스 (예: C#)를 확장 하는 것이 아닙니다. 기존 언어를 확장 하려면 언어 서비스의 확장성 가이드를 참조 하세요 (예를 들어는 ["Roslyn".NET 컴파일러 플랫폼](../extensibility/dotnet-compiler-platform-roslyn-extensibility.md)).

## <a name="language-server-protocol-features-supported"></a>지원 되는 언어 서버 프로토콜 기능

다음과 같은 LSP 기능이 Visual Studio에서 지금까지 지원 됩니다.

메시지 | Visual studio에서에서 지원
--- | ---
초기화 | 예
초기화됨 | 예
종료 | 예
종료 | 예
$/cancelRequest | 예
window/showMessage | 예
window/showMessageRequest | 예
window/logMessage | 예
원격 분석/이벤트 |
client/registerCapability |
client/unregisterCapability |
workspace/didChangeConfiguration | 예
workspace/didChangeWatchedFiles | 예
workspace/symbol | 예
workspace/executeCommand | 예
workspace/applyEdit | 예
textDocument/publishDiagnostics | 예
textDocument/didOpen | 예
textDocument/didChange | 예
textDocument/willSave |
textDocument/willSaveWaitUntil |
textDocument/didSave | 예
textDocument/didClose | 예
textDocument/완료 | 예
completion/resolve | 예
textDocument/가리키기 | 예
textDocument/signatureHelp | 예
textDocument/참조 | 예
textDocument/documentHighlight |
textDocument/documentSymbol | 예
textDocument/서식 지정 | 예
textDocument/rangeFormatting | 예
textDocument/onTypeFormatting |
textDocument/definition | 예
textDocument/codeAction | 예
textDocument/codeLens |
codeLens/resolve |
textDocument/documentLink |
documentLink/resolve |
textDocument/rename | 예

## <a name="getting-started"></a>시작

### <a name="create-a-vsix-project"></a>VSIX 프로젝트 만들기

LSP 기반 언어 서버를 사용 하는 언어 서비스 확장을 만들려면 먼저 확인 해야 합니다는 **Visual Studio 확장 개발** VS 인스턴스에 대 한 설치 하는 작업입니다.

다음으로 이동 하 여 새 빈 VSIXProject 만듭니다 **파일** > **새 프로젝트** > **Visual C#**  >   **확장성** > **VSIX 프로젝트**:

![vsix 프로젝트 만들기](media/lsp-vsix-project.png)

미리 보기 릴리스에 대 한 VSIX의 형태로 LSP에 대 한 VS 지원 됩니다 ([Microsoft.VisualStudio.LanguageServer.Client.Preview](https://marketplace.visualstudio.com/items?itemName=vsext.LanguageServerClientPreview)). 확장 하려는 개발자는 LSP 언어 서버를 사용 하 여 확장 프로그램을 만들려면이 VSIX에 종속성을 수행 해야 합니다. 서버 언어 확장을 설치 하려는 하는 고객 따라서 **언어 서버 프로토콜 클라이언트 미리 보기 VSIX를 먼저 설치 해야 합니다.**

VSIX 종속성을 정의 하려면 프로그램 VSIX에 대 한 VSIX 매니페스트 디자이너 (프로젝트에서 source.extension.vsixmanifest 파일을 두 번 클릭) 하 여 열고 이동 **종속성**:

![서버 프로토콜 클라이언트 언어에 대 한 참조를 추가 합니다.](media/lsp-reference-lsp-dependency.png)

다음과 같은 새 종속성을 만듭니다.

![언어 서버 프로토콜 클라이언트 종속성 정의](media/lsp-define-lsp-dependency.png)

* **소스**: 수동으로 정의
* **이름**: 언어 서버 프로토콜 클라이언트 미리 보기
* **Identifier**: Microsoft.VisualStudio.LanguageServer.Client.Preview
* **버전 범위**: [1.0,2.0)
* **종속성 확인 방법은**: 사용자가 설치 된
* **Download URL**: [https://marketplace.visualstudio.com/items?itemName=vsext.LanguageServerClientPreview](https://marketplace.visualstudio.com/items?itemName=vsext.LanguageServerClientPreview)

> [!NOTE]
> **다운로드 URL** 확장 프로그램을 설치 하는 사용자가 필요한 종속성을 설치 하는 방법을 확인할 수 있도록 입력 해야 합니다.

### <a name="language-server-and-runtime-installation"></a>언어 서버 및 런타임 설치

기본적으로 Visual Studio에서 언어 LSP 기반 서버를 지원 하기 위해 만든 확장 언어 서버 자체 또는 실행 하는 데 필요한 런타임을 포함 되지 않습니다. 확장 개발자는 language 서버와 필요한 런타임을 배포 하는 일을 담당 합니다. 이렇게 하려면 몇 가지 있습니다.

* 언어 서버가 콘텐츠 파일로 VSIX에 포함할 수 있습니다.
* 언어 서버를 설치 하기 위해 MSI를 만들기 및/또는 런타임 필요 합니다.
* 서버 런타임 및 언어를 확보 하는 방법을 마켓플레이스를 위해서 사용자에 게 지침을 제공 합니다.

### <a name="textmate-grammar-files"></a>TextMate 문법 파일

LSP 언어에 대 한 텍스트 색 지정을 제공 하는 방법에 대 한 사양이 포함 되지 않습니다. Visual Studio에서 언어에 대 한 사용자 지정 색 지정을 제공 하려면 확장 개발자는 TextMate 문법 파일을 사용할 수 있습니다. 사용자 지정 TextMate 문법 또는 테마 파일을 추가 하려면 다음이 단계를 수행 합니다.

1. 내부 확장 프로그램 "문법" 라는 폴더를 만듭니다 (또는 원하는 수)입니다.

2. "문법" 폴더 안에 *.tmlanguage, *.plist, *.tmtheme, 또는 사용자 지정 색 지정을 제공 하는 원하는 *.json 파일을 포함 합니다.

3. 선택한 파일을 마우스 오른쪽 단추로 클릭 **속성**합니다. 빌드 작업을 **콘텐츠** 및 **VSIX에 포함** 속성을 true로 합니다.

4. .Pkgdef 파일을 만들고이 다음과 같은 줄을 추가 합니다.

  ```xml
  [$RootKey$\TextMate\Repositories]
  "MyLang"="$PackageFolder$\Grammars"
  ```

5. 선택한 파일을 마우스 오른쪽 단추로 클릭 **속성**합니다. 빌드 작업을 **콘텐츠** 및 **VSIX에 포함** 속성을 true로 합니다.

이전 단계를 완료 한 후 "문법" 폴더를 패키지의 설치에 추가 저장소 원본과 디렉터리에 이름이 'MyLang' ('MyLang' 명확성에 대 한 이름만 이며 고유한 문자열일 수)입니다. Potentials로 획득 문법 (.tmlanguage 파일)와이 디렉터리에 테마 파일 (.tmtheme 파일)의 모든 고 TextMate와 함께 제공 되는 기본 제공 문법을 대체 합니다. 문법 파일 선언 된 확장에 열리는 파일의 확장명 일치 TextMate 단계 됩니다.

## <a name="creating-a-simple-language-client"></a>간단한 언어 클라이언트 만들기

### <a name="main-interface---ilanguageclientdotnetapimicrosoftvisualstudiolanguageserverclientilanguageclientviewvisualstudiosdk-2017"></a>기본 인터페이스- [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017)

VSIX 프로젝트를 만든 후 다음 NuGet 패키지를 프로젝트에 추가 합니다.

* [Microsoft.VisualStudio.LanguageServer.Client](https://www.nuget.org/packages/Microsoft.VisualStudio.LanguageServer.Client)

> [!NOTE]
> 이전 단계를 완료 한 후 NuGet 패키지에 대 한 종속성 라인 있는 경우 Newtonsoft.Json 및 StreamJsonRpc 패키지도 프로젝트에 추가 됩니다. **Visual Studio의 버전에 해당 새 버전을 설치할 것이 확실 하지 않은 경우 이러한 패키지를 업데이트 하지 마십시오 하는 확장이 대상**합니다. 어셈블리는 포함 되지 VSIX-에 대신, 이러한 선택 됩니다 Visual Studio 설치 디렉터리에서입니다. 확장 프로그램은 사용자의 컴퓨터에 설치 된 것 보다 최신 버전의 어셈블리를 참조 하는 경우 *작동 하지 것입니다*합니다.

구현 하는 새 클래스를 만들 수 있습니다는 [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017) 인터페이스, 언어 LSP 기반 서버에 연결 하는 언어 클라이언트에 필요한 주 인터페이스입니다.

다음은 샘플입니다.

```csharp
namespace MockLanguageExtension
{
    [ContentType("bar")]
    [Export(typeof(ILanguageClient))]
    public class BarLanguageClient : ILanguageClient
    {
        public string Name => "Bar Language Extension";

        public IEnumerable<string> ConfigurationSections => null;

        public object InitializationOptions => null;

        public IEnumerable<string> FilesToWatch => null;

        public event AsyncEventHandler<EventArgs> StartAsync;
        public event AsyncEventHandler<EventArgs> StopAsync;

        public async Task<Connection> ActivateAsync(CancellationToken token)
        {
            await Task.Yield();

            ProcessStartInfo info = new ProcessStartInfo();
            info.FileName = Path.Combine(Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location), "Server", @"MockLanguageServer.exe");
            info.Arguments = "bar";
            info.RedirectStandardInput = true;
            info.RedirectStandardOutput = true;
            info.UseShellExecute = false;
            info.CreateNoWindow = true;

            Process process = new Process();
            process.StartInfo = info;

            if (process.Start())
            {
                return new Connection(process.StandardOutput.BaseStream, process.StandardInput.BaseStream);
            }

            return null;
        }

        public async Task OnLoadedAsync()
        {
            await StartAsync?.InvokeAsync(this, EventArgs.Empty);
        }

        public async Task OnServerInitializeFailedAsync(Exception e)
        {
            return Task.CompletedTask;
        }

        public async Task OnServerInitializedAsync()
        {
            return Task.CompletedTask;
        }
    }
}
```

구현 해야 하는 주요 메서드는 [OnLoadedAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.onloadedasync?view=visualstudiosdk-2017) 및 [ActivateAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.activateasync?view=visualstudiosdk-2017)합니다. [OnLoadedAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.onloadedasync?view=visualstudiosdk-2017) Visual Studio에 확장 작업량이 높고 언어 서버를 시작할 수 때 호출 됩니다. 이 메서드를 호출할 수 있습니다는 [StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017) 바로 시작 되어야 언어 서버 또는 추가 논리를 수행 하 고 호출 신호로에 대리자 [StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017) 나중입니다. **언어 서버를 활성화 하려면 특정 시점에 StartAsync를 호출 해야 합니다.**

[ActivateAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.activateasync?view=visualstudiosdk-2017) 결국 호출 하 여 호출 하는 방법의 [StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017) 위임; 언어 서버를 시작 하 고 연결을 설정 하는 논리를 포함 합니다. 서버에 쓰고 서버에서 읽기 위한 스트림을 포함 하는 연결 개체를 반환 합니다. 여기에 throw 되는 예외를 포착 되 고 Visual Studio에서 메시지는 정보 표시줄을 통해 사용자에 게 표시 합니다.

### <a name="activation"></a>활성화

언어 클라이언트 클래스에서 구현 되 고 나면 정의할 방법을 수 Visual Studio에 로드 하 고 활성화에 대 한 두 가지 특성을 정의할 수 필요 합니다.

```csharp
  [Export(typeof(ILanguageClient))]
  [ContentType("bar")]
```

### <a name="mef"></a>MEF

Visual Studio를 사용 하 여 [MEF](https://github.com/Microsoft/vs-mef/blob/master/doc/index.md) (Managed Extensibility Framework)의 확장 지점을 관리할 수 있습니다. [내보내기](https://msdn.microsoft.com/library/system.componentmodel.composition.exportattribute(v=vs.110).aspx) 이 클래스는 확장 지점으로 선택 및 적절 한 번에 로드는 Visual Studio에 특성을 나타냅니다.

MEF를 사용 하려면 또한 VSIX 매니페스트의 자산으로 MEF를 정의 해야 합니다.

VSIX 매니페스트 디자이너를 열고 탐색 하 고 **자산** 탭:

![MEF 자산 추가](media/lsp-add-asset.png)

새 자산을 만드는 새를 클릭 합니다.

![MEF 자산을 정의 합니다.](media/lsp-define-asset.png)

* **Type**: Microsoft.VisualStudio.MefComponent
* **소스**: 현재 솔루션의 프로젝트
* **프로젝트**: [project]

### <a name="content-type-definition"></a>콘텐츠 형식 정의

현재 언어 LSP 기반 서버 확장을 로드 하는 유일한 방법은 파일 콘텐츠 형식에 따라 됩니다. 즉, 언어 클라이언트 클래스를 정의 하는 경우 (구현 하는 [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017)), 종류를 정의 해야 합니다 열, 확장 스냅인 로드 될 때 파일입니다. 사용자 정의 된 콘텐츠 형식과 일치 하는 파일이 열린 경우 확장은 로드 되지 않습니다.

이 작업은 하나 이상의 ContentTypeDefinition 클래스 정의 통해 수행 됩니다.

```csharp
namespace MockLanguageExtension
{
    public class BarContentDefinition
    {
        [Export]
        [Name("bar")]
        [BaseDefinition(CodeRemoteContentDefinition.CodeRemoteContentTypeName)]
        internal static ContentTypeDefinition BarContentTypeDefinition;


        [Export]
        [FileExtension(".bar")]
        [ContentType("bar")]
        internal static FileExtensionToContentTypeDefinition BarFileExtensionDefinition;
    }
}
```

이전 예에서 콘텐츠 형식 정의 인 파일에 대해 만들어집니다 `.bar` 파일 확장명입니다. 콘텐츠 형식 정의 이름 "표시줄" 제공할지 및 **해야** 에서 파생 [CodeRemoteContentTypeName](/dotnet/api/microsoft.visualstudio.languageserver.client.coderemotecontentdefinition.coderemotecontenttypename?view=visualstudiosdk-2017)합니다.

콘텐츠 형식 정의 추가한 후 언어 클라이언트 클래스에서 클라이언트 언어 확장을 로드 해야 할 때을 정의할 수 있습니다.

```csharp
    [ContentType("bar")]
    [Export(typeof(ILanguageClient))]
    public class BarLanguageClient : ILanguageClient
    {
    }
```

LSP 언어 서버에 대 한 지원 추가 하지 않아도 Visual Studio에서 사용자 고유의 프로젝트 시스템을 구현할 수 있습니다. 고객 언어 서비스 사용을 시작 하려면 Visual Studio에서 단일 파일 또는 폴더를 열 수 있습니다. 사실, 지원 LSP 언어 서버 폴더/파일 열기 시나리오에만 작동 하도록 설계 되었습니다. 사용자 지정 프로젝트 시스템을 구현 하는 경우 일부 기능 (예: 설정) 작동 하지 않습니다.

## <a name="advanced-features"></a>고급 기능

### <a name="settings"></a>설정

사용자 지정 언어 서버 관련 설정을 Visual Studio에서 LSP 지원의 미리 보기 릴리스에 사용할 수 있지만 향상 되 고 아직 진행을 지원 합니다. 설정 언어 서버 지원 하며 일반적으로 언어 서버 데이터를 내보내는 방법을 제어 하는 데 관련이 있습니다. 예를 들어 언어 서버에는 보고 된 오류의 최대 수에 대 한 설정이 있을 수 있습니다. 확장 프로그램 작성자는 기본값을 정의 특정 프로젝트에 대해 사용자가 변경할 수 있습니다.

아래 LSP 언어 서비스 확장 프로그램에 설정에 대 한 지원을 추가 하려면 다음이 단계를 수행 합니다.

1. JSON 파일 (예: "MockLanguageExtensionSettings.json")을 설정 및 기본값을 포함 하는 프로젝트에 추가 합니다. 예:

  ```json
  {
    "foo.maxNumberOfProblems": -1
  }
  ```
2. JSON 파일을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다. 변경 된 **빌드** 동작을 "콘텐츠" 및 "VSIX에 포함 ' 속성을 true로 합니다.

3. JSON 파일에 정의 된 설정에 대 한 접두사 목록을 다시 돌아와 ConfigurationSections 구현 (Visual Studio 코드에서이을 매핑합니다 package.json에 구성 섹션 이름):

  ```csharp
  public IEnumerable<string> ConfigurationSections
  {
      get
      {
          yield return "foo";
      }
  }
  ```
4. .Pkgdef 파일을 프로젝트에 추가 (새 텍스트 파일을 추가 하 고 파일 확장명.pkgdef로 변경). Pkgdef 파일에는이 정보를 포함 되어야 합니다.

  ```xml
    [$RootKey$\OpenFolder\Settings\VSWorkspaceSettings\[settings-name]]
    @="$PackageFolder$\[settings-file-name].json"
  ```

5. .Pkgdef 파일을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다. 변경 된 **빌드** "콘텐츠" 및 "VSIX에 포함" 속성을 true로 동작 합니다.

6. 열립니다는 `source.extension.vsixmanifest` 파일을 자산에 추가 **자산** 탭:

  ![vspackage 자산 편집](media/lsp-add-vspackage-asset.png)

  * **Type**: Microsoft.VisualStudio.VsPackage
  * **소스**: 파일 시스템의 파일
  * **경로**: [pkgdef 파일 경로]

### <a name="user-editing-of-settings-for-a-workspace"></a>사용자 작업 영역에 대 한 설정 편집

1. 사용자는 소유 하 고 서버에 파일을 포함 하는 작업 영역을 엽니다.
2. 사용자는 "VSWorkspaceSettings.json" 라는 ".vs" 폴더의 파일을 추가 합니다.
3. 사용자는 서버에서 제공 하는 설정에 대 한 VSWorkspaceSettings.json 파일에 줄을 추가 합니다. 예:

  ```json
  {
    "foo.maxNumberOfProblems": 10
  }
  ```
### <a name="enabling-diagnostics-tracing"></a>진단 추적 사용
문제를 디버깅할 때 유용할 수 있는 서버와 클라이언트 간의 모든 메시지를 출력 하려면 진단 추적을 설정할 수 있습니다.  진단 추적을 사용 하도록 설정 하려면 다음을 수행 합니다.

1. 열기 또는 만들기 작업 영역 설정 파일 "VSWorkspaceSettings.json" ("사용자의 작업 영역에 대 한 설정을 편집" 참조).
2. 설정 json 파일에 다음 줄을 추가 합니다.

```json
{
    "foo.server.trace": "Off"
}
```

추적의 자세한 정도 대 한 가능한 값을 세 가지가 있습니다.
* "Off": 완전히 종료 추적
* "Messages": 추적 기능을 하지만 유일한 메서드 이름 및 응답 ID를 추적 합니다.
* "Verbose": 추적 기능을 합니다. 전체 rpc 메시지 추적 됩니다.

추적 내용에 대해 설정 되어 있을 때 "%temp%\VisualStudio\LSP" 디렉터리에에서 있는 파일에 기록 됩니다.  로그는 명명 형식에 따라 `[LanguageClientName]-[Datetime Stamp].log`합니다.  현재 추적 폴더 열기 시나리오에만 사용할 수 있습니다.  언어 서버를 활성화 하는 단일 파일을 열면 진단 추적 지원이 필요가 없습니다.

### <a name="custom-messages"></a>사용자 지정 메시지

쉽게 메시지를 전달 하 고 표준 언어 서버 프로토콜의 일부분이 아닌 언어 서버에서 받는 메시지 Api 위치에 있습니다. 사용자 지정 메시지를 처리 하려면 구현 [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017) 언어 클라이언트 클래스에서 인터페이스입니다. [VS StreamJsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/doc/index.md) 라이브러리 언어 클라이언트와 서버 간에 사용자 지정 메시지를 전송 하는 데 사용 됩니다. 다른 Visual Studio 확장명 마찬가지로 LSP 언어 클라이언트 확장 이므로, 결정할 수 있습니다 (즉 LSP에서 지원 되지 않는) 추가 기능을 추가 하려면 (다른 Visual Studio Api를 사용 하 여) Visual Studio를 사용자 지정 메시지를 통해 확장에.

#### <a name="receiving-custom-messages"></a>사용자 지정 메시지 받기

언어 서버에서 사용자 지정 메시지를 받으려면 구현는 [CustomMessageTarget](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.custommessagetarget?view=visualstudiosdk-2017) 속성 [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017) 하 고 사용자 지정 메시지를 처리 하는 방법을 알고 있는 개체를 반환 합니다. . 아래 예제:

```csharp
internal class MockCustomLanguageClient : MockLanguageClient, ILanguageClientCustomMessage
{
    private JsonRpc customMessageRpc;

    public MockCustomLanguageClient() : base()
    {
        CustomMessageTarget = new CustomTarget();
    }

    public object CustomMessageTarget
    {
        get;
        set;
    }

    public class CustomTarget
    {
        public void OnCustomNotification(JToken arg)
        {
            // Provide logic on what happens OnCustomNotification is called from the language server
        }

        public string OnCustomRequest(string test)
        {
            // Provide logic on what happens OnCustomRequest is called from the language server
        }
    }
}
```

#### <a name="sending-custom-messages"></a>사용자 지정 메시지 보내기

언어 서버에 사용자 지정 메시지를 보내도록 구현는 [AttachForCustomMessageAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.attachforcustommessageasync?view=visualstudiosdk-2017) 메서드를 [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017)합니다. 이 메서드는 언어 서버 시작 되 고 준비 메시지를 받을 때 호출 됩니다. A [JsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/src/StreamJsonRpc/JsonRpc.cs) 유지할 사용 하 여 언어 서버에 메시지를 보낼 수 있습니다를 매개 변수로 전달 하 [VS StreamJsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/doc/index.md) Api입니다. 아래 예제:

```csharp
internal class MockCustomLanguageClient : MockLanguageClient, ILanguageClientCustomMessage
{
    private JsonRpc customMessageRpc;

    public MockCustomLanguageClient() : base()
    {
        CustomMessageTarget = new CustomTarget();
    }

    public async Task AttachForCustomMessageAsync(JsonRpc rpc)
    {
        await Task.Yield();

        this.customMessageRpc = rpc;
    }

    public async Task SendServerCustomNotification(object arg)
    {
        await this.customMessageRpc.NotifyWithParameterObjectAsync("OnCustomNotification", arg);
    }

    public async Task<string> SendServerCustomMessage(string test)
    {
        return await this.customMessageRpc.InvokeAsync<string>("OnCustomRequest", test);
    }
}
```

### <a name="middle-layer"></a>중간 계층

때로는 LSP 메시지를 보내고 받는 언어 서버를 확장 개발자는 경우가 있습니다. 예를 들어 확장 개발자는 특정 LSP 메시지를 보낸 메시지 매개 변수를 변경할 수도 LSP 기능 (예: 완료)에 대 한 언어 서버에서 반환 된 결과 수정할 수 있습니다. 필요한 경우 확장 개발자 LSP 메시지를 가로채기 위해 MiddleLayer API를 사용할 수 있습니다.

각 LSP 메시지 인터 셉 션 용 자체 중간 계층 인터페이스를 있습니다. 특정 메시지를 가로채기 위해 해당 메시지에 대 한 중간 계층 인터페이스를 구현 하는 클래스를 만듭니다. 그런 다음 구현는 [ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017) 에서 개체의 인스턴스를 반환 하 고 언어 클라이언트 클래스에서 인터페이스는 [MiddleLayer](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.middlelayer?view=visualstudiosdk-2017) 속성입니다. 아래 예제:

```csharp
public class MockLanguageClient: ILanguageClient, ILanguageClientCustomMessage
{
    public object MiddleLayer => MiddleLayerProvider.Instance;

    private class MiddleLayerProvider : ILanguageClientWorkspaceSymbolProvider
    {
        internal readonly static MiddleLayerProvider Instance = new MiddleLayerProvider();

        private MiddleLayerProvider()
        {
        }

        public async Task<SymbolInformation[]> RequestWorkspaceSymbols(WorkspaceSymbolParams param, Func<WorkspaceSymbolParams, Task<SymbolInformation[]>> sendRequest)
        {
            // Send along the request as given
            SymbolInformation[] symbols = await sendRequest(param);

            // Only return symbols that are "files"
            return symbols.Where(sym => string.Equals(new Uri(sym.Location.Uri).Scheme, "file", StringComparison.OrdinalIgnoreCase)).ToArray();
        }
    }
}
```

중간 계층 기능은 아직 개발 중인 및 하지 아직 포괄적인 있습니다.

## <a name="sample-lsp-language-server-extension"></a>샘플 LSP 언어 서버 확장

Visual Studio에서 LSP 클라이언트 API를 사용 하 여 예제 확장 프로그램의 소스 코드를 보려면 VSSDK 확장성-샘플 [LSP 샘플](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/LanguageServerProtocol)합니다.

## <a name="faq"></a>FAQ

**Visual Studio에서 다양 한 기능 지원을 제공 하기 위해 내 LSP 언어 서버를 보완 하기 위해 사용자 지정 프로젝트 시스템을 구축 하려고 하는 작업에 대 한 할?**

Visual Studio의 언어 LSP 기반 서버에 대 한 지원 의존는 [폴더 열기 기능](https://blogs.msdn.microsoft.com/visualstudio/2016/04/12/open-any-folder-with-visual-studio-15-preview/) 특히 사용자 지정 프로젝트 시스템을 요구 하지 않도록 디자인 되었습니다. 지침에 따라 사용자 고유의 사용자 지정 프로젝트 시스템을 빌드할 수 [여기](https://github.com/Microsoft/VSProjectSystem), 하지만 설정과 같은 일부 기능은 작동 하지 않을 수 있습니다. LSP 언어 서버에 대 한 기본 초기화 논리 언어 서버 수 있도록 초기화 하는 동안 사용자 지정 논리를 제공 하도록 할 수는 사용자 지정 프로젝트 시스템을 사용 하므로 현재 열려 있는 폴더의 루트 폴더 위치에 전달 하는 제대로 시작 합니다.

**디버거 지원을 추가 하려면 어떻게 해야 합니까?**

에 대 한 지원을 제공할 것은 [프로토콜 디버깅 일반적인](https://code.visualstudio.com/docs/extensionAPI/api-debugging) 이후 릴리스에서 합니다.

**이미 있는 경우 VS 지원 되는 언어 서비스 설치 (예를 들어 JavaScript)를 설치할 수 있습니까 여전히 LSP 언어 서버 확장 (예: linting) 추가 기능을 제공 하는?**

예, 하지만 일부 기능이 제대로 작동 합니다. LSP 언어 서버 확장에 대 한 궁극적인 목표 Visual Studio에서 지원 되지 않음 언어 서비스를 사용 하는입니다. LSP 언어 서버를 사용 하 여 추가 지원을 제공 하는 확장을 만들 수 있지만 일부 기능 (IntelliSense) 등에서 원활한 환경이 되지 않습니다. 일반적으로 LSP 언어 서버 확장 기존 세션을 확장 하지 않을 새 언어 경험을 제공 하는 데 사용할 수는 것이 좋습니다.

**완료 된 LSP 언어 서버 VSIX 게시 위치**

마켓플레이스 지침 참조 [여기](walkthrough-publishing-a-visual-studio-extension.md)합니다.
