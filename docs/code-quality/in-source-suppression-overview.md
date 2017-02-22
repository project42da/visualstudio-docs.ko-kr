---
title: "ISS 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 비표시 오류(Suppression), 코드 분석"
  - "코드 분석, 소스 비표시 오류(Suppression)"
ms.assetid: f1a2dc6a-a9eb-408c-9078-2571e57d207d
caps.latest.revision: 40
caps.handback.revision: 40
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ISS 개요
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

ISS\(In Source Suppression\)는 위반을 초래하는 코드 세그먼트에 **SuppressMessage** 특성을 추가하여 관리 코드의 코드 분석 위반 내용을 표시하지 않거나 무시하는 기능입니다.  **SuppressMessage** 특성은 조건부 특성으로, 컴파일할 때 CODE\_ANALYSIS 컴파일 기호를 정의한 경우에만 관리 코드 어셈블리의 IL 메타데이터에 포함됩니다.  
  
 C\+\+\/CLI에서 헤더 파일에서 CA\_SUPPRESS\_MESSAGE 또는 CA\_GLOBAL\_SUPPRESS\_MESSAGE 매크로를 특성을 추가합니다.  
  
 ISS\(In Source Suppression\) 메타데이터가 실수로 포함되지 않도록 하려면 릴리스 빌드에는 ISS를 사용하지 않아야 합니다.  ISS 메타데이터가 포함되면 처리하는 데는 많은 리소스가 필요하므로 응용 프로그램의 성능도 저하될 수 있습니다.  
  
> [!NOTE]
>  이러한 특성을 직접 코드로 작성할 필요는 없습니다.  자세한 내용은 [방법: 메뉴 항목을 사용하여 경고 표시 안 함](../code-quality/how-to-suppress-warnings-by-using-the-menu-item.md)을 참조하십시오.  C\+\+ 코드에 메뉴 항목을 사용할 수 없습니다.  
  
## SuppressMessage 특성  
 **오류 목록**에서 코드 분석 경고를 마우스 오른쪽 단추로 클릭하고 **메시지 표시 안 함**을 클릭하면 코드나 프로젝트의 전역 비표시 오류 파일에 **SuppressMessage** 특성이 추가됩니다.  
  
 **SuppressMessage** 특성은 다음과 같은 형식으로 구성됩니다.  
  
```vb  
<Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")>  
```  
  
```c#  
[Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")]  
  
```  
  
 \[C\+\+\]  
  
```  
CA_SUPPRESS_MESSAGE("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")  
  
```  
  
 다음은 각 항목에 대한 설명입니다.  
  
-   **Rule Category** \- 규칙이 정의된 범주입니다.  코드 분석 규칙 범주에 대한 자세한 내용은 [관리 코드 경고에 대한 코드 분석](../code-quality/code-analysis-for-managed-code-warnings.md)을 참조하십시오.  
  
-   **Rule Id** \- 규칙의 식별자입니다.  규칙 식별자에는 짧은 이름과 긴 이름을 모두 사용할 수 있습니다.  짧은 이름은 CAXXXX이고, 긴 이름은 CAXXXX:FriendlyTypeName입니다.  
  
-   **Justification** \- 메시지를 표시하지 않는 이유를 설명하는 데 사용되는 텍스트입니다.  
  
-   **Message Id** \- 각 메시지에 대한 문제를 나타내는 고유한 식별자입니다.  
  
-   **Scope** \- 경고가 표시되지 않는 대상입니다.  대상을 지정하지 않으면 특성의 대상으로 설정됩니다.  지원되는 범위는 다음과 같습니다.  
  
    -   Module  
  
    -   네임스페이스  
  
    -   리소스  
  
    -   형식  
  
    -   멤버  
  
-   **Target** \- 경고가 표시되지 않는 대상을 지정하는 데 사용되는 식별자입니다.  정규화된 항목 이름을 포함해야 합니다.  
  
## SuppressMessage 사용  
 **SuppressMessage** 특성의 인스턴스가 적용되는 수준에서 코드 분석 경고는 표시되지 않습니다.  이 특성은 위반이 발생하는 코드에 비표시 오류 정보를 연결하기 위한 것입니다.  
  
 일반적인 형식의 비표시 오류\(Suppression\)에는 규칙 범주 및 규칙 이름을 읽기 쉽게 나타낸 선택적 표현이 포함된 규칙 ID가 포함됩니다.  예를 들면 다음과 같습니다.  
  
 `[SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]`  
  
 ISS 메타데이터를 최소화해야 할 확실한 성능상의 이유가 있다면 규칙 이름은 생략할 수 있습니다.  규칙 범주와 규칙 ID만으로도 충분히 고유한 규칙 식별자가 만들어집니다.  예를 들면 다음과 같습니다.  
  
 `[SuppressMessage("Microsoft.Design", "CA1039")]`  
  
 유지 관리 편의성 문제로 인해 이 형식은 사용하지 않는 것이 좋습니다.  
  
