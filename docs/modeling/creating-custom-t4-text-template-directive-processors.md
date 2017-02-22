---
title: "사용자 지정 T4 텍스트 템플릿 지시문 프로세서 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "텍스트 템플릿, 사용자 지정 지시문 처리기"
ms.assetid: 422b47af-5441-4b02-b5ad-1b8b328457e3
caps.latest.revision: 29
caps.handback.revision: 29
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 사용자 지정 T4 텍스트 템플릿 지시문 프로세서 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

*텍스트 템플릿 변환 프로세스*에서는 *텍스트 템플릿* 파일을 입력으로 사용하고 텍스트 파일을 출력으로 생성합니다.  *텍스트 템플릿 변환 엔진*은 이 프로세스를 제어하며 텍스트 템플릿 변환 호스트 및 하나 이상의 텍스트 템플릿 *지시문 프로세서*와 상호 작용하여 프로세스를 완료합니다.  자세한 내용은 [텍스트 템플릿 변환 프로세스](../modeling/the-text-template-transformation-process.md)를 참조하십시오.  
  
 사용자 지정 지시문 프로세서를 만들려면 <xref:Microsoft.VisualStudio.TextTemplating.DirectiveProcessor> 또는 <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor>에서 상속하는 클래스를 만듭니다.  
  
 둘의 차이점은 <xref:Microsoft.VisualStudio.TextTemplating.DirectiveProcessor>가 사용자에게 매개 변수를 얻고 템플릿 출력 파일을 생성하는 코드를 생성하는 데 필요한 최소한의 인터페이스를 구현하지만,  <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor>는 requires\/provides 디자인 패턴을 구현한다는 것입니다.  <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor>는 두 가지 특수 매개 변수 `requires` 및 `provides`를 처리합니다.  예를 들어, 사용자 지정 지시문 프로세서는 사용자에게 파일 이름을 얻어 파일을 열고 읽은 다음 파일의 텍스트를 `fileText`라는 변수에 저장할 수 있습니다.  <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor> 클래스의 하위 클래스는 사용자에게 `requires` 매개 변수 값으로 파일 이름을 얻고 `provides` 매개 변수의 값으로 텍스트를 저장할 변수의 이름을 얻을 수 있습니다.  이 프로세서는 파일을 열고 읽은 다음 파일의 텍스트를 지정된 변수에 저장합니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 텍스트 템플릿에서 사용자 지정 지시문 프로세서를 호출하기 전에 프로세서를 등록해야 합니다.  
  
 레지스트리 키를 추가하는 방법에 대한 자세한 내용은 [사용자 지정 지시문 처리기 배포](../modeling/deploying-a-custom-directive-processor.md)를 참조하십시오.  
  
## 사용자 지정 지시문  
 사용자 지정 지시문은 다음과 같습니다.  
  
 `<#@ MyDirective Processor="MyDirectiveProcessor" parameter1="value1" … #>`  
  
 텍스트 템플릿에서 외부 데이터나 리소스에 액세스하려면 사용자 지정 지시문 프로세서를 사용할 수 있습니다.  
  
 여러 텍스트 템플릿이 단일 지시문 프로세서에서 제공하는 기능을 공유할 수 있으므로 지시문 프로세서는 다시 사용할 수 있도록 코드를 구분하는 방법을 제공합니다.  기본 제공 `include` 지시문을 사용하여 코드를 구분하고 여러 텍스트 템플릿에서 공유할 수 있기 때문에 이 지시문도 유사한 기능을 합니다.  차이점은 `include` 지시문이 제공하는 모든 기능이 고정되어 있고 매개 변수를 받아들이지 않는다는 것입니다.  텍스트 템플릿에 일반 기능을 제공하고 템플릿에서 매개 변수를 전달할 수 있도록 하려면 사용자 지정 지시문 프로세서를 만들어야 합니다.  
  
 사용자 지정 지시문 프로세서의 몇 가지 예는 다음과 같습니다.  
  
-   사용자 이름과 암호를 매개 변수로 받아들이는, 데이터베이스에서 데이터를 반환하는 지시문 프로세서  
  
-   파일 이름을 매개 변수로 받아들이는, 파일을 열고 읽는 지시문 프로세서  
  
### 사용자 지정 지시문 프로세서의 주요 부분  
 지시문 프로세서를 개발하려면 <xref:Microsoft.VisualStudio.TextTemplating.DirectiveProcessor> 또는 <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor>에서 상속하는 클래스를 만들어야 합니다.  
  
 구현해야 하는 가장 중요한 `DirectiveProcessor` 메서드는 다음과 같습니다.  
  
-   `bool IsDirectiveSupported(string directiveName)` \- 지시문 처리기가 명명된 지시문을 처리할 수 있으면 `true`를 반환합니다.  
  
-   `void ProcessDirective (string directiveName, IDictionary<string, string> arguments)` \- 템플릿 엔진은 템플릿에서 지시문이 발견될 때마다 이 메서드를 호출합니다.  프로세서는 결과를 저장해야 합니다.  
  
 ProcessDirective\(\)를 모두 호출한 후 템플릿 엔진은 다음 메서드를 호출합니다.  
  
-   `string[] GetReferencesForProcessingRun()` \- 템플릿 코드에 필요한 어셈블리의 이름을 반환합니다.  
  
-   `string[] GetImportsForProcessingRun()` \- 템플릿 코드에서 사용할 수 있는 네임스페이스를 반환합니다.  
  
-   `string GetClassCodeForProcessingRun()` \- 템플릿 코드에서 사용할 수 있는 메서드, 속성 및 기타 선언의 코드를 반환합니다.  이렇게 하는 가장 쉬운 방법은 C\# 또는 Visual Basic 코드가 포함된 문자열을 작성하는 것입니다.  지시문 프로세서가 CLR 언어를 사용하는 템플릿에서 호출될 수 있도록 하려면 CodeDom 트리로 문을 생성한 다음 템플릿에서 사용하는 언어로 트리를 serialize한 결과를 반환하면 됩니다.  
  
-   자세한 내용은 [연습: 사용자 지정 지시문 프로세서 만들기](../modeling/walkthrough-creating-a-custom-directive-processor.md)를 참조하십시오.  
  
## 단원 내용  
 [사용자 지정 지시문 처리기 배포](../modeling/deploying-a-custom-directive-processor.md)  
 사용자 지정 지시문 프로세서를 등록하는 방법에 대해 설명합니다.  
  
 [연습: 사용자 지정 지시문 프로세서 만들기](../modeling/walkthrough-creating-a-custom-directive-processor.md)  
 사용자 지정 지시문 프로세서를 만드는 방법, 지시문 프로세스를 등록 및 테스트하는 방법, 출력 파일의 형식을 HTML로 지정하는 방법에 대해 설명합니다.