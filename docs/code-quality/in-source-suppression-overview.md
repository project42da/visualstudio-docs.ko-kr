---
title: "억제 (suppression) 개요에서 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source suppression, code analysis
- code analysis, source suppression
ms.assetid: f1a2dc6a-a9eb-408c-9078-2571e57d207d
caps.latest.revision: "40"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 92babbf3c7a5863d178463b69525bdb722bf28ad
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="in-source-suppression-overview"></a>ISS 개요
소스에서은 표시 하거나 추가 하 여 관리 코드에서 코드 분석 위반을 무시 하는 **SuppressMessage** 특성을 위반을 발생 시키는 코드 세그먼트입니다. **SuppressMessage** 컴파일 타임에 CODE_ANALYSIS 컴파일 기호가 정의 되어 있는 경우에 관리 코드 어셈블리의 IL 메타 데이터에 포함 된 조건부 특성입니다.  
  
 C++/CLI에서 CA_SUPPRESS_MESSAGE 또는 CA_GLOBAL_SUPPRESS_MESSAGE 매크로를 헤더 파일에 사용하여 특성을 추가합니다.  
  
 릴리스 빌드에 소스에서 메타 데이터를 실수로 전달 하지 않으려면 소스 비 표시 오류는 사용 하지 있습니다. 소스에서 처리 비용 때문에 소스에서 메타 데이터를 포함 하 여 대 응용 프로그램의 성능이 저하 될 수 있습니다.  
  
> [!NOTE]
>  않아도 손 코드 이러한 특성 직접 합니다. 자세한 내용은 참조 [하는 방법: 메뉴 항목을 사용 하 여 경고 표시 안 함](../code-quality/how-to-suppress-warnings-by-using-the-menu-item.md)합니다. 메뉴 항목의 c + + 코드에 대 한 공간이 없습니다.  
  
## <a name="suppressmessage-attribute"></a>SuppressMessage 특성  
 코드 분석 경고를 마우스 오른쪽 단추로 클릭할 때는 **오류 목록** 클릭 하 고 **메시지 표시 안 함**, **SuppressMessage** 특성이 코드 또는 추가 됩니다는 프로젝트의 전역 비 표시 오류 파일입니다.  
  
 **SuppressMessage** 특성 형식은 다음과 같습니다.  
  
```vb  
<Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")>  
```  
  
```csharp  
[Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")]  
  
```  
  
 [C++]  
  
```  
CA_SUPPRESS_MESSAGE("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")  
  
```  
  
 여기서  
  
-   **규칙 범주** -규칙이 정의 되어 있는 범주입니다. 코드 분석 규칙 범주에 대 한 자세한 내용은 참조 [관리 코드 경고에 대 한 코드 분석](../code-quality/code-analysis-for-managed-code-warnings.md)합니다.  
  
-   **규칙 Id** -규칙의 식별자입니다. 지원 규칙 식별자에 대 한 단기 및 장기 이름을 모두 포함 됩니다. 짧은 이름은 CAXXXX; 긴 이름은 CAXXXX:FriendlyTypeName입니다.  
  
-   **양쪽 맞춤** -메시지를 표시 하지 않기 위한 이유를 문서화 하는 데 사용 되는 텍스트입니다.  
  
-   **메시지 Id** -각 메시지에 대 한 문제의 고유 식별자입니다.  
  
-   **범위** -경고가 표시 되 고 대상입니다. 대상이 지정 되지 않은 경우 특성의 대상으로 설정 됩니다. 지원 되는 범위는 다음과 같습니다.  
  
    -   Module  
  
    -   네임스페이스  
  
    -   리소스  
  
    -   형식  
  
    -   멤버  
  
-   **대상** -경고가 표시 되 고 대상을 지정 하는 데 사용 하는 식별자입니다. 정식 항목 이름을 포함 해야 합니다.  
  
## <a name="suppressmessage-usage"></a>SuppressMessage 사용  
 있는 수준에서 코드 분석 경고는 표시 되지 않습니다.의 인스턴스는 **SuppressMessage** 특성은 적용 됩니다. 이 목적은 코드를 억제 (suppression) 정보를 위반이 발생 합니다.  
  
 일반적인 형태의 억제 (suppression) 규칙 범주와 선택적 사람이 읽을 수의 표현이 들어 있는 규칙 이름에 규칙 식별자를 포함 합니다. 예를 들어 개체에 적용된  
  
 `[SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]`  
  
 소스에서 메타 데이터 최소화 엄격한 성능상의 이유로 인 규칙 이름은 생략할 수 있습니다. 규칙 범주와 규칙 ID는 충분히 고유한 규칙 식별자를 구성 합니다. 예를 들어 개체에 적용된  
  
 `[SuppressMessage("Microsoft.Design", "CA1039")]`  
  
 이 형식은 유지 관리 문제 때문에 권장 되지 않습니다.  
  
