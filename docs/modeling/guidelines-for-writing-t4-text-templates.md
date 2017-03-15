---
title: "T4 텍스트 템플릿 작성에 대 한 지침 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04dd3fc4-10e8-488a-bdea-4d615f50f063
caps.latest.revision: 9
author: alancameronwills
ms.author: awills
manager: douge
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fd26c504273cae739ccbeef5e406891def732985
ms.openlocfilehash: 7d9dd7193455a625b0410eaca3b2bd243c109743
ms.lasthandoff: 02/22/2017

---
# <a name="guidelines-for-writing-t4-text-templates"></a>T4 텍스트 템플릿 작성 지침
이러한 일반적인 지침 프로그램 코드 또는 다른 응용 프로그램 리소스에서 생성 하는 경우에 도움이 될 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 규칙은 고정 되지 않는 합니다.  
  
## <a name="guidelines-for-design-time-t4-templates"></a>디자인 타임 T4 템플릿 지침  
 디자인 타임 T4 템플릿은의 코드를 생성 하는 템플릿이 프로그램 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 디자인 타임에는 프로젝트입니다. 자세한 내용은 참조 [T4 텍스트 템플릿을 사용 하 여 디자인 타임 코드 생성](../modeling/design-time-code-generation-by-using-t4-text-templates.md)합니다.  
  
 응용 프로그램의 가변 측면을 생성 합니다.  
 코드 생성 프로젝트 중에 변경 또는 응용 프로그램의 서로 다른 버전 간에 변경 될 응용 프로그램의 측면에서 가장 유용 합니다. 생성 되는 어떤를 보다 쉽게 확인할 수 있도록 더 고정 측면에서 이러한 가변 측면을 구분 합니다. 예를 들어, 응용 프로그램 웹 사이트를 제공 하는 경우 다른 한 페이지에서 탐색 경로 정의 하는 논리에서 함수를 제공 합니다. 표준 페이지를 구분 합니다.  
  
 하나 이상의 원본 모델에 가변 측면을 인코딩하십시오.  
 모델은 파일이 나 데이터베이스를 생성 하는 코드의 변수 부분에 대 한 특정 값을 가져오려면 읽는 각 서식 파일은. 데이터베이스, XML 파일을 직접 디자인, 다이어그램 또는 도메인별 언어 모델 일 수 있습니다. 여러 파일을 생성 한 모델을 사용 하는 일반적으로 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트입니다. 각 파일은 별도 서식 파일에서 생성 됩니다.  
  
 프로젝트에서 하나 이상의 모델을 사용할 수 있습니다. 예를 들어 웹 페이지 및 페이지의 레이아웃에 대 한 별도 모델 간의 탐색에 대 한 모델을 정의할 수 있습니다.  
  
 모델에 집중 된 사용자의 요구와 어휘 구현에 있습니다.  
 예를 들어 웹 사이트 응용 프로그램에서 모델을 웹 페이지 및 하이퍼링크를 가리키는 것 예상 합니다.  
  
 이상적으로 프레젠테이션 모델이 나타내는 정보를 적합 한 형태를 선택 합니다. 예를 들어 웹 사이트를 통해 탐색 경로의 모델 상자와 화살표의 다이어그램을 수 있습니다.  
  
 생성된 된 코드를 테스트 합니다.  
 수동 또는 자동화 된 테스트를 사용 하 여 결과 코드는 사용자가 필요로 하는 대로 작동 하는지 확인 합니다. 코드가 생성 되는 동일한 모델에서 테스트를 생성 하지 않습니다.  
  
 경우에 따라 일반 테스트 모델에서 직접 수행할 수 있습니다. 예를 들어 웹 사이트의 모든 페이지 간 탐색을 통해 연결할 수 있는지 확인 하는 테스트를 작성할 수 있습니다.  
  
 사용자 지정 코드 허용: partial 클래스를 생성 합니다.  
 작성 하는 코드를 직접 또한 생성 된 코드에 허용 합니다. 문제가 발생할 수 있는 모든 변형을 고려 하려면 코드 생성 체계에 대 한 거의 하지 않습니다. 따라서에 추가 하거나 생성된 된 코드의 일부를 재정의할 하시면 됩니다. 여기서는 생성 된 자료는.NET 언어에서와 같은 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 또는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], 두 가지 전략은 특히 유용 합니다.  
  
-   생성 된 클래스 부분 이어야 합니다. 이 콘텐츠는 생성 된 코드를 추가할 수 있습니다.  
  
