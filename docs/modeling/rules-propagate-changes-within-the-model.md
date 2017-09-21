---
title: "규칙에는 모델 내에서 변경 내용을 전파 하기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도메인별 언어에서 프로그래밍 도메인 모델"
  - "도메인별 언어에서 규칙"
ms.assetid: 1690a38a-c8f5-4bc6-aab9-015771ec6647
caps.latest.revision: 30
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 30
---
# 규칙에는 모델 내에서 변경 내용을 전파 하기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

시각화 및 모델링 SDK \(VMSDK\)에서 다른 요소에서 변경 전파 하는 저장소 규칙을 만들 수 있습니다. 저장소의 모든 요소에는 변경 사항이 발생 규칙 실행 될 가장 바깥쪽 트랜잭션이 커밋될 때 일반적으로 예약 됩니다. 다양 한 유형의 여러 종류의 요소를 추가 또는 삭제와 같은 이벤트에 대 한 규칙이 있습니다. 요소, 모양 또는 다이어그램의 특정 형식에 규칙을 연결할 수 있습니다. 여러 기본 제공 기능 규칙으로 정의 됩니다: 다이어그램 모델이 변경 될 때 업데이트 되도록 규칙을 보장 하는 예를 들어 있습니다. 사용자 고유의 규칙을 추가 하 여 도메인별 언어를 사용자 지정할 수 있습니다.  
  
 속성을 모델 요소, 관계, 모양 또는 커넥터 및 해당 도메인을 변경, 즉 저장소 – 내 변경 내용 전파에 대 한 저장소 규칙은 특히 유용 합니다. 사용자가 취소 또는 다시 실행 명령을 호출할 때에 규칙이 실행 되지 않습니다. 대신, 트랜잭션 관리자가 저장소 콘텐츠는 올바른 상태로 복원할 합니다. 저장소 외부의 리소스에 대 한 변경 내용을 전파 하려는 경우 저장소 이벤트를 사용 합니다. 자세한 내용은 [이벤트 처리기로 모델 외부의 변경 내용 전파](../modeling/event-handlers-propagate-changes-outside-the-model.md)을 참조하세요.  
  
 예를 들어, 사용자 \(또는 코드\) ExampleDomainClass 형식의 새 요소를 만들 때마다 다른 종류의 추가 요소는 모델의 다른 부분에 생성 않도록 지정. AddRule를 쓰고 ExampleDomainClass에 연결할 수 있습니다. 추가 요소를 만드는 규칙에 코드를 작성 합니다.  
  
```c#  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using Microsoft.VisualStudio.Modeling;  
  
namespace ExampleNamespace  
{  
 // Attribute associates the rule with a domain class:  
 [RuleOn(typeof(ExampleDomainClass), FireTime=TimeToFire.TopLevelCommit)]  
 // The rule is a class derived from one of the abstract rules:  
 class MyAddRule : AddRule  
 {  
  // Override the abstract method:  
  public override void ElementAdded(ElementAddedEventArgs e)  
  {  
    base.ElementAdded(e);  
    ExampleDomainClass element = e.ModelElement;  
    Store store = element.Store;  
    // Ignore this call if we're currently loading a model:  
    if (store.TransactionManager.CurrentTransaction.IsSerializing)   
       return;  
  
    // Code here propagates change as required – for example:  
      AnotherDomainClass echo = new AnotherDomainClass(element.Partition);  
      echo.Name = element.Name;  
      echo.Parent = element.Parent;    
    }  
  }  
 // The rule must be registered:  
 public partial class ExampleDomainModel  
 {  
   protected override Type[] GetCustomDomainModelTypes()  
   {  
     List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());  
     types.Add(typeof(MyAddRule));  
     // If you add more rules, list them here.   
     return types.ToArray();  
   }  
 }  
}  
  
```  
  
> [!NOTE]
>  규칙의 코드는 저장소; 내부 요소에 대해서만 상태를 변경 해야 즉, 규칙은 모델 요소, 관계, 모양, 연결선, 다이어그램 또는 해당 속성만 변경 해야 합니다. 저장소 외부의 리소스에 대 한 변경 내용을 전파 하려는 경우를 저장 하는 이벤트를 정의 합니다. 자세한 내용은 [이벤트 처리기로 모델 외부의 변경 내용 전파](../modeling/event-handlers-propagate-changes-outside-the-model.md)을 참조하세요.  
  
