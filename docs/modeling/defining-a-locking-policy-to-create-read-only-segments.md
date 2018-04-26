---
title: 잠금 정책을 정의하여 읽기 전용 세그먼트 만들기
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 48a9ebdf7df8e03813e1819e907c9aab2d558ee0
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="defining-a-locking-policy-to-create-read-only-segments"></a>잠금 정책을 정의하여 읽기 전용 세그먼트 만들기
불변성 API는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Visualization and Modeling SDK 프로그램 잠금 일부 또는 전체 도메인 특정 언어 (DSL) 모델을 읽을 있지만 변경 되지 않습니다 수 있도록 허용 합니다. 이 읽기 전용 옵션이 사용할 수, 예를 들어 사용자가 동료 들이 주석 달기 및 DSL 모델 검토를 요청할 수 있지만가 원래 변경할 거부할 수 있도록 합니다.

 정의할 수는 또한를 사용 하는 DSL의 작성자는 *잠금 정책을 합니다.* 잠금 정책 허용, 허용 되지 않음 또는 필수 되는 잠금을 정의 합니다. 예를 들어 하는 DSL을 게시할 때 새 명령을 사용 하 여 확장 하는 타사 개발자가 요청할 수 있습니다. 하지만 모델의 지정 된 부분의 읽기 전용 상태를 변경 하지 못하도록 잠금 정책을 사용할 수도 있습니다.