-   클래스에서 상속 하는 쌍에서 생성 되어야 합니다. 기본 클래스에는 생성 된 메서드 및 속성을 모두 포함 되어야 하 고 파생된 클래스 생성자만 포함 해야 합니다. 따라서 직접 작성 된 코드를 생성된 된 메서드를 재정의할 수 있습니다.  
  
 생성 된 XML 같은 다른 언어를 사용 하 여는 `<#@include#>` 지시문을 직접 작성 하 고 생성 된 콘텐츠의 간단한 조합을 확인 합니다. 더 복잡 한 경우에 직접 작성 된 파일을 모두 사용 하 여 생성 된 파일을 결합 하는 후 처리 단계를 작성 해야 할 수 있습니다.  
  
 포함 파일 또는 런타임 템플릿에 공통 자료를 이동 합니다.  
 사용 하 여 비슷한 블록 텍스트와 여러 서식 파일에서 코드의 반복을 방지 하려면는 `<#@ include #>` 지시문입니다. 자세한 내용은 참조 [T4 Include 지시문](../modeling/t4-include-directive.md)합니다.  
  
 또한 빌드를 별도 프로젝트에서 런타임 텍스트 템플릿 수 있으며 다음 디자인 타임 템플릿을에서 호출할 수 있습니다. 이 위해 사용 하 여는 `<#@ assembly #>` 지시문을 별도 프로젝트에 액세스 합니다. 예를 보려면 [상속에 텍스트 "템플릿" Gareth Jones 블로그의](http://go.microsoft.com/fwlink/?LinkId=208373)합니다.  
  
 큰 블록의 코드를 별도 어셈블리로 이동 하는 것이 좋습니다.  
 대규모 코드 블록 및 클래스 기능 블록에 있는 경우에 별도 프로젝트에서 컴파일하는 메서드를이 코드의 일부를 이동 하려면 유용할 수 있습니다. 사용할 수는 `<#@ assembly #>` 지시문 코드 서식 파일에 액세스할 수 있습니다. 자세한 내용은 참조 [T4 Assembly 지시문](../modeling/t4-assembly-directive.md)합니다.  
  
 서식 파일을 상속할 수 있는 추상 클래스에 메서드를 넣을 수 있습니다. 추상 클래스 <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation?displayProperty=fullName>.</xref:Microsoft.VisualStudio.TextTemplating.TextTransformation?displayProperty=fullName> 에서 상속 해야 자세한 내용은 참조 [T4 템플릿 지시문](../modeling/t4-template-directive.md)합니다.  
  
 구성 파일이 아닌 코드를 생성 합니다.  
 변수 응용 프로그램을 작성 하는 한 가지 방법은 구성 파일을 허용 하는 일반 프로그램 코드를 작성 하는 것입니다. 이러한 방식으로 작성 된 응용 프로그램은 매우 유연 하 고 응용 프로그램을 다시 작성 하지 않고 비즈니스 요구 사항이 변경 될 때 다시 구성할 수 있습니다. 그러나이 방법의 단점은 응용 프로그램 낮다는 것 보다는 보다 구체적인 응용 프로그램입니다. 또한, 때문에 항상 제네릭 형식을 처리 하는 프로그램 코드를 읽고 유지 관리 하기가 매우 어려울 수 있습니다.  
  
 반면, 가변 부분이 컴파일 전에 생성 된 응용 프로그램 강력한 형식을 사용할 수 있습니다. 따라서 소프트웨어의 부분을 훨씬 쉽고 더 안정적으로 직접 작성 한 코드를 작성 하 고 생성 된 프로그램과 통합할 수 있습니다.  
  
 코드 생성의 모든 이점을 얻으려면 구성 파일 대신 프로그램 코드를 생성 하려고 합니다.  
  
 생성 된 코드 폴더를 사용 하 여  
 서식 파일 및 생성된 된 파일 라는 프로젝트 폴더에 배치 **생성 된 코드**하기 위해 아니라는 직접 편집 해야 하는 파일의 선택을 취소 합니다. 재정의 하거나 생성된 된 클래스에 추가 하려면 사용자 지정 코드를 만드는 경우 이러한 클래스는 폴더에에서 배치 라는 **사용자 지정 코드**합니다. 일반적인 프로젝트의 구조는 다음과 같습니다.  
  
```  
MyProject  
   Custom Code  
      Class1.cs  
      Class2.cs  
   Generated Code  
      Class1.tt  
          Class1.cs  
      Class2.tt  
          Class2.cs  
   AnotherClass.cs  
  
```  
  
## <a name="guidelines-for-run-time-preprocessed-t4-templates"></a>런타임에 전처리 된 T4 템플릿 지침  
 공통 자료를 상속 된 템플릿으로 이동 합니다.  
 메서드 및 T4 텍스트 템플릿 간에 텍스트 블록을 공유 하려면 상속을 사용할 수 있습니다. 자세한 내용은 참조 [T4 템플릿 지시문](../modeling/t4-template-directive.md)합니다.  
  
 사용할 수도 있습니다 런타임 템플릿의 파일만 포함 됩니다.  
  
 Partial 클래스에 큰 코드 본문을 이동 합니다.  
 각 런타임 서식 파일 서식 파일 이름이 같은 partial 클래스 정의 생성 합니다. 동일한 클래스의 다른 부분 정의 포함 하는 코드 파일을 작성할 수 있습니다. 이 방식으로 클래스에 메서드, 필드 및 생성자를 추가할 수 있습니다. 템플릿의 코드 블록에서 이러한 멤버를 호출할 수 있습니다.  
  
 이 작업의 장점은 IntelliSense를 사용할 수 있으므로 코드를 작성할 수입니다. 또한, 표시 및 기본 논리와는 더 나은 구분을 얻을 수 있습니다.  
  
 예를 들어 **MyReportText.tt**:  
  
 `The total is: <#= ComputeTotal() #>`  
  
 **MyReportText Methods.cs**:  
  
 `private string ComputeTotal() { ... }`  
  
 사용자 지정 코드 허용: 확장 지점을 제공 합니다.  
 가상 메서드를 생성 하는 것이 좋습니다. \<#+ 클래스 기능 블록 # >. 따라서 단일 템플릿을 수정 하지 않고 여러 컨텍스트에서 사용할 수 있습니다. 서식 파일을 수정 하는 대신 최소한의 추가 논리를 제공 하는 파생된 클래스를 생성할 수 있습니다. 런타임 템플릿에서 수 또는 파생된 클래스에는 일반 코드 이거나 수 있습니다.  
  
 예를 들어 MyStandardRunTimeTemplate.tt에:  
  
```  
This page is copyright <#= CompanyName() #>.  
<#+ protected virtual string CompanyName() { return ""; } #>  
```  
  
 응용 프로그램의 코드:  
  
```  
class FabrikamTemplate : MyStandardRunTimeTemplate  
{  
  protected override string CompanyName() { return "Fabrikam"; }  
}  
...  
  string PageToDisplay = new FabrikamTemplate().TextTransform();  
  
```  
  
## <a name="guidelines-for-all-t4-templates"></a>모든 T4 템플릿 지침  
 텍스트 생성에서 별도 데이터 수집  
 계산 및 텍스트 블록을 혼합 하지 마십시오. 첫 번째를 사용 하 여 각 텍스트 템플릿에 \<# 코드 블록 # > 변수를 설정 하 고 복잡 한 계산을 수행할 수 있습니다. 서식 파일 또는 첫 번째의 기본값은 첫 번째 텍스트 블록에서 \<#+ 클래스 기능 블록 # >, 긴 식을 하지 않도록 하 고 텍스트 블록을 포함 하지 않는 한 루프 및 조건문을 방지 합니다. 이 연습을 통해 서식 파일 보다 쉽게 읽고 유지 관리 합니다.  
  
 사용 하지 않는 `.tt` 포함 파일  
 와 같은 다른 파일 이름 확장명을 사용 하 여 `.ttinclude` 포함 파일입니다. 사용 하 여 `.tt` 수 있는 파일을 같이 런타임 또는 디자인 타임 텍스트 템플릿 처리만 합니다. 경우에 따라 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 인식 `.tt` 파일을 자동으로 처리를 위해 해당 속성을 설정 합니다.  
  
 고정 된 프로토타입으로 각 서식 파일을 시작 합니다.  
 생성 되 고 정확한 지 확인 하려면 코드 또는 텍스트의 예제를 작성 합니다. 그런 다음 해당 확장명.tt을 변경 하 고 증분 방식으로 모델을 참조 하 여 콘텐츠를 수정 하는 코드를 삽입 합니다.  
  
 형식화 된 모델을 사용 하는 것이 좋습니다.  
 XML 또는 데이터베이스 스키마 모델에 대 한를 만들 수는 있지만 도메인별 언어 (DSL)를 만들 유용할 수 있습니다. DSL는 스키마 및 속성의 특성을 나타내는 각 노드를 나타내는 클래스를 생성 하는 이점이 있습니다. 즉, 비즈니스 모델을 기준으로 프로그래밍할 수 있습니다. 예:  
  
```  
Team Members:  
<# foreach (Person p in team.Members)   
 { #>   
    <#= p.Name #>   
<# } #>  
```  
  
 모델에 대 한 다이어그램을 사용 하는 것이 좋습니다.  
 많은 모델이 가장 효과적으로 제공으로 되 고 관리 단순히 텍스트 테이블 특히 매우 큰 경우.  
  
 그러나 일부의 비즈니스 요구 사항에 대 한 관계 및 워크플로, 복잡 한 집합을 명확 하 게 하는 것이 중요 있으며 다이어그램에서 가장 적합 합니다. 다이어그램의 장점은 사용자 및 다른 이해 관계자와 쉽게 논의할 수 있다는 것입니다. 비즈니스 요구의 수준 모델에서 코드를 생성 하 여 코드 보다 유연한 때 결정할 요구 사항이 변경 합니다.  
  
 또한 도메인 관련 언어 (DSL)로 고유한 유형의 다이어그램을 디자인할 수 있습니다. UML와 Dsl에서 코드를 생성할 수 있습니다. 자세한 내용은 참조 [분석 및 아키텍처 모델링](../modeling/analyze-and-model-your-architecture.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [T4 텍스트 템플릿을 사용하여 디자인 타임 코드 생성](../modeling/design-time-code-generation-by-using-t4-text-templates.md)   
 [T4 텍스트 템플릿을 사용하여 런타임 텍스트 생성](../modeling/run-time-text-generation-with-t4-text-templates.md)