## <a name="suppressing-multiple-violations-within-a-method-body"></a>메서드 본문 내에서 여러 위반을 억제합니다.  
 특성은 메서드에만 적용할 수 있으며 메서드 본문 안에 포함할 수 없습니다. 그러나을 위반 하 게 메서드 내에서 여러 항목을 구분 하기 위해 메시지 ID로의 식별자를 지정할 수 있습니다.  
  
 [!code-cpp[InSourceSuppression#1](../code-quality/codesnippet/CPP/in-source-suppression-overview_1.cpp)]
 [!code-vb[InSourceSuppression#1](../code-quality/codesnippet/VisualBasic/in-source-suppression-overview_1.vb)]
 [!code-csharp[InSourceSuppression#1](../code-quality/codesnippet/CSharp/in-source-suppression-overview_1.cs)]  
  
## <a name="generated-code"></a>생성된 코드  
 관리 코드 컴파일러 및 일부 타사 도구에는 코드를 빠르게 개발을 용이 하 게 하려면 코드를 생성 합니다. 소스 파일에 표시 되는 컴파일러에서 생성 된 코드는 일반적으로 기본적으로 **GeneratedCodeAttribute** 특성입니다.  
  
 코드 분석 경고 및 생성 된 코드에 대 한 오류를 표시 하지 않을 것인지를 선택할 수 있습니다. 이러한 경고 및 오류를 표시 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 생성 된 코드에 대 한 경고 표시 안 함](../code-quality/how-to-suppress-code-analysis-warnings-for-generated-code.md)합니다.  
  
 코드 분석에서 무시 참고 **GeneratedCodeAttribute** 전체 어셈블리 또는 단일 매개 변수 중 하나에 적용 된 경우. 이러한 경우는 거의 발생 합니다.  
  
## <a name="global-level-suppressions"></a>전역 수준 비 표시 오류  
 관리 코드 분석 도구는 검사 **SuppressMessage** 어셈블리, 모듈, 형식, 멤버 또는 매개 변수 수준에서 적용 되는 특성입니다. 리소스와 네임 스페이스에 대해 위반을 발생 시킵니다. 이러한 위반의 전역 수준에서 적용 해야 하 고 범위가 한정 되 고 대상으로 합니다. 예를 들어 다음과 같은 메시지가 표시는 네임 스페이스 위반을 하지 않습니다.  
  
 `[module: SuppressMessage("Microsoft.Design", "CA1020:AvoidNamespacesWithFewTypes", Scope = "namespace", Target = "MyNamespace")]`  
  
> [!NOTE]
>  네임 스페이스 범위와 함께 경고를 표시 하지 않는 네임 스페이스 자체에 대 한 경고를 표시 하지 않습니다. 네임 스페이스 내의 형식에 대 한 경고를 숨기지는 않습니다.  
  
 모든 비 표시 오류는 명시적 범위를 지정 하 여 표현할 수 있습니다. 이러한 비 표시이 오류는 전역 수준에서 활성화 되어야 합니다. 형식을 데코레이팅하여 구성원 수준 억제 (suppression)를 지정할 수 없습니다.  
  
 Global 수준 비 표시 오류는를 명시적으로 제공 되는 사용자 소스에 매핑되지 않는 컴파일러에서 생성 된 코드를 참조 하는 메시지를 표시 하지 않는 유일한 방법입니다. 예를 들어 다음 코드는 컴파일러에서 내보낸 생성자에 대 한 위반을 표시 하지 않습니다.  
  
 `[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="Microsoft.Tools.FxCop.Type..ctor()")]`  
  
> [!NOTE]
>  대상에는 항상 정규화 된 항목 이름을 포함합니다.  
  
## <a name="global-suppression-file"></a>전역 억제 (suppression) 파일  
 전역 비 표시 오류 파일은 전역 수준 비 표시 오류 또는 대상을 지정 하지 않는 비 표시 오류 중 하나인 비 표시 오류를 유지 관리 합니다. 예를 들어 어셈블리 수준 위반에 대해가이 파일에 저장 됩니다. 또한 일부 ASP.NET 비 표시 오류 프로젝트 수준 설정을 뒤 폼 코드에 사용할 수 없기 때문에이 파일에 저장 됩니다. 전역 비 표시를 만들고 선택 하는 처음으로 프로젝트에 추가 **프로젝트 억제 (suppression) 파일에** 의 옵션은 **메시지 표시 안 함** 오류 목록 창에 명령 합니다. 자세한 내용은 참조 [하는 방법: 메뉴 항목을 사용 하 여 경고 표시 안 함](../code-quality/how-to-suppress-warnings-by-using-the-menu-item.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Diagnostics.CodeAnalysis>