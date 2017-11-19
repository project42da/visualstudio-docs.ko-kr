---
title: "T4 텍스트 템플릿 작성 지침 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04dd3fc4-10e8-488a-bdea-4d615f50f063
caps.latest.revision: "9"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 6baa3086d1a81ce433a077ab1ed0dff4cb152308
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="guidelines-for-writing-t4-text-templates"></a>T4 텍스트 템플릿 작성 지침
다음 일반 지침 프로그램 코드 또는 다른 응용 프로그램 리소스에서 생성 하는 경우 유용할 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 이들이 하지 규칙 수정 합니다.  
  
## <a name="guidelines-for-design-time-t4-templates"></a>디자인 타임 T4 템플릿에 대 한 지침  
 디자인 타임 T4 템플릿은의 코드를 생성 하는 템플릿이 프로그램 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 디자인 타임에 프로젝트입니다. 자세한 내용은 참조 [T4 텍스트 템플릿을 사용 하 여 디자인 타임 코드 생성](../modeling/design-time-code-generation-by-using-t4-text-templates.md)합니다.  
  
 응용 프로그램의 변수 측면을 생성 합니다.  
 프로젝트에서 변경 될 수 있습니다 또는 응용 프로그램의 서로 다른 버전 간에 변경 될 하는 응용 프로그램에서 이러한 요소에 대 한 코드 생성 가장 유용 합니다. 생성 되는 기능을 보다 쉽게 확인할 수 있습니다 수 있도록 더 고정 측면에서 이러한 변수 측면을 충분히를 구분 합니다. 예를 들어 응용 프로그램이 웹 사이트를 제공 하는 경우 표준 페이지 기능을 다른 한 페이지에서 탐색 경로 정의 하는 논리 제공을 구분 합니다.  
  
 하나 이상의 원본 모델에 있는 변수 측면을으로 인코딩하십시오.  
 모델은 파일이 나 데이터베이스를 생성 하는 코드를의 변수 부분에 대 한 특정 값을 가져오는 각 서식 파일을 읽을 수 있는. 모델은 데이터베이스, 디자인, 다이어그램, 또는 도메인 특정 언어의 XML 파일 일 수 있습니다. 여러 파일을 생성 한 모델을 사용 하는 일반적으로 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트. 각 파일은 별도 서식 파일에서 생성 됩니다.  
  
 프로젝트에서 하나 이상의 모델을 사용할 수 있습니다. 예를 들어 웹 페이지 및 페이지의 레이아웃에 대 한 별도 모델 간의 탐색에 대 한 모델을 정의할 수 있습니다.  
  
 모델에 집중 사용자의 요구 사항과 어휘 구현에 있습니다.  
 예를 들어 웹 사이트 응용 프로그램에서 웹 페이지와 하이퍼링크를 참조 하는 모델을 예상 합니다.  
  
 이상적으로 한 표현 유형의 모델이 나타내는 정보를 적합 한 형식을 선택 합니다. 예를 들어 웹 사이트를 통해 탐색 경로의 모델은 상자와 화살표로 다이어그램 수 있습니다.  
  
 생성된 된 코드를 테스트 합니다.  
 수동 또는 자동화 된 테스트를 사용 하 여 결과 코드는 사용자가 필요로 하는 대로 작동 하는지 확인 합니다. 코드 생성 되는 동일한 모델에서 테스트를 생성 하지 마십시오.  
  
 경우에 따라 테스트를 일반 모델에서 직접 수행할 수 있습니다. 예를 들어 웹 사이트의 모든 페이지 간 탐색을 통해 연결할 수 있는지 확인 하는 테스트를 작성할 수 있습니다.  
  
 사용자 지정 코드에 대 한 허용: partial 클래스를 생성 합니다.  
 또한 생성된 된 코드를 직접 기록 하는 코드에 대 한 허용 합니다. 코드 생성 체계에서 발생할 수 있는 모든 가능한 변형을 계정 수에 대 한 거의 하지 않습니다. 따라서를를 추가 하 여 생성된 된 코드 중 일부를 재정의할 하시면 됩니다. 여기서는 생성 된 자료는.NET 언어에서와 같은 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 또는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], 두 가지 전략은 특히 유용 합니다.  
  
-   생성 된 클래스를 부분 이어야 합니다. 따라서 생성된 된 코드에 콘텐츠를 추가할 수 있습니다.  
  
