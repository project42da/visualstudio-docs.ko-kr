---
title: "도메인별 언어 사용자 지정 하는 코드 작성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도메인별 언어 프로그래밍"
ms.assetid: a4a17f5b-9c97-4575-b2d1-3182c1896b72
caps.latest.revision: 29
caps.handback.revision: 29
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 도메인별 언어 사용자 지정 하는 코드 작성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 섹션에서는 사용자 지정 코드에 액세스, 수정 또는 도메인\-특정 언어에서 모델 만들기를 사용 하는 방법을 보여 줍니다.  
  
 여러 컨텍스트 DSL로 작동 하는 코드를 작성할 수 있습니다.  
  
-   **사용자 지정 명령입니다.** 다이어그램에서 마우스 오른쪽 단추로 클릭 하 여 사용자를 호출할 수 있습니다 한 모델을 수정할 수 있는 명령을 만들 수 있습니다.  자세한 내용은 [방법: 바로 가기 메뉴에 명령 추가](../Topic/How%20to:%20Add%20a%20Command%20to%20the%20Shortcut%20Menu.md)를 참조하십시오.  
  
-   **유효성을 검사 합니다.** 모델을 올바른 상태 인지 확인 하는 코드를 작성할 수 있습니다.  자세한 내용은 [도메인별 언어에서 유효성 검사](../modeling/validation-in-a-domain-specific-language.md)를 참조하십시오.  
  
-   **기본 동작을 재정의 합니다.** Dsldefinition.dsl에서 생성 된 코드의 많은 부분을 수정할 수 있습니다.  자세한 내용은 [생성된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)를 참조하십시오.  
  
-   **텍스트 변환 합니다.** 모델에 액세스 하 고, 예를 들어 프로그램 코드를 생성 하려면 텍스트 파일을 생성 하는 코드를 포함 하는 텍스트 서식 파일을 작성할 수 있습니다.  자세한 내용은 [도메인별 언어에서 코드 생성](../modeling/generating-code-from-a-domain-specific-language.md)를 참조하십시오.  
  
-   **다른 Visual Studio 확장 합니다.** 읽고 모델 수정 별도 VSIX 확장을 작성할 수 있습니다.  자세한 내용은 [방법: 프로그램 코드로 파일에서 모델 열기](../modeling/how-to-open-a-model-from-file-in-program-code.md)를 참조하십시오.  
  
 보관 이라는 데이터 구조에서 Dsldefinition.dsl에 정의 된 클래스의 인스턴스는  *메모리 저장소* \(IMS\) 또는  *저장소*.  항상 DSL에 정의 된 클래스 생성자에는 인수로 저장소를 사용 합니다.  예를 들어, DSL을 예제 라는 클래스를 정의 하는 경우  
  
 `Example element = new Example (theStore);`  
  
 개체 저장소 \(대신 단지는 일반 개체\)에 유지 하면 여러 가지 이점을 제공을 합니다.  
  
-   **트랜잭션이**.  일련의 트랜잭션 관련된 변경 내용 그룹화 할 수 있습니다.  
  
     `using (Transaction t = store.TransactionManager.BeginTransaction("updates"))`  
  
     `{`  
  
     `// make several changes to Store elements here`  
  
     `t.Commit();`  
  
     `}`  
  
     최종 commit\(\)을 수행 하지 않도록 변경 하는 동안 예외가 발생 하는 경우 저장소 이전 상태로 다시 설정 됩니다.  오류 모델 불안정 한 상태에 놓이지 않도록 하려면 비교할 수 있습니다.  자세한 내용은 [프로그램 코드에서 모델 탐색 및 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)를 참조하십시오.  
  
-   **이항 관계**.  두 클래스 사이의 관계를 정의 하는 경우 인스턴스 양 끝에서 다른 쪽 끝을 이동 하는 속성을 가집니다.  양 항상 동기화 됩니다.  예를 들어, 부모 및 자식 이라는 역할에 parenthood 관계를 정의 하는 경우를 작성할 수 있습니다.  
  
     `John.Children.Add(Mary)`  
  
     다음 식은 모두 이제 적용 됩니다.  
  
     `John.Children.Contains(Mary)`  
  
     `Mary.Parents.Contains(John)`  
  
     작성 하 여 동일한 효과 얻을 수 있습니다.  
  
     `Mary.Parents.Add(John)`  
  
     자세한 내용은 [프로그램 코드에서 모델 탐색 및 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)를 참조하십시오.  
  
-   **규칙 및 이벤트**.  지정 된 변경 될 때마다 발생 하는 규칙을 정의할 수 있습니다.  규칙, 예를 들어, 셰이프를 다이어그램에는 제시 모델 요소를 최신으로 유지 하려면 사용 됩니다.  자세한 내용은 [변경 내용에 대한 대응 및 전파](../modeling/responding-to-and-propagating-changes.md)를 참조하십시오.  
  
-   **Serialization**.  저장소 파일을 포함 하는 개체를 serialize 하는 표준 방법을 제공 합니다.  직렬화 및 역직렬화에 대 한 규칙을 사용자 지정할 수 있습니다.  자세한 내용은 [파일 저장소 및 XML Serialization 사용자 지정](../modeling/customizing-file-storage-and-xml-serialization.md)를 참조하십시오.  
  
## 참고 항목  
 [도메인별 언어 사용자 지정 및 확장](../modeling/customizing-and-extending-a-domain-specific-language.md)