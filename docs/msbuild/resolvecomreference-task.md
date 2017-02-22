---
title: "ResolveComReference Task | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/msbuild/2003#ResolveComReference"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MSBuild, ResolveCOMReference task"
  - "ResolveCOMReference task [MSBuild]"
ms.assetid: c9bf5fcf-6453-40ea-b50f-a212adc3e9b5
caps.latest.revision: 26
caps.handback.revision: 26
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# ResolveComReference Task
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

하나 이상의 형식 라이브러리 이름이나 .tlb 파일의 목록을 가져오고 이러한 형식 라이브러리를 디스크상의 위치로 확인합니다.  
  
## 매개 변수  
 다음 표에서는 `ResolveCOMReference` 작업의 매개 변수에 대해 설명합니다.  
  
|Parameter|설명|  
|---------------|--------|  
|`DelaySign`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 어셈블리에 공개 키를 두고,  `false`이면 어셈블리에 완전히 서명합니다.|  
|`EnvironmentVariables`|선택적 `String[]` 매개 변수입니다.<br /><br /> 등호로 구분된 환경 변수 쌍의 배열입니다.  이 변수는 생성된 tlbimp.exe 및 aximp.exe에 전달되면서 일반 환경 블록에 추가되거나 일부 일반 환경 블록을 재정의합니다.|  
|`ExecuteAsTool`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`이면 적절한 대상 프레임워크의 tlbimp.exe 및 aximp.exe가 out\-of\-proc로 실행되어 필요한 래퍼 어셈블리를 생성합니다.  이 기능을 멀티 타기팅이라고 합니다.|  
|`IncludeVersionInInteropName`|선택적 `Boolean` 매개 변수입니다.<br /><br /> `true`인 경우 typelib 버전이 래퍼 이름에 포함됩니다.  기본값은 `false`입니다.|  
|`KeyContainer`|선택적 `String` 매개 변수입니다.<br /><br /> 공개\/개인을 보관하는 컨테이너를 지정합니다.<br /><br /> 키 쌍.|  
|`KeyFile`|선택적 `String` 매개 변수입니다.<br /><br /> 공개\/개인을 포함하는 항목을 지정합니다.<br /><br /> 키 쌍.|  
|`NoClassMembers`|선택적 `Boolean` 매개 변수입니다.|  
|`ResolvedAssemblyReferences`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 확인된 어셈블리 참조를 지정합니다.|  
|`ResolvedFiles`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 출력 매개 변수입니다.<br /><br /> 이 작업에 대한 입력으로 제공된 형식 라이브러리의 실제 위치에 해당하는 디스크 상의 정규화된 파일을 지정합니다.|  
|`ResolvedModules`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.|  
|`SdkToolsPath`|선택적 [String](assetId:///String?qualifyHint=False&autoUpgrade=True) 매개 변수입니다.<br /><br /> `ExecuteAsTool`이 `true`이면 이 매개 변수는 대상으로 지정되는 프레임워크 버전의 SDK 도구 경로로 설정해야 합니다.|  
|`StateFile`|선택적 assetId:///String?qualifyHint=False&autoUpgrade=True 매개 변수입니다.<br /><br /> COM 구성요소 타임스탬프의 캐시 파일을 지정합니다.  래퍼가 없는 경우 모든 실행으로 모든 래퍼가 재생성됩니다.|  
|`TargetFrameworkVersion`|선택적 assetId:///String?qualifyHint=False&autoUpgrade=True 매개 변수입니다.<br /><br /> 프로젝트의 대상 프레임워크 버전을 지정합니다.<br /><br /> 기본값은 `String.Empty`입니다.  대상 프레임워크를 기준으로 참조에 대한 필터링이 없다는 의미입니다.|  
|`TargetProcessorArchitecture`|선택적 assetId:///String?qualifyHint=False&autoUpgrade=True 매개 변수입니다.<br /><br /> 기본 대상 프로세서 아키텍처를 지정합니다.  전환 후 tlbimp.exe\/컴퓨터 플래그로 전달됩니다.<br /><br /> 매개 변수 값은 <xref:Microsoft.Build.Utilities.ProcessorArchitecture>의 멤버이어야 합니다.|  
|`TypeLibFiles`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> COM 참조에 대한 형식 라이브러리 파일 경로를 지정합니다.  이 매개 변수에 포함된 항목에는 항목 메타데이터가 있을 수 있습니다.  자세한 내용은 아래의 "TypeLibFiles 항목 메타데이터" 단원을 참조하십시오.|  
|`TypeLibNames`|선택적 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 매개 변수입니다.<br /><br /> 확인할 형식 라이브러리 이름을 지정합니다.  이 매개 변수에 포함된 항목에는 항목 메타데이터가 있어야 합니다.  자세한 내용은 아래의 "TypeLibNames 항목 메타데이터" 단원을 참조하십시오.|  
|`WrapperOutputDirectory`|선택적 `String` 매개 변수입니다.<br /><br /> 생성된 interop 어셈블리가 배치되는 디스크 상의 위치입니다.  이 항목 메타데이터를 지정하지 않으면 작업에서 프로젝트 파일이 있는 디렉터리의 절대 경로를 사용합니다.|  
  
## 설명  
  
## TypeLibNames 항목 메타데이터  
 다음 표에서는 `TypeLibNames` 매개 변수에 전달된 항목에 대해 사용할 수 있는 항목 메타데이터를 설명합니다.  
  
|Metadata|설명|  
|--------------|--------|  
|`GUID`|필수적 항목 메타데이터입니다.<br /><br /> 형식 라이브러리에 대한 GUID입니다.  이 항목 메타데이터를 지정하지 않으면 작업이 실패합니다.|  
|`VersionMajor`|필수적 항목 메타데이터입니다.<br /><br /> 형식 라이브러리의 주 버전입니다.  이 항목 메타데이터를 지정하지 않으면 작업이 실패합니다.|  
|`VersionMinor`|필수적 항목 메타데이터입니다.<br /><br /> 형식 라이브러리의 부 버전입니다.  이 항목 메타데이터를 지정하지 않으면 작업이 실패합니다.|  
|`LocaleIdentifier`|선택적 항목 메타데이터입니다.<br /><br /> 형식 라이브러리의 LCID\(로캘 식별자\)입니다.  사용자, 영역 또는 응용 프로그램에 의해 기본 설정된 언어를 식별하는 값을 32비트로 지정합니다.  이 항목 메타데이터를 지정하지 않으면 작업에서 기본 로캘 식별자인 "0"을 사용합니다.|  
|`WrapperTool`|선택적 항목 메타데이터입니다.<br /><br /> 이 형식 라이브러리에 대한 어셈블리 래퍼를 생성하는 데 사용되는 래퍼 도구를 지정합니다.  이 항목 메타데이터를 지정하지 않으면 작업에서 기본 래퍼 도구인 "tlbimp"를 사용합니다.  typelibs의 선택 가능한 항목은 다음과 같으며 대\/소문자를 구분하지 않습니다.<br /><br /> -   `Primary`: COM 구성 요소에 대해 이미 생성된 주 interop 어셈블리를 사용하려는 경우 이 래퍼 도구를 사용합니다.  이 래퍼 도구를 사용할 경우 래퍼 출력 디렉터리를 지정하지 마십시오. 이를 지정하면 작업이 실패합니다.<br />-   `TLBImp`: COM 구성 요소에 대해 interop 어셈블리를 생성하려는 경우 이 래퍼 도구를 사용합니다.<br />-   `AXImp`: ActiveX 컨트롤에 대 한 interop 어셈블리를 생성 하려는 경우이 래퍼 도구를 사용 합니다.|  
  
## TypeLibFiles 항목 메타데이터  
 다음 표에서는 `TypeLibFiles` 매개 변수에 전달된 항목에 대해 사용할 수 있는 항목 메타데이터를 설명합니다.  
  
|Metadata|설명|  
|--------------|--------|  
|`WrapperTool`|선택적 항목 메타데이터입니다.<br /><br /> 이 형식 라이브러리에 대한 어셈블리 래퍼를 생성하는 데 사용되는 래퍼 도구를 지정합니다.  이 항목 메타데이터를 지정하지 않으면 작업에서 기본 래퍼 도구인 "tlbimp"를 사용합니다.  typelibs의 선택 가능한 항목은 다음과 같으며 대\/소문자를 구분하지 않습니다.<br /><br /> -   `Primary`: COM 구성 요소에 대해 이미 생성된 주 interop 어셈블리를 사용하려는 경우 이 래퍼 도구를 사용합니다.  이 래퍼 도구를 사용할 경우 래퍼 출력 디렉터리를 지정하지 마십시오. 이를 지정하면 작업이 실패합니다.<br />-   `TLBImp`: COM 구성 요소에 대해 interop 어셈블리를 생성하려는 경우 이 래퍼 도구를 사용합니다.<br />-   `AXImp`: ActiveX 컨트롤에 대 한 interop 어셈블리를 생성 하려는 경우이 래퍼 도구를 사용 합니다.|  
  
> [!NOTE]
>  형식 라이브러리를 고유하게 식별하는 정보를 많이 제공할수록 작업이 디스크 상의 올바른 파일로 해석될 가능성이 커집니다.  
  
## 설명  
 위에 나열된 매개 변수 외에도 이 작업은 <xref:Microsoft.Build.Utilities.Task> 클래스의 매개 변수를 상속합니다.  추가 매개 변수 목록과 해당 설명은 [Task Base Class](../msbuild/task-base-class.md)를 참조하십시오.  
  
## 참고 항목  
 [작업](../msbuild/msbuild-tasks.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)