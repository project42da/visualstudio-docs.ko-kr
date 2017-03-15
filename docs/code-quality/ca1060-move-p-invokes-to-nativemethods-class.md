---
title: "CA1060: P/Invoke를 NativeMethods 클래스로 이동 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MovePInvokesToNativeMethodsClass"
  - "CA1060"
helpviewer_keywords: 
  - "CA1060"
  - "MovePInvokesToNativeMethodsClass"
ms.assetid: 06686c8c-6ad3-42f7-a355-cbaefa347cfc
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 21
---
# CA1060: P/Invoke를 NativeMethods 클래스로 이동
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|MovePInvokesToNativeMethodsClass|  
|CheckId|CA1060|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 메서드가 플랫폼 호출 서비스를 사용하여 비관리 코드에 액세스하며 **NativeMethods** 클래스 중 하나의 멤버가 아닙니다.  
  
## 규칙 설명  
 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> 특성 또는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 `Declare` 키워드를 사용하여 정의된 메서드를 사용하여 표시된 것과 같은 플랫폼 호출 메서드는 비관리 코드에 액세스합니다.  이들 메서드는 다음 클래스 중 하나에 있어야 합니다.  
  
-   **NativeMethods** \- 이 클래스는 비관리 코드 권한에 대해 스택 워크를 제한하지 않습니다. \(<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName>가 이 클래스에 적용되어서는 안 됩니다.\) 이 클래스는 스택 워크가 수행되기 때문에 어디에서나 사용할 수 있는 메서드를 위한 것입니다.  
  
-   **SafeNativeMethods** \- 이 클래스는 비관리 코드 권한에 대해 스택 워크를 제한합니다. \(<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName>가 이 클래스에 적용됩니다.\) 이 클래스는 누가 호출하더라도 안전한 메서드를 위한 것입니다.  메서드가 모든 호출자에게 유해하지 않기 때문에 이들 메서드의 호출자는 사용이 안전한지 확인하기 위해 전체 보안 검토를 수행할 필요가 없습니다.  
  
