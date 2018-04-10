---
title: '... 텍스트 템플릿 사용 하는 방법 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 47824561813dfc422dfb19460f1c90f7ed78d1ad
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2018
---
# <a name="how-to--with-text-templates"></a>텍스트 템플릿 사용 방법
텍스트 템플릿 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 어떤 종류의 텍스트를 생성 하는 효과적인 방법을 제공 합니다. 텍스트 템플릿 텍스트를 생성 하려면 디자인 타임에 프로젝트 코드의 일부를 생성 하 고 응용 프로그램의 일부로 실행 시 사용할 수 있습니다. 이 항목에서는 가장 자주 요약 "작업 방법...?" 라는 메시지가 표시 질문 합니다.  
  
 이 항목에서는 여러 답변이 글머리 기호 뒤에 나오는 대안입니다.  
  
 텍스트 템플릿 한 일반적인 내용은 참조 하세요 [코드 생성 및 T4 텍스트 템플릿](../modeling/code-generation-and-t4-text-templates.md)합니다.  
  
## <a name="how-to-"></a>어떻게...  
  
### <a name="generate-part-of-my-application-code"></a>내 응용 프로그램 코드의 일부를 생성 합니다.  
 구성이 I 또는 *모델* 데이터베이스 또는 파일의 합니다. 내 코드의 일부 해당 모델에 따라 달라 집니다.  
  
