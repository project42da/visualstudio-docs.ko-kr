---
title: "잠금 정책을 정의하여 읽기 전용 세그먼트 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa549c71-2bf6-4b08-b7b2-7756dd6f1dc8
caps.latest.revision: 12
caps.handback.revision: 12
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 잠금 정책을 정의하여 읽기 전용 세그먼트 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

불변성 API에는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] SDK 모델링 및 시각화 수를 잠금 또는 일부 dsl \(DSL\) 모델의 프로그램을 읽을 수 있지만 변경 되지 않도록 합니다.  사용자가 DSL 모델을 검토 하 고 주석을 추가 하는 동료에 게 요청할 수 있습니다 하지만 하 고 원본을 변경 하지 못하도록 수 있습니다 있도록이 읽기 전용 옵션, 예를 들어, 사용할 수 있습니다.  
  
 또한, 저자는 DSL의 사용자 정의할 수 있습니다의  *잠금 정책.* 어떤 잠금 허용 허용 되지 않습니다 또는 필수입니다 잠금 정책을 정의 합니다.  예를 들어, DSL을 게시 하는 경우 타사 개발자가 새 명령으로 확장할 수 하도록 유도할 수 있습니다.  하지만 이러한 모델의 지정 된 파트의 읽기 전용 상태를 변경 하지 못하도록 잠금 정책을 사용할 수 있습니다.  
  
> [!NOTE]
>  리플렉션을 사용 하 여 잠금 정책을 우회할 수도 있습니다.  그 명확한 경계를 타사 개발자에 게 제공 하지만 강력한 보안을 제공 하지 않습니다.  
  
 자세한 내용 및 예제에 사용할 수 있는 해당 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)][시각화 및 모델링 SDK](란?LinkId%20=%20186128) 웹 사이트입니다.  
  
## 설정 및 잠금 가져오기  
 저장소, 파티션, 또는 개별 요소의 잠금을 설정할 수 있습니다.  예를 들어,이 문을 모델 요소가 삭제 되는 것을 방지할 수 있으며 또한 해당 속성이 변경 되지 않도록 합니다.  
  
```  
using Microsoft.VisualStudio.Modeling.Immutability; ...  
element.SetLocks(Locks.Delete | Locks.Property);  
```  
  
 요소 만들기, 파티션 및 역할에 대 한 re\-ordering 링크 간의 이동 관계에 변경 하지 못하도록 다른 잠금 값을 사용할 수 있습니다.  
  
 잠금은 사용자 동작 하 고 프로그램 코드를 적용합니다.  프로그램 코드를 변경 하려고 시도 하는 경우는 `InvalidOperationException` throw 됩니다.  잠금은 실행 취소 또는 다시 실행 작업에서 무시 됩니다.  
  
 요소의 모든 잠금을 지정 된 집합에 사용 하 여 있는지 검색할 수 있습니다 `IsLocked(Locks)` 를 사용 하 여 요소에 대 한 잠금은 현재 집합을 얻을 수 있습니다 및 `GetLocks()`.  
  
 트랜잭션을 사용 하지 않고 잠금을 설정할 수 있습니다.  잠금 데이터베이스 저장소의 일부가 아닙니다.  예를 들어 Onvaluechanged에서 잠금 값의 변경에는 저장소에 설정 하는 경우 실행 취소 작업의 일부가 변경 허용 해야 합니다.  
  
 이러한 방법에 정의 된 확장 메서드는 해당 <xref:Microsoft.VisualStudio.Modeling.Immutability> 네임 스페이스입니다.  
  
### 잠금이 파티션 및 저장소  
 잠금이 파티션 및 상점에도 적용할 수 있습니다.  파티션을 설정 되어 잠금 파티션에 모든 요소에 적용 됩니다.  따라서 예를 들어, 다음 문을 모든 요소에는 파티션, 자체 잠금 상태에 관계 없이 삭제 되지 않도록 합니다.  그럼에도 불구 하 고 다른 것과 같은 잠금 `Locks.Property` 의 개별 요소에는 설정할 수 없습니다.  
  
```  
partition.SetLocks(Locks.Delete);  
```  
  
 저장소에 설정 되어 있는 잠금 파티션 및 요소에 해당 잠금이 설정에 관계 없이 모든 요소에 적용 됩니다.  
  
