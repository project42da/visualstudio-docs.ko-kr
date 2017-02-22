---
title: "도메인 속성의 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도메인별 언어, 도메인 속성"
ms.assetid: a9471562-d6f2-46bf-9872-e0d66ba03150
caps.latest.revision: 24
caps.handback.revision: 24
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 도메인 속성의 속성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

*도메인 속성*은 값을 포함할 수 있는 모델 요소의 기능입니다.  예를 들어 `Person` 도메인 클래스는 `Name` 및 `BirthDate` 속성을 포함할 수 있습니다.  DSL 정의에서 도메인 속성은 다이어그램의 도메인 클래스 상자와 DSL 탐색기의 도메인 클래스 아래에 나열됩니다.  자세한 내용은 [도메인별 언어 정의 방법](../modeling/how-to-define-a-domain-specific-language.md)을 참조하십시오.  
  
> [!NOTE]
>  "속성"이라는 단어는 두 가지 용도로 사용됩니다.  *도메인 속성*은 도메인 클래스에 대해 정의하는 기능입니다.  반면 DSL의 요소는 대부분 DSL 정의의 *속성* 창에 나열되는 **속성**을 포함합니다.  예를 들어 모든 도메인 속성에는 이 항목에서 설명하는 속성 집합이 포함됩니다.  
  
 런타임에 사용자가 도메인 클래스 인스턴스를 만들면 도메인 속성의 값을 속성 창에서 확인할 수 있으며 모양에 표시할 수 있습니다.  
  
 대부분의 도메인 속성은 일반 CLR 속성으로 구현됩니다.  그러나 프로그래밍 측면에서 도메인 속성은 일반 프로그램 속성보다 많은 기능을 포함합니다.  
  
-   속성 상태를 모니터링하는 규칙과 이벤트를 정의할 수 있습니다.  자세한 내용은 [변경 내용에 대한 대응 및 전파](../modeling/responding-to-and-propagating-changes.md)을 참조하십시오.  
  
-   트랜잭션을 통해 상태 불일치를 방지할 수 있습니다.  자세한 내용은 [프로그램 코드에서 모델 탐색 및 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)을 참조하십시오.  
  
 다이어그램 또는 DSL 탐색기에서 도메인 속성을 선택하면 속성 창에서 다음 항목을 확인할 수 있습니다.  이러한 항목을 사용하는 방법에 대한 자세한 내용은 [도메인별 언어 사용자 지정 및 확장](../modeling/customizing-and-extending-a-domain-specific-language.md)을 참조하세요.  
  
|속성|설명|기본값|  
|--------|--------|---------|  
|**설명**|생성된 디자이너의 UI\(사용자 인터페이스\)를 문서화하는 데 사용되는 설명입니다.|\<none\>|  
|**표시 이름**|이 도메인 속성에 대해 생성된 디자이너에 표시되는 이름입니다.  "Song Title"과 같이 공백과 문장 부호를 포함할 수 있습니다.|\<none\>|  
|**Element Name Provider**|`Is Element Name`을 `true`로 설정한 경우에만 해당됩니다.  도메인 클래스의 새 요소에 대해 이름을 제공하는 코드를 작성하여 기본 동작을 재정의할 수 있습니다.<br /><br /> DSL 프로젝트의 코드 파일에서 <xref:Microsoft.VisualStudio.Modeling.ElementNameProvider>로부터 파생되는 클래스를 만듭니다.<br /><br /> 그런 다음 DSL 탐색기에서 DSL 루트를 마우스 오른쪽 단추로 클릭하고 외부 형식 추가를 클릭합니다.  클래스의 이름을 입력합니다.<br /><br /> 이 도메인 속성을 다시 선택하고 드롭다운 목록에서 클래스 이름을 선택합니다.|\<none\>|  
|**Getter Access Modifier**|도메인 클래스의 액세스 수준입니다\(`public` 또는 `internal`\).  이 속성은 프로그램 코드가 속성에 액세스할 수 있는 범위를 제어합니다.|`public`|  
|**Help Keyword**|이 도메인 속성에 대해 F1 도움말을 인덱싱하는 데 사용되는 선택적 키워드입니다.|\<none\>|  
|**Is Browsable**|`True`이면 이 DSL의 모델을 열 때 사용자에 대해 속성 창에 도메인 속성이 표시됩니다.<br /><br /> `False`이면 UI에서 도메인 속성이 숨겨집니다.<br /><br /> 도메인 속성을 읽기 전용으로 표시하려면 **Is UI Read Only**를 설정합니다.|`True`|  
|**Is Element Name**|`True`인 경우 이 도메인 속성은 DSL 탐색기에서 모델 요소의 이름으로 표시됩니다.<br /><br /> 새 모델 요소는 이 속성의 고유한 기본값을 받게 됩니다.  이러한 값이 생성되는 방식을 제어하려면 **Element Name Provider**를 설정합니다.|`False`|  
|**Is UI Read Only**|`True`이면 UI를 사용하여 도메인 속성 값을 변경할 수 없습니다.  그러나 프로그램에서는 값을 계속 설정할 수 있으며 설정된 값은 속성 창에 표시됩니다.<br /><br /> 사용자가 볼 수 없도록 도메인 속성을 숨기려면 **Is Browsable**을 설정합니다.  프로그램의 액세스를 제어하려면 **Setter Access Modifier**를 설정합니다.|`False`|  
|**Kind**|도메인 속성의 종류입니다\(`Normal`, `Calculated`, `CustomStorage`\).  자세한 내용은 [계산 및 사용자 지정 저장소 속성](../modeling/calculated-and-custom-storage-properties.md)을 참조하십시오.|`Normal`|  
|**이름**|이 도메인 속성의 이름입니다.  SongTitle과 같은 유효한 식별자여야 합니다.|\<none\>|  
|**참고**|이 도메인 속성과 관련된 비공식적인 참고 사항입니다.|\<none\>|  
|**Setter Access Modifier**|setter의 액세스 한정자입니다.  이 속성은 프로그램 코드가 속성을 설정할 수 있는 범위를 제어합니다.|`public`|  
|**형식**|속성의 형식입니다.  사용 가능한 형식 목록에 추가하려면 DSL 탐색기에서 DSL 루트를 마우스 오른쪽 단추로 클릭하고 **외부 형식 추가**를 클릭합니다.|`String`|  
  
## 참고 항목  
 [Domain\-Specific Language Tools Glossary](http://msdn.microsoft.com/ko-kr/ca5e84cb-a315-465c-be24-76aa3df276aa)