---
title: 'CA2000: 범위를 벗어나기 전에 개체를 삭제하십시오.'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2000
- Dispose objects before losing scope
- DisposeObjectsBeforeLosingScope
helpviewer_keywords:
- CA2000
- DisposeObjectsBeforeLosingScope
ms.assetid: 0c3d7d8d-b94d-46e8-aa4c-38df632c1463
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 436dec37598aac31d0de2e7cb495f49b2a0bf41e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="ca2000-dispose-objects-before-losing-scope"></a>CA2000: 범위를 벗어나기 전에 개체를 삭제하십시오.
|||
|-|-|
|TypeName|DisposeObjectsBeforeLosingScope|
|CheckId|CA2000|
|범주|Microsoft.Reliability|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인
 로컬 개체는 <xref:System.IDisposable> 형식을 만들 하지만 개체에 대 한 모든 참조가 범위를 벗어나기 전에 개체 삭제 되지 않습니다.

## <a name="rule-description"></a>규칙 설명
 모든 참조가 범위를 벗어나기 전에 삭제 가능한 개체를 명시적으로 삭제 되지 않습니다, 하는 경우 가비지 수집기가 개체의 종료자를 실행 하는 경우 임의의 시점에는 개체가 삭제 됩니다. 예외 이벤트가 발생할 수 있으므로 되지 못하도록 하는 종료 자가 실행에서 개체의 개체를 명시적으로 삭제 대신 합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법
 이 규칙 위반 문제를 해결 하려면 호출 <xref:System.IDisposable.Dispose%2A> 모든 참조가 범위를 벗어나기 전에 개체에 있습니다.

 사용할 수 있는 참고는 `using` 문 (`Using` 에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)])를 구현 하는 개체를 래핑하 `IDisposable`합니다. 이런이 방식으로 래핑된 개체를 닫으면 자동으로 삭제 됩니다는 `using` 블록입니다.

 다음은 몇 가지 상황 여기서는 IDisposable 개체를 보호 하는 데 충분 하지 않습니다 문을 사용 하 고 적용 되려면 CA2000 발생할 수 있습니다.

-   삭제 가능한 개체 하려면 수행 해야 하는 개체를 사용 하 여 외부 try/finally 블록에 구성 되어 블록입니다.

-   삭제 가능한 개체에 대 한 초기화를 수행 하지 using의 생성자에 문의 합니다.

-   한 가지 예외 처리기로만 보호 되는 생성자를 중첩 합니다. 예를 들어 개체에 적용된

    ```csharp
    using (StreamReader sr = new StreamReader(new FileStream("C:\myfile.txt", FileMode.Create)))
    { ... }
    ```

     CA2000 절대로 닫히지 되 고 FileStream 개체 StreamReader 개체의 생성에 오류가 발생할 수 있기 때문에 발생 하도록 하면 됩니다.

-   동적 개체는 IDisposable 개체 삭제 패턴을 구현 하는 섀도 개체를 사용 해야 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우
 `Dispose`와 같은 <xref:System.IO.Stream.Close%2A>를 호출하는 개체에 대해 메서드를 호출하지 않은 경우나 경고를 발생시킨 메서드가 사용자의 개체를 래핑하는 IDisposable 개체를 반환하는 경우 이 규칙에서 경고를 표시해야 합니다.

## <a name="related-rules"></a>관련된 규칙
 [CA2213: 삭제 가능한 필드는 삭제해야 합니다.](../code-quality/ca2213-disposable-fields-should-be-disposed.md)

 [CA2202: 개체를 여러 번 삭제하지 마십시오.](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)

## <a name="example"></a>예제
 삭제 가능한 개체를 반환 하는 메서드를 구현 하는 경우 catch 블록 없이 try/finally 블록을 사용 하 여 개체가 삭제 되는지 되도록 합니다. Try/finally 블록을 사용 하 여 오류 지점에서 발생 하 고 해당 개체가 삭제 되었는지 확인 하는 예외를 허용 합니다.

 OpenPort1 메서드에서 SomeMethod에 대 한 호출 나 SerialPort ISerializable 개체를 열기 호출이 실패할 수 있습니다. 이 구현 CA2000 경고가 발생 합니다.

 OpenPort2 메서드 두 SerialPort 개체에는 선언 된 및로 설정 하는 null입니다.