### 잠금을 사용 하 여  
 다음 예제와 같은 체계를 구현 하려면 잠금을 사용할 수 있습니다.  
  
-   모든 요소와 관계 된 메모를 나타내는 제외 하 고 변경 내용을 허용 하지 않습니다.  이 사용자를 변경 하지 않고 모델에 주석을 달 수 있습니다.  
  
-   다이어그램에서 파티션을 변경할 수 있도록 기본 파티션의 변경 내용을 허용 하지 않습니다.  사용자는 다이어그램을 다시 정렬할 수 있지만 원본이 되는 모델을 변경할 수 없습니다.  
  
-   저장소 그룹을 별도 데이터베이스에 등록 된 사용자를 제외 하 고 변경 내용을 허용 하지 않습니다.  다른 사용자에 대 한 다이어그램 및 모델에 읽기 전용입니다.  
  
-   다이어그램의 Boolean 속성을 설정 하면 모델의 변경 내용을 허용 하지 않습니다. true로.  해당 속성을 변경 하려면 메뉴 명령을 제공 합니다.  이 수를 수행 하는 사용자를 실수로 변경 하는 확인 하십시오 수 있습니다.  
  
-   추가 및 삭제 요소를 특정 클래스의 관계를 허용 하지 않습니다 있지만 속성을 변경할 수 있습니다.  이 사용자가 속성을 채울 수 있는 고정된 폼을 제공 합니다.  
  
## 잠금 값  
 잠금은 저장소, 파티션 또는 개별 모델 요소에 설정할 수 있습니다.  잠금 수를 `Flags` 열거형:를 사용 하 여 해당 값을 조합할 수 있습니다 ' &#124;'.  
  
-   잠금에 모델 요소를 항상 잠금 해당 파티션의 포함 됩니다.  
  
-   잠금이 파티션 항상 저장소의 잠금이 포함합니다.  
  
 파티션에 잠금을 설정 하거나 저장 및 동시에 개별 요소의 잠금을 해제할 수 없습니다.  
  
|값|않으면 `IsLocked(Value)` 마찬가지입니다|  
|-------|-----------------------------------|  
|없음|제한이 없습니다.|  
|Property|요소 도메인 등록 정보는 변경할 수 없습니다.  이 도메인 클래스는 관계에서의 역할에 의해 생성 된 속성에는 적용 되지 않습니다.|  
|Add|새 요소에 대 한 링크에 파티션을 만들 수 없거나 또는 저장 합니다.<br /><br /> 에 적용할 수 없습니다 `ModelElement`.|  
|이동|요소가 경우 파티션 간에 이동할 수 없습니다 `element.IsLocked(Move)` true 인 경우 `targetPartition.IsLocked(Move)` 마찬가지입니다.|  
|Delete|요소는 요소 자체를이 잠금이 설정 된 경우 모든 요소를 삭제, 포함 된 요소 및 모양 등 전파 합니다. 삭제할 수 없습니다.<br /><br /> 사용할 수 있는 `element.CanDelete()` 요소를 삭제할 수 있는지 여부를 검색 합니다.|  
|다시 정렬|순서는 roleplayer에 대 한 링크를 변경할 수 없습니다.|  
|RolePlayer|이 요소를 기반으로 하는 링크의 집합을 변경할 수 없습니다.  예를 들어,이 요소에서 새 요소를 포함할 수 없습니다.  이 요소는 대상 있는 링크는 영향을 주지 않습니다.<br /><br /> 이 요소에 대 한 링크 이면 소스와 대상 적용 되지 않습니다.|  
|모두|다른 값의 비트 논리합입니다.|  
  