> [!NOTE]
>  리플렉션을 사용 하 여 잠금 정책을 우회할 수 있습니다. 이 다른 공급 업체의 개발자는 명확한 경계를 제공 하지만 강력한 보안을 제공 하지 않습니다.

 자세한 내용 및 예제는 Visual Studio에서 사용할 수 있는 [Visualization and Modeling SDK](https://code.msdn.microsoft.com/Visualization-and-Modeling-313535db) 웹 사이트입니다.

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="setting-and-getting-locks"></a>설정 및 잠금 가져오기
 저장소, 파티션 또는 개별 요소에 대해 잠금을 설정할 수 있습니다. 예를 들어이 문은 모델 요소를 삭제 하는 하며 수의 속성 변경 되지 않도록 하지 못할 수도 됩니다.

```
using Microsoft.VisualStudio.Modeling.Immutability; ...
element.SetLocks(Locks.Delete | Locks.Property);
```

 관계, 요소 만들기, 파티션 및 역할에 다시 정렬 링크 간에 이동 하는 변경할 수 없도록 다른 잠금 값을 사용할 수 있습니다.

 잠금에는 프로그램 코드 및 사용자 작업에 모두 적용 됩니다. 프로그램 코드를 변경 하려고 하는 경우는 `InvalidOperationException` throw 됩니다. 잠금이 취소 또는 다시 실행 작업에서 무시 됩니다.

 요소에 하는지 모든 잠금이 지정된 된 집합을 사용 하 여 검색할 수 있는 `IsLocked(Locks)` 를 사용 하 여 현재 집합의 요소에 대 한 잠금 가져올 수 있습니다 `GetLocks()`합니다.

 트랜잭션을 사용 하지 않고 잠금을 설정할 수 있습니다. 잠금 데이터베이스 저장소의 일부가 아닙니다. 저장소에서 값의 변경에 따른에서 잠금을 설정한 경우 예를 들어 OnValueChanged에서 허용 해야 변경 내용을 실행 취소 작업의 일부분인.

 이러한 메서드는에 정의 된 확장 메서드는 <xref:Microsoft.VisualStudio.Modeling.Immutability> 네임 스페이스입니다.

### <a name="locks-on-partitions-and-stores"></a>파티션 및 저장소에 대 한 잠금
 잠금이는 파티션 및 저장소에 적용할 수도 있습니다. 잠금을 파티션에 설정 된 파티션에 있는 모든 요소에 적용 됩니다. 따라서 예를 들어 다음 문은 하면 파티션의 모든 요소 자신의 잠금 상태에 관계 없이 삭제 되지 않도록 없습니다. 그럼에도 불구 하 고 기타 잠금 수와 같은 `Locks.Property` 여전히 개별 요소에 설정할 수 없습니다.

```
partition.SetLocks(Locks.Delete);
```

 저장소에 설정 하는 잠금을 파티션과 요소에 해당 잠금 설정에 관계 없이 모든 해당 요소에 적용 됩니다.

### <a name="using-locks"></a>잠금을 사용 하 여
 다음 예와 같이 체계를 구현 하는 잠금을 사용할 수 있습니다.

-   모든 요소와 메모를 표시 하는 것을 제외 하 고 관계에 대 한 변경을 허용 하지 않습니다. 따라서 사용자가 모델을 변경 하지 않고 주석을 달 수 있습니다.

-   다이어그램 파티션에 허용 하지만 기본 파티션에 대 한 변경 내용을 허용 되지 않습니다. 사용자는 다이어그램을 다시 정렬할 수 있지만 기본 모델을 변경할 수 없습니다.

-   별도 데이터베이스에 등록 된 사용자 그룹을 제외 하 고 저장소에 변경 내용을 허용 하지 않습니다. 다른 사용자에 대 한 다이어그램 및 모델은 읽기 전용입니다.

-   다이어그램의 부울 속성을 설정 하는 경우 모델의 변경 내용을 허용 되지 않고 true로 합니다. 해당 속성을 변경 하는 메뉴 명령을 제공 합니다. 이렇게 하면 사용자가 이루어지지 않으면 실수로 변경 됩니다.

-   속성 변경은 허용 하지만 추가 및 삭제의 요소와 특정 클래스의 관계를 허용 하지 않습니다. 이로써 사용자에 고정된 폼 속성을 채울 수 있습니다.

## <a name="lock-values"></a>잠금 값
 잠금은 저장소, 파티션 또는 개별 모델 요소에서 설정할 수 있습니다. 잠금이 0이 `Flags` 열거형:를 사용 하 여 해당 값을 결합할 수 있습니다 '&#124;'.

-   ModelElement의 잠금에는 항상 해당 파티션 잠금이 포함합니다.

-   잠금이 파티션 저장소의 잠금 항상 포함 됩니다.

 파티션을에 잠금을 설정 하 고 또는 저장 하 고, 동시에 개별 요소에 대 한 잠금을 사용 하지 않도록 설정할 수 없습니다.

|값|즉 하는 경우 `IsLocked(Value)` true|
|-----------|------------------------------------------|
|없음|제한이 없습니다.|
|속성|도메인 요소 속성을 변경할 수 없습니다. 관계의 도메인 클래스의 역할을 통해 생성 되는 속성에는 적용 되지 않습니다.|
|추가|파티션의 새 포인트 및 링크를 만들 수 없습니다 하거나 저장 합니다.<br /><br /> 에 적용할 수 없는 `ModelElement`합니다.|
|이동|요소 경우 파티션 간에 이동할 수 없습니다 `element.IsLocked(Move)` 가 true 인 경우 `targetPartition.IsLocked(Move)` 가 true입니다.|
|삭제|이 잠금은 요소 자체에 설정 되거나 있는 요소 중 하나에서 삭제 전파, 포함 된 요소 및 모양과 같은 요소를 삭제할 수 없습니다.<br /><br /> 사용할 수 있습니다 `element.CanDelete()` 요소를 삭제할 수 있는지 여부를 검색 합니다.|
|순서 변경|에 한 roleplayer 링크의 순서를 변경할 수 없습니다.|
|RolePlayer|이 요소에서 생성 되는 링크의 집합을 변경할 수 없습니다. 예를 들어,이 요소 아래에 새 요소를 포함할 수 없습니다. 이 요소는 대상 링크는 영향을 주지 않습니다.<br /><br /> 이 요소는 링크를 해당 원본과 대상 영향 받지 않습니다.|
|모두|다른 값의 비트 Or입니다.|

## <a name="locking-policies"></a>잠금 정책
 DSL의 작성자를 정의할 수 있습니다는 *잠금 정책을*합니다. 잠금 정책을 특정 잠금을 설정 또는 특정 잠금을 설정 해야 하도록 요구 하는 것에서 수 없도록 SetLocks(), 작업을 조정 합니다. 사용자 또는 개발자가 동일한 방식으로 변수를 선언할 수는 DSL의 용도 실수로 contravening에서 권장 하는 잠금 정책을 사용 하면 일반적으로 `private`합니다.

 요소의 형식에 종속 된 모든 요소에 대해 잠금을 설정 하는 잠금 정책을 사용할 수 있습니다. 때문에 이것이 `SetLocks(Locks.None)` 은 요소를 처음 만들거나 파일에서 deserialize 할 때 항상 호출 됩니다.

 그러나 요소에 대 한 잠금이 수명 동안의 변경 하는 정책을 사용할 수 없습니다. 에 대 한 호출을 사용 해야 해당 효과 얻기 위해 `SetLocks()`합니다.

 잠금 정책을 정의 하려면 해야 합니다.

-   <xref:Microsoft.VisualStudio.Modeling.Immutability.ILockingPolicy>를 구현하는 클래스를 만듭니다.

-   이 클래스 DSL의 DocData를 통해 사용할 수 있는 서비스를 추가 합니다.

### <a name="to-define-a-locking-policy"></a>잠금 정책을 정의 하려면
 <xref:Microsoft.VisualStudio.Modeling.Immutability.ILockingPolicy> 다음 정의 있습니다.

```
public interface ILockingPolicy
{
  Locks RefineLocks(ModelElement element, Locks proposedLocks);
  Locks RefineLocks(Partition partition, Locks proposedLocks);
  Locks RefineLocks(Store store, Locks proposedLocks);
}
```

 이러한 메서드를 호출할 때 호출 됩니다 `SetLocks()` 저장소, 파티션 또는 모델 요소에 있습니다. 각 방법에서는 제안 된 잠금 집합이 함께 제공 됩니다. 제안 된 집합을 반환할 수 있습니다 또는 추가 하 고 잠금을 뺄 수 있습니다.

 예를 들어:

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

 다른 코드를 호출 하는 경우에 사용자가 요소를 삭제할 수 있는지 확인 하려면 `SetLocks(Lock.Delete):`

 `return proposedLocks & (Locks.All ^ Locks.Delete);`

 MyClass의 모든 요소의 모든 속성의 변경 허용 되지 않습니다.

 `return element is MyClass ? (proposedLocks | Locks.Property) : proposedLocks;`

### <a name="to-make-your-policy-available-as-a-service"></a>정책에를 서비스로 사용할 수 있도록 하려면
 사용자 `DslPackage` 프로젝트에서 다음 예제와 유사한 코드를 포함 하는 새 파일을 추가 합니다.

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