### 규칙을 정의 하려면  
  
1.  클래스 앞으로 규칙을 정의 `RuleOn` 특성입니다. 특성은 도메인 클래스, 관계 또는 다이어그램 요소 중 하나는 규칙에 연결합니다. 규칙은 추상 일 수 있는이 클래스의 모든 인스턴스에 적용 됩니다.  
  
2.  반환 된 집합에 추가 하 여 규칙을 등록 `GetCustomDomainModelTypes()` 도메인 모델 클래스에 있습니다.  
  
3.  추상 규칙 클래스 중 하나에서 규칙 클래스를 파생 하 고 실행 메서드의 코드를 작성 합니다.  
  
 다음 섹션에서는 이러한 단계를 자세히 설명합니다.  
  
### 도메인 클래스에 규칙을 정의 하려면  
  
-   사용자 지정 코드 파일에서 클래스를 정의 하 고 사용 하 여 접두사는 <xref:Microsoft.VisualStudio.Modeling.RuleOnAttribute> 특성:  
  
    ```  
    [RuleOn(typeof(ExampleElement),   
         // Usual value – but required, because it is not the default:  
         FireTime = TimeToFire.TopLevelCommit)]   
    class MyRule ...  
  
    ```  
  
-   도메인 클래스, 도메인 관계, 모양, 연결선 또는 다이어그램에 첫 번째 매개 변수에서 주체 종류 수 있습니다. 일반적으로 도메인 클래스 및 관계에 규칙을 적용 합니다.  
  
     `FireTime` 는 일반적으로 `TopLevelCommit`합니다. 이렇게 하면 트랜잭션의 모든 주요 변경 사항이 발생 한 후에 규칙이 실행 됩니다. 대신 사용 하는 인라인; 변경 후 곧 규칙을 실행 하는 및 LocalCommit \(않을 수도 있는 가장 바깥쪽\) 현재 트랜잭션이 끝날 때 규칙을 실행 합니다. 큐에서 순서에 영향을 하는 규칙의 우선 순위를 설정할 수도 있지만 필요한 결과 달성 하는 안정적이 지 않은 방법을.  
  
-   추상 클래스의 주체 형식으로 지정할 수 있습니다.  
  
-   규칙 주체 클래스의 모든 인스턴스에 적용 됩니다.  
  
-   기본값 `FireTime` TimeToFire.TopLevelCommit 됩니다. 이렇게 하면 규칙에 따라 가장 바깥쪽 트랜잭션이 커밋될 때 실행 됩니다. TimeToFire.Inline 것이 좋습니다. 이렇게 하면 규칙을 트리거하는 이벤트가 직후 실행 됩니다.  
  
### 규칙을 등록 하려면  
  
-   규칙 클래스에서 반환 된 형식의 목록에 추가 `GetCustomDomainModelTypes` 도메인 모델:  
  
    ```  
    public partial class ExampleDomainModel  
     {  
       protected override Type[] GetCustomDomainModelTypes()  
       {  
         List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());  
         types.Add(typeof(MyAddRule));  
         // If you add more rules, list them here.   
         return types.ToArray();  
       }  
     }  
  
    ```  
  
-   파일 내부 도메인 모델 클래스의 이름을 정확히 알지 못하는 경우 확인 **Dsl\\GeneratedCode\\DomainModel.cs**  
  
-   DSL 프로젝트의 사용자 지정 코드 파일에서이 코드를 작성 합니다.  
  
### 규칙의 코드를 작성 하려면  
  
