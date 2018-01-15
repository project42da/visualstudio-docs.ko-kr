---
title: "방법: 트랜잭션을 사용 하 여 모델을 업데이트할 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ecff3cb7585d9c80037ff8cdbd087b39a584f2aa
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="how-to-use-transactions-to-update-the-model"></a>방법: 트랜잭션을 사용하여 모델 업데이트
트랜잭션은 변경 내용을 저장소에 대 한 그룹으로 취급 됩니다 있는지 확인 합니다. 그룹화 된 변경 내용은 커밋하거나 하나의 단위로 롤백할 수 있습니다.  
  
 프로그램 코드를 수정, 추가, 또는의 저장소에서 모든 요소를 삭제 될 때마다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Visualization and Modeling SDK 트랜잭션 내에서는 그렇게 해야 합니다. 활성 인스턴스가 없어야 <xref:Microsoft.VisualStudio.Modeling.Transaction> 변경이 발생할 때 저장소와 연결 합니다. 이 모든 모델 요소, 관계, 셰이프, 다이어그램 및 해당 속성에 적용 됩니다.  
  
 트랜잭션 메커니즘을 사용 하면 일관성 없는 상태를 피할 수 있습니다. 트랜잭션 중에 오류가 발생 하는 경우 모든 변경 내용이 롤백됩니다. 사용자는 실행 취소 명령의 수행 하는 경우 최근 각 트랜잭션은 한 번으로 처리 됩니다. 사용자는 별도 트랜잭션을 명시적으로 배치 하지 않는 한 최근 변경의 부분을 취소할 수 없습니다.  
  
## <a name="opening-a-transaction"></a>트랜잭션을 열기  
 와 트랜잭션을 관리 하는 가장 편리한 방법은 `using` 문 안에 한 `try...catch` 문:  
  
```  
Store store; ...  
try  
{  
  using (Transaction transaction =  
    store.TransactionManager.BeginTransaction("update model"))  
    // Outermost transaction must always have a name.  
  {  
    // Make several changes in Store:  
    Person p = new Person(store);  
    p.FamilyTreeModel = familyTree;  
    p.Name = "Edward VI";  
    // end of changes to Store  
  
    transaction.Commit(); // Don't forget this!  
  } // transaction disposed here  
}  
catch (Exception ex)  
{  
  // If an exception occurs, the Store will be   
  // rolled back to its previous state.  
}  
```  
  
 최종 수 없는 예외가 `Commit()` 발생 변경 하는 동안 저장소를 이전 상태로 다시 설정 됩니다. 이 오류 형태로 두지 마십시오 모델 일관성이 없는 상태에 있는지 확인 수 있습니다.  
  
 임의 개수의 한 트랜잭션 내에서 변경 내용 만들 수 있습니다. 새 트랜잭션이 활성화 된 트랜잭션 내부 열 수 있습니다. 중첩 된 트랜잭션을 커밋하거나 롤백할 포함 하는 트랜잭션 종료 되기 전에 합니다. 자세한 내용은 참조에 대 한 예제는 <xref:Microsoft.VisualStudio.Modeling.Transaction.TransactionDepth%2A> 속성입니다.  
  
 변경 내용을 영구적, 하려면 `Commit` 삭제 하기 전에 트랜잭션. 예외가 발생 하지는 트랜잭션 내부는 저장소 변경 되기 전에 상태로 다시 설정 됩니다.  
  
## <a name="rolling-back-a-transaction"></a>트랜잭션 롤백  
 저장소에 남아 또는 트랜잭션 전에 상태로 되돌아갑니다 되도록 이러한 전략 중 하나를 사용할 수 있습니다.  
  
1.  트랜잭션의 범위 내 잡히지 않아 하는 예외를 발생 시킵니다.  
  
2.  명시적으로 트랜잭션을 롤백하십시오.  
  
    ```  
    this.Store.TransactionManager.CurrentTransaction.Rollback();  
    ```  
  
## <a name="transactions-do-not-affect-non-store-objects"></a>트랜잭션이 아닌 저장소 개체에 영향을 주지 않습니다.  
 트랜잭션을 저장소의 상태를 제어합니다. 파일, 데이터베이스 또는 DSL 정의 외부에서 일반 형식으로 선언 해야 하는 개체와 같은 외부 항목에 적용 된 변경 내용을 취소할 수 없습니다.  
  
 예외는 변경 내용 저장소와 일치 하지 않는 않을 수, 예외 처리기에서이 가능성을 처리 해야 합니다. 외부 리소스 저장소 개체와 동기화 된 상태로 유지 되도록 가지 방법은 이벤트 처리기를 사용 하 여 저장소의 요소에 각 외부 개체를 결합 하는 것입니다. 자세한 내용은 참조 [이벤트 처리기 전파 변경 내용을 바깥쪽 the 모델](../modeling/event-handlers-propagate-changes-outside-the-model.md)합니다.  
  
## <a name="rules-fire-at-the-end-of-a-transaction"></a>트랜잭션이 끝날 때 규칙 실행  
 트랜잭션이 끝날 때 트랜잭션이 삭제 되기 전에 저장소의 요소에 연결 된 규칙 발생 합니다. 각 규칙은 변경 된 모델 요소에 적용 되는 메서드입니다. 예를 들어 해당 모델 요소, 변경 될 때 셰이프 상태를 업데이트 하는 "픽스업" 규칙 있으며 모델 요소를 만들 때 도형을 만드는입니다. 지정 된 발생 한 순서 없이 있습니다. 규칙에 의해 수행 된 변경을 다른 규칙을 시작 될 수 있습니다.  
  
 사용자 고유의 규칙을 정의할 수 있습니다. 규칙에 대 한 자세한 내용은 참조 [에 대응 하 고 변경 내용을 전파](../modeling/responding-to-and-propagating-changes.md)합니다.  
  
 규칙 실행 취소, 다시 실행, 또는 rollback 명령 후 발생 하지 않습니다.  
  
## <a name="transaction-context"></a>트랜잭션 컨텍스트  
 각 트랜잭션에 사전 원하는 모든 정보를 저장할 수 있습니다.  
  
 `store.TransactionManager`  
  
 `.CurrentTransaction.TopLevelTransaction`  
  
 `.Context.Add(aKey, aValue);`  
  
 규칙 간에 정보를 전송 하는 데 특히 유용 합니다.  
  
## <a name="transaction-state"></a>트랜잭션 상태입니다.  
 방지 하기 위해 필요한 경우도 변경을 실행 취소 하거나 트랜잭션을 다시 실행 하 여 발생 하는 경우 변경 내용을 전파 합니다. 예를 들어 저장소의 다른 값을 업데이트할 수 있는 속성 값 처리기를 작성 하는 경우이 오류가 발생할 수 있습니다. 실행 취소 작업을 이전 상태로 저장소에 있는 모든 값을 다시 설정 하기 때문에 업데이트 된 값을 계산할 필요는 없습니다. 이 코드를 사용 합니다.  
  
```  
if (!this.Store.InUndoRedoOrRollback) {...}  
```  
  
 규칙은 저장소 파일에서 처음 로드 되는 경우에 발생할 수 있습니다. 이러한 변경 내용에 응답을 방지 하려면 다음을 사용 합니다.  
  
```  
if (!this.Store.InSerializationTransaction) {...}  
  
```