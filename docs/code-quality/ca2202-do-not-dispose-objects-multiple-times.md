---
title: 'CA2202: 개체 여러 번 삭제 하지 마십시오 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2202
- Do not dispose objects multiple times
- DoNotDisposeObjectsMultipleTimes
helpviewer_keywords:
- CA2202
ms.assetid: fa85349a-cf1e-42c8-a86b-eacae1f8bd96
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3439739626a81636020a6b645ba5820a59747f2d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca2202-do-not-dispose-objects-multiple-times"></a>CA2202: 개체를 여러 번 삭제하지 마십시오.
|||  
|-|-|  
|TypeName|DoNotDisposeObjectsMultipleTimes|  
|CheckId|CA2202|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 여러 번 호출 될 수 있는 코드 경로가 메서드 구현 포함 되어 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 또는 Dispose와 동일한 동일한 개체에 대 한 일부 형식에 대 한 close () 메서드와 같은 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 정확 하 게 구현 A <xref:System.IDisposable.Dispose%2A> 메서드는 예외를 throw 하지 않고 여러 번 호출할 수 있습니다. 그러나이 확실 하지 및 발생을 방지 하려면 한 <xref:System.ObjectDisposedException?displayProperty=fullName> 호출 하지 않아야 <xref:System.IDisposable.Dispose%2A> 개체에 대 한 번 이상.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA2000: 범위를 벗어나기 전에 개체를 삭제하십시오.](../code-quality/ca2000-dispose-objects-before-losing-scope.md)  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 코드 경로가 있으므로 관계 없이 구현을 변경 <xref:System.IDisposable.Dispose%2A> 개체에 대해 한 번만 호출 됩니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다. 경우에 <xref:System.IDisposable.Dispose%2A> 개체가 여러 번 안전 하 게 호출 가능한 것으로 알려져에 대 한 구현 나중에 변경 될 수 있습니다.  
  
## <a name="example"></a>예  
 중첩 된 `using` 문 (`Using` Visual basic에서) CA2202 경고 위반이 발생할 수 있습니다. 경우 중첩 내부 IDisposable 리소스 `using` 외부의 리소스를 포함 하는 문을 `using` 문에서 `Dispose` 중첩된 리소스의 메서드는 포함 된 리소스를 해제 합니다. 이러한 상황이 발생 하는 경우는 `Dispose` 메서드 외부의 `using` 문에서 리소스를 두 번째로를 삭제 하려고 합니다.  
  
 다음 예제에서는 <xref:System.IO.Stream> 외부에서 생성 된 개체의 Dispose 메서드가에서 문을 사용 하는 내부 끝날 때 해제가 문을 사용 하는 <xref:System.IO.StreamWriter> 포함 된 개체는 `stream` 개체입니다. 외부의 끝에 `using` 문에서 `stream` 개체를 두 번 해제 합니다. 두 번째 릴리스 CA2202에 위반 됩니다.  
  
```  
using (Stream stream = new FileStream("file.txt", FileMode.OpenOrCreate))  
{  
    using (StreamWriter writer = new StreamWriter(stream))  
    {  
        // Use the writer object...  
    }  
}  
  
```  
  
## <a name="example"></a>예  
 이 문제를 해결 하려면 사용을 `try` / `finally` 외부 대신 블록 `using` 문. 에 `finally` 차단 되어 있는지 확인 합니다는 `stream` 리소스가 null이 됩니다.  
  
```  
Stream stream = null;  
try  
{  
    stream = new FileStream("file.txt", FileMode.OpenOrCreate);  
    using (StreamWriter writer = new StreamWriter(stream))  
    {  
        stream = null;  
        // Use the writer object...  
    }  
}  
finally  
{  
    if(stream != null)  
        stream.Dispose();  
}  
  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IDisposable?displayProperty=fullName>   
 [삭제 패턴](/dotnet/standard/design-guidelines/dispose-pattern)