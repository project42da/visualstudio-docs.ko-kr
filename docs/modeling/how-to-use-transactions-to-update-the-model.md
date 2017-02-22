---
title: "방법: 트랜잭션을 사용하여 모델 업데이트 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e24436a5-7f97-401b-bc83-20d188d10d5b
caps.latest.revision: 7
caps.handback.revision: 7
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 방법: 트랜잭션을 사용하여 모델 업데이트
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

트랜잭션을 해당 저장소에 대 한 변경 내용을 그룹으로 처리 됩니다 있는지 확인 하십시오.  그룹화 된 변경 내용이 커밋되거나 한 단위로 롤백될 수 있습니다.  
  
 때마다 프로그램 코드를 수정, 추가, 또는 저장소에서 모든 요소를 삭제 합니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] SDK, 모델링 및 시각화 트랜잭션 내 요청을 수행 해야 합니다.  현재 인스턴스를 해야 될 <xref:Microsoft.VisualStudio.Modeling.Transaction> 변경이 발생 하면 저장소와 관련 된.  이 모든 모델 요소, 관계, 도형, 다이어그램, 및 해당 속성에 적용 됩니다.  
  
 트랜잭션 메커니즘 일관성이 없는 상태가 되지 않도록 하는 데 도움이 됩니다.  트랜잭션 중에 오류가 발생 하면 모든 변경 내용이 롤백됩니다.  사용자는 실행 취소 명령을 수행 하는 경우 최근 각 트랜잭션은 한 단계로 처리 됩니다.  별도 트랜잭션을 명시적으로 설정 하지 않으면 사용자의 최근 변경 내용을 취소할 수 없습니다.  
  
## 트랜잭션 열기  
 가장 편리한 방법은 트랜잭션 관리 사용 되는 `using` 문을 묶습니다는 `try...catch` 문을:  
  
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
  
 최종 방지 예외 경우 `Commit()` 저장소 이전 상태로 재설정 됩니다 변경 하는 동안 발생 합니다.  오류 모델 불안정 한 상태에 놓이지 않도록 수 있습니다.  
  
 하나의 트랜잭션 내 변경 내용 원하는 만큼을 만들 수 있습니다.  새 트랜잭션이 현재 트랜잭션 안에서 열 수 있습니다.  중첩 된 트랜잭션은 있어야 커밋하거나 포함 된 트랜잭션이 끝나기 전에.  자세한 내용은 예제를 참조 하십시오은 <xref:Microsoft.VisualStudio.Modeling.Transaction.TransactionDepth%2A> 속성입니다.  
  
 변경 내용을 영구적으로 유지 하려면 `Commit` 삭제 되기 전에 트랜잭션.  트랜잭션 내에서 catch 되지 않는 예외가 발생 하는 경우 저장소 변경 이전 상태로 다시 설정 합니다.  
  
## 트랜잭션 롤백  
 저장소에 남아 또는 트랜잭션 이전의 상태로 되돌리는 수 이러한 전술 중 하나를 사용 하십시오.  
  
1.  트랜잭션의 범위 내를 catch 되지 않는 예외가 발생 합니다.  
  
2.  명시적으로 트랜잭션을 롤백 하십시오.  
  
    ```  
    this.Store.TransactionManager.CurrentTransaction.Rollback();  
    ```  
  
## 트랜잭션이 아닌 저장소 개체에 영향을 미치는합니다  
 거래는 저장소의 상태를 제어합니다.  파일, 데이터베이스, 또는 외부 DSL 정의 일반 형식으로 선언 된 개체와 같은 외부 항목에 대 한 일부 변경 내용을 취소할 수 없습니다.  
  
 예외 변경 저장소 일관성 없는 남겨 두는 경우 가능성 예외 처리기에서 처리 해야 합니다.  외부 리소스 저장소 개체와 동기화 된 상태로 남아 있는지 확인 하는 방법을 매장 요소에 이벤트 처리기를 사용 하 여 각 외부 개체를 결합 하는 것.  자세한 내용은 [이벤트 처리기로 모델 외부의 변경 내용 전파](../modeling/event-handlers-propagate-changes-outside-the-model.md)를 참조하십시오.  
  
## 트랜잭션 끝에 규칙 화재  
 트랜잭션을 삭제 하기 전에 트랜잭션 끝에 요소를 저장소에 연결 된 규칙 발생 합니다.  각 규칙 변경 된 모델 요소에 적용 되는 메서드입니다.  예를 들어, 해당 모델 요소가 변경 되 면 업데이트 상태 셰이프의 "수정" 규칙이 및 모델 요소를 만들 때 어떤 모양이 만들어집니다.  지정 된 발생 순서 없이 있습니다.  변경에 다른 규칙이 실행 수 있습니다.  
  
 직접 규칙을 정의할 수 있습니다.  규칙에 대한 자세한 내용은 [변경 내용에 대한 대응 및 전파](../modeling/responding-to-and-propagating-changes.md)을 참조하십시오.  
  
 규칙 실행 취소, 다시 실행, 또는 rollback 명령 이후에 발생 하지 않습니다.  
  
## 트랜잭션 컨텍스트  
 각 트랜잭션 사전에 원하는 정보를 저장할 수 있습니다.  
  
 `store.TransactionManager`  
  
 `.CurrentTransaction.TopLevelTransaction`  
  
 `.Context.Add(aKey, aValue);`  
  
 규칙 간에 정보를 전송 하는 데 특히 유용 합니다.  
  
## 트랜잭션 상태입니다.  
 변경 실행 취소 또는 트랜잭션을 다시 실행으로 인해 발생 하는 경우 방지 하기 위해 필요에 따라서는 변경을 전파 합니다.  저장소에서 다른 값을 업데이트 하는 속성 값 처리기를 작성 하 여, 예를 들어 경우일 수 있습니다.  실행 취소 작업 이전 상태로 저장소에 있는 모든 값을 다시 설정 하기 때문에 업데이트 된 값을 계산할 수 없습니다.  이 코드를 사용 합니다.  
  
```  
if (!this.Store.InUndoRedoOrRollback) {...}  
```  
  
 저장소 파일에서 초기에 로드 되 면 규칙 실행 수 있습니다.  이러한 변경 내용에 응답을 사용 하지 않으려면이 옵션을 사용 하십시오.  
  
```  
if (!this.Store.InSerializationTransaction) {...}  
  
```