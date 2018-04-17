---
title: 재정의 및 생성 된 클래스를 확장 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, providing overridable classes
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 80dd80a88b0244008efde9b10a1706ff18ba6136
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="overriding-and-extending-the-generated-classes"></a>생성된 클래스 재정의 및 확장
DSL 정의 플랫폼 도구 도메인 특정 언어를 기반으로 하는 강력한 집합을 작성할 수 있습니다. 재정의 하 고 DSL 정의에서 생성 되는 클래스를 확장 하 여 확장 하 고 조정 작업을 만들 수 있습니다. 이러한 클래스 DSL 정의 다이어그램에 명시적으로 정의 된 도메인 클래스 뿐 아니라 뿐만 아니라 도구 상자, 탐색기, serialization 및 등을 정의 하는 다른 클래스를 포함 합니다.  
  
## <a name="extensibility-mechanisms"></a>확장 메커니즘  
 몇 가지 메커니즘은 생성 된 코드를 확장할 수 있도록 제공 됩니다.  
  
### <a name="overriding-methods-in-a-partial-class"></a>Partial 클래스에서 메서드를 재정의  
 Partial 클래스 정의 둘 이상의 위치에 정의 해야 하는 클래스를 사용 합니다. 이 옵션을 사용 하면 사용자가 직접 작성 하는 코드에서 생성된 된 코드를 구분할 수 있습니다. 수동으로 작성 된 코드에서 생성된 된 코드에서 상속 된 클래스를 재정의할 수 있습니다.  
  
 예를 들어 라는 도메인 클래스 DSL 정의에서 정의 하는 경우 `Book`, 재정의 메서드를 추가 하는 사용자 지정 코드를 작성할 수 있습니다.  
  
 `public partial class Book`  
  
 `{`  
  
 `protected override void OnDeleting()`  
  
 `{`  
  
 `MessageBox.Show("Deleting book " + this.Title);`  
  
 `base.OnDeleting();`  
  
 `} }`  
  
> [!NOTE]
>  생성된 된 클래스의 메서드를 재정의 하려면 항상 생성된 된 파일에서 분리 된 파일에 코드를 작성 합니다. 일반적으로 파일 CustomCode 명명 된 폴더에 포함 되어 있습니다. 생성 된 코드를 변경할 경우 DSL 정의에서 코드를 다시 생성 하면 손실 됩니다.  
  
 방법을 재정의할 수를 검색 하려면 입력 **재정의** 클래스에서 뒤에 공백이 있습니다. IntelliSense 도구 설명 열에 표시 하는 방법을 재정의할 수 있습니다.  
  
### <a name="double-derived-classes"></a>이중 파생 클래스  
 대부분의 메서드는 생성 된 클래스에는 고정된 된 집합의 모델링 네임 스페이스의 클래스에서 상속 됩니다. 그러나 일부 메서드는 생성된 된 코드에 정의 됩니다. 일반적으로, 즉 재정의할 수 없습니다. 메서드는 동일한 클래스의 다른 부분 정의에 정의 되어 있는 한 partial 클래스에 재정의할 수 없습니다.  
  
 그럼에도 불구 하 고 설정 하 여 이러한 메서드를 재정의할 수 있습니다는 **Double 파생 생성** 도메인 클래스에 대 한 플래그입니다. 이 원인 두 개의 클래스를 생성, 다른의 추상 기본 클래스 중 하나입니다. 모든 메서드 및 속성 정의 기본 클래스를 파생된 클래스에서 생성자만 합니다.  
  
 예를 들어 Library.dsl, 샘플에에서는 `CirculationBook` 도메인 클래스에는 `Generates``Double Derived` 속성이로 설정 `true`합니다. 해당 도메인 클래스에 대해 생성 된 코드는 두 개의 클래스가 포함 되어 있습니다.  
  
-   `CirculationBookBase`추상 변수가 모든 메서드 및 속성을 포함 하 고 있습니다.  
  
-   `CirculationBook`에서 파생 된 `CirculationBookBase`합니다. 해당 생성자를 제외 하 고 비어 있습니다.  
  
 모든 메서드를 재정의 하려면 등 작성 하는 파생된 클래스의 부분 정의 `CirculationBook`합니다. 생성 된 메서드와 모델링 프레임 워크에서 상속 된 메서드를 재정의할 수 있습니다.  
  
 이 메서드는 모든 종류의 모델 요소, 관계, 셰이프, 다이어그램 및 커넥터를 비롯 하 여 요소를 사용할 수 있습니다. 생성 된 다른 클래스의 메서드를 재정의할 수 있습니다. 일부는 ToolboxHelper 더블 파생은 항상 같은 클래스를 생성 합니다.  
  
