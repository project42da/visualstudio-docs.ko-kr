---
title: 'CA1060: 이동 P-호출를 NativeMethods 클래스로'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MovePInvokesToNativeMethodsClass
- CA1060
helpviewer_keywords:
- MovePInvokesToNativeMethodsClass
- CA1060
ms.assetid: 06686c8c-6ad3-42f7-a355-cbaefa347cfc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d6035553f8d3a4518fe99e7800a61f1b5921d947
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1060-move-pinvokes-to-nativemethods-class"></a>CA1060: P/Invoke를 NativeMethods 클래스로 이동
|||
|-|-|
|TypeName|MovePInvokesToNativeMethodsClass|
|CheckId|CA1060|
|범주|Microsoft.Design|
|변경 수준|주요 변경|

## <a name="cause"></a>원인
 플랫폼 호출 서비스를 사용 하 여 관리 되지 않는 코드에 액세스 하는 메서드와 중의 구성원이 아닙니다는 **NativeMethods** 클래스입니다.

## <a name="rule-description"></a>규칙 설명
 사용 하 여 표시 된 것과 같은 플랫폼 호출 메서드는 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> 특성 또는 사용 하 여 정의 된 메서드는는 `Declare` 키워드 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], 비관리 코드에 액세스 합니다. 이러한 메서드는 다음 클래스 중 하나 여야 합니다.

-   **NativeMethods** -이 클래스는 관리 되지 않는 코드 권한에 대 한 스택 워크를 억제 하지 않습니다. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> 이 클래스에 적용 하지 않아야 합니다.) 이 클래스는 스택 워크가 수행 됩니다 어디서 나 사용할 수 있는 방법에 대 한 합니다.

-   **SafeNativeMethods** -이 클래스를 비관리 코드 권한에 대해 스택 워크를 표시 하지 않습니다. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> 이 클래스에 적용 됩니다.) 이 클래스는 메서드를 호출 하는 사용자에 대해 안전 하 게 보호를 위한. 메서드는 모든 호출자에 게 무시 해도 때문에 사용이 안전한 지 확인 하려면 높은 수준의 보안 검토를 수행 하는 이러한 메서드의 호출자에 게 필요는 없습니다.