## 메서드 본문에서 여러 위반 표시하지 않기  
 특성은 메서드에만 적용할 수 있으며 메서드 본문에는 포함할 수 없습니다.  그러나 식별자를 메시지 ID로 지정하여 메서드 내에서 발생하는 여러 위반을 구별할 수 있습니다.  
  
 [!code-cpp[InSourceSuppression#1](../code-quality/codesnippet/CPP/in-source-suppression-overview_1.cpp)]
 [!code-vb[InSourceSuppression#1](../code-quality/codesnippet/VisualBasic/in-source-suppression-overview_1.vb)]
 [!code-cs[InSourceSuppression#1](../code-quality/codesnippet/CSharp/in-source-suppression-overview_1.cs)]  
  
## 생성된 코드  
 관리 코드 컴파일러와 일부 타사 도구에서는 코드 개발 속도를 향상시키기 위해 코드를 생성합니다.  컴파일러에서 생성된 코드는 소스 파일에서 보통 **GeneratedCodeAttribute** 특성으로 표시됩니다.  
  
 생성된 코드에 대한 코드 분석 경고 및 오류를 표시하지 않도록 선택할 수 있습니다.  이러한 경고 및 오류를 표시하지 않는 방법에 대한 자세한 내용은 [방법: 생성된 코드에 대한 경고 표시 안 함](../code-quality/how-to-suppress-code-analysis-warnings-for-generated-code.md)을 참조하십시오.  
  
 **GeneratedCodeAttribute**를 전체 어셈블리나 하나의 매개 변수에 적용하면 코드 분석에서 이를 무시합니다.  이러한 상황은 거의 발생하지 않습니다.  
  
## 전역 수준 비표시 오류  
 관리 코드 분석 도구에서는 어셈블리, 모듈, 형식, 멤버 또는 매개 변수 수준에서 적용되는 **SuppressMessage** 특성을 검사하며,  리소스와 네임스페이스에 대해 위반을 발생시킵니다.  이러한 위반은 전역 수준에서 적용해야 하며 범위와 대상을 지정해야 합니다.  예를 들어, 다음 메시지는 네임스페이스 위반을 표시하지 않습니다.  
  
 `[module: SuppressMessage("Microsoft.Design", "CA1020:AvoidNamespacesWithFewTypes", Scope = "namespace", Target = "MyNamespace")]`  
  
> [!NOTE]
>  네임스페이스 범위가 지정된 경고를 표시하지 않도록 하면 네임스페이스 자체에 대한 경고는 표시되지 않습니다.  그러나 네임스페이스 내의 형식에 대한 경고는 표시됩니다.  
  
 모든 비표시 오류는 명시적 범위를 지정하여 나타낼 수 있습니다.  이러한 비표시 오류는 전역 수준에 있어야 합니다.  형식을 데코레이팅하여 멤버 수준 비표시 오류를 지정할 수는 없습니다.  
  
 명시적으로 제공되는 사용자 소스에 매핑되지 않는 컴파일러 생성 코드 참조 메시지를 표시하지 않기 위한 유일한 방법은 전역 수준 비표시 오류를 사용하는 것입니다.  예를 들어, 다음 코드에서는 컴파일러에서 내보낸 생성자에 대한 위반을 표시하지 않습니다.  
  
 `[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="Microsoft.Tools.FxCop.Type..ctor()")]`  
  
> [!NOTE]
>  대상에는 항상 정규화된 항목 이름이 포함됩니다.  
  
## 전역 비표시 오류 파일  
 전역 비표시 오류 파일에는 전역 수준 비표시 오류나 대상이 지정되지 않은 비표시 오류가 저장됩니다.  예를 들어, 어셈블리 수준의 비표시 오류 위반이 이 파일에 저장됩니다.  또한 양식에 숨겨진 코드에는 프로젝트 수준 설정을 사용할 수 없으므로 일부 ASP.NET 비표시 오류도 이 파일에 저장됩니다.  오류 목록 창에서 **메시지 표시 안함** 명령의 **프로젝트 비표시 오류\(Suppression\) 파일**을 처음 선택하면 전역 비표시 오류가 생성되어 프로젝트에 추가됩니다.  자세한 내용은 [방법: 메뉴 항목을 사용하여 경고 표시 안 함](../code-quality/how-to-suppress-warnings-by-using-the-menu-item.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Diagnostics.CodeAnalysis>