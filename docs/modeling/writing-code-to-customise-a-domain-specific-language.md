---
title: "도메인 특정 언어를 사용자 지정 하는 코드를 작성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, programming
ms.assetid: a4a17f5b-9c97-4575-b2d1-3182c1896b72
caps.latest.revision: "29"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 2d456f84078e54694deb11fda0082ac40d278dd2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="writing-code-to-customise-a-domain-specific-language"></a>도메인별 언어를 사용자 지정하는 코드 작성
이 섹션을 액세스, 수정 또는 도메인 특정 언어에 모델을 만들 사용자 지정 코드를 사용 하는 방법을 보여 줍니다.  
  
 DSL을 사용 하는 코드를 작성할 수 있는 몇 가지 컨텍스트 가지가 있습니다.  
  
-   **사용자 지정 명령입니다.** 사용자가 다이어그램을 마우스 오른쪽 단추로 클릭 하 여 호출할 수 및 모델을 수정할 수 있는 명령을 만들 수 있습니다. 자세한 내용은 참조 [하는 방법: 바로 가기 메뉴에 명령을 추가](../modeling/how-to-add-a-command-to-the-shortcut-menu.md)합니다.  
  
-   **유효성 검사 합니다.** 모델 올바른 상태 인지 확인 하는 코드를 작성할 수 있습니다. 자세한 내용은 참조 [도메인 특정 언어의 유효성 검사](../modeling/validation-in-a-domain-specific-language.md)합니다.  
  
-   **기본 동작을 재정의 합니다.** DslDefinition.dsl에서 생성 되는 코드의 여러 측면을 수정할 수 있습니다. 자세한 내용은 참조 [재정의 및 생성 된 클래스를 확장](../modeling/overriding-and-extending-the-generated-classes.md)합니다.  
  
-   **텍스트 변환 합니다.** 모델에 액세스 하 고 예를 들어 프로그램 코드를 생성 하는 텍스트 파일을 생성 하는 코드를 포함 하는 텍스트 템플릿을 작성할 수 있습니다. 자세한 내용은 참조 [도메인 특정 언어에서 코드 생성](../modeling/generating-code-from-a-domain-specific-language.md)합니다.  
  
-   **다른 Visual Studio 확장명입니다.** 읽기 및 모델을 수정 하는 별도 VSIX 확장을 작성할 수 있습니다. 자세한 내용은 참조 [하는 방법: 프로그램 코드 파일에서 모델 열기](../modeling/how-to-open-a-model-from-file-in-program-code.md)  
  
 DslDefinition.dsl에서 정의 하는 클래스의 인스턴스 라는 데이터 구조에 유지 되는 *메모리 내 저장소* (IMS) 또는 *저장소*합니다. 항상 DSL에서 정의 하는 클래스 생성자에 인수로으로 저장소를 사용 합니다. 예를 들어 DSL 예제 라는 클래스를 정의 하는 경우:  
  
 `Example element = new Example (theStore);`  
  
 여러 가지 이점을 제공 개체 (대신 방금 같이 일반적인 개체) 저장소에 유지 합니다.  
  
-   **트랜잭션을**합니다. 일련의 관련된 변경 내용 트랜잭션으로 그룹화 할 수 있습니다.  
  
     `using (Transaction t = store.TransactionManager.BeginTransaction("updates"))`  
  
     `{`  
  
     `// make several changes to Store elements here`  
  
     `t.Commit();`  
  
     `}`  
  
     변경 하는 동안 예외가 발생 하는 최종 commit ()가 수행 되지 않습니다는 저장소를 이전 상태로 다시 설정 됩니다. 이 오류 형태로 두지 마십시오 모델 일관성이 없는 상태에 있는지 확인 하도록 도와줍니다. 자세한 내용은 참조 [탐색 및 프로그램 코드에서 모델 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)합니다.  
  
-   **이진 관계**합니다. 두 클래스 간의 관계를 정의 하는 경우 양쪽 끝에서 인스턴스는 다른 쪽 끝으로 이동 하는 속성을 가집니다. 양쪽 항상 동기화 됩니다. 예를 들어, 부모 및 자식 라는 역할과 parenthood 관계를 정의 하는 경우 작성할 수 있습니다.  
  
     `John.Children.Add(Mary)`  
  
     다음 식은 모두 이제:  
  
     `John.Children.Contains(Mary)`  
  
     `Mary.Parents.Contains(John)`  
  
     작성 하 여 동일한 결과 얻을 수 있습니다.  
  
     `Mary.Parents.Add(John)`  
  
     자세한 내용은 참조 [탐색 및 프로그램 코드에서 모델 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)합니다.  
  
-   **규칙 및 이벤트**합니다. 지정 된 변경 될 때마다 발생 하는 규칙을 정의할 수 있습니다. 예를 들어 규칙을 표시 하는 동일한 모델 요소를 최신 상태로 다이어그램에서 셰이프를 유지 하는 데 사용 됩니다. 자세한 내용은 참조 [에 대응 하 고 변경 내용을 전파](../modeling/responding-to-and-propagating-changes.md)합니다.  
  
-   **Serialization**합니다. 저장소 파일에 포함 된 개체를 serialize 하는 표준 방법을 제공 합니다. 직렬화 및 역직렬화에 대 한 규칙을 사용자 지정할 수 있습니다. 자세한 내용은 참조 [사용자 지정 파일 저장소 및 XML Serialization](../modeling/customizing-file-storage-and-xml-serialization.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [도메인별 언어 사용자 지정 및 확장](../modeling/customizing-and-extending-a-domain-specific-language.md)