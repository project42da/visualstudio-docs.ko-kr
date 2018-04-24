---
title: Visual Studio에 TextTransform 유틸리티를 사용 하 여 파일을 생성합니다.
ms.date: 03/22/2018
ms.topic: conceptual
helpviewer_keywords:
- text templates, TextTransform utility
- TextTransform.exe
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 065d9e23a8ae8b5e328786bb195d191df1388abb
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="generate-files-with-the-texttransform-utility"></a>TextTransform 유틸리티를 사용 하 여 파일을 생성 합니다.

TextTransform.exe는 텍스트 템플릿을 변형 하는 데 사용할 수 있는 명령줄 도구입니다. TextTransform.exe를 호출할 때 인수로 텍스트 템플릿 파일의 이름을 지정 합니다. TextTransform.exe는 텍스트 변환 엔진을 호출 하 고 텍스트 서식 파일을 처리 합니다. TextTransform.exe는 일반적으로 스크립트에서 호출 됩니다. 그러나 않습니다 일반적으로 필요 하므로 Visual Studio에서 또는 빌드 프로세스에서 텍스트 변환 작업을 수행할 수 있습니다.

> [!NOTE]
> 빌드 프로세스의 일환으로 텍스트 변형 작업을 실행 하려는 경우에 MSBuild 텍스트 변환 작업을 사용 하는 것이 좋습니다. 자세한 내용은 참조 [빌드 프로세스에서 코드 생성](../modeling/code-generation-in-a-build-process.md)합니다. 된 컴퓨터에서에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 가 설치 되어 응용 프로그램을 작성할 수 있습니다 또는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 텍스트 템플릿을 변형할 수 있는 확장 합니다. 자세한 내용은 참조 [사용자 지정 호스트를 사용 하 여 텍스트 템플릿 처리](../modeling/processing-text-templates-by-using-a-custom-host.md)합니다.

 TextTransform.exe은 다음 디렉터리에 있습니다.

 **\Program Files (x86)\Microsoft Visual Studio\2017\Professional\Common7\IDE**

Professional edition에 대 한 또는

 **\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE**

 Enterprise edition.

이전 버전의 Visual Studio에서는 파일은 다음 위치에 있습니다.

**\Program Files (x86)\Common Files\Microsoft Shared\TextTemplating\{version}**

여기서 {버전}는 설치 된 이전 버전에 따라 다릅니다.

## <a name="syntax"></a>구문

```
TextTransform [<options>] <templateName>
```

### <a name="parameters"></a>매개 변수

|**인수**|**설명**|
|------------------|---------------------|
|`templateName`|변환 하려는 경우 템플릿 파일의 이름을 식별 합니다.|

|**옵션**|**설명**|
|----------------|---------------------|
|**-out** \<filename>|변환의 출력을 쓸 파일입니다.|
|**-r** \<assembly>|컴파일 및 텍스트 템플릿을 실행에 사용 되는 어셈블리입니다.|
|**-u** \<namespace>|서식 파일을 컴파일하는 데 사용 되는 네임 스페이스입니다.|
|**-I** \<includedirectory>|지정 된 텍스트 서식 파일에 포함 된 텍스트 템플릿을 포함 하는 디렉터리입니다.|
|**-P** \<referencepath>|텍스트 템플릿 내에 지정 된 어셈블리 또는 사용 하 여 검색 하려면 디렉터리는 **-r** 옵션입니다.<br /><br /> 예를 들어 Visual Studio API에 대 한 사용 되는 어셈블리를 포함 하려면 사용<br /><br /> `-P "%VSSHELLFOLDER%\Common7\IDE\PublicAssemblies"`|
|**-dp** \<processorName>!\<className>!\<assemblyName&#124;codeBase>|이름, 전체 형식 이름 및 텍스트 템플릿 내에서 사용자 지정 지시문 처리를 사용할 수 있는 지시문 프로세서의 어셈블리입니다.|
|**-a** [processorName]![directiveName]!\<parameterName>!\<parameterValue>|지시문 프로세서에 대 한 매개 변수 값을 지정 합니다. 매개 변수 이름 및 값을 지정 하면 매개 변수가 모든 지시문 프로세서에 사용할 수 있는 됩니다. 지시문 프로세서를 지정 하면 지정 된 프로세서 수입니다. 지시문 이름을 지정 하면 지정된 된 지시문을 처리 되는 경우에 사용할 수는 매개 변수는.<br /><br /> 매개 변수 값에 지시문 프로세서 또는 텍스트 서식 파일에서 액세스를 사용 하 여 [ITextTemplatingEngineHost.ResolveParameterValue](https://msdn.microsoft.com/library/microsoft.visualstudio.texttemplating.itexttemplatingenginehost.resolveparametervalue.aspx)합니다. 텍스트 템플릿을 포함 `hostspecific` template 지시문에에서 메시지를 호출 하 고 `this.Host`합니다. 예를 들어:<br /><br /> `<#@template language="c#" hostspecific="true"#> [<#= this.Host.ResolveParameterValue("", "", "parameterName") #>]`.<br /><br /> 항상 입력의 '!' 옵션 프로세서와 지시문 이름은 생략 한 경우에 표시 합니다. 예를 들어:<br /><br /> `-a !!param!value`|
|**-h**|도움말을 제공 합니다.|

## <a name="related-topics"></a>관련 항목

|작업|항목|
|----------|-----------|
|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 솔루션에서 파일을 생성합니다.|[T4 텍스트 템플릿을 사용하여 디자인 타임 코드 생성](../modeling/design-time-code-generation-by-using-t4-text-templates.md)|
|고유한 데이터 소스를 변형하는 지시문 프로세서를 작성합니다.|[T4 텍스트 변환 사용자 지정](../modeling/customizing-t4-text-transformation.md)|
|사용자의 응용 프로그램에서 텍스트 템플릿을 호출할 수 있도록 텍스트 템플릿 호스트를 작성 합니다.|[사용자 지정 호스트를 사용하여 텍스트 템플릿 처리](../modeling/processing-text-templates-by-using-a-custom-host.md)|