---
title: 'CA1901: P Invoke 선언은 이식 가능 해야'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
helpviewer_keywords:
- CA1901
- PInvokeDeclarationsShouldBePortable
ms.assetid: 90361812-55ca-47f7-bce9-b8775d3b8803
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ed9821d9b80309311a6fd108c4a29f52b2e882bf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="ca1901-pinvoke-declarations-should-be-portable"></a>CA1901: P/Invoke 선언은 이식 가능해야 합니다.
|||
|-|-|
|TypeName|PInvokeDeclarationsShouldBePortable|
|CheckId|CA1901|
|범주|Microsoft.Portability|
|변경 수준|주요-P/Invoke 어셈블리 외부에 표시 되 면입니다. 주요 변경 아님-P/Invoke 어셈블리 외부에서 볼 수 없는 경우.|

## <a name="cause"></a>원인
 이 규칙은 P/Invoke의 반환 값과 각 매개 변수의 크기를 계산 하 고 32 비트 및 64 비트 플랫폼에서 비관리 코드로 마샬링될 때 해당 크기가 올바른지 확인 합니다. 이 규칙의 가장 일반적인 위반 플랫폼에 관계 없이, 포인터 크기의 변수는 필수는 고정 크기의 정수를 전달 하는 것입니다.

## <a name="rule-description"></a>규칙 설명
 이 규칙을 위반 하는 다음 시나리오 중 하나에 발생 합니다.

-   로 입력 해야 하는 경우 반환 값 또는 매개 변수는 고정 크기 정수로 입력 됩니다는 `IntPtr`합니다.

-   반환 값 또는 매개 변수로 형식화 되는 `IntPtr` 고정 크기의 정수로 때 입력 해야 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 사용 하 여이 위반을 해결할 수 있습니다 `IntPtr` 또는 `UIntPtr` 대신 핸들을 나타내는 데 `Int32` 또는 `UInt32`합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 이 경고를 억제 하면 안 됩니다.

## <a name="example"></a>예제
 다음 예제에서는이 규칙 위반을 보여 줍니다.

```csharp
internal class NativeMethods
{
    [DllImport("shell32.dll", CharSet=CharSet.Auto)]
    internal static extern IntPtr ExtractIcon(IntPtr hInst,
        string lpszExeFileName, IntPtr nIconIndex);
}
```

 이 예제에서는 `nIconIndex` 로 매개 변수는 선언는 `IntPtr`, 32 비트 플랫폼 및 64 비트 플랫폼에서는 8 바이트에 넓은 4 바이트입니다. 관리 되지 않는 선언 함을 확인할 수 있습니다 `nIconIndex` 모든 플랫폼에서 부호 없는 4 바이트 정수입니다.

```csharp
HICON ExtractIcon(HINSTANCE hInst, LPCTSTR lpszExeFileName,
    UINT nIconIndex);
```

## <a name="example"></a>예제
 위반을 해결 하려면 다음에 선언을 변경 합니다.

```csharp
internal class NativeMethods{
    [DllImport("shell32.dll", CharSet=CharSet.Auto)] 
    internal static extern IntPtr ExtractIcon(IntPtr hInst,
        string lpszExeFileName, uint nIconIndex);
}
```

## <a name="see-also"></a>참고 항목
 [Portability Warnings](../code-quality/portability-warnings.md)