---
title: "빠른 작업 | Microsoft 문서"
ms.custom: 
ms.date: 03/10/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: e173fb7d-c5bd-4568-ba0f-aa61913b3244
author: BrianPeek
ms.author: brpeek
manager: ghogen
dev_langs:
- CSharp
- VB
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 46846db26bee30841e6cb35913d533b512d01ba0
ms.openlocfilehash: 226e51ace56d51945cc380aaaf3450ae7dacf8e4
ms.lasthandoff: 03/27/2017

---
# <a name="quick-actions"></a>빠른 작업

[빠른 작업](refactoring-code-generation-quick-actions.md#quick-actions)을 사용하면 단일 작업으로 쉽게 코드를 리팩터링하거나, 생성하거나, 수정할 수 있습니다.  특별히 C#이나 Visual Basic에 적용되는 많은 빠른 작업이 있지만 일부는 C# 및 Visual Basic 프로젝트 모두에 적용되기도 합니다.  이러한 작업은 전구 아이콘 ![작은 전구 아이콘](media/vs2015_lightbulbsmall.png "VS2017_LightBulbSmall")을 사용하거나 커서가 적절한 코드 줄에 있을 때 **Ctrl+.**를 눌러 적용할 수 있습니다.

빨간색 오류 표시선이 나타나는 경우 전구가 표시되며 Visual Studio에서는 문제 해결 방법에 대한 제안이 나타납니다. 예를 들어 빨간색 오류 표시선으로 나타난 오류가 있는 경우 해당 오류에 대한 해결 방법을 사용할 수 있을 때 전구가 나타납니다. 어떤 언어든지 타사에서 SDK에 포함하는 방식 등을 통해 사용자 지정 진단 및 제안을 제공할 수 있으며 Visual Studio 전구는 이러한 규칙을 기반으로 켜집니다.  

### <a name="to-see-a-light-bulb"></a>전구를 표시하려면  

1. 대부분의 경우 전구는 오류 지점에 마우스를 가져갈 때 자연스럽게 나타나거나 오류가 있는 줄로 캐럿을 이동할 때 편집기의 왼쪽 여백에 자동으로 나타납니다. 빨간색 오류 표시선이 보이면 마우스로 가리켜 전구를 표시할 수 있습니다. 줄에서 오류가 발생한 위치로 이동하기 위해 마우스나 키보드를 사용할 때 전구가 표시되도록 할 수도 있습니다.  

2. **Ctrl +** 줄의 임의 위치를 눌러 전구를 호출하고 잠재적 해결 방법 목록으로 바로 이동합니다.  

   ![마우스로 가리킨 전구](../ide/media/vs2015_lightbulb_hover.png "VS2017_LightBulb_Hover")  

### <a name="to-see-potential-fixes"></a>잠재적 해결 방법을 보려면  
아래쪽 화살표나 잠재적 해결 방법 표시 링크를 클릭하여 전구가 수행할 수 있는 빠른 작업 목록을 표시합니다.  

![확장된 전구](../ide/media/vs2015_lightbulb_hover_expanded.png "VS2017_LightBulb_hover_expanded")

## <a name="common-quick-actions"></a>일반적인 빠른 작업
다음은 C# 및 Visual Basic 코드 모두에 적용할 수 있는 일반적인 빠른 작업 중 일부입니다.

### <a name="add-missing-casesdefault-caseboth"></a>누락된 사례/기본 사례/모두 추가
C#의 `switch` 문이나 Visual Basic의 `Select Case` 문을 만들 때 코드 동작을 사용하여 누락된 사례 항목, 기본 사례 문 또는 모두를 자동으로 추가할 수 있습니다.  빈 문의 경우 다음과 같습니다.

```CSharp
enum MyEnum
{
    Item1,
    Item2,
    Item3
}

...

MyEnum myEnum = MyEnum.Item1;

switch(myEnum)
{
}
```

```VB
Enum MyEnum
    Item1
    Item2
    Item3
End Enum

...

Dim myEnum as MyEnum = MyEnum.Item1

Select Case myEnum
End Select
```

**Add Both**(모두 추가) 빠른 작업을 사용하여 누락된 사례와 기본 사례를 모두 입력하면 다음과 같이 생성됩니다.

```CSharp
switch(myEnum)
{
    case MyEnum.Item1:
        break;
    case MyEnum.Item2:
        break;
    case MyEnum.Item3:
        break;
    default:
        break;    
}
```

```VB
Select Case myEnum
    Case MyEnum.Item1
        Exit Select
    Case MyEnum.Item2
        Exit Select
    Case Else
        Exit Select
End Select
```

### <a name="correct-misspelled-type"></a>철자가 잘못된 형식 수정
Visual Studio에서 실수로 형식의 철자를 잘못 입력한 경우 이 빠른 작업은 자동으로 수정합니다.  이러한 항목은 전구 메뉴에 **"Change '*misspelled type*' to '*correct type*'(‘철자가 잘못된 형식’을(를) ‘올바른 형식’(으)로 변경)**으로 표시됩니다.  예를 들면 다음과 같습니다.

```CSharp
// Before
private viod MyMethod()
{
}

// Change 'viod' to 'void'

// After
private void MyMethod()
{
}
```

```VB
' Before
Function MyFunction as Intger
End Function

' Change 'Intger' to 'Integer'

' After
Function MyFunction as Integer
End Function
```

### <a name="remove-unnecessary-cast"></a>불필요한 캐스트 제거
형식을 캐스트가 필요 없는 다른 형식으로 캐스트하는 경우 **불필요한 캐스트 제거** 빠른 작업 항목은 코드에서 캐스트를 제거합니다.

```CSharp
// before
int number = (int)3;

// Remove Unnecessary Cast

// after
int number = 3;
```

```VB
' Before
Dim number as Integer = CType(3, Integer)

' Remove Unnecessary Cast

' After
Dim number as Integer = 3
```

### <a name="replace-method-with-property--replace-property-with-method"></a>메서드를 속성으로 대체/속성을 메서드로 대체
이러한 빠른 작업은 메서드를 속성으로 변환하거나 그 반대로 변환합니다.  아래 예제에서는 메서드에서 속성으로 변경을 보여 줍니다.  반대되는 경우에는 *Before* 및 *After* 섹션을 반대로 하면 됩니다.

```CSharp
private int MyValue;

// Before
public int GetMyValue()
{
    return MyValue;
}

// Replace 'GetMyValue' with property

// After
public int MyValue
{
    get { return MyValue; }
}
```

```VB
Dim MyValue As Integer

' Before
Function GetMyValue() As Integer
    Return MyValue
End Function

' Replace 'GetMyValue' with property

' After
ReadOnly Property MyValue As Integer
    Get
        Return MyValue
    End Get
End Property
```

### <a name="make-method-synchronous"></a>메서드 동기화
메서드에서 `async`/`Async` 키워드를 사용하면 해당 메서드 내 어딘가에서 `await`/`Await` 키워드도 사용될 것으로 예상됩니다.  그러나 그렇지 않을 경우 빠른 작업은 `async`/`Async` 키워드를 제거하고 반환 형식을 변경하여 메서드를 동기화할 수 있음을 나타냅니다.  [빠른 작업] 메뉴에서 **Make method synchronous**(메서드 동기화) 옵션을 사용합니다.

```CSharp
// Before
async Task<int> MyAsyncMethod()
{
    return 3;
}

// Make method synchronous

// After
int MyAsyncMethod()
{
    return 3;
}
```

```VB
' Before
Async Function MyAsyncMethod() As Task(Of Integer)
    Return 3
End Function

' Make method synchronous

' After
Function MyAsyncMethod() As Integer
    Return 3
End Function
```

### <a name="make-method-asynchronous"></a>메서드 비동기화
메서드 내에서 `await`/`Await` 키워드를 사용하는 경우 메서드 자체가 `async`/`Async` 키워드로 표시되는 것으로 예상됩니다.  그러나 그렇지 않을 경우 빠른 작업은 메서드를 비동기화할 수 있음을 나타냅니다.  [빠른 작업] 메뉴에서 **Make method/Function asynchronous**(메서드/함수 비동기화) 옵션을 사용합니다.

```CSharp
// Before
int MyAsyncMethod()
{
    return await Task.Run(...);
}

// Make method synchronous

// After
async Task<int> MyAsyncMethod()
{
    return await Task.Run(...);
}
```

```VB
' Before
Function MyAsyncMethod() as Integer
    Return  Await Task.Run(...)
End Function

' Make method synchronous

' After
Async Function MyAsyncMethod() As Task(Of Integer)
    Return Await Task.Run(...)
End Function
```

### <a name="remove-unnecesary-usingsimports"></a>불필요한 using/Import 제거
**Remove Unnecessary Usings/Imports**(불필요한 Using/Import 제거) 빠른 작업은 현재 파일에 대해 사용되지 않은 `using` 및 `Import` 문을 제거합니다.  이 항목을 선택하면 사용되지 않은 네임스페이스 가져오기가 바로 제거됩니다.

### <a name="add-usingsimports-for-types-in-reference-assemblies-nuget-packages-or-other-types-in-your-solution"></a>참조 어셈블리나 NuGet 패키지의 형식 또는 솔루션의 다른 형식에 대해 using/Import 추가
솔루션의 다른 프로젝트에 있는 형식을 사용하면 빠른 작업이 자동으로 표시되지만 **도구 > 옵션 > C#** 또는 **Basic > 고급** 탭에서 다른 작업을 사용하도록 설정해야 합니다.  

* 참조 어셈블리의 형식에 대해 using/import 제안
* NuGet 패키지의 형식에 대해 using/import 제안

사용하도록 설정한 경우 현재 가져오지 않고 참조 어셈블리 또는 NuGet 패키지에 있는 네임스페이스의 형식을 사용하면 using/import 문이 생성됩니다.

```CSharp
// Before
Debug.WriteLine("Hello");

// using System.Diagnostics;

// After
using System.Diagnostics;

Debug.WriteLine("Hello");
```

```VB
' Before
Debug.WriteLine("Hello")

' Imports System.Diagnostics

// After
Imports System.Diagnostics

Debug.WriteLine("Hello")
```

### <a name="convert-to-interpolated-string"></a>보간된 문자열로 변환
[보간된 문자열](/dotnet/articles/csharp/language-reference/keywords/interpolated-strings)은 포함된 변수로 문자열을 표현하는 간단한 방법이며, **[String.Format](https://msdn.microsoft.com/library/system.string.format(v=vs.110).aspx)** 메서드와 유사합니다.  이 빠른 작업은 문자열이 연결되는 사례를 인식하거나 **String.Format**을 사용하여 사용법을 보간된 문자열로 변경합니다.

```CSharp
// Before
int num = 3;
string s = string.Format("My string with {0} in the middle", num);

// Convert to interpolated string

// After
int num = 3;
string s = $"My string with {num} in the middle";
```

```VB
' Before
Dim num as Integer = 3
Dim s as String = String.Format("My string with {0} in the middle", num)

' Convert to interpolated string

' After
Dim num as Integer = 3
Dim s As String = $"My string with {num} in the middle"
```

# <a name="see-also"></a>참고 항목
* [코드 스타일 및 빠른 작업](code-styles-and-quick-actions.md)