-   **UnsafeNativeMethods** \- 이 클래스는 비관리 코드 권한에 대해 스택 워크를 제한합니다. \(<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute?displayProperty=fullName>가 이 클래스에 적용됩니다.\) 이 클래스는 잠재적으로 위험한 메서드를 위한 것입니다.  스택 워크가 수행되지 않으므로 이들 메서드의 모든 호출자는 전체 보안 검토를 수행하여 사용이 안전한지 확인해야 합니다.  
  
 이들 클래스는 `internal`\(Visual Basic의 경우 `Friend`\)로 선언되고 새 인스턴스가 만들어지지 않도록 하기 위해 private 생성자를 선언합니다.  이들 클래스의 메서드는 `static` 및 `internal`\(Visual Basic의 경우 `Shared` 및 `Friend`\)이어야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 메서드를 적절한 **NativeMethods** 클래스로 이동합니다.  대부분의 응용 프로그램에서는 P\/Invoke를 이름이 **NativeMethods**인 새 클래스로 이동하면 됩니다.  
  
 그러나 다른 응용 프로그램에서 사용하기 위한 라이브러리를 개발하는 경우에는 다른 두 클래스, 즉 **SafeNativeMethods** 및 **UnsafeNativeMethods**를 정의해야 할 수 있습니다.  이러한 클래스는 **NativeMethods** 클래스와 비슷하지만 **SuppressUnmanagedCodeSecurityAttribute**라는 특수한 특성을 사용하여 표시됩니다.  이 특성을 적용하면 런타임이 모든 호출자에게 **UnmanagedCode** 권한이 있는지를 확인하기 위한 전체 스택 워크를 수행하지 않으며  대개 시작 시에만 이 권한을 확인합니다.  확인이 수행되지 않기 때문에 이와 같은 관리되지 않는 메서드 호출에 대한 성능을 크게 향상시킬 수 있으며, 권한이 제한된 코드를 사용하여 이러한 메서드를 호출할 수도 있습니다.  
  
 그러나 이 특성을 사용할 때는 주의를 기울여야 합니다.  잘못 구현할 경우 심각한 보안 관련 문제가 발생할 수 있습니다.  
  
 메서드를 구현하는 방법에 대한 자세한 내용은 **NativeMethods** 예제, **SafeNativeMethods** 예제 및 **UnsafeNativeMethods** 예제를 참조하십시오.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 메서드를 선언합니다.  이 위반을 해결하려면 **RemoveDirectory** P\/Invoke를 P\/Invoke만을 보관하도록 지정된 해당 클래스로 이동해야 합니다.  
  
 [!code-vb[FxCop.Design.DllImportNativeMethods#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_1.vb)]
 [!code-cs[FxCop.Design.DllImportNativeMethods#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_1.cs)]  
  
## NativeMethods 예제  
  
### 설명  
 **NativeMethods** 클래스는 **SuppressUnmanagedCodeSecurityAttribute**를 사용하여 표시해서는 안 되기 때문에 이 클래스에 있는 P\/Invoke에는 **UnmanagedCode** 권한이 필요합니다.  대부분의 응용 프로그램은 로컬 컴퓨터에서 완전 신뢰로 실행되므로 일반적으로 이는 문제가 되지 않습니다.  그러나 재사용 가능한 라이브러리를 개발하는 경우에는 **SafeNativeMethods** 또는 **UnsafeNativeMethods** 클래스를 정의해야 할 수 있습니다.  
  
 다음 예제에서는 user32.dll에서 **MessageBeep** 함수를 래핑하는 **Interaction.Beep** 메서드를 보여 줍니다.  **MessageBeep** P\/Invoke는 **NativeMethods** 클래스에 배치됩니다.  
  
### 코드  
 [!code-cs[FxCop.Design.NativeMethods#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_2.cs)]
 [!code-vb[FxCop.Design.NativeMethods#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_2.vb)]  
  
## SafeNativeMethods 예제  
  
### 설명  
 모든 응용 프로그램에 안전하게 노출할 수 있으며 부정적인 결과를 유발하지 않는 P\/Invoke 메서드는 이름이 **SafeNativeMethods**인 클래스에 배치해야 합니다.  그러면 권한을 요청할 필요가 없으며 메서드를 호출하는 위치에 대해 크게 신경쓰지 않아도 됩니다.  
  
 다음 예제에서는 kernel32.dll에서 **GetTickCount** 함수를 래핑하는 **Environment.TickCount** 속성을 보여 줍니다.  
  
### 코드  
 [!code-vb[FxCop.Design.NativeMethodsSafe#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_3.vb)]
 [!code-cs[FxCop.Design.NativeMethodsSafe#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_3.cs)]  
  
## UnsafeNativeMethods 예제  
  
### 설명  
 안전하게 호출할 수 없고 부정적인 결과를 유발할 수 있는 P\/Invoke 메서드는 이름이 **UnsafeNativeMethods**인 클래스에 배치해야 합니다.  이러한 메서드는 실수로 사용자에게 노출하는 일이 없도록 엄격하게 확인해야 합니다.  규칙 [CA2118: SuppressUnmanagedCodeSecurityAttribute 사용을 검토하십시오.](../code-quality/ca2118-review-suppressunmanagedcodesecurityattribute-usage.md)를 사용하면 이 작업을 수행하는 데 도움이 됩니다.  또한 이 메서드는 사용되는 경우 **UnmanagedCode** 대신 다른 권한을 요청해야 합니다.  
  
 다음 예제에서는 user32.dll에서 **ShowCursor** 함수를 래핑하는 **Cursor.Hide** 메서드를 보여 줍니다.  
  
### 코드  
 [!code-vb[FxCop.Design.NativeMethodsUnsafe#1](../code-quality/codesnippet/VisualBasic/ca1060-move-p-invokes-to-nativemethods-class_4.vb)]
 [!code-cs[FxCop.Design.NativeMethodsUnsafe#1](../code-quality/codesnippet/CSharp/ca1060-move-p-invokes-to-nativemethods-class_4.cs)]  
  
## 참고 항목  
 [디자인 경고](../code-quality/design-warnings.md)