-   다음 기본 클래스 중 하나에서 규칙 클래스를 파생 합니다.  
  
    |기본 클래스|트리거|  
    |------------|---------|  
    |<xref:Microsoft.VisualStudio.Modeling.AddRule>|요소, 링크 또는 셰이프 추가 됩니다.<br /><br /> 이 사용 하 여 새 요소 외에도 새 관계를 검색 합니다.|  
    |<xref:Microsoft.VisualStudio.Modeling.ChangeRule>|도메인 속성 값이 변경 됩니다. 메서드 인수는 이전 및 새 값을 제공합니다.<br /><br /> 이 규칙은 트리거됩니다 모양의 경우 때 기본 제공 `AbsoluteBounds` 모양이 이동 하는 경우 속성 변경 합니다.<br /><br /> 대부분의 경우에서 재정의 하는 편리한 방법을 `OnValueChanged` 또는 `OnValueChanging` 속성 처리기에 있습니다. 이러한 메서드는 바로 앞 이나 변경 된 후 호출 됩니다. 이와 반대로 규칙 트랜잭션이 끝날 때 일반적으로 실행 됩니다. 자세한 내용은 [도메인 속성 값 변경 처리기](../modeling/domain-property-value-change-handlers.md)을 참조하세요. **Note:**  이 규칙은 링크를 만들거나 삭제 하는 경우에 트리거되지 않습니다. 대신 작성 한 `AddRule` 및 `DeleteRule` 도메인 관계에 대 한 합니다.|  
    |<xref:Microsoft.VisualStudio.Modeling.DeletingRule>|요소 또는 링크를 삭제할 때 발생 합니다. ModelElement.IsDeleting 속성은 트랜잭션이 끝날 때까지 true입니다.|  
    |<xref:Microsoft.VisualStudio.Modeling.DeleteRule>|요소 또는 링크 삭제 된 경우 수행 됩니다. 규칙에는 다른 모든 규칙 실행 된 DeletingRules를 포함 한 후 실행 됩니다. False 이면 ModelElement.IsDeleting 이며 ModelElement.IsDeleted 마찬가지입니다. 이후 실행 취소를 허용 하려면 요소가 제거 되지 않습니다 실제로 메모리에서 있지만 Store.ElementDirectory에서 제거 됩니다.|  
    |<xref:Microsoft.VisualStudio.Modeling.MoveRule>|요소는 다른 하나의 저장소 파티션에서 이동 됩니다.<br /><br /> \(표시는이 관련이 없는 도형의 그래픽 위치입니다.\)|  
    |<xref:Microsoft.VisualStudio.Modeling.RolePlayerChangeRule>|도메인 관계에만이 규칙이 적용 됩니다. 링크의 양쪽 끝에 모델 요소를 명시적으로 할당 하는 경우 트리거됩니다.|  
    |<xref:Microsoft.VisualStudio.Modeling.RolePlayerPositionChangeRule>|요소에서 링크의 순서가 링크 MoveBefore 또는 MoveToIndex 메서드를 사용 하 여 변경 될 때 트리거됩니다.|  
    |<xref:Microsoft.VisualStudio.Modeling.TransactionBeginningRule>|트랜잭션을 만들 때 실행 합니다.|  
    |<xref:Microsoft.VisualStudio.Modeling.TransactionCommittingRule>|트랜잭션이 커밋할 수 되려고 할 때 실행 합니다.|  
    |<xref:Microsoft.VisualStudio.Modeling.TransactionRollingBackRule>|트랜잭션이 롤백될 수 되려고 할 때 실행 합니다.|  
  
-   각 클래스에 메서드를 재정의 합니다. 형식 `override` 검색 하기 위해 클래스에 있습니다. 이 메서드의 매개 변수 변경 되는 요소를 식별 합니다.  
  
 규칙에 대 한 다음 사항을 확인 합니다.  
  
1.  트랜잭션에서 변경 내용 집합이 여러 규칙을 트리거할 수 있습니다. 일반적으로 규칙은 가장 바깥쪽 트랜잭션이 커밋될 때 실행 됩니다. 지정 되지 않은 순서로 실행 됩니다.  
  
2.  규칙은 트랜잭션 내에서는 항상 실행 됩니다. 따라서 변경 하는 새 트랜잭션을 만들 필요가 없습니다.  
  
3.  트랜잭션이 롤백될 때, 또는 실행 취소 또는 다시 실행 작업을 수행할 때에 규칙이 실행 되지 않습니다. 이러한 작업 저장소의 모든 내용은 이전 상태로 다시 설정 합니다. 따라서 규칙 스토어 외부에 있는 항목의 상태가 변경 되 면 것 수 유지 synchronism 저장소와 함께 콘텐츠. 저장소 외부의 상태를 업데이트 하려면 이벤트를 사용 하는 것이 좋습니다. 자세한 내용은 [이벤트 처리기로 모델 외부의 변경 내용 전파](../modeling/event-handlers-propagate-changes-outside-the-model.md)을 참조하세요.  
  