-   쌍으로 다른 클래스를 생성 합니다. 기본 클래스에는 생성 된 메서드 및 속성을 모두 포함 되어야 하 고 파생된 클래스는 생성자를 포함 해야 합니다. 따라서 직접 작성 된 코드를 생성된 된 메서드를 재정의할 수 있습니다.  
  
 XML과 같은 다른 생성 된 언어를 사용 하 여는 `<#@include#>` 지시문을 직접 작성 하 고 생성 된 콘텐츠의 간단한 조합을 확인 합니다. 보다 복잡 한 경우 직접 작성 된 모든 파일을 사용 하 여 생성 된 파일을 결합 하는 후 처리 단계를 작성 해야 합니다.  
  
 포함 파일 또는 런타임에 템플릿에 공통 자료를 이동 합니다.  
 사용 하 여 유사한 텍스트 블록 및 여러 서식 파일에서 코드를 다시 반복할 필요가 `<#@ include #>` 지시문입니다. 자세한 내용은 참조 [T4 Include 지시문](../modeling/t4-include-directive.md)합니다.  
  
 별도 프로젝트에 런타임 텍스트 템플릿을 빌드할 수도 수 있으며 다음 디자인 타임 템플릿을에서 호출할 수 있습니다. 이 위해 사용 하 여는 `<#@ assembly #>` 지시문 별도 프로젝트에 액세스할 수 있습니다. 예제를 보려면 [상속에 텍스트 "템플릿" Gareth Jones 블로그에서](http://go.microsoft.com/fwlink/?LinkId=208373)합니다.  
  
 큰 블록의 코드를 별도 어셈블리로 이동 하는 것이 좋습니다.  
 큰 코드 블록 및 클래스 기능 블록을 설정한 경우이 코드의 일부를 별도 프로젝트에 컴파일되는 메서드를 이동 유용할 수도 있습니다. 사용할 수는 `<#@ assembly #>` 지시문 코드 서식 파일에 액세스할 수 있습니다. 자세한 내용은 참조 [T4 Assembly 지시문](../modeling/t4-assembly-directive.md)합니다.  
  
 서식 파일을 상속할 수 있는 추상 클래스에 메서드를 넣을 수 있습니다. 추상 클래스에서 상속 해야 <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation?displayProperty=fullName>합니다. 자세한 내용은 참조 [T4 템플릿 지시문](../modeling/t4-template-directive.md)합니다.  
  
 구성 파일이 아닌 코드를 생성  
 변수 응용 프로그램을 작성 한 가지 방법은 구성 파일을 허용 하는 일반 프로그램 코드를 작성 하는 것입니다. 이런이 방식으로 작성 된 응용 프로그램은 매우 유연 하 고 응용 프로그램을 다시 작성 하지 않고는 비즈니스 요구 사항 변경 될 때 다시 구성할 수 있습니다. 그러나이 방법의 단점은 응용 프로그램 낮다는 것 보다 더 구체적인 응용 프로그램입니다. 또한 때문에 항상 가장 일반적인 형식을 처리 하는 프로그램 코드는를 읽고 유지 관리 하기가 더 어려워집니다 됩니다.  
  
 이와 반대로 변수 부분으로 이루어진 컴파일 전에 생성 된 응용 프로그램 강력한 형식일 수 있습니다. 따라서 소프트웨어의 부분을 훨씬 쉽고 안정적으로 직접 작성 된 코드를 작성 하 고 생성 된 프로그램과 통합할 수 있습니다.  
  
 코드 생성의 모든 이점을 가져오려면 구성 파일 대신 프로그램 코드를 생성 하려고 합니다.  
  
 코드 생성 폴더를 사용 하 여  
 서식 파일 및 생성 된 파일 이름이 프로젝트 폴더에 배치 **생성 된 코드**, 되도록 이러한 없는지 직접 편집 해야 하는 파일의 선택을 취소 합니다. 재정의 하거나 생성된 된 클래스에 추가 사용자 지정 코드를 만드는 경우 해당 클래스 라고 하는 폴더에 넣습니다 **사용자 지정 코드**합니다. 일반적인 프로젝트의 구조는 다음과 같습니다.  
  
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
  
## <a name="guidelines-for-run-time-preprocessed-t4-templates"></a>런타임에 전처리 된 T4 템플릿에 대 한 지침  
 공통 자료를 상속 된 템플릿으로 이동 합니다.  
 메서드 및 T4 텍스트 템플릿 간에 텍스트 블록을 공유 하려면 상속을 사용할 수 있습니다. 자세한 내용은 참조 [T4 템플릿 지시문](../modeling/t4-template-directive.md)합니다.  
  
 사용할 수도 있습니다 타임 템플릿 파일만 포함 됩니다.  
  
 Partial 클래스에 많은 양의 코드 본문을 이동 합니다.  
 각 런타임 템플릿은 템플릿와 동일한 이름을 가진 partial 클래스 정의 생성 합니다. 동일한 클래스의 다른 부분 정의 포함 하는 코드 파일을 작성할 수 있습니다. 이런이 방식으로 클래스에 메서드, 필드 및 생성자를 추가할 수 있습니다. 이러한 멤버는 서식 파일에서 코드 블록에서 호출할 수 있습니다.  
  
 이 작업의 장점은 IntelliSense를 사용할 수 있으므로 코드를 작성할 수입니다. 또한 프레젠테이션과 기본 논리 구분을 향상 시킬 수 있습니다.  
  
 예를 들어 **MyReportText.tt**:  
  
 `The total is: <#= ComputeTotal() #>`  
  
 **MyReportText Methods.cs**:  
  
 `private string ComputeTotal() { ... }`  
  
 사용자 지정 코드에 대 한 허용: 확장 지점을 제공  
 가상 메서드를 생성 하는 것이 좋습니다. \<#+ 클래스 기능 블록 #> 합니다. 이렇게 하면 단일 템플릿을 수정 하지 않고 여러 컨텍스트에서 사용할 수 있습니다. 서식 파일을 수정 하는 대신 최소 추가 논리를 제공 하는 파생된 클래스를 생성할 수 있습니다. 파생된 클래스 일반 코드 이거나 이거나 런타임에 템플릿을 수 있습니다.  
  
 예를 들어 MyStandardRunTimeTemplate.tt:  
  
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
  
## <a name="guidelines-for-all-t4-templates"></a>모든 T4 템플릿에 대 한 지침  
 텍스트 생성에서 별도 데이터 수집  
 계산 및 텍스트 블록을 혼합 하지 마십시오. 각 텍스트 템플릿에 사용 하 여 첫 번째 \<# 코드가 차단 #> 변수를 설정 하 고 복잡 한 계산을 수행할 합니다. 서식 파일 또는 첫 번째의 기본값은 첫 번째 텍스트 블록에서 \<#+ 클래스 기능 블록 #>, 긴 식을 하지 않도록 하 고 텍스트 블록을 포함 하지 않는 한 루프와 조건을 방지 합니다. 이 방법을 사용 하면 서식 파일 보다 쉽게 읽고 유지 관리할 수 있습니다.  
  
 사용 하지 않는 `.tt` 포함 파일  
 와 같은 다른 파일 이름 확장명을 사용 하 여 `.ttinclude` 포함 파일입니다. 사용 하 여 `.tt` 되도록 원하는 파일을 같이 런타임 또는 디자인 타임 텍스트 템플릿 처리에 대 한 유일한 합니다. 경우에 따라 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 인식 `.tt` 파일을 자동으로 처리를 위해 해당 속성을 설정 합니다.  
  
 고정 된 프로토타입으로 각 서식 파일을 시작 합니다.  
 생성 되 고이 정확한 지 확인 하려면 코드 또는 텍스트의 예를 작성 합니다. 그런 다음 해당 확장명.tt을 변경 하 고 증분 방식으로 모델을 참조 하 여 콘텐츠를 수정 하는 코드를 삽입 합니다.  
  
 형식화 된 모델을 사용 하는 것이 좋습니다.  
 모델에 대 한 XML 또는 데이터베이스 스키마를 만들 수 있지만 도메인 특정 언어 DSL ()을 만들 유용할 수도 있습니다. DSL는 스키마 및 속성의 특성을 나타내는 각 노드를 나타내는 클래스를 생성 하기 쉽습니다. 즉, 비즈니스 모델을 기준으로 프로그래밍할 수 있습니다. 예:  
  
```  
Team Members:  
<# foreach (Person p in team.Members)   
 { #>   
    <#= p.Name #>   
<# } #>  
```  
  
 모델에 대 한 다이어그램을 사용 하는 것이 좋습니다.  
 가장 효과적으로 많은 모델이 표시 하 고 매우 큰 경우에 특히 텍스트 테이블 처럼 간단 하 게 관리 됩니다.  
  
 그러나 일부 종류의 비즈니스 요구 사항에 대 한이 관계 및 작업 흐름의 복잡 한 집합을 명확 하 게 중요 및 다이어그램은 가장 적합 한 보통 합니다. 다이어그램의 이점은 사용자 및 기타 관련자와 쉽게 논의할 수 된다는 점입니다. 비즈니스 요구 사항 수준에서 모델에서 코드를 생성 하 여 하면 코드 보다 유연한 요구 사항이 변경 됩니다.  
  
 또한 도메인 특정 언어 (DSL)으로 고유 다이어그램 형식의 디자인할 수 있습니다. UML 및 Dsl 모두에서 코드를 생성할 수 있습니다. 자세한 내용은 참조 [분석 및 모델링 아키텍처](../modeling/analyze-and-model-your-architecture.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [T4 텍스트 템플릿을 사용하여 디자인 타임 코드 생성](../modeling/design-time-code-generation-by-using-t4-text-templates.md)   
 [T4 텍스트 템플릿을 사용하여 런타임 텍스트 생성](../modeling/run-time-text-generation-with-t4-text-templates.md)