-   텍스트 템플릿에서 코드 파일의 일부를 생성 합니다. 자세한 내용은 참조 [T4 텍스트 템플릿을 사용 하 여 디자인 타임 코드 생성](../modeling/design-time-code-generation-by-using-t4-text-templates.md) 및 [템플릿을 작성을 시작 하는 가장 좋은 방법은 무엇입니까?](#starting)합니다.  
  
### <a name="generate-files-at-run-time-passing-data-into-the-template"></a>서식 파일에 데이터를 전달 합니다. 런타임 시 파일을 생성 합니다.  
 런타임 시 응용 프로그램에 여러 표준 텍스트와 데이터를 포함 하는 보고서 등의 텍스트 파일을 생성 합니다. 수백 대의 쓰기 방지 하려는 `write` 문.  
  
-   런타임 텍스트 템플릿을 프로젝트에 추가 합니다. 이 템플릿은 인스턴스화할 텍스트를 생성 하려면 사용할 수 있는 코드에서 클래스를 만듭니다. 생성자 매개 변수에서 데이터를 전달할 수 있습니다. 자세한 내용은 참조 [T4 텍스트 템플릿을 사용 하는 런타임 텍스트 생성](../modeling/run-time-text-generation-with-t4-text-templates.md)합니다.  
  
-   런타임에만 사용할 수 있는 템플릿에서 생성 하려는 경우에 표준 텍스트 서식 파일을 사용할 수 있습니다. 작성 하는 경우는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 확장, 텍스트 템플릿 서비스를 호출할 수 있습니다. 자세한 내용은 참조 [VS 확장에서 텍스트 변환 호출](../modeling/invoking-text-transformation-in-a-vs-extension.md)합니다. 다른 컨텍스트에서 텍스트 템플릿 엔진을 사용할 수 있습니다. 자세한 내용은 <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName>을 참조하세요.  
  
     사용 하 여는 \<#@parameter#> 지시문을 이러한 서식 파일에 매개 변수를 전달 합니다. 자세한 내용은 참조 [T4 매개 변수 지시문](../modeling/t4-parameter-directive.md)합니다.  
  
### <a name="read-another-project-file-from-a-template"></a>서식 파일에서 다른 프로젝트 파일 읽기  
 파일을 읽는 동일한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 템플릿으로 프로젝트:  
  
-   먼저 `hostSpecific="true"`를 `<#@template#>` 지시문에 삽입합니다.  
  
     사용자 코드에서 사용 하 여 `this.Host.ResolvePath(filename)` 파일의 전체 경로를 가져옵니다.  
  
### <a name="invoke-methods-from-a-template"></a>서식 파일에서 메서드를 호출 합니다.  
 메서드에에서 이미 있는 경우, 예를 들어 표준 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 클래스:  
  
-   사용 하 여는 \<#@assembly#> 지시문을 사용 하 여 어셈블리를 로드 \<#@import#> 네임 스페이스 컨텍스트를 설정 합니다. 자세한 내용은 참조 [T4 Import 지시문](../modeling/t4-import-directive.md)합니다.  
  
     자주 어셈블리의 동일한 집합을 사용 하 고 가져올 지시문, 경우에 지시문 프로세서를 작성 하는 것이 좋습니다. 각 서식 파일에는 어셈블리와 모델 파일을 로드 하 고 네임 스페이스 컨텍스트를 설정할 수 있는 지시문 프로세서를 호출할 수 있습니다. 자세한 내용은 참조 [사용자 지정 T4 텍스트 템플릿 지시문 프로세서 만들기](../modeling/creating-custom-t4-text-template-directive-processors.md)합니다.  
  
 메서드를 직접 작성 됩니다 하는 경우:  
  
-   런타임 텍스트 템플릿을 작성 하는 경우 런타임 텍스트 템플릿에와 동일한 이름을 가진 partial 클래스 정의 작성 합니다. 이 클래스를 추가 하는 메서드를 추가 합니다.  
  
-   클래스 기능 제어 블록 쓰기 `<#+ ... #>` 를 선언할 수 있는 메서드, 속성 및 전용 클래스에 있습니다. 텍스트 서식 파일을 컴파일할 때 클래스로 변환 합니다. 표준 제어 블록이 `<#...#>` 및 텍스트는 단일 메서드에 변환 되 고 클래스 기능 블록은 별도 구성원으로 삽입 됩니다. 자세한 내용은 참조 [텍스트 템플릿 제어 블록](../modeling/text-template-control-blocks.md)합니다.  
  
     메서드를 클래스 기능 포함 된 텍스트 블록에 포함할 수로 정의 합니다.  
  
     클래스 기능 수 있는 별도 파일에 배치 하는 것이 좋습니다. `<#@include#>` 하나 이상의 템플릿 파일에 있습니다.  
  
-   별도 어셈블리 (클래스 라이브러리)에 메서드를 작성 하 고 서식 파일에서이 호출 합니다. 사용 하 여는 `<#@assembly#>` 지시문을 어셈블리를 로드 하 고 `<#@import#>` 네임 스페이스 컨텍스트를 설정 합니다. 어셈블리를 디버깅 하는 동안 다시 작성 하기 위해 수가 중지 했다가 다시 시작 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 자세한 내용은 참조 [T4 텍스트 템플릿 지시문](../modeling/t4-text-template-directives.md)합니다.  
  
### <a name="generate-many-files-from-one-model-schema"></a>한 모델 스키마에서 여러 파일 생성  
 경우 종종 동일한 XML 또는 데이터베이스 스키마가 있는 모델에서 파일을 생성 합니다.  
  
-   지시문 프로세서를 작성 하는 것이 좋습니다. 따라서 여러 어셈블리 문을 바꾸고 테이프를 단일 사용자 지정 지시문을 사용해 각 서식 파일에서 가져올 수 있습니다. 지시문 프로세서를 로드할 수 있고 모델 파일을 구문 분석 합니다. 자세한 내용은 참조 [사용자 지정 T4 텍스트 템플릿 지시문 프로세서 만들기](../modeling/creating-custom-t4-text-template-directive-processors.md)합니다.  
  
### <a name="generate-files-from-a-complex-model"></a>복잡 한 모델에서 파일을 생성 합니다.  
  
-   도메인 특정 언어 DSL ()을 나타내는 모델을 만드는 것이 좋습니다. 따라서 훨씬 더 쉽게 작성할 템플릿, 형식 및 모델에 있는 요소의 이름을 반영 하는 속성을 사용 하기 때문에 있습니다. 파일을 구문 분석 또는 XML 노드를 탐색할 필요가 없습니다. 예를 들어:  
  
     `foreach (Book book in this.Library) { ... }`  
  
     자세한 내용은 참조 [도메인 특정 언어 시작](../modeling/getting-started-with-domain-specific-languages.md) 및 [도메인 특정 언어에서 코드 생성](../modeling/generating-code-from-a-domain-specific-language.md)합니다.  
  
### <a name="get-data-from-includevsprvscode-qualityincludesvsprvsmdmd"></a>데이터 가져오기 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]  
 제공 하는 서비스를 사용 하려면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 집합에 의해는 `hostSpecific` 특성과 부하는 `EnvDTE` 어셈블리. 예를 들어:  
  
```csharp  
<#@ template hostspecific="true" language="C#" #>  
<#@ output extension=".txt" #>  
<#@ assembly name="EnvDTE" #>  
<#  
  IServiceProvider serviceProvider = (IServiceProvider)this.Host;  
  EnvDTE.DTE dte = (EnvDTE.DTE) serviceProvider.GetService(typeof(EnvDTE.DTE));  
#>  
  
Number of projects in this VS solution:  <#= dte.Solution.Projects.Count #>  
  
```  
  
### <a name="execute-text-templates-in-the-build-process"></a>빌드 프로세스에서 텍스트 템플릿 실행  
  
-   자세한 내용은 참조 [빌드 프로세스에서 코드 생성](../modeling/code-generation-in-a-build-process.md)합니다.  
  
## <a name="more-general-questions"></a>보다 일반적인 질문  
  
###  <a name="starting"></a> 텍스트 템플릿을 작성을 시작 하는 가장 좋은 방법은 무엇입니까?  
  
1.  생성된 된 파일의 특정 예제를 작성 합니다.  
  
2.  삽입 하 여 텍스트 템플릿을로 변환 된 `<#@template #>` 지시문 지시문 및 코드 입력된 파일이 나 모델을 로드 하는 데 필요한 합니다.  
  
3.  식 및 코드 블록으로 파일의 일부를 점진적으로 대체 합니다.  
  
### <a name="what-is-a-model"></a>"모델" 이란?  
  
-   서식 파일에서 읽은 입력 합니다. 파일 또는 데이터베이스 수 있습니다. XML 또는 Visio 드로잉 또는 도메인 특정 언어 DSL (), 또는 UML 모델, 수도 있고 일반 텍스트 일 수 없습니다. 여러 개의 파일 분산할 수 있습니다. 일반적으로 둘 이상의 템플릿을 모델 하나를 읽습니다.  
  
     용어 "모델"의 구현은 생성 된 프로그램 코드 또는 다른 파일 보다 더 직접적으로 비즈니스의 일부 측면 나타내는 것입니다. 예를 들어 생성 된 소프트웨어에서 감독 하는 통신 네트워크 계획을 나타낼 수도 있습니다.  
  
### <a name="what-is-the-benefit-of-using-text-templates"></a>텍스트 템플릿을 사용 하는 장점은 무엇입니까?  
 일반적으로 여러 코드 또는 다른 파일에서에서 생성 한 모델. 모델은 생성된 된 코드 보다 더 직접적 요구 사항을 나타냅니다. 구현 정보를 생략 하 고 코드 보다는 요구 사항을 기준으로 기록 됩니다. 요구 사항이 변경-일반적으로-보다 쉽고 프로그램 코드의 여러 부분 보다 안정적으로 모델을 업데이트할 수 있습니다.  
  
 따라서 코드 생성은 민첩 한 개발 방법의 관점에서 보면 매우 유용한 도구입니다.  
  
### <a name="what-best-practices-are-there-for-text-templates"></a>"모범 사례"는 무엇입니까 텍스트 템플릿에 대 한?  
  
-   자세한 내용은 참조 [T4 텍스트 템플릿 작성 지침](../modeling/guidelines-for-writing-t4-text-templates.md)합니다.  
  
### <a name="what-is-t4"></a>"T4" 이란?  
  
-   에 다른 이름을 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 텍스트 템플릿 기능 여기에서 설명 합니다. 게시 되지 않은 이전 버전을 "텍스트 템플릿 변환"에 대 한 약어 했습니다.
