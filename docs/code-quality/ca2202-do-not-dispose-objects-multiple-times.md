---
title: "CA2202: 개체를 여러 번 삭제하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2202"
  - "Do not dispose objects multiple times"
  - "DoNotDisposeObjectsMultipleTimes"
helpviewer_keywords: 
  - "CA2202"
ms.assetid: fa85349a-cf1e-42c8-a86b-eacae1f8bd96
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2202: 개체를 여러 번 삭제하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotDisposeObjectsMultipleTimes|  
|CheckId|CA2202|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 메서드 구현에 같은 개체에 대해 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 또는 Dispose와 동일한 기능의 메서드\(예: 특정 형식의 Close\(\) 메서드\)를 여러 번 호출할 수 있는 코드 경로가 포함되어 있습니다.  
  
## 규칙 설명  
 올바르게 구현된 <xref:System.IDisposable.Dispose%2A> 메서드는 여러 번 호출해도 예외가 throw되지 않을 수 있습니다.  하지만 이것은 확실하게 보장되는 것이 아니므로 <xref:System.ObjectDisposedException?displayProperty=fullName>이 생성되지 않도록 하려면 개체에 대해 <xref:System.IDisposable.Dispose%2A>를 한 번만 호출해야 합니다.  
  
## 관련 규칙  
 [CA2000: 범위를 벗어나기 전에 개체를 삭제하십시오.](../code-quality/ca2000-dispose-objects-before-losing-scope.md)  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 코드 경로에 관계없이 개체에 대해 <xref:System.IDisposable.Dispose%2A>가 한 번만 호출되도록 구현을 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  개체에 대해 <xref:System.IDisposable.Dispose%2A>를 여러 번 호출해도 안전하다고 알려져 있을지라도 나중에 구현이 변경될 수 있습니다.  
  
## 예제  
 중첩된 `using` 문\(Visual Basic에서는 `Using`\)으로 인해 CA2202 경고 위반이 발생할 수 있습니다.  중첩 내부 `using` 문의 IDisposable 리소스에 외부 `using` 문의 리소스가 포함되어 있으면 중첩 리소스의 `Dispose` 메서드가 포함된 리소스를 해제합니다.  이 상황이 발생하면 외부 `using` 문의 `Dispose` 메서드가 두 번째로 리소스를 삭제하려고 합니다.  
  
 다음 예제에서는 using 문 밖에서 만든 <xref:System.IO.Stream> 개체가 `stream` 개체가 포함된 <xref:System.IO.StreamWriter> 개체의 Dispose 메서드에 있는 using 문 내부의 끝에서 해제됩니다.  외부 `using` 문 끝에서 `stream` 개체가 두 번 해제됩니다.  두 번째 릴리스는 CA2202 위반입니다.  
  
```  
using (Stream stream = new FileStream("file.txt", FileMode.OpenOrCreate))  
{  
    using (StreamWriter writer = new StreamWriter(stream))  
    {  
        // Use the writer object...  
    }  
}  
  
```  
  
## 예제  
 이 문제를 해결하려면 외부 `using` 문 대신 `try`\/`finally` 블록을 사용합니다.  `finally` 블록에서 `stream` 리소스가 null이 아닌지 확인합니다.  
  
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
  
## 참고 항목  
 <xref:System.IDisposable?displayProperty=fullName>   
 [삭제 패턴](../Topic/Dispose%20Pattern.md)