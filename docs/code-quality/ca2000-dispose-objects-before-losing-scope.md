---
title: "CA2000: 범위를 벗어나기 전에 개체를 삭제하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2000"
  - "Dispose objects before losing scope"
  - "DisposeObjectsBeforeLosingScope"
helpviewer_keywords: 
  - "CA2000"
  - "DisposeObjectsBeforeLosingScope"
ms.assetid: 0c3d7d8d-b94d-46e8-aa4c-38df632c1463
caps.latest.revision: 32
caps.handback.revision: 32
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2000: 범위를 벗어나기 전에 개체를 삭제하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DisposeObjectsBeforeLosingScope|  
|CheckId|CA2000|  
|범주|Microsoft.Reliability|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 <xref:System.IDisposable> 형식의 지역 개체가 만들어졌지만 해당 개체에 대한 모든 참조가 범위를 벗어나기 전에 개체가 삭제되지 않습니다.  
  
## 규칙 설명  
 삭제 가능한 개체에 대한 모든 참조가 범위를 벗어나기 전에 삭제 가능한 개체가 명시적으로 삭제되지 않으면 가비지 수집기가 개체의 종료자를 실행할 때 비활성화 시점에서 개체가 삭제됩니다.  개체 종료자의 실행을 방지하는 예외적인 이벤트가 발생할 수 있으므로 대신 개체를 명시적으로 삭제해야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 개체에 대한 모든 참조가 범위를 벗어나기 전에 개체에 대해 <xref:System.IDisposable.Dispose%2A>를 호출합니다.  
  
 `using` 문\([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 `Using`\)을 사용하여 `IDisposable`을 구현하는 개체를 래핑할 수 있습니다.  이 방법으로 래핑한 개체는 `using` 블록의 끝에서 자동으로 삭제됩니다.  
  
 다음 경우에는 using 문이 IDisposable 개체를 보호하는 데 충분하지 않고 CA2000가 발생할 수 있습니다.  
  
-   삭제 가능한 개체를 반환하려면 개체가 using 블록 외부의 try\/finally 블록에 작성되어야 합니다.  
  
-   using 문 생성자에서 삭제 가능한 개체의 멤버를 초기화하지 않아야 합니다.  
  
-   한 가지 예외 처리기에 의해서만 보호되는 중첩 생성자입니다.  예를 들면 다음과 같습니다.  
  
    ```  
    using (StreamReader sr = new StreamReader(new FileStream("C:\myfile.txt", FileMode.Create)))  
    { ... }  
    ```  
  
     StreamReader 개체의 생성 실패로 인해 FileStream 개체를 닫지 못하게 될 수 있으므로 CA2000이 발생합니다.  
  
-   동적 개체는 IDisposable 개체의 Dispose 패턴을 구현하기 위해 섀도 개체를 사용해야 합니다.  
  
## 경고를 표시하지 않는 경우  
 경고를 발생시킨 메서드 IDisposable 개체가 래핑하는 개체를 반환하는 경우 혹은 \( <xref:System.IO.Stream.Close%2A> 같은\) `Dispose` 개체의 메서드로 불려오지 않는다면 규칙으로 부터 경고를 억압하지 마세요.  
  
## 관련 규칙  
 [CA2213: 삭제 가능한 필드는 삭제해야 합니다.](../code-quality/ca2213-disposable-fields-should-be-disposed.md)  
  
 [CA2202: 개체를 여러 번 삭제하지 마십시오.](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)  
  
## 예제  
 삭제 가능한 개체를 반환하는 메서드를 구현하는 경우 catch 블록 없이 try\/finally 블록을 사용하여 개체가 삭제되는지 확인합니다.  try\/finally 블록을 사용하여 오류 지점에서 예외가 발생하는 것을 허용하며 해당 개체가 삭제되도록 합니다.  
  
 OpenPort1 메서드에서 ISerializable 개체 SerialPort를 열려고 호출하거나 SomeMethod를 호출하면 실패할 수 있습니다.  이 구현에서는 CA2000 경고가 발생합니다.  
  
 OpenPort2 메서드에 두 개의 SerialPort 개체가 선언되고 null로 설정됨:  
  
-   메서드 작업의 성공 여부를 테스트하는 데 사용되는 `tempPort`입니다.  
  
-   메서드의 반환 값에 사용되는 `port`입니다.  
  
 `tempPort`가 생성되어 `try` 블록에 열리며 기타 필요한 작업이 동일한 `try` 블록에서 수행됩니다.  `try` 블록 끝에서 열린 포트가 반환될 `port` 개체에 할당되고 `tempPort` 개체는 `null`로 설정됩니다.  
  
 `finally` 블록은 `tempPort`의 값을 확인합니다.  null이 아닌 경우 메서드 작업이 실패하고 리소스가 해제되도록 `tempPort`가 닫힙니다.  메서드 작업이 성공하면 반환된 포트 개체가 열린 SerialPort 개체를 포함하고, 작업이 실패하면 null입니다.  
  
 [!code-vb[FxCop.Reliability.CA2000.DisposeObjectsBeforeLosingScope#1](../code-quality/codesnippet/VisualBasic/ca2000-dispose-objects-before-losing-scope_1.vb)]
 [!code-vb[FxCop.Reliability.CA2000.DisposeObjectsBeforeLosingScope#1](../code-quality/codesnippet/VisualBasic/ca2000-dispose-objects-before-losing-scope_1.vb)]
 [!code-cs[FxCop.Reliability.CA2000.DisposeObjectsBeforeLosingScope#1](../code-quality/codesnippet/CSharp/ca2000-dispose-objects-before-losing-scope_1.cs)]  
  
## 예제  
 기본적으로 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러에는 오버플로에 대한 모든 산술 연산자 검사가 있습니다.  따라서 Visual Basic 산술 연산은 <xref:System.OverflowException>을 throw할 수 있습니다.  이로 인해 CA2000 같은 규칙에서 예기치 않은 위반이 발생할 수 있습니다.  예를 들어, Visual Basic 컴파일러가 StreamReader를 삭제하지 않도록 하는 예외를 throw할 수 있는 추가에 대해 오버플로 확인 명령을 내보내고 있기 때문에 다음 CreateReader1 함수가 CA2000 위반을 생성합니다.  
  
 이 문제를 해결하려면 프로젝트의 Visual Basic 컴파일러에서 오버플로 검사 내보내기를 비활성화하거나 다음 CreateReader2 함수 같은 코드를 수정할 수 있습니다.  
  
 오버플로 검사 내보내기를 비활성화하려면 솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  **컴파일**을 클릭하고 **고급 컴파일 옵션**을 클릭한 다음 **정수 오버플로 검사 해제**를 선택합니다.  
  
 [!CODE [FxCop.Reliability.CA2000.DisposeObjectsBeforeLosingScope.VBOverflow#1](FxCop.Reliability.CA2000.DisposeObjectsBeforeLosingScope.VBOverflow#1)]  
  
## 참고 항목  
 <xref:System.IDisposable>   
 [삭제 패턴](../Topic/Dispose%20Pattern.md)