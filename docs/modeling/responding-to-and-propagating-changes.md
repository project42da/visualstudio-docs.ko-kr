---
title: "변경 내용에 대한 대응 및 전파 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도메인별 언어, 이벤트"
ms.assetid: fc2e9ac5-7a84-44ed-9945-94e45f89c227
caps.latest.revision: 24
caps.handback.revision: 24
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 변경 내용에 대한 대응 및 전파
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

요소 작성, 업데이트 또는 삭제 되 면이 모델의 다른 부분에 나 파일, 데이터베이스 또는 기타 구성 요소와 같은 외부 리소스에 변경 전파 하는 코드를 작성할 수 있습니다.  
  
## 단원 내용  
 기본적으로 다음과 같은 순서로 이러한 기술을 고려해 야 합니다.  
  
|기술|시나리오|자세한 내용|  
|--------|----------|------------|  
|도메인 계산 된 속성을 정의 합니다.|다른 모델에서 속성의 값이 계산 되는 도메인 속성입니다.  예를 들어 가격의 합 인 가격 요소 관련 있습니다.|[계산 및 사용자 지정 저장소 속성](../modeling/calculated-and-custom-storage-properties.md)|  
|사용자 지정 저장소 도메인 속성을 정의 합니다.|다른 부품 모델 또는 외부적으로 저장 되는 도메인 속성입니다.  예를 들어, 모델 트리에서로 식 문자열을 분석할 수 있습니다.|[계산 및 사용자 지정 저장소 속성](../modeling/calculated-and-custom-storage-properties.md)|  
|재정의 OnValueChanging 및 OnDeleting 처리기를 변경 합니다.|다양 한 요소를 동기화 하 고 외부 값의 모델을 동기화 상태를 유지 합니다.<br /><br /> 값에 정의 된 범위를 제한 합니다.<br /><br /> 직전과 직후 속성 값 및 다른 변경 내용 이라고 합니다.  변경에서 예외를 throw 하 여 종료할 수 있습니다.|[도메인 속성 값 변경 처리기](../modeling/domain-property-value-change-handlers.md)|  
|규칙|직전에 변경이 발생 한 트랜잭션의 실행을 위해 대기 하는 규칙을 정의할 수 있습니다.  실행 취소 또는 다시 실행을 실행 됩니다지 않습니다.  저장소의 한 부분을 다른 동기화 유지를 사용 합니다.|[규칙에는 모델 내에서 변경 내용을 전파 하기](../modeling/rules-propagate-changes-within-the-model.md)|  
|저장소 이벤트|모델링 저장소 추가 또는 요소 또는 링크를 삭제 하거나 속성 값을 변경 하는 등 이벤트에 대 한 알림을 제공 합니다.  이벤트는 실행 취소 및 다시 실행에도 실행 됩니다.  저장소 이벤트를 사용 하 여 저장소에서 다른 값을 업데이트 합니다.|[이벤트 처리기로 모델 외부의 변경 내용 전파](../modeling/event-handlers-propagate-changes-outside-the-model.md)|  
|.NET 이벤트|셰이프에 다른 제스처 마우스 클릭에 응답 하는 이벤트 처리기가 있습니다.  각 개체에 대해 이러한 이벤트에 대해 등록 해야 합니다.  등록 재정의 된 Initializeinstanceresources에서 일반적으로 수행 해야 하 고 각 요소에 대해 작업을 수행 해야 합니다.<br /><br /> 이러한 이벤트는 일반적으로 트랜잭션 밖에 서 발생합니다.|[방법: 모양 또는 데코레이터 클릭 가로채기](../Topic/How%20to:%20Intercept%20a%20Click%20on%20a%20Shape%20or%20Decorator.md)|  
|범위 규칙|경계 셰이프를 특별히 제한 하는 범위 규칙 사용 됩니다.|[BoundsRules로 모양 위치 및 크기 제한](../modeling/boundsrules-constrain-shape-location-and-size.md)|  
|선택 규칙|어떤 사용자가 선택할 수 있습니다 특별히 선택 규칙을 제한 합니다.|[방법: 현재 선택 항목 액세스 및 제약](../modeling/how-to-access-and-constrain-the-current-selection.md)|  
|OnAssocatedPropertyChanged|도형 및 연결선 그림자, 화살촉, 색상, 선 두께 및 스타일 등의 기능을 사용 하 여 모델 요소의 상태를 나타냅니다.|[모양 및 연결선을 업데이트하여 모델 반영](../modeling/updating-shapes-and-connectors-to-reflect-the-model.md)|  
  
## **규칙 및 저장소 이벤트 비교**  
 모델에 변경 사항이 발생 하면 변경 notifiers, 규칙 및 이벤트를 실행 합니다.  
  
 규칙 변경 발생 했습니다 최종 트랜잭션 시 일반적으로 적용 되 고 트랜잭션에서 변경 내용을 커밋한 후 이벤트가 적용 됩니다.  
  
 저장소 이벤트를 사용 하 여 개체가 외부 저장소 및 규칙 저장소 내에서 일관성을 유지할 수 있는 모델을 동기화 합니다.  
  
-   **사용자 지정 규칙 만들기** 추상 규칙에서 파생 된 클래스는 사용자 지정 규칙을 만듭니다.  또한 사용자 지정 규칙에 대 한 프레임 워크에 알려야 합니다.  자세한 내용은 [규칙에는 모델 내에서 변경 내용을 전파 하기](../modeling/rules-propagate-changes-within-the-model.md)를 참조하십시오.  
  
-   **이벤트 구독** 이벤트를 구독할 수 있습니다 전에 이벤트 처리기와 대리자를 만듭니다.  다음 사용 하는 <xref:Microsoft.VisualStudio.Modeling.Store.EventManagerDirectory%2A>이벤트를 등록 하는 속성입니다.  자세한 내용은 [이벤트 처리기로 모델 외부의 변경 내용 전파](../modeling/event-handlers-propagate-changes-outside-the-model.md)를 참조하십시오.  
  
-   **변경 내용을 취소 하 고** 트랜잭션 실행을 취소 하면 이벤트 발생 되지만 규칙이 적용 되지 않습니다.  값을 원래 값으로 하는 규칙은 변경 하 고 해당 변경 내용을 취소 하는 경우 실행 취소 작업 중 다시 설정 됩니다.  이벤트가 발생 하는 경우 다시 원래 값으로 값을 수동으로 변경 해야 합니다.  Transactons 및 실행 취소 정보를 참조 하십시오. [방법: 트랜잭션을 사용하여 모델 업데이트](../modeling/how-to-use-transactions-to-update-the-model.md).  
  
-   **규칙 및 이벤트를 전달 하는 이벤트 인수** 두 이벤트 및 규칙 전달 됩니다는 `EventArgs` 모델 방법에 대 한 정보를 포함 하는 매개 변수를 변경 합니다.  
  
## 참고 항목  
 [방법: 모양 또는 데코레이터 클릭 가로채기](../Topic/How%20to:%20Intercept%20a%20Click%20on%20a%20Shape%20or%20Decorator.md)   
 [도메인별 언어 사용자 지정 하는 코드 작성](../modeling/writing-code-to-customise-a-domain-specific-language.md)