### <a name="custom-constructors"></a>사용자 지정 생성자  
 생성자를 재정의할 수 없습니다. 이중 파생 클래스에도 생성자는 파생된 클래스에 있어야 합니다.  
  
 직접 생성자를 제공 하려는 경우 이렇게 하려면 설정 하 여 `Has Custom Constructor` DSL 정의의 도메인 클래스에 대 한 합니다. 클릭할 때 **모든 템플릿 변형**, 생성된 된 코드는 해당 클래스에 대 한 생성자를 포함 하지 것입니다. 누락 된 생성자를 호출을 포함 됩니다. 그러면 오류 보고서 솔루션을 빌드할 경우. 오류를 보려면 보고서를 제공 해야 설명 하는 생성된 된 코드에서 주석을 두 번 클릭 합니다.  
  
 Partial 클래스 정의 생성 된 파일을 별개의 파일에 작성 하 고 생성자를 제공 합니다.  
  
### <a name="flagged-extension-points"></a>플래그가 지정 된 확장 지점  
 플래그가 지정 된 확장 지점에 속성이 나 사용자 지정 방법을 제공한 나타내기 위해 확인란을 설정할 수 있는 DSL 정의의 자리입니다. 사용자 지정 생성자는 한 가지 예입니다. 다른 예로 설정은 `Kind` 계산 또는 사용자 지정 저장소 설정을 도메인 속성의는 **사용자 지정은** 연결 작성기에 대 한 플래그입니다.  
  
 플래그를 설정 하 고 코드를 다시 생성 하는 경우에 각각의 경우에서 빌드 오류가 발생 합니다. 오류 설명을 제공 해야 하는 참조를 두 번 클릭 합니다.  
  
### <a name="rules"></a>규칙  
 트랜잭션 관리자를 사용 하는 지정 된 이벤트 발생의 속성 변경과 같은 트랜잭션의 종료 되기 전에 실행 되는 규칙을 정의할 수 있습니다. 규칙은 저장소에 다양 한 요소 간의 synchronism 유지 하기 위해 일반적으로 사용 됩니다. 예를 들어 규칙이 다이어그램 모델의 현재 상태를 표시 하는지 확인에 사용 됩니다.  
  
 규칙 클래스 별로에 정의 된, 각 개체에 대 한 규칙을 등록 하는 코드를 보유 하지 않습니다. 자세한 내용은 참조 [규칙 전파 변경 내에서 모델](../modeling/rules-propagate-changes-within-the-model.md)합니다.  
  
### <a name="store-events"></a>이벤트 저장  
 모델링 저장소의 속성 값을 변경, 요소 추가 및 삭제를 비롯 한 스토어에 대 한 변경은 특정 형식에 대 한 수신 대기 하도록 사용할 수 있으며 등 하는 이벤트 메커니즘을 제공 합니다. 이벤트 처리기는 변경이 수행 된 트랜잭션 종료 후 호출 됩니다. 일반적으로 이러한 이벤트는 외부 저장소 리소스를 업데이트 하는 데 사용 됩니다.  
  
### <a name="net-events"></a>.NET 이벤트  
 도형에 일부 이벤트를 구독할 수 있습니다. 예를 들어 셰이프의 마우스 클릭을 수신할 수 있습니다. 각 개체에 대 한 이벤트를 구독 하는 코드를 작성 해야 합니다. InitializeInstanceResources()의 재정의에이 코드를 작성할 수 있습니다.  
  
 일부 이벤트 셰이프에 데코레이터를 그리는 데 사용 되는 ShapeFields에 생성 됩니다. 예를 들어 참조 [하는 방법: 도형 또는 Decorator 클릭 가로채기](../modeling/how-to-intercept-a-click-on-a-shape-or-decorator.md)합니다.  
  
 이러한 이벤트는 일반적으로 트랜잭션 내 없고 합니다. 저장소에서 변경 하려는 경우 트랜잭션을 만들어야 합니다.