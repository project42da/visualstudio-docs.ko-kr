---
title: "Csc 작업 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/developer/msbuild/2003#Csc"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Csc 작업[MSBuild]"
  - "MSBuild를 Csc 작업"
ms.assetid: d8c19b36-f5ca-484b-afa6-8ff3b90e103a
caps.latest.revision: 26
caps.handback.revision: 26
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# Csc 작업
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

CSC.exe를 래핑하고 실행 파일 (.exe 파일), 동적 연결 라이브러리 (.dll 파일) 또는 코드 모듈 (.netmodule 파일)을 생성 합니다. CSC.exe에 대 한 자세한 내용은 참조 [C# 컴파일러 옵션](/dotnet/csharp/language-reference/compiler-options/index)합니다.  
  
## <a name="parameters"></a>매개 변수  
 다음 표에서는 `Csc` 작업의 매개 변수에 대해 설명합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`AdditionalLibPaths`|선택적 `String[]` 매개 변수입니다.<br /><br /> 참조를 검색할 추가 디렉터리를 지정합니다. 자세한 내용은 참조 [/lib (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/lib-compiler-option)합니다.|  
|`AddModules`|선택적 `String` 매개 변수입니다.<br /><br /> 이 어셈블리의 일부가 될 모듈을 하나 이상 지정합니다. 자세한 내용은 참조 [/addmodule (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/addmodule-compiler-option)합니다.|  
|`AllowUnsafeBlocks`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 경우 `true`, 를 사용 하는 코드를 컴파일하는 [안전 하지 않은](/dotnet/csharp/language-reference/keywords/unsafe) 키워드입니다. 자세한 내용은 참조 [/unsafe (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/unsafe-compiler-option)합니다.|  
|`ApplicationConfiguration`|선택적 `String` 매개 변수입니다.<br /><br /> 어셈블리 바인딩 설정을 포함 하는 응용 프로그램 구성 파일을 지정 합니다.|  
|`BaseAddress`|선택적 `String` 매개 변수입니다.<br /><br /> DLL을 로드할 기본 설정 기준 주소를 지정합니다. 이 DLL에 대 한 기본 기준 주소를 설정한는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 공용 언어 런타임. 자세한 내용은 참조 [/baseaddress (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/baseaddress-compiler-option)합니다.|  
|`CheckForOverflowUnderflow`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 정수 데이터 형식의 범위를 오버플로 하는 산술 런타임 시 예외가 발생 하는지 여부를 지정 합니다. 자세한 내용은 참조 [/checked (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/checked-compiler-option)합니다.|  
|`CodePage`|선택적 `Int32` 매개 변수입니다.<br /><br /> 컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지를 지정합니다. 자세한 내용은 참조 [/codepage (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/codepage-compiler-option)합니다.|  
|`DebugType`|선택적 `String` 매개 변수입니다.<br /><br /> 디버그 형식을 지정합니다. `DebugType` 수 `full` 또는 `pdbonly`합니다. 기본값은 `full`, 디버거를 실행 중인 프로그램에 연결할 수 있게 해줍니다. 지정 `pdbonly` 프로그램에 디버거를 시작 하지만 어셈블러는 실행 프로그램을 디버거에 연결 된 경우에 표시 하는 경우 코드를 디버깅할 수 있도록 원본입니다.<br /><br /> 이 매개 변수 재정의 `EmitDebugInformation` 매개 변수입니다.<br /><br /> 자세한 내용은 참조 [/debug (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/debug-compiler-option)합니다.|  
|`DefineConstants`|선택적 `String` 매개 변수입니다.<br /><br /> 전처리기 기호를 정의합니다. 자세한 내용은 참조 [(C# 컴파일러 옵션)을 정의 /](/dotnet/csharp/language-reference/compiler-options/define-compiler-option)합니다.|  
|`DelaySign`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 경우 `true`, 어셈블리에 완전히 서명된 되도록 지정 합니다. 경우 `false`, 만 어셈블리의 공개 키를 저장 하려면를 지정 합니다.<br /><br /> 이 매개 변수에 영향이 없으면 함께 사용 해야는 `KeyFile` 또는 `KeyContainer` 매개 변수입니다.<br /><br /> 자세한 내용은 참조 [/delaysign (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/delaysign-compiler-option)합니다.|  
|`DisabledWarnings`|선택적 `String` 매개 변수입니다.<br /><br /> 사용 하지 않을 경고 목록을 지정 합니다. 자세한 내용은 참조 [/nowarn (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/nowarn-compiler-option)합니다.|  
|`DocumentationFile`|선택적 `String` 매개 변수입니다.<br /><br /> XML 파일에 대해 문서 주석을 처리합니다. 자세한 내용은 참조 [/doc (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/doc-compiler-option)합니다.|  
|`EmitDebugInformation`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 경우 `true`, 작업 디버깅 정보를 생성 하는 프로그램 데이터베이스 (.pdb) 파일에 배치 합니다. 경우 `false`, 이 작업에 디버깅 정보가 내보냅니다. 기본값은 `false`입니다. 자세한 내용은 참조 [/debug (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/debug-compiler-option)합니다.|  
|`ErrorReport`|선택적 `String` 매개 변수입니다.<br /><br /> Microsoft에는 C#의 내부 오류를 보고 하는 편리한 방법을 제공 합니다. 이 매개 변수 값을 가질 수 `prompt`, `send`, 또는 `none`합니다. 매개 변수 설정 된 경우 `prompt`, 내부 컴파일러 오류가 발생 하는 경우에 메시지가 표시 됩니다. 프롬프트를 사용 하면 Microsoft에 버그 보고서를 전자적으로 보낼 수 있습니다. 매개 변수 설정 된 경우 `send`, 버그 보고서를 자동으로 전송 됩니다. 매개 변수 설정 된 경우 `none`, 오류는 컴파일러의 텍스트 출력에만 보고 합니다. 기본값은 `none`입니다. 자세한 내용은 참조 [/errorreport (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/errorreport-compiler-option)합니다.|  
|`FileAlignment`|선택적 `Int32` 매개 변수입니다.<br /><br /> 출력 파일에 있는 섹션의 크기를 지정합니다. 자세한 내용은 참조 [/filealign (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/filealign-compiler-option)합니다.|  
|`GenerateFullPaths`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 경우 `true`, 컴파일러 출력에 파일에 절대 경로 지정 합니다. 경우 `false`, 파일의 이름을 지정 합니다. 기본값은 `false`입니다. 자세한 내용은 참조 [/fullpaths (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/fullpaths-compiler-option)합니다.|  
|`KeyContainer`|선택적 `String` 매개 변수입니다.<br /><br /> 암호화 키 컨테이너의 이름을 지정합니다. 자세한 내용은 참조 [/keycontainer (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/keycontainer-compiler-option)합니다.|  
|`KeyFile`|선택적 `String` 매개 변수입니다.<br /><br /> 암호화 키를 포함하는 파일 이름을 지정합니다. 자세한 내용은 참조 [/keyfile (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/keyfile-compiler-option)합니다.|  
|`LangVersion`|선택적 `String` 매개 변수입니다.<br /><br /> 사용할 언어의 버전을 지정합니다. 자세한 내용은 참조 [/langversion (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/langversion-compiler-option)합니다.|  
|`LinkResources`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 에 대 한 링크를 만듭니다는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 출력 파일에는 리소스는 리소스 파일 출력 파일에 배치 되지 않습니다.<br /><br /> 이 매개 변수로 전달 된 항목 라는 선택적 메타 데이터 항목을 가질 수 있습니다 `LogicalName` 및 `Access`합니다. `LogicalName` 에 해당 하는 `identifier` 의 매개 변수는 `/linkresource` 스위치 및 `Access` 에 해당 `accessibility-modifier` 매개 변수입니다. 자세한 내용은 참조 [/linkresource (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/linkresource-compiler-option)합니다.|  
|`MainEntryPoint`|선택적 `String` 매개 변수입니다.<br /><br /> 위치를 지정 된 `Main` 메서드. 자세한 내용은 참조 [/main (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/main-compiler-option)합니다.|  
|`ModuleAssemblyName`|선택적 `String` 매개 변수입니다.<br /><br /> 이 모듈의 일부가 될 어셈블리의 이름을 지정 합니다.|  
|`NoConfig`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 경우 `true`, csc.rsp 파일을 사용 하 여 컴파일하면 하지 않도록 컴파일러에 지시 합니다. 자세한 내용은 참조 [/noconfig (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/noconfig-compiler-option)합니다.|  
|`NoLogo`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 경우 `true`, 컴파일러 배너 정보를 표시 하지 않습니다. 자세한 내용은 참조 [/nologo (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/nologo-compiler-option)합니다.|  
|`NoStandardLib`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 경우 `true`, 전체 시스템 네임 스페이스를 정의 하는 mscorlib.dll의 가져오기를 방지 합니다. 정의 하거나 사용자 고유의 System 네임 스페이스 및 개체를 생성 하려는 경우이 매개 변수를 사용 합니다. 자세한 내용은 참조 [/nostdlib (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/nostdlib-compiler-option)합니다.|  
|`NoWin32Manifest`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 경우 `true`, 기본 Win32 매니페스트를 포함 하지 않습니다.|  
|`Optimize`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 경우 `true`, 를 최적화할 수 있습니다. 경우 `false`, 최적화를 비활성화 합니다. 자세한 내용은 참조 [/optimize (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/optimize-compiler-option)합니다.|  
|`OutputAssembly`|선택적 `String` 출력 매개 변수입니다.<br /><br /> 출력 파일의 이름을 지정합니다. 자세한 내용은 참조 [/out (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/out-compiler-option)합니다.|  
|`PdbFile`|선택적 `String` 매개 변수입니다.<br /><br /> 디버그 정보 파일 이름을 지정합니다. 기본 이름은.pdb 확장명이 있는 출력 파일 이름입니다.|  
|`Platform`|선택적 `String` 매개 변수입니다.<br /><br /> 출력 파일의 대상으로 프로세서 플랫폼을 지정합니다. 이 매개 변수 값을 가질 수 `x86`, `x64`, 또는 `anycpu`합니다. 기본값은 `anycpu`입니다. 자세한 내용은 참조 [/platform (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option)합니다.|  
|`References`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 현재 프로젝트에 지정된 된 항목에서 공용 형식 정보를 가져오려는 작업을 시킵니다. 자세한 내용은 참조 [/reference (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/reference-compiler-option)합니다.<br /><br /> 지정할 수는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 참조 별칭는 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 파일 메타 데이터를 추가 하 여 `Aliases` 원래 "참조" 항목에 있습니다. 예를 들어, 다음 CSC 명령줄에서 "LS1" 별칭을 설정 하려면:<br /><br /> `csc /r:LS1=MyCodeLibrary.dll /r:LS2=MyCodeLibrary2.dll *.cs`<br /><br /> 사용 합니다.<br /><br /> `<Reference Include="MyCodeLibrary"> <Aliases>LS1</Aliases> </Reference>`|  
|`Resources`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 포함 된 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 출력 파일에는 리소스입니다.<br /><br /> 이 매개 변수로 전달 된 항목 라는 선택적 메타 데이터 항목을 가질 수 있습니다 `LogicalName` 및 `Access`합니다. `LogicalName` 에 해당 하는 `identifier` 의 매개 변수는 `/resource` 스위치 및 `Access` 에 해당 `accessibility-modifier` 매개 변수입니다. 자세한 내용은 참조 [/resource (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/resource-compiler-option)합니다.|  
|`ResponseFiles`|선택적 `String` 매개 변수입니다.<br /><br /> 이 작업에 대 한 명령을 포함 하는 응답 파일을 지정 합니다. 자세한 내용은 참조 [@ (지시 파일 지정)](/dotnet/csharp/language-reference/compiler-options/response-file-compiler-option)합니다.|  
|`Sources`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 하나 이상 지정 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 소스 파일입니다.|  
|`TargetType`|선택적 `String` 매개 변수입니다.<br /><br /> 출력 파일의 파일 형식을 지정합니다. 이 매개 변수 값을 가질 수 있습니다 `library`, 코드 라이브러리를 만드는 `exe`, 콘솔 응용 프로그램을 만드는 `module`, 모듈을 만드는 또는 `winexe`, 는 Windows 프로그램을 만듭니다. 기본값은 `library`입니다. 자세한 내용은 참조 [/target (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/target-compiler-option)합니다.|  
|`TreatWarningsAsErrors`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 경우 `true`, 모든 경고를 오류로 처리 합니다. 자세한 내용은 참조 [/warnaserror (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/warnaserror-compiler-option)합니다.|  
|`UseHostCompilerIfAvailable`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 사용 가능한 경우 in-process 컴파일러 개체를 사용 하 여 작업을 지시 합니다. 에서만 사용 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.|  
|`Utf8Output`|선택적 `Boolean` 매개 변수입니다.<br /><br /> 컴파일러 utf-8 인코딩을 사용 하 여 출력을 기록 합니다. 자세한 내용은 참조 [/utf8output (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/utf8output-compiler-option)합니다.|  
|`WarningLevel`|선택적 `Int32` 매개 변수입니다.<br /><br /> 표시할 컴파일러에 대 한 경고 수준을 지정 합니다. 자세한 내용은 참조 [/warn (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/warn-compiler-option)합니다.|  
|`WarningsAsErrors`|선택적 `String` 매개 변수입니다.<br /><br /> 오류로 처리할 경고 목록을 지정합니다. 자세한 내용은 참조 [/warnaserror (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/warnaserror-compiler-option)합니다.<br /><br /> 이 매개 변수 재정의 `TreatWarningsAsErrors` 매개 변수입니다.|  
|`WarningsNotAsErrors`|선택적 `String` 매개 변수입니다.<br /><br /> 오류로 처리하지 않을 경고 목록을 지정합니다. 자세한 내용은 참조 [/warnaserror (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/warnaserror-compiler-option)합니다.<br /><br /> 이 매개 변수는 유용한 경우는 `TreatWarningsAsErrors` 매개 변수는 설정 `true`합니다.|  
|`Win32Icon`|선택적 `String` 매개 변수입니다.<br /><br /> 출력 파일을 원하는 모양 파일 탐색기에서 제공 하는 어셈블리에.ico 파일을 삽입 합니다. 자세한 내용은 참조 [/win32icon (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/win32icon-compiler-option)합니다.|  
|`Win32Manifest`|선택적 `String` 매개 변수입니다.<br /><br /> 포함 될 Win32 매니페스트를 지정 합니다.|  
|`Win32Resource`|선택적 `String` 매개 변수입니다.<br /><br /> 출력 파일에 Win32 리소스 (.res) 파일을 삽입합니다. 자세한 내용은 참조 [/win32res (C# 컴파일러 옵션)](/dotnet/csharp/language-reference/compiler-options/win32res-compiler-option)합니다.|  
  
## <a name="remarks"></a>설명  
 위에 나열 된 매개 변수 외에도이 작업에서 매개 변수를 상속는 `Microsoft.Build.Tasks.ManagedCompiler` 클래스에서 상속 되는 <xref:Microsoft.Build.Tasks.ToolTaskExtension> 에서 상속 된 클래스에서 자체는 <xref:Microsoft.Build.Utilities.ToolTask> 클래스. 이러한 추가 매개 변수 및 해당 설명 목록을 참조 하십시오. [ToolTaskExtension 기본 클래스](../msbuild/tooltaskextension-base-class.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Csc` 작업의 소스 파일에서 실행 파일을 컴파일할 수는 `Compile` 항목 컬렉션입니다.  
  
```  
<CSC  
    Sources="@(Compile)"  
    OutputAssembly="$(AppName).exe"  
    EmitDebugInformation="true" />  
```  
  
## <a name="see-also"></a>참고 항목  
 [작업 참조](../msbuild/msbuild-task-reference.md)   
 [작업](../msbuild/msbuild-tasks.md)