4.  일부 규칙은 모델 파일에서 로드 되 면 실행 됩니다. 로드 하거나 저장 진행 중인지 여부를 확인 하려면 `store.TransactionManager.CurrentTransaction.IsSerializing`합니다.  
  
5.  규칙의 코드에서 더 많은 규칙 트리거를 만드는 경우 발생 하는 목록의 끝에 추가 됩니다 하며 트랜잭션이 완료 되기 전에 실행 됩니다. 다른 모든 규칙 후 DeletedRules 실행 됩니다. 규칙을 하나 거래 각 변경에 대해 한 번에에서 여러 번 실행할 수 있습니다.  
  
6.  규칙에서 정보를 전달 하려면에서 정보를 저장할 수는 `TransactionContext`합니다. 트랜잭션 동안 유지 관리 되는 사전입니다. 트랜잭션이 종료 될 때 삭제 됩니다. 각 규칙에는 이벤트 인수에 대 한 액세스를 제공합니다. 기억 규칙 예측 가능한 순서로 실행 되지 않습니다.  
  
7.  다른 대안을 고려한 후 규칙을 사용 합니다. 예를 들어 값이 변경 될 때 속성을 업데이트 하려는 경우에 계산 된 속성을 사용 하는 것이 좋습니다. 크기 또는 모양의 위치를 제한 하려는 경우 사용 하 여 한 `BoundsRule`합니다. 속성 값의 변경에 응답 하는 경우 추가 `OnValueChanged` 속성에는 처리기. 자세한 내용은 [변경 내용에 대한 대응 및 전파](../modeling/responding-to-and-propagating-changes.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 두 개의 요소를 연결 하는 도메인 관계를 인스턴스화할 때 속성을 업데이트 합니다. 뿐만 아니라 사용자 만드는 경우 링크를 다이어그램에서 뿐만 아니라 프로그램 코드에 링크를 만드는 경우이 규칙이 트리거됩니다.  
  
 이 예제를 테스트 하려면 작업 흐름 솔루션 템플릿을 사용 하 여 DSL 만들고 Dsl 프로젝트의 파일에 다음 코드를 삽입 합니다. 빌드 및 솔루션을 실행 하 고 디버깅 프로젝트에서 샘플 파일을 엽니다. 메모 모양 및 흐름 요소 간에 주석 링크를 그립니다. 주석에서 텍스트에 연결 하는 가장 최근의 요소에 대해 보고 하도록 변경 합니다.  
  
 실제로 모든 AddRule에 대 한 일반적으로 DeleteRule를 작성할 것 있습니다.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using Microsoft.VisualStudio.Modeling;  
  
namespace Company.TaskRuleExample  
{  
  
  [RuleOn(typeof(CommentReferencesSubjects))]  
  public class RoleRule : AddRule  
  {  
  
    public override void ElementAdded(ElementAddedEventArgs e)  
    {  
      base.ElementAdded(e);  
      CommentReferencesSubjects link = e.ModelElement as CommentReferencesSubjects;  
      Comment comment = link.Comment;  
      FlowElement subject = link.Subject;  
      Transaction current = link.Store.TransactionManager.CurrentTransaction;  
      // Don't want to run when we're just loading from file:  
      if (current.IsSerializing) return;  
      comment.Text = "Flow has " + subject.FlowTo.Count + " outgoing connections";  
    }  
  
  }  
  
  public partial class TaskRuleExampleDomainModel  
  {  
    protected override Type[] GetCustomDomainModelTypes()  
    {  
      List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());  
      types.Add(typeof(RoleRule));  
      return types.ToArray();  
    }  
  }  
  
}  
  
```  
  
## 참고 항목  
 [이벤트 처리기로 모델 외부의 변경 내용 전파](../modeling/event-handlers-propagate-changes-outside-the-model.md)   
 [BoundsRules로 모양 위치 및 크기 제한](../modeling/boundsrules-constrain-shape-location-and-size.md)