-   `tempPort`성공 하는 메서드 작업을 테스트 하는 데 사용 됩니다.

-   `port`메서드의 반환 값에 사용 됩니다.

 `tempPort` 구현 되 고 열에 `try` 블록 및 기타 필요한에서 동일한 작업을 수행 `try` 블록입니다. 끝에는 `try` 블록, 열린된 포트에 할당 되는 `port` 반환 되는 개체 및 `tempPort` 개체로 설정 됩니다 `null`합니다.

 `finally` 의 값을 확인 하는 블록 `tempPort`합니다. Null 인 경우 메서드는 작업이 실패 하 고 `tempPort` 리소스를 해제 되도록 닫혀 있습니다. 반환 된 포트 개체는 작업이 실패 한 경우 null 됩니다는 메서드의 연산을 성공한 경우 열려 있는 SerialPort 개체를 포함 됩니다.

```csharp
public SerialPort OpenPort1(string portName)
{
   SerialPort port = new SerialPort(portName);
   port.Open();  //CA2000 fires because this might throw
   SomeMethod(); //Other method operations can fail
   return port;
}

public SerialPort OpenPort2(string portName)
{
   SerialPort tempPort = null;
   SerialPort port = null;
   try
   {
      tempPort = new SerialPort(portName);
      tempPort.Open();
      SomeMethod();
      //Add any other methods above this line
      port = tempPort;
      tempPort = null;

   }
   finally
   {
      if (tempPort != null)
      {
         tempPort.Close();
      }
   }
   return port;
}
```

```vb
Public Function OpenPort1(ByVal PortName As String) As SerialPort

   Dim port As New SerialPort(PortName)
   port.Open()    'CA2000 fires because this might throw
   SomeMethod()   'Other method operations can fail
   Return port

End Function


Public Function OpenPort2(ByVal PortName As String) As SerialPort

   Dim tempPort As SerialPort = Nothing
   Dim port As SerialPort = Nothing

   Try
      tempPort = New SerialPort(PortName)
      tempPort.Open()
      SomeMethod()
      'Add any other methods above this line
      port = tempPort
      tempPort = Nothing

   Finally
      If Not tempPort Is Nothing Then
         tempPort.Close()
      End If


   End Try

   Return port

End Function
```

## <a name="example"></a>예제
 기본적으로는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러는 오버플로 검사 하는 모든 산술 연산자. 따라서 모든 Visual Basic의 산술 연산은 throw 될 수 있습니다는 <xref:System.OverflowException>합니다. CA2000 등의 규칙에서 예기치 않은 위반이 발생할 수 있습니다. 예를 들어 Visual Basic 컴파일러를 표시 하 고는 오버플로 StreamReader를 삭제 하지 못하도록 하는 예외를 throw 할 수 있는 추가 대 한 지침을 검사 하기 때문에 다음 CreateReader1 함수 CA2000 위반을 생성 합니다.

 이 해결 하려면 프로젝트에서 Visual Basic 컴파일러에 의해 오버플로 검사 내보내기를 비활성화할 수 있습니다 또는 다음 CreateReader2 함수에서와 같이 코드를 수정할 수 있습니다.

 오버플로 검사 내보내기를 사용 하지 않으려면 솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다. 클릭 **컴파일**, 클릭 **고급 컴파일 옵션**, 한 다음 확인 **정수 오버플로 검사 해제**합니다.

  [!code-vb[FxCop.Reliability.CA2000.DisposeObjectsBeforeLosingScope#1](../code-quality/codesnippet/VisualBasic/ca2000-dispose-objects-before-losing-scope-vboverflow_1.vb)]

## <a name="see-also"></a>참고 항목
 <xref:System.IDisposable> [삭제 패턴](/dotnet/standard/design-guidelines/dispose-pattern)