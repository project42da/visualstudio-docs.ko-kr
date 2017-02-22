---
title: "Vbc Task | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#Vbc"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Vbc task [MSBuild]"
  - "MSBuild, Vbc task"
ms.assetid: 595278b1-2782-4577-b1ba-b4b5ab5625a3
caps.latest.revision: 19
caps.handback.revision: 19
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Vbc Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

실행 파일\(.exe\), 동적 연결 라이브러리\(.dll\) 또는 코드 모듈을 생성하는 vbc.exe를 래핑합니다.  netmodule\)을 생성합니다.  vbc.exe에 대한 자세한 내용은 [Visual Basic Command\-Line Compiler](/dotnet/visual-basic/reference/command-line-compiler/index)를 참조하십시오.  
  
## 매개 변수  
 다음 표에서는 `Vbc` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`AdditionalLibPaths`|선택적 `String[]` 매개 변수입니다.<br /><br /> References 특성에서 지정한 어셈블리를 조회할 추가 폴더를 지정합니다.|  
|`AddModules`|선택적 `String[]` 매개 변수입니다.<br /><br /> 컴파일러가 지정된 파일의 모든 형식 정보를 현재 컴파일 중인 프로젝트에서 사용할 수 있도록 만듭니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/addmodule](/dotnet/visual-basic/reference/command-line-compiler/addmodule) 스위치에 해당합니다.|  
|`BaseAddress`|선택적 `String` 매개 변수입니다.<br /><br /> DLL의 기준 주소를 지정합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/baseaddress](/dotnet/visual-basic/reference/command-line-compiler/baseaddress) 스위치에 해당합니다.|  
|`CodePage`|선택적 `Int32` 매개 변수입니다.<br /><br /> 컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지를 지정합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/codepage](/dotnet/visual-basic/reference/command-line-compiler/codepage) 스위치에 해당합니다.|  
|`DebugType`|선택적 `String[]` 매개 변수입니다.<br /><br /> 컴파일러에서 디버깅 정보를 생성하도록 합니다.  이 매개 변수는 다음 값을 가질 수 있습니다.<br /><br /> -   `full`<br />-   `pdbonly`<br /><br /> 기본값은 실행 프로그램에 디버거를 연결할 수 있는 `full`입니다.  `pdbonly`를 값으로 지정하면 디버거에서 프로그램을 시작할 때 소스 코드를 디버깅할 수 있지만 어셈블리 언어 코드는 실행 프로그램을 디버거에 연결할 때만 표시됩니다.  자세한 내용은 [\/debug](/dotnet/visual-basic/reference/command-line-compiler/debug)를 참조하십시오.|  
|`DefineConstants`|선택적 `String[]` 매개 변수입니다.<br /><br /> 조건부 컴파일러 상수를 정의합니다.  기호\/값 쌍은 세미콜론으로 구분되고 다음 구문을 사용하여 지정됩니다.<br /><br /> *symbol1* `=` *value1* `;` *symbol2* `=` *value2*<br /><br /> 이 매개 변수는 vbc.exe 컴파일러의 [\/define](/dotnet/visual-basic/reference/command-line-compiler/define) 스위치에 해당합니다.|  
|`DelaySign`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 작업에서 어셈블리에 공개 키를 배치합니다.  `false`이면 작업에서 어셈블리에 완전히 서명합니다.  기본값은 `false`입니다. 이 매개 변수를 적용하려면 `KeyFile` 매개 변수나 `KeyContainer` 매개 변수를 함께 사용해야 합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/delaysign](/dotnet/visual-basic/reference/command-line-compiler/delaysign) 스위치에 해당합니다.|  
|`DisabledWarnings`|선택적 `String` 매개 변수입니다.<br /><br /> 지정한 경고를 표시하지 않습니다.  경고 식별자의 숫자 부분만 지정해야 합니다.  경고가 여러 개인 경우 세미콜론으로 구분할 수 있습니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn) 스위치에 해당합니다.|  
|`DocumentationFile`|선택적 `String` 매개 변수입니다.<br /><br /> 문서 주석을 지정한 XML 파일로 처리합니다.  이 매개 변수는 `GenerateDocumentation` 특성을 재정의합니다.  자세한 내용은 [\/doc](/dotnet/visual-basic/reference/command-line-compiler/doc)를 참조하십시오.|  
|`EmitDebugInformation`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 작업에서 디버깅 정보를 생성하여 .pdb 파일에 배치합니다.  자세한 내용은 [\/debug](/dotnet/visual-basic/reference/command-line-compiler/debug)를 참조하십시오.|  
|`ErrorReport`|선택적 `String` 매개 변수입니다.<br /><br /> 작업에서 내부 컴파일러 오류를 보고하는 방식을 지정합니다.  이 매개 변수는 다음 값을 가질 수 있습니다.<br /><br /> -   `prompt`<br />-   `send`<br />-   `none`<br /><br /> `prompt`를 지정한 경우 내부 컴파일러 오류가 발생하면 오류 데이터를 Microsoft에 보낼지 선택할 수 있는 옵션이 사용자에게 표시됩니다.<br /><br /> `send`를 지정한 경우 내부 컴파일러 오류가 발생하면 오류 데이터가 Microsoft에 자동으로 전달됩니다.<br /><br /> 기본값은 오류를 텍스트 출력으로만 보고하는 `none`입니다.<br /><br /> 이 매개 변수는 vbc.exe 컴파일러의 [\/errorreport](/dotnet/visual-basic/reference/command-line-compiler/errorreport) 스위치에 해당합니다.|  
|`FileAlignment`|선택적 `Int32` 매개 변수입니다.<br /><br /> 출력 파일에서 섹션을 배치할 위치를 바이트로 지정합니다.  이 매개 변수는 다음 값을 가질 수 있습니다.<br /><br /> -   `512`<br />-   `1024`<br />-   `2048`<br />-   `4096`<br />-   `8192`<br /><br /> 이 매개 변수는 vbc.exe 컴파일러의 [\/filealign](/dotnet/visual-basic/reference/command-line-compiler/filealign) 스위치에 해당합니다.|  
|`GenerateDocumentation`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 문서 정보를 생성하여 이 정보를 작업에서 작성하고 있는 실행 파일이나 라이브러리의 이름과 함께 XML 파일에 배치합니다.  자세한 내용은 [\/doc](/dotnet/visual-basic/reference/command-line-compiler/doc)를 참조하십시오.|  
|`Imports`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 지정한 항목 컬렉션에서 네임스페이스를 가져옵니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/imports](/dotnet/visual-basic/reference/command-line-compiler/imports) 스위치에 해당합니다.|  
|`KeyContainer`|선택적 `String` 매개 변수입니다.<br /><br /> 암호화 키 컨테이너의 이름을 지정합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/keycontainer](/dotnet/visual-basic/reference/command-line-compiler/keycontainer) 스위치에 해당합니다.|  
|`KeyFile`|선택적 `String` 매개 변수입니다.<br /><br /> 암호화 키를 포함하는 파일 이름을 지정합니다.  자세한 내용은 [\/keyfile](/dotnet/visual-basic/reference/command-line-compiler/keyfile)을 참조하십시오.|  
|`LangVersion`|선택적 [String](assetId:///String?qualifyHint=False&autoUpgrade=True) 매개 변수입니다.<br /><br /> "9"와 "10" 중에서 언어의 버전을 지정합니다.|  
|`LinkResources`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 출력 파일에 .NET Framework 리소스에 대한 링크를 만듭니다. 이 리소스 파일은 출력 파일에 저장되지 않습니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/linkresource](/dotnet/visual-basic/reference/command-line-compiler/linkresource) 스위치에 해당합니다.|  
|`MainEntryPoint`|선택적 `String` 매개 변수입니다.<br /><br /> `Sub Main` 프로시저를 포함하는 클래스나 모듈을 지정합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/main](/dotnet/visual-basic/reference/command-line-compiler/main) 스위치에 해당합니다.|  
|`ModuleAssemblyName`|선택적 `String` 매개 변수입니다.<br /><br /> 이 모듈이 속해 있는 어셈블리를 지정합니다.|  
|`NoConfig`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 컴파일러에서 vbc.rsp 파일을 사용하지 않도록 지정합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/noconfig](/dotnet/visual-basic/reference/command-line-compiler/noconfig) 매개 변수에 해당합니다.|  
|`NoLogo`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 컴파일러 배너 정보를 표시하지 않습니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/nologo](/dotnet/visual-basic/reference/command-line-compiler/nologo) 스위치에 해당합니다.|  
|`NoStandardLib`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 컴파일러에서 표준 라이브러리를 참조하지 않도록 합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/nostdlib](/dotnet/visual-basic/reference/command-line-compiler/nostdlib) 스위치에 해당합니다.|  
|`NoVBRuntimeReference`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 내부 전용입니다.  True인 경우 Microsoft.VisualBasic.dll에 대한 자동 참조가 방지됩니다.|  
|`NoWarnings`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 작업에서 모든 경고를 표시하지 않습니다.  자세한 내용은 [\/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn)을 참조하십시오.|  
|`Optimize`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 컴파일러에서 최적화를 사용합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/optimize](/dotnet/visual-basic/reference/command-line-compiler/optimize) 스위치에 해당합니다.|  
|`OptionCompare`|선택적 `String` 매개 변수입니다.<br /><br /> 문자열 비교 방법을 지정합니다.  이 매개 변수는 다음 값을 가질 수 있습니다.<br /><br /> -   `binary`<br />-   `text`<br /><br /> `binary` 값은 작업에서 이진 문자열 비교를 사용하도록 지정합니다.  `text` 값은 작업에서 텍스트 문자열 비교를 사용하도록 지정합니다.  이 매개 변수의 기본값은 `binary`입니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/optioncompare](/dotnet/visual-basic/reference/command-line-compiler/optioncompare) 스위치에 해당합니다.|  
|`OptionExplicit`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 변수를 명시적으로 선언해야 합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/optionexplicit](/dotnet/visual-basic/reference/command-line-compiler/optionexplicit) 스위치에 해당합니다.|  
|`OptionInfer`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 변수의 형식 유추가 허용됩니다.|  
|`OptionStrict`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 작업에서 엄격한 형식 의미를 적용하여 암시적 형식 변환을 제한합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/optionstrict](/dotnet/visual-basic/reference/command-line-compiler/optionstrict) 스위치에 해당합니다.|  
|`OptionStrictType`|선택적 `String` 매개 변수입니다.<br /><br /> 경고를 생성할 엄격한 형식 의미 체계를 지정합니다.  현재는 "custom"만 지원됩니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/optionstrict](/dotnet/visual-basic/reference/command-line-compiler/optionstrict) 스위치에 해당합니다.|  
|`OutputAssembly`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 출력 파일의 이름을 지정합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/out](/dotnet/visual-basic/reference/command-line-compiler/out) 스위치에 해당합니다.|  
|`Platform`|선택적 `String` 매개 변수입니다.<br /><br /> 출력 파일에서 대상으로 삼을 프로세서 플랫폼을 지정합니다.  이 매개 변수의 값으로는 `x86`, `x64`, `Itanium` 또는 `anycpu`를 사용할 수 있습니다.  기본값은 `anycpu`입니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/platform](/dotnet/visual-basic/reference/command-line-compiler/platform) 스위치에 해당합니다.|  
|`References`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 작업에서 지정된 항목의 공개 형식 정보를 현재 프로젝트에 가져올 수 있도록 합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/reference](/dotnet/visual-basic/reference/command-line-compiler/reference) 스위치에 해당합니다.|  
|`RemoveIntegerChecks`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 정수 오버플로 오류 검사를 비활성화합니다.  기본값은 `false`입니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/removeintchecks](/dotnet/visual-basic/reference/command-line-compiler/removeintchecks) 스위치에 해당합니다.|  
|`Resources`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> .NET Framework 리소스를 출력 파일에 포함합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/resource](/dotnet/visual-basic/reference/command-line-compiler/resource) 스위치에 해당합니다.|  
|`ResponseFiles`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 이 작업에 대한 명령이 들어 있는 지시 파일을 지정합니다.  이 매개 변수는 vbc.exe 컴파일러의 [@\(지시 파일 지정\)](/dotnet/visual-basic/reference/command-line-compiler/specify-response-file) 옵션에 해당합니다.|  
|`RootNamespace`|선택적 `String` 매개 변수입니다.<br /><br /> 모든 형식 선언을 위한 루트 네임스페이스를 지정합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/rootnamespace](/dotnet/visual-basic/reference/command-line-compiler/rootnamespace) 스위치에 해당합니다.|  
|`SdkPath`|선택적 `String` 매개 변수입니다.<br /><br /> mscorlib.dll 및 microsoft.visualbasic.dll의 위치를 지정합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/sdkpath](/dotnet/visual-basic/reference/command-line-compiler/sdkpath) 스위치에 해당합니다.|  
|`Sources`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 하나 이상의 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 소스 파일을 지정합니다.|  
|`TargetCompactFramework`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 작업에서 [!INCLUDE[Compact](../extensibility/includes/compact_md.md)]를 대상으로 삼습니다.  이 스위치는 vbc.exe 컴파일러의 [\/netcf](/dotnet/visual-basic/reference/command-line-compiler/netcf) 스위치에 해당합니다.|  
|`TargetType`|선택적 `String` 매개 변수입니다.<br /><br /> 출력 파일의 파일 형식을 지정합니다.  이 매개 변수의 값으로는 코드 라이브러리를 만드는 `library`, 콘솔 응용 프로그램을 만드는 `exe`, 모듈을 만드는 `module` 또는 Windows 프로그램을 만드는 `winexe`를 사용할 수 있습니다.  기본값은 `library`입니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/target](/dotnet/visual-basic/reference/command-line-compiler/target) 스위치에 해당합니다.|  
|`Timeout`|선택적 `Int32` 매개 변수입니다.<br /><br /> 작업 실행 파일이 얼마 후에 종료될 지를 밀리초 단위로 지정합니다.  기본값은 제한 시간이 없음을 나타내는 `Int.MaxValue`입니다.|  
|`ToolPath`|선택적 `String` 매개 변수입니다.<br /><br /> 작업에서 내부 실행 파일\(vbc.exe\)을 로드할 위치를 지정합니다.  이 매개 변수를 지정하지 않으면 작업에서는 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]를 실행하고 있는 버전의 Framework에 해당하는 SDK 설치 경로가 사용됩니다.|  
|`TreatWarningsAsErrors`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 모든 경고가 오류로 취급됩니다.  자세한 내용은 [\/warnaserror](/dotnet/visual-basic/reference/command-line-compiler/warnaserror)를 참조하십시오.|  
|`UseHostCompilerIfAvailable`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 작업에서 가능한 경우 in\-process 컴파일러 개체를 사용하도록 지시합니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에만 사용됩니다.|  
|`Utf8Output`|선택적 `Boolean` 매개 변수입니다.<br /><br /> UTF\-8 인코딩을 사용하여 컴파일러 출력을 기록합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/utf8output](/dotnet/visual-basic/reference/command-line-compiler/utf8output) 스위치에 해당합니다.|  
|`Verbosity`|선택적 `String` 매개 변수입니다.<br /><br /> 컴파일러의 출력을 어느 정도로 자세하게 설정할지 지정합니다.  자세한 정도는 `Quiet`, `Normal`\(기본값\) 또는 `Verbose`가 될 수 있습니다.|  
|`WarningsAsErrors`|선택적 `String` 매개 변수입니다.<br /><br /> 오류로 취급할 경고 목록을 지정합니다.  자세한 내용은 [\/warnaserror](/dotnet/visual-basic/reference/command-line-compiler/warnaserror)를 참조하십시오.<br /><br /> 이 매개 변수는 `TreatWarningsAsErrors` 매개 변수를 재정의합니다.|  
|`WarningsNotAsErrors`|선택적 `String` 매개 변수입니다.<br /><br /> 오류로 취급하지 않을 경고 목록을 지정합니다.  자세한 내용은 [\/warnaserror](/dotnet/visual-basic/reference/command-line-compiler/warnaserror)를 참조하십시오.<br /><br /> 이 매개 변수는 `TreatWarningsAsErrors` 매개 변수를 `true`로 설정한 경우에만 사용됩니다.|  
|`Win32Icon`|선택적 `String` 매개 변수입니다.<br /><br /> 출력 파일의 파일 탐색기에서 원하는 모양을 제공 하는 어셈블리에.ico 파일을 삽입 합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/win32icon](/dotnet/visual-basic/reference/command-line-compiler/win32icon) 스위치에 해당합니다.|  
|`Win32Resources`|선택적 `String` 매개 변수입니다.<br /><br /> Win32 리소스 파일\(.res\)을 출력 파일에 삽입합니다.  이 매개 변수는 vbc.exe 컴파일러의 [\/win32resource](/dotnet/visual-basic/reference/command-line-compiler/win32resource) 스위치에 해당합니다.|  
  
## 설명  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.ToolTask> 클래스에서 상속하는 <xref:Microsoft.Build.Tasks.ToolTaskExtension> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [ToolTaskExtension Base Class](../msbuild/tooltaskextension-base-class.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 프로젝트를 컴파일합니다.  
  
```  
<VBC  
   Sources="@(sources)"  
   Resources="strings.resources"  
   Optimize="true"  
   OutputAssembly="out.exe"/>  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](/dotnet/visual-basic/reference/command-line-compiler/index)   
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)