-   **UnsafeNativeMethods** -이 클래스를 비관리 코드 권한에 대해 스택 워크를 표시 하지 않습니다. (<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName> 이 클래스에 적용 됩니다.) 이 클래스는 잠재적으로 위험한 메서드는 있습니다. 이러한 메서드의 호출자는 사용이 안전한 없는 스택 워크가 수행 됩니다 되도록 전체 보안 검토를 수행 해야 합니다.

 이러한 클래스로 선언 됩니다 `internal` (`Friend`, Visual Basic에서) 새 인스턴스가 만들어지지 않도록 방지 하기 위해 private 생성자를 선언 하 고 있습니다. 이러한 클래스에 메서드 `static` 및 `internal` (`Shared` 및 `Friend` Visual basic에서).

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 적절 한 메서드를 이동 **NativeMethods** 클래스입니다. 대부분의 응용 프로그램에 대 한 P/Invoke 라는 새 클래스를 이동 **NativeMethods** 충분 합니다.

 그러나 다른 응용 프로그램에서 사용 하기 위해 라이브러리를 개발 하는 경우 고려해 야 라고 하는 다른 두 개의 클래스를 정의 **SafeNativeMethods** 및 **UnsafeNativeMethods**합니다. 이러한 클래스와 유사는 **NativeMethods** 클래스; 그러나 라고 하는 특수 한 특성을 사용 하 여 표시 됩니다 **SuppressUnmanagedCodeSecurityAttribute**합니다. 런타임이이 특성이 적용 되 면 모든 호출자에 게 되도록 전체 스택 워크를 수행 하지는 **UnmanagedCode** 권한. 대개 시작 시이 권한을 확인 합니다. 관리 되지 않는 이러한 방법에 대 한 호출 성능을 크게 향상 시킬 수를 확인 하지 때문에 코드는 이러한 메서드를 호출할 권한이 제한 된 수 있습니다.

 그러나 매우 주의 하 여이 특성을 사용 해야 합니다. 제대로 구현 된 경우 심각한 보안 관련 문제가 가질 수 있습니다.

 메서드를 구현 하는 방법에 대 한 정보를 참조 하십시오.는 **NativeMethods** 예제에서는 **SafeNativeMethods** 예제 및 **UnsafeNativeMethods** 예제입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 규칙에서는 경고를 표시해야 합니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙을 위반 하는 메서드를 선언 합니다. 위반을 해결 하는 **RemoveDirectory** 만 P/Invoke를 보유 하도록 설계 된 적절 한 클래스 P/Invoke를 이동 해야 합니다.

 [!code-vb[FxCop.Design.DllImportNativeMethods#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_1.vb)]
 [!code-csharp[FxCop.Design.DllImportNativeMethods#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_1.cs)]

## <a name="nativemethods-example"></a>NativeMethods 예제

### <a name="description"></a>설명
 때문에 **NativeMethods** 클래스를 사용 하 여 표시 하지 말아야 **SuppressUnmanagedCodeSecurityAttribute**, P/Invoke 그에 포함 된 내용의 **UnmanagedCode** 권한입니다. 대부분의 응용 프로그램을 로컬 컴퓨터에서 실행 되므로 완전 신뢰로 실행이 일반적으로 문제가 되지 않습니다. 그러나 재사용 가능한 라이브러리를 개발 하는 경우 고려해 야 정의 **SafeNativeMethods** 또는 **UnsafeNativeMethods** 클래스입니다.

 다음 예제와 **Interaction.Beep** 메서드를 래핑하는 **MessageBeep** user32.dll의 함수입니다. **MessageBeep** P/Invoke에 저장 됩니다는 **NativeMethods** 클래스입니다.

### <a name="code"></a>코드
 [!code-csharp[FxCop.Design.NativeMethods#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_2.cs)]
 [!code-vb[FxCop.Design.NativeMethods#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_2.vb)]

## <a name="safenativemethods-example"></a>SafeNativeMethods 예제

### <a name="description"></a>설명
 모든 응용 프로그램에 안전 하 게 노출할 수 있는 하 고 모든 파생 작업이 없는 P/Invoke 메서드가 라고 하는 클래스에 입력 해야 **SafeNativeMethods**합니다. 권한을 요청할 필요가 및에서 호출 되는 위치에 많은 주의를 기울여야 필요가 없습니다.

 다음 예제와 **Environment.TickCount** 속성을 래핑하는 **GetTickCount** kernel32.dll에서 함수입니다.

### <a name="code"></a>코드
 [!code-vb[FxCop.Design.NativeMethodsSafe#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_3.vb)]
 [!code-csharp[FxCop.Design.NativeMethodsSafe#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_3.cs)]

## <a name="unsafenativemethods-example"></a>UnsafeNativeMethods 예제

### <a name="description"></a>설명
 P/Invoke 메서드를 호출할 수 없습니다 안전 하 게 하 고 부작용을 일으킬 수 있는 명명 된 클래스에 입력 해야 **UnsafeNativeMethods**합니다. 노출 되지 않습니다 사용자에 게 실수로 있는지 확인 하려면 이러한 메서드를 엄격 하 게 확인 해야 합니다. 규칙 [CA2118: SuppressUnmanagedCodeSecurityAttribute 사용을 검토](../code-quality/ca2118-review-suppressunmanagedcodesecurityattribute-usage.md) 이 도움이 됩니다. 또는 메서드 대신 요구 하는 다른 권한이 있어야 **UnmanagedCode** 사용 하는 경우.

 다음 예제에서는 한 **Cursor.Hide** 메서드를 래핑하는 **ShowCursor** user32.dll의 함수입니다.

### <a name="code"></a>코드
 [!code-vb[FxCop.Design.NativeMethodsUnsafe#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_4.vb)]
 [!code-csharp[FxCop.Design.NativeMethodsUnsafe#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_4.cs)]

## <a name="see-also"></a>참고 항목
 [디자인 경고](../code-quality/design-warnings.md)