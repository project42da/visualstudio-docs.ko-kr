---
title: 'CA1063: IDisposable을 올바르게 구현하십시오.'
ms.date: 02/12/2018
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ImplementIDisposableCorrectly
- CA1063
helpviewer_keywords:
- CA1063
- ImplementIDisposableCorrectly
ms.assetid: 12afb1ea-3a17-4a3f-a1f0-fcdb853e2359
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9205c20730681969550c3a2368e6ec889056648b
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca1063-implement-idisposable-correctly"></a>CA1063: IDisposable을 올바르게 구현하십시오.

|||
|-|-|
|TypeName|ImplementIDisposableCorrectly|
|CheckId|CA1063|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

`IDisposable` 올바르게 구현 되지 않았습니다. 이 문제에 대 한 일부의 이유는 다음과 같습니다.

- IDisposable는 클래스에서 다시 구현입니다.

- 마무리 다시 재정의 됩니다.

- Dispose는 재정의 됩니다.

- Dispose ()는 공용이 날인이 찍 또는 Dispose를 명명 합니다.

- Dispose(bool) 보호, 가상 또는 봉인 되지 않습니다.

- Unsealed 형식의 dispose () Dispose(true) 호출 해야 합니다.

- 봉인 되지 않은 형식에 대 한 Finalize 구현 중 하나 또는 모두가 Dispose(bool) 또는 사례 클래스 종료자를 호출 하지 않습니다.

이러한 패턴 중 하나를 위반 하면이 경고가 트리거됩니다.

선언 및 IDisposable 인터페이스를 구현 하는 봉인 되지 않은 모든 형식은 고유한 보호 된 가상 void Dispose(bool) 메서드를 제공 해야 합니다. Dispose () Dipose(true)를 호출 해야 하 고 Finalize와 호출 해야 합니다. 선언 및 IDisposable 인터페이스를 구현 하는 봉인 되지 않은 형식을 만드는 경우 Dispose(bool)를 정의 하 고 메서드를 호출 해야 합니다. 자세한 내용은 참조 [관리 되지 않는 리소스 정리](/dotnet/standard/garbage-collection/unmanaged) 에 [.NET Framework 디자인 지침](/dotnet/standard/design-guidelines/index)합니다.

## <a name="rule-description"></a>규칙 설명

모든 IDisposable 형식은 Dispose 패턴을 올바르게 구현해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결 하는 방법

코드를 검사 하 고이 위반 문제를 해결 하는 다음과 같은 해결 방법이 결정 합니다.

- {0}에 의해 구현 되 고 대신 기본 클래스 Dispose 구현을 재정의 하는 인터페이스 목록에서 IDisposable을 제거 합니다.

- {0} 형식에서 종료자를 제거 하 고 Dispose (bool disposing)를 재정의 '삭제'가 false 코드 경로에서 종료 논리를 배치 합니다.

- Dispose (bool disposing)를 재정의 {0} 제거 입력 하 고 '삭제'가 true 코드 경로에 삭제 논리를 저장 합니다.

- 해당 {0}는 public 및 sealed로 선언 된 것을 확인 합니다.

- 'Dispose' {0}를 바꾸고 public 및 sealed로 선언 되어 있는지 확인 합니다.

- 해당 {0}는 protected로 선언 되어 있는지 확인 하 고, 가상, 봉인 되지 않은 확인 하십시오.

- Dispose(true), 호출 다음 GC 호출 되도록 {0}를 수정 합니다. 현재 개체 인스턴스에 대해 SuppressFinalize ('this' 또는 'm e'에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)])를 반환 합니다.

- 다음을 반환 하 고와 있도록 {0}를 수정 합니다.

- 선언 및 IDisposable 인터페이스를 구현 하는 봉인 되지 않은 형식을 만드는 경우 IDisposable 구현이 단원의 앞에서 설명한 패턴을 따르는지를 확인 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서는 경고를 표시해야 합니다.

## <a name="pseudo-code-example"></a>의사 코드 예제

다음 의사 코드 및 네이티브 리소스를 관리 하는 사용 하는 클래스에 Dispose(bool)을 구현 하는 방법의 일반적인 예제를 제공 합니다.

```csharp
public class Resource : IDisposable
{
    private IntPtr nativeResource = Marshal.AllocHGlobal(100);
    private AnotherResource managedResource = new AnotherResource();

    // Dispose() calls Dispose(true)
    public void Dispose()
    {
        Dispose(true);
        GC.SuppressFinalize(this);
    }

    // NOTE: Leave out the finalizer altogether if this class doesn't
    // own unmanaged resources itself, but leave the other methods
    // exactly as they are.
    ~Resource()
    {
        // Finalizer calls Dispose(false)
        Dispose(false);
    }

    // The bulk of the clean-up code is implemented in Dispose(bool)
    protected virtual void Dispose(bool disposing)
    {
        if (disposing)
        {
            // free managed resources
            if (managedResource != null)
            {
                managedResource.Dispose();
                managedResource = null;
            }
        }
        // free native resources if there are any.
        if (nativeResource != IntPtr.Zero)
        {
            Marshal.FreeHGlobal(nativeResource);
            nativeResource = IntPtr.Zero;
        }
    }
}
```