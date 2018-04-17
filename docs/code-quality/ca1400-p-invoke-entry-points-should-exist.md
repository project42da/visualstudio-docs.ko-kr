---
title: ': P Invoke 진입점 ca1400 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1400
- PInvokeEntryPointsShouldExist
helpviewer_keywords:
- PInvokeEntryPointsShouldExist
- CA1400
ms.assetid: 1d64e470-7b2f-4cca-8fb0-ac92829e6332
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 53e677308d5dcb5e89b410e4ab06a33a6c0caab4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1400-pinvoke-entry-points-should-exist"></a>CA1400: P/Invoke 진입점이 있어야 합니다.
|||  
|-|-|  
|TypeName|PInvokeEntryPointsShouldExist|  
|CheckId|CA1400|  
|범주|Microsoft.Interoperability|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 Public 또는 protected 메서드가로 표시 된 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>합니다. 관리되지 않는 라이브러리를 찾을 수 없거나 해당 메서드와 라이브러리의 함수가 일치하지 않습니다. 규칙을 찾을 수 없으면 메서드 이름을 지정 된 대로 정확 하 게 찾습니다 ANSI 또는 와이드 문자 버전의 메서드에 'A' 또는 'W'를 사용 하 여 메서드 이름을 접미사로 붙여 서. 일치 하는 항목이 __stdcall 이름 형식을 사용 하 여 함수를 찾으려고 시도 (_MyMethod@12, 여기서 12는 인수의 길이 나타냄). 일치 하는 항목이 메서드 이름 '#'로 시작 하는 경우 규칙은 함수에 대 한 이름 대신 서 수 참조로 검색 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 컴파일 타임 검사 안 함은 사용할 수 있는지 확인 하기로 표시 된 메서드가 <xref:System.Runtime.InteropServices.DllImportAttribute> 참조 된 관리 되지 않는 DLL에 있는 합니다. 지정된 된 이름을 가진 함수가 라이브러리에 있거나 메서드에 대 한 인수는 함수 인수를 일치 하지 않습니다, 공용 언어 런타임 예외를 throw 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 이러한 변수가 있는 메서드를 수정는 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성입니다. 관리 되지 않는 라이브러리 있고 메서드를 포함 하는 어셈블리와 동일한 디렉터리에 있는지 확인 합니다. 존재 하 고 제대로 참조 라이브러리 이면 메서드 이름, 반환 형식 및 인수 서명 라이브러리 함수와 일치 하는지 확인 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 관리 되지 않는 라이브러리 참조 하는 관리 되는 어셈블리와 동일한 디렉터리에 있으면이 규칙에서는 경고를에서 표시 하지 마십시오. 관리 되지 않는 라이브러리를 찾을 수 없는 경우에는이 규칙에서 경고를 표시 하지 않아도 안전 수도 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 규칙을 위반 하는 형식을 보여 줍니다. 라고 하는 함수가 `DoSomethingUnmanaged` kernel32.dll에서 발생 합니다.  
  
 [!code-csharp[FxCop.Interoperability.DLLExists#1](../code-quality/codesnippet/CSharp/ca1400-p-invoke-entry-points-should-exist_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>