## 잠금 정책  
 DSL의 작성자는 사용자 정의할 수 있습니다의  *잠금 정책*.  설정 또는 특정 잠금 설정 해야 따라 라 만들어 질 중에서 특정 잠금을 방지할 수 있습니다 있도록 잠금 정책, Setlocks\(\)의 작업을 조정 합니다.  일반적으로 잠금 정책 사용자 또는 개발자가 실수로 DSL의 사용을 같은 방식으로 변수를 선언할 수 있습니다 contravening 하지 못하게 사용 됩니다 `private`.  
  
 잠금 정책을 사용 하면 잠금 모든 요소에는 요소 형식에 따라 설정할 수 있습니다.  이것은 `SetLocks(Locks.None)` 요소를 처음 만들거나 파일에서 deserialize 할 때 항상 호출 됩니다.  
  
 그러나 정책 요소에 대 한 잠금이 수명 동안의 변화를 사용할 수 없습니다.  그 효과 얻기 위해 호출을 사용 해야 `SetLocks()`.  
  
 잠금 정책을 정의 하려면 다음을 수행 해야 합니다.  
  
-   구현 하는 클래스를 만들 <xref:Microsoft.VisualStudio.Modeling.Immutability.ILockingPolicy>.  
  
-   이 클래스는 DSL의 Docdata를 통해 사용할 수 있는 서비스를 추가 합니다.  
  
### 잠금 정책 정의 하기  
 <xref:Microsoft.VisualStudio.Modeling.Immutability.ILockingPolicy>다음 정의 다음과 같습니다.  
  
```  
public interface ILockingPolicy  
{  
  Locks RefineLocks(ModelElement element, Locks proposedLocks);  
  Locks RefineLocks(Partition partition, Locks proposedLocks);  
  Locks RefineLocks(Store store, Locks proposedLocks);  
}  
```  
  
 이러한 메서드를 호출할 때 `SetLocks()` 저장소, 파티션, 또는 모델 요소입니다.  각 방법에서, 제안 된 잠금 집합으로 제공 됩니다.  제안 된 집합을 반환할 수 있습니다 또는 추가한 잠금 뺄 수 있습니다.  
  
 예를 들면 다음과 같습니다.  
  
```  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Immutability;  
namespace Company.YourDsl.DslPackage // Change  
{  
  public class MyLockingPolicy : ILockingPolicy  
  {  
    /// <summary>  
    /// Moderate SetLocks(this ModelElement target, Locks locks)  
    /// </summary>  
    /// <param name="element">target</param>  
    /// <param name="proposedLocks">locks</param>  
    /// <returns></returns>  
    public Locks RefineLocks(ModelElement element, Locks proposedLocks)  
    {  
      // In my policy, users can never delete an element,  
      // and other developers cannot easily change that:  
      return proposedLocks | Locks.Delete);  
    }  
    public Locks RefineLocks(Store store, Locks proposedLocks)  
    {  
      // Only one user can change this model:  
      return Environment.UserName == "aUser"   
           ? proposedLocks : Locks.All;  
    }  
  
```  
  
 다른 코드를 호출 하는 경우에 사용자가 요소를 항상 삭제할 수 있는지 확인.`SetLocks(Lock.Delete):`  
  
 `return proposedLocks & (Locks.All ^ Locks.Delete);`  
  
 Myclass의 모든 요소의 모든 속성을 변경 하지 못하도록 하려면:  
  
 `return element is MyClass ?  (proposedLocks | Locks.Property) : proposedLocks;`  
  
### 정책으로 서비스를 사용할 수 있게 하려면  
 사용자 `DslPackage` 프로젝트, 다음 예제와 유사한 코드를 포함 하는 새 파일을 추가 합니다.  
  
```  
using Microsoft.VisualStudio.Modeling;  
using Microsoft.VisualStudio.Modeling.Immutability;  
namespace Company.YourDsl.DslPackage // Change  
{   
  // Override the DocData GetService() for this DSL.  
  internal partial class YourDslDocData // Change  
  {  
    /// <summary>  
    /// Custom locking policy cache.  
    /// </summary>  
    private ILockingPolicy myLockingPolicy = null;  
  
    /// <summary>  
    /// Called when a service is requested.  
    /// </summary>  
    /// <param name="serviceType">Service requested</param>  
    /// <returns>Service implementation</returns>  
    public override object GetService(System.Type serviceType)  
    {  
      if (serviceType == typeof(SLockingPolicy)   
       || serviceType == typeof(ILockingPolicy))  
      {  
        if (myLockingPolicy == null)  
        {  
          myLockingPolicy = new MyLockingPolicy();  
        }  
        return myLockingPolicy;  
      }  
      // Request is for some other service.  
      return base.GetService(serviceType);  
    }  
}  
```