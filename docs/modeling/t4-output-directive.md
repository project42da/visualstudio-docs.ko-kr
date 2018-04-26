---
title: T4 Output 지시문
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 6044dd970029b3f233f8b20eb2e334b5041ceb33
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="t4-output-directive"></a>T4 Output 지시문

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 텍스트 템플릿에서 `output` 지시문은 변환된 파일의 인코딩과 파일 이름 확장명을 정의하는 데 사용됩니다.

 예를 들어 경우 프로그램 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트 라는 템플릿 파일에 포함 되어 **MyTemplate.tt** 다음 지시문이 들어 있는:

 `<#@output extension=".cs"#>`

 그런 다음 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 라는 파일이 생성 됩니다 **MyTemplate.cs**

 전처리된 런타임 텍스트 템플릿에는 `output` 지시문이 필요하지 않습니다. 대신 응용 프로그램은 `TextTransform()`을 호출하여 생성된 문자열을 가져옵니다. 자세한 내용은 참조 [T4 텍스트 템플릿을 사용 하는 런타임 텍스트 생성](../modeling/run-time-text-generation-with-t4-text-templates.md)합니다.

## <a name="using-the-output-directive"></a>output 지시문 사용

```
<#@ output extension=".fileNameExtension" [encoding="encoding"] #>
```

 각 텍스트 템플릿에 `output` 지시문이 두 개 이상 있어서는 안 됩니다.

## <a name="extension-attribute"></a>확장 특성
 생성된 텍스트 출력 파일의 파일 이름 확장명을 지정합니다.

 기본값은 **.cs**

 예제: `<#@ output extension=".txt" #>`

 `<#@ output extension=".htm" #>`

 `<#@ output extension=".cs" #>`

 `<#@ output extension=".vb" #>`

 허용 되는 값: 모든 유효한 파일 이름 확장명입니다.

## <a name="encoding-attribute"></a>인코딩 특성
 출력 파일을 생성할 때 사용할 인코딩을 지정합니다. 예를 들면 다음과 같습니다.

 `<#@ output encoding="utf-8"#>`

 기본값은 텍스트 템플릿 파일에 사용되는 인코딩입니다.

 허용 되는 값: `us-ascii`

 `utf-16BE`

 `utf-16`

 `utf-8`

 `utf-7`

 `utf-32`

 `0`(시스템 기본값)

 일반적으로는 <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=fullName>가 반환하는 모든 인코딩으로 된 WebName 문자열 또는 CodePage 번호를 사용할 수 있습니다.