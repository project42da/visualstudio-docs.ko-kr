---
title: "빠른 작업 | Microsoft 문서"
ms.custom: 
ms.date: 05/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: e173fb7d-c5bd-4568-ba0f-aa61913b3244
author: kempb
ms.author: kempb
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 8bf0b097be929b30627e0f1139c6e0b145933ab4
ms.openlocfilehash: ec2ae70312c7cb5f26630246046cadc7c210e1c2
ms.contentlocale: ko-kr
ms.lasthandoff: 05/26/2017

---
# 빠른 작업
<a id="quick-actions" class="xliff"></a>

[빠른 작업](refactoring-code-generation-quick-actions.md#quick-actions)을 사용하면 단일 작업으로 쉽게 코드를 리팩터링하거나, 생성하거나, 수정할 수 있습니다.  특별히 C#이나 Visual Basic에 적용되는 많은 빠른 작업이 있지만 일부는 C# 및 Visual Basic 프로젝트 모두에 적용되기도 합니다.  이러한 작업은 전구 아이콘 ![작은 전구 아이콘](~/ide/media/vs2015_lightbulbsmall.png "VS2017_LightBulbSmall")을 사용하거나 커서가 적절한 코드 줄에 있을 때 **Ctrl+.**를 눌러 적용할 수 있습니다.

빨간색 오류 표시선이 나타나는 경우 전구가 표시되며 Visual Studio에서는 문제 해결 방법에 대한 제안이 나타납니다. 예를 들어 빨간색 오류 표시선으로 나타난 오류가 있는 경우 해당 오류에 대한 해결 방법을 사용할 수 있을 때 전구가 나타납니다. 어떤 언어든지 타사에서 SDK에 포함하는 방식 등을 통해 사용자 지정 진단 및 제안을 제공할 수 있으며 Visual Studio 전구는 이러한 규칙을 기반으로 켜집니다.  

### 전구를 표시하려면
<a id="to-see-a-light-bulb" class="xliff"></a>  

1. 대부분의 경우 전구는 오류 지점에 마우스를 가져갈 때 자연스럽게 나타나거나 오류가 있는 줄로 캐럿을 이동할 때 편집기의 왼쪽 여백에 자동으로 나타납니다. 빨간색 오류 표시선이 보이면 마우스로 가리켜 전구를 표시할 수 있습니다. 줄에서 오류가 발생한 위치로 이동하기 위해 마우스나 키보드를 사용할 때 전구가 표시되도록 할 수도 있습니다.  

2. **Ctrl +** 줄의 임의 위치를 눌러 전구를 호출하고 잠재적 해결 방법 목록으로 바로 이동합니다.  

   ![마우스로 가리킨 전구](~/ide/media/vs2015_lightbulb_hover.png "VS2017_LightBulb_Hover")  

### 잠재적 해결 방법을 보려면
<a id="to-see-potential-fixes" class="xliff"></a>  
아래쪽 화살표나 잠재적 해결 방법 표시 링크를 클릭하여 전구가 수행할 수 있는 빠른 작업 목록을 표시합니다.  

![확장된 전구](../ide/media/vs2015_lightbulb_hover_expanded.png "VS2017_LightBulb_hover_expanded")

## 일반적인 빠른 작업
<a id="common-quick-actions" class="xliff"></a>
다음은 C# 및 Visual Basic 코드 모두에 적용할 수 있는 일반적인 빠른 작업 중 일부입니다.

### 누락된 사례/기본 사례/모두 추가
<a id="add-missing-casesdefault-caseboth" class="xliff"></a>
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

### 철자가 잘못된 형식 수정
<a id="correct-misspelled-type" class="xliff"></a>
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

### 불필요한 캐스트 제거
<a id="remove-unnecessary-cast" class="xliff"></a>
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

### 메서드를 속성으로 대체/속성을 메서드로 대체
<a id="replace-method-with-property--replace-property-with-method" class="xliff"></a>
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

### 메서드 동기화
<a id="make-method-synchronous" class="xliff"></a>
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

### 메서드 비동기화
<a id="make-method-asynchronous" class="xliff"></a>
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

### 불필요한 using/Import 제거
<a id="remove-unnecesary-usingsimports" class="xliff"></a>
**Remove Unnecessary Usings/Imports**(불필요한 Using/Import 제거) 빠른 작업은 현재 파일에 대해 사용되지 않은 `using` 및 `Import` 문을 제거합니다.  이 항목을 선택하면 사용되지 않은 네임스페이스 가져오기가 바로 제거됩니다.

### 참조 어셈블리나 NuGet 패키지의 형식 또는 솔루션의 다른 형식에 대해 using/Import 추가
<a id="add-usingsimports-for-types-in-reference-assemblies-nuget-packages-or-other-types-in-your-solution" class="xliff"></a>
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

### 보간된 문자열로 변환
<a id="convert-to-interpolated-string" class="xliff"></a>
[보간된 문자열](/dotnet/csharp/language-reference/keywords/interpolated-strings)은 포함된 변수로 문자열을 표현하는 간단한 방법이며, **[String.Format](https://msdn.microsoft.com/library/system.string.format.aspx)** 메서드와 유사합니다.  이 빠른 작업은 문자열이 연결되는 사례를 인식하거나 **String.Format**을 사용하여 사용법을 보간된 문자열로 변경합니다.

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

### 병합 충돌 표식 제거
<a id="remove-merge-conflict-markers" class="xliff"></a>
이러한 빠른 작업을 통해 충돌 코드 및 표식을 제거하는 “변경을 적용”하여 병합 충돌을 해결할 수 있습니다. Visual Studio 2017(버전 15.3 - Preview)에서만 사용할 수 있습니다.

![리팩터링 - 병합 충돌 해결](~/ide/media/vside-refactoring-merge-conflicts.png)

### 매개 변수에 대한 null 검사 추가
<a id="add-null-checks-for-parameters" class="xliff"></a>
빠른 작업을 통해 매개 변수가 null인지 알려주는 검사를 코드에 추가할 수 있습니다. Visual Studio 2017(버전 15.3 - Preview)에서만 사용할 수 있습니다.

![리팩터링 - null 검사 추가](~/ide/media/vside-refactoring-nullcheck.png)

### 생성자 생성기 기능 향상
<a id="constructor-generator-improvements" class="xliff"></a>
생성자를 만들 경우 이 빠른 작업을 통해 생성할 속성 또는 필드를 선택할 수 있고 빈 본문에서 생성자를 생성할 수도 있습니다. 빠른 작업을 사용하여 호출 사이트에서 기존 생성자에 매개 변수를 추가할 수도 있습니다. Visual Studio 2017(버전 15.3 - Preview)에서만 사용할 수 있습니다.

![리팩터링 - 생성자 생성](~/ide/media/vside-refactoring-constructors.png)

### 사용하지 않는 변수 제거
<a id="remove-unused-variables" class="xliff"></a>
이 빠른 작업을 통해 코드에서 사용된 적이 없고 사용되지 않는 변수를 제거할 수 있습니다. Visual Studio 2017(버전 15.3 - Preview)에서만 사용할 수 있습니다.

![리팩터링 - 사용하지 않는 변수](~/ide/media/vside-refactoring-unusedvars.png)

### 재정의 생성
<a id="generate-overrides" class="xliff"></a>
이 빠른 작업을 통해 클래스 또는 구조체의 빈 줄에서 재정의를 만들 수 있습니다. **Pick Members**(멤버 선택) 대화 상자에서 재정의할 멤버를 선택할 수 있습니다. Visual Studio 2017(버전 15.3 - Preview)에서만 사용할 수 있습니다.

![리팩터링 - 재정의](~/ide/media/vside-refactoring-overrides.png)

![리팩터링 - 재정의 대화 상자](~/ide/media/vside-refactoring-overrides-dialog.png)

### 숫자 리터럴에 대한 기본 변경
<a id="change-base-for-numeric-literals" class="xliff"></a>
이 빠른 작업을 통해 기본 숫자 시스템 간에 숫자 리터럴을 변환할 수 있습니다. 예를 들어 숫자를 16진수 또는 이진 형식으로 변경할 수 있습니다. Visual Studio 2017(버전 15.3 - Preview)에서만 사용할 수 있습니다.

![리팩터링 - 기본 변경](~/ide/media/vside-refactoring-changebase1.png)

![리팩터링 - 기본 변경](~/ide/media/vside-refactoring-changebase2.png)

### 자릿수 구분 기호를 리터럴로 삽입
<a id="insert-digit-separators-into-literals" class="xliff"></a>
이 빠른 작업을 통해 구분 기호 문자를 리터럴 값으로 추가할 수 있습니다. Visual Studio 2017(버전 15.3 - Preview)에서만 사용할 수 있습니다.

![리팩터링 - 자릿수 구분 기호 변경](~/ide/media/vside-refactoring-separators.png)

### **if** 구문을 **switch**로 변환
<a id="convert-if-construct-to-switch" class="xliff"></a>
이 빠른 작업을 통해 **if-then-else** 구문을 **switch** 구문으로 변환할 수 있습니다. Visual Studio 2017(버전 15.3 - Preview)에서만 사용할 수 있습니다.

```CSharp
// Before
if (obj is string s)
{
  Console.WriteLine("obj is a string: " + s);  
}

else if (obj is int i && i > 10)
{
  Console.WriteLine("obj is an int greater than 10");
}

// Convert to switch

// After
switch (obj)
{
  case string s:
    Console.WriteLine("Obj is a string: " + s);
    break;
  case int i when i > 10:
    Console.WriteLine("obj is an int greater than 10");
    break;
}
```

```VB
' Before
If TypeOf obj Is String s Then
    Console.WriteLine("obj is a string: " + s)
Else If TypeOf obj Is Integer i And i > 10 Then
    Console.WriteLine("obj is an int greater than 10")
End If

' Convert to switch

' After
Select Case obj
  Case String s
    Console.WriteLine("Obj is a string: " + s)
    Exit Sub
  Case Integer i when i > 10
    Console.WriteLine("obj is an int greater than 10")
    Exit Sub
End Select
```

# 참고 항목
<a id="see-also" class="xliff"></a>
* [코드 스타일 및 빠른 작업](code-styles-and-quick-actions.md)

