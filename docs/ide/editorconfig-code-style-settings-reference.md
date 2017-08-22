---
title: "EditorConfig에 대한 .NET Coding 규칙 설정 | Microsoft Docs"
ms.custom: 
ms.date: 12/14/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- editor
ms.assetid: 
caps.latest.revision: 1
author: kaseyu
ms.author: kaseyu
manager: davidcsa
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
ms.translationtype: HT
ms.sourcegitcommit: 8a544bd1e1242bb6fabe00f7842ac33ed9d9d444
ms.openlocfilehash: 71a0fadaefad47b16182f1166968207a26cc1d40
ms.contentlocale: ko-kr
ms.lasthandoff: 08/14/2017

---

# <a name="net-coding-convention-settings-for-editorconfig"></a>EditorConfig에 대한 .NET Coding 규칙 설정
.NET 코딩 규칙은 [EditorConfig](https://docs.microsoft.com/en-us/visualstudio/ide/create-portable-custom-editor-options) 파일을 사용하여 구성됩니다. EditorConfig 파일을 사용하면 **개별 .NET 코딩 규칙을 활성화/비활성화**하고 (심각도 수준을 통해) **규칙을 적용하려는 수준을 구성**할 수 있습니다. EditorConfig를 사용하여 코드 베이스에 일관성을 적용하는 방법에 대한 자세한 내용을 보려면 [이 문서](https://docs.microsoft.com/en-us/visualstudio/ide/create-portable-custom-editor-options)를 참고하세요.

지원되는 .NET 코딩 규칙 범주에는 세 가지가 있습니다.
- **[언어 규칙](#language)**은 C# 또는 Visual Basic 언어(예: `var`/명시적 형식)에 적용되는 규칙이며 식 본문 멤버를 사용합니다.
- **[서식 설정 규칙](#formatting)**은 제어 블록에서 간격을 보다 쉽게 읽을 수 있기 위한(예: Allman 중괄호) 코드의 레이아웃 및 구조에 대한 규칙입니다.
- **[명명 규칙](#naming)**은 개체를 명명하는 방식을 유지하는 규칙입니다(예: `async` 메서드는 "Async"로 끝나야 함). 

# <a name="language">언어 규칙</a>
## <a name="overview"></a>개요
**규칙 형식:**
`options_name = false|true : none|suggestion|warning|error`

코드 스타일 옵션에 대해 **true**(이 옵션 선호) 또는 **false**(이 옵션 선호 안 함), 콜론(`:`) 및 심각도(`none`, `silent`, `suggestion`, `warning` 또는 `error`)를 지정해야 합니다. 심각도는 코드 베이스에서 원하는 스타일의 적용 수준을 의미합니다.

`none` 및 `silent`는 동의어이며 사용자에게 표시되어야 한함을 의미하지 않습니다. 이 항목에는 이 규칙을 비활성화하는 효과가 있습니다.

심각도 | 효과
------------ | -------------
none/silent | 이 스타일을 따르지 않을 경우 사용자에게 아무 메시지도 표시되지 않지만 코드 생성 기능은 이 스타일로 생성됩니다. 
suggestion | 이 스타일을 따르지 않을 경우 사용자에게 제안으로 표시됩니다(처음 두 문자에 점선이 밑줄로 표시됨).
경고 | 이 스타일을 따르지 않을 경우 컴파일러 경고가 표시됩니다.
오류 | 이 스타일을 따르지 않을 경우 컴파일러 오류가 표시됩니다.

## <a name="net-language-convention-options"></a>.NET 언어 규칙 옵션

- **[.NET 코드 스타일 설정](#this_and_me)**
    - ["This." 및 "Me." 한정](#this_and_me)
        - [필드](#this_and_me_fields)
        - [속성](#this_and_me_properties)
        - [메서드](#this_and_me_methods)
        - [이벤트](#this_and_me_events)
    - [형식 참조를 위한 언어 키워드(int, string 등) 및 프레임워크 형식 이름](#language_keywords)
        - [로컬 항목, 매개 변수 및 멤버](#language_keywords_variables)
        - [멤버 액세스 식](#language_keywords_member_access)
    - [식 수준 기본 설정](#expression_level)
        - [개체 이니셜라이저](#expression_level_object_initializers)
        - [컬렉션 이니셜라이저](#expression_level_collection_initializers)
        - [명시적 튜플 이름](#expression_level_tuple_names)
        - ["null" 검사에 식 병합](#expression_level_null_checking)
        - ["null" 검사의 Null 전파](#expression_level_null_propogation)
- **[CSharp 코드 스타일 설정](#csharp_codestyle)**
    - ["var"](#var)
        - [기본 제공 형식에 "var" 사용](#var_built_in)
        - [형식이 명확한 경우 "var" 사용](#var_apparent)
        - [다른 곳에서 "var" 사용](#var_elsewhere)
    - [식 본문 멤버](#expression_body)
        - [메서드](#expression_bodied_members_methods)
        - [생성자](#expression_bodied_members_constructors)
        - [연산자](#expression_bodied_members_operators)
        - [속성](#expression_bodied_members_properties)
        - [인덱서](#expression_bodied_members_indexers)
        - [접근자](#expression_bodied_members_accessors)
    - [패턴 일치](#pattern_matching)
        - ["캐스트" 검사를 포함하는 "is"](#pattern_matching_is_cast)
        - ["null" 검사를 포함하는 "as"](#pattern_matching_as_null)
    - [인라인 변수 선언](#inlined_variable_declarations)
    - [식 수준 기본 설정](#expression_level_csharp) -[`default` 식 단순화](#expression_level_default)
    - ["Null" 검사 기본 설정](#null_checking)
        - [Throw 식](#null_checking_throw_expressions)
        - [조건부 대리자 호출](#null_checking_conditional_delegate_calls)
    - [코드 블록 기본 설정](#code_block)
        - [중괄호 기본 사용](#prefer_braces)

## <a name="this_and_me">"This." 및 "Me." 한정</a>
### <a name="this_and_me_fields">필드(IDE0003/IDE0009)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|  `dotnet_style_qualification_for_field` | C# 및 Visual Basic | false:none | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 비정적 메서드에서 사용되는 모든 비정적 필드 앞에 `this.`(C#) 또는 `Me.`(Visual Basic)를 추가하는 것이 좋습니다. | **C#:** <br>`this.capacity = 0;` <br><br> **Visual Basic:** <br> `Me.capacity = 0`
| False | 비정적 메서드에서 사용되는 모든 비정적 필드 앞에 `this.`(C#) 또는 `Me.`(Visual Basic)를 추가하지 않는 것이 좋습니다. | **C#:** <br>`capacity = 0;` <br><br> **Visual Basic:** <br>`capacity = 0`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp and VisualBasic code style settings:
[*.cs,*.vb]
dotnet_style_qualification_for_field = false:suggestion
```

### <a name="this_and_me_properties">속성(IDE0003/IDE0009)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`dotnet_style_qualification_for_property`| C# 및 Visual Basic | false:none | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 비정적 메서드에서 사용되는 모든 비정적 속성 앞에 `this.`(C#) 또는 `Me.`(Visual Basic)를 추가하는 것이 좋습니다.| **C#:** <br>`this.ID = 0;` <br><br> **Visual Basic:** <br>`Me.ID = 0`
| False | 비정적 메서드에서 사용되는 모든 비정적 속성 앞에 `this.`(C#) 또는 `Me.`(Visual Basic)를 추가하지 *않는* 것이 좋습니다. | **C#:** <br>`ID = 0;` <br><br> **Visual Basic:** <br> `ID = 0`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp and VisualBasic code style settings:
[*.cs,*.vb]
dotnet_style_qualification_for_property = false:suggestion
```

### <a name="this_and_me_methods">메서드(IDE0003/IDE0009) </a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`dotnet_style_qualification_for_method`| C# 및 Visual Basic | false:none | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 비정적 메서드 내에서 호출되는 모든 비정적 메서드 앞에 `this.`(C#) 또는 `Me.`(VB)를 추가하는 것이 좋습니다.| **C#:** <br>`this.Display();` <br><br> **Visual Basic:** <br> `Me.Display()`
| False | 비정적 메서드 내에서 호출되는 모든 비정적 메서드 앞에 `this.`(C#) 또는 `Me.`(VB)를 추가하지 *않는* 것이 좋습니다. | **C#:** <br>`Display();` <br><br> **Visual Basic:** <br> `Display()`


#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_qualification_for_method = false:suggestion
```

### <a name="this_and_me_events">이벤트(IDE0003/IDE0009) </a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`dotnet_style_qualification_for_event`| C# 및 Visual Basic | false:none | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 비정적 메서드 내에서 참조되는 모든 비정적 이벤트 앞에 `this.`(C#) 또는 `Me.`(VB)를 추가하는 것이 좋습니다.| **C#:** <br>`this.Elapsed += Handler;` <br><br> **Visual Basic:** <br> `AddHandler Me.Elapsed, AddressOf Handler`
| False | 비정적 메서드 내에서 참조되는 모든 비정적 이벤트 앞에 `this.`(C#) 또는 `Me.`(VB)를 추가하지 *않는* 것이 좋습니다. | **C#:** <br>`Elapsed += Handler;` <br><br> **Visual Basic:** <br>`AddHandler Elapsed, AddressOf Handler`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_qualification_for_event = false:suggestion
```

## <a name="language_keywords">형식 참조를 위한 언어 키워드(int, string 등) 및 프레임워크 형식 이름</a>
### <a name="language_keywords_variables">로컬 항목, 매개 변수 및 멤버(IDE0012/IDE0014)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`dotnet_style_predefined_type_for_locals_parameters_members`| C# 및 Visual Basic | true:none | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 로컬 항목, 매개 변수 및 형식 멤버의 경우 언어 키워드로 형식을 나타내는 형식(`int`, `double`, `float`, `short`, `long`, `decimal`, `string`)에서 형식 이름(`Int32`, `Int64` 등) 대신 키워드를 사용하는 것이 좋습니다.| **C#:** <br>`private int _member;` <br><br> **Visual Basic:** `Private _member As Integer`
| False | 로컬 항목, 매개 변수 및 형식 멤버의 경우 언어 키워드로 형식을 나타내는 형식(`int`, `double`, `float`, `short`, `long`, `decimal`, `string`)에서 키워드 대신 형식 이름(`Int32`, `Int64` 등)을 사용하는 것이 좋습니다.  | **C#:** <br>`private Int32 _member;` <br><br> **Visual Basic:** <br> `Private _member As Int32`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_predefined_type_for_locals_parameters_members = true:suggestion
``` 

### <a name="language_keywords_member_access">멤버 액세스 식(IDE0013/IDE0015)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`dotnet_style_predefined_type_for_member_access`| C# 및 Visual Basic | true:none | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 멤버 액세스 식이 키워드 표현(`int`, `double`, `float`, `short`, `long`, `decimal`, `string`)과 함께 형식에 사용될 때마다 키워드를 사용하는 것이 좋습니다.| **C#:** <br>`var local = int.MaxValue;` <br><br> **Visual Basic:** <br> `Dim local = Integer.MaxValue`
| False | 멤버 액세스 식이 키워드 표현(`int`, `double`, `float`, `short`, `long`, `decimal`, `string`)과 함께 형식에 사용될 때마다 형식 이름을 사용하는 것이 좋습니다. | **C#:** <br>`var local = Int32.MaxValue;` <br><br> **Visual Basic:** <br> `Dim local = Int32.MaxValue`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_predefined_type_for_member_access = true:suggestion
``` 

## <a name="expression_level">식 수준 기본 설정</a>
### <a name="expression_level_object_initializers">개체 이니셜라이저(IDE0017)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`dotnet_style_object_initializer`| C# 및 Visual Basic | true:suggestion | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 가능한 경우 개체 이니셜라이저를 사용하여 개체를 초기화하는 것이 좋습니다.| **C#:** <br>`var c = new Customer(){ Age = 21 };` <br><br> **Visual Basic:** <br> `Dim c = New Customer() With { .Age = 21 }`
| False | 개체 이니셜라이저를 사용하여 개체를 초기화하지 *않는* 것이 좋습니다. | **C#:** <br>`var c = new Customer();`<br>`c.Age = 21;` <br><br> **Visual Basic:** <br>`Dim c = new Customer() `<br>`c.Age = 21`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_object_initializer = true:suggestion
``` 

### <a name="expression_level_collection_initializers">컬렉션 이니셜라이저(IDE0028)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`dotnet_style_collection_initializer`| C# 및 Visual Basic | true:suggestion | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 가능한 경우 컬렉션 이니셜라이저를 사용하여 컬렉션을 초기화하는 것이 좋습니다.| **C#:** <br>`var list = new List<int>{ 1, 2, 3 };` <br><br> **Visual Basic:** <br> `Dim list = new List(Of Integer) From { 1, 2, 3}`
| False | 컬렉션 이니셜라이저를 사용하여 컬렉션을 초기화하지 *않는* 것이 좋습니다. | **C#:** <br>`var list = new List<int>();`<br>`list.Add(1);`<br>`list.Add(2);`<br>`list.Add(3);` <br><br> **Visual Basic:** <br>`Dim list = new List(Of Integer)`<br>`list.Add(1)`<br>`list.Add(2)`<br>`list.Add(3)`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_collection_initializer = true:suggestion
```

### <a name="expression_level_tuple_names">명시적 튜플 이름(IDE0033)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`dotnet_style_explicit_tuple_names`| C# 7.0+ 및 Visual Basic 15+ | true:suggestion | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | ItemX 속성보다 튜플 이름을 사용하는 것이 좋습니다.| **C#:** <br>`(string name, int age) customer = GetCustomer();`<br>`var name = customer.name;` <br><br> **Visual Basic:** <br> `Dim customer As (name As String, age As Integer) = GetCustomer()`<br>`Dim name = customer.name`
| False | 튜플 이름보다 ItemX 속성을 사용하는 것이 좋습니다. | **C#:** <br>`(string name, int age) customer = GetCustomer();`<br>`var name = customer.Item1;` <br><br> **Visual Basic:** <br>`Dim customer As (name As String, age As Integer) = GetCustomer()`<br> `Dim name = customer.Item1`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_explicit_tuple_names = true:suggestion
``` 

### <a name="expression_level_null_checking">"null" 검사에 식 병합(IDE0029)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`dotnet_style_coalesce_expression`| C# 및 Visual Basic | true:suggestion | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 3개로 구성된 연산자 검사보다 null 병합 식을 사용하는 것이 좋습니다.| **C#:** <br>`var v = x ?? y;` <br><br> **Visual Basic:** <br> `Dim v = If(x, y)`
| False | null 병합 식보다 3개로 구성된 연산자 검사를 사용하는 것이 좋습니다. | **C#:** <br>`var v = x != null ? x : y; // or`<br>`var v = x == null ? y : x;` <br><br> **Visual Basic:** <br>`Dim v = If(x Is Nothing, y, x) ' or`<br> `Dim v = If(x IsNot Nothing, x, y)`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_coalesce_expression = true:suggestion
``` 

### <a name="expression_level_null_propogation">"null" 검사의 Null 전파(IDE0031)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`dotnet_style_null_propagation`| C# 6.0 이상 및 Visual Basic 14 이상 | true:suggestion | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 가능한 경우 null 조건부 연산자를 사용하는 것이 좋습니다.| **C#:** <br>`var v = o?.ToString();` <br><br> **Visual Basic:** <br> `Dim v = o?.ToString()`
| False | 가능한 경우 3개로 구성된 null 검사를 사용하는 것이 좋습니다. | **C#:** <br>`var v = o == null ? null : o.ToString(); // or`<br>`var v = o != null ? o.String() : null;` <br><br> **Visual Basic:** <br>`Dim v = If(o Is Nothing, Nothing, o.ToString()) ' or`<br> `Dim v = If(o IsNot Nothing, o.ToString(), Nothing)`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_null_propagation = true:suggestion
``` 

# <a name="csharp_codestyle">CSharp 코드 스타일 설정</a>
## <a name="var">"var" 및 명시적 형식</a>
### <a name="var_built_in">기본 제공 형식의 "var"(IDE0007, IDE0008)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_style_var_for_built_in_types`| C# | true:none | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | `int` 등의 기본 제공 시스템 형식에 `var`을 사용하는 것이 좋습니다.| **C#:** <br>`var x = 5;`
| False | `int` 등의 기본 제공 시스템 형식에 `var`을 사용하지 않는 것이 좋습니다. | **C#:** <br>`int x = 5;`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_style_var_for_built_in_types = true:suggestion
``` 

### <a name="var_apparent">형식이 명확한 경우 "var" 사용(IDE0007, IDE0008)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_style_var_when_type_is_apparent`| C# | true:none | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 선언 식의 오른쪽에서 형식이 이미 언급된 경우 `var`을 사용하는 것이 좋습니다.| **C#:** <br>`var obj = new C();`
| False | 선언 식의 오른쪽에서 형식이 이미 언급된 경우 `var`을 사용하지 않는 것이 좋습니다. | **C#:** <br>`C obj = new C();`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_style_var_when_type_is_apparent = true:suggestion
``` 

### <a name="var_elsewhere">다른 곳에서 "var" 사용(IDE0007, IDE0008) </a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_style_var_elsewhere`| C# | true:none | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 다른 코드 스타일 규칙에 의해 재정의되지 않는 경우 항상 `var`을 사용하는 것이 좋습니다.| **C#:** <br>`var f = this.Init();`
| False | 다른 코드 스타일 규칙에 의해 재정의되지 않는 경우 항상 var을 사용하지 않는 것이 좋습니다.| **C#:** <br>`bool f = this.Init();`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_style_var_elsewhere = true:suggestion
``` 

##<a name="expression_bodied_members">식 본문 멤버</a>
### <a name="expression_bodied_members_methods">메서드(IDE0022)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_style_expression_bodied_methods`| C# 6.0+ | false:none | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 메서드에 식 본문 멤버를 사용하는 것이 좋습니다.| **C#:** <br>`public int GetAge() => this.Age;`
| False | 메서드에 식 본문 멤버를 사용하지 않는 것이 좋습니다.| **C#:** <br>`public int GetAge() { return this.Age; }`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_methods = false:none
``` 

### <a name="expression_bodied_members_constructors">생성자(IDE0021)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_style_expression_bodied_constructors`| C# 7.0+ | false:none | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 생성자에 식 본문 멤버를 사용하는 것이 좋습니다.| **C#:** <br>`public Customer(int age) => Age = age;`
| False | 생성자에 식 본문 멤버를 사용하지 않는 것이 좋습니다.| **C#:** <br>`public Customer(int age) { Age = age; }`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_constructors = false:none
``` 

### <a name="expression_bodied_members_operators">연산자(IDE0023, IDE0024)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_style_expression_bodied_operators` | C# 7.0+ | false:none | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 연산자에 식 본문 멤버를 사용하는 것이 좋습니다.| **C#:** <br>`public static ComplexNumber operator +(ComplexNumber c1, ComplexNumber c2)`<br>`=> new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary);`
| False | 연산자에 식 본문 멤버를 사용하지 않는 것이 좋습니다.| **C#:** <br>`public static ComplexNumber operator +(ComplexNumber c1, ComplexNumber c2)`<br>`{ return new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary); }`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_operators = false:none
``` 

### <a name="expression_bodied_members_properties">속성(IDE0025)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_style_expression_bodied_properties` | C# 7.0+ | true:none | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 속성에 식 본문 멤버를 사용하는 것이 좋습니다.| **C#:** <br>`public int Age => _age;`
| False | 속성에 식 본문 멤버를 사용하지 않는 것이 좋습니다.| **C#:** <br>`public int Age { get { return _age; }}`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_properties = true:none
``` 

### <a name="expression_bodied_members_indexers">인덱서(IDE0026)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_style_expression_bodied_indexers` | C# 7.0+ | true:none | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 인덱서에 식 본문 멤버를 사용하는 것이 좋습니다.| **C#:** <br>`public T this[int i] => _value[i];`
| False | 인덱서에 식 본문 멤버를 사용하지 않는 것이 좋습니다.| **C#:** <br>`public T this[int i] { get { return _values[i]; } }`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_indexers = false:none
``` 

### <a name="expression_bodied_members_accessors">접근자(IDE0027)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_style_expression_bodied_accessors` | C# 7.0+ | true:none | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 접근자에 식 본문 멤버를 사용하는 것이 좋습니다.| **C#:** <br>`public int Age { get => _age; set => _age = value; }`
| False | 접근자에 식 본문 멤버를 사용하지 않는 것이 좋습니다.| **C#:** <br>`public int Age { get { return _age; } set { _age = value; } }`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_accessors = false:none
``` 

## <a name="pattern_matching">패턴 일치</a>
### <a name="pattern_matching_is_cast">"cast" 검사를 포함하는 "is"(IDE0020)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_style_pattern_matching_over_is_with_cast_check` | C# 7.0+ | true:suggestion | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 캐스트를 포함하는 `is` 식보다 패턴 일치를 사용하는 것이 좋습니다.| **C#:** <br>`if (o is int i) {...}`
| False | 패턴 일치보다 형식 캐스트를 포함하는 `is` 식을 사용하는 것이 좋습니다.| **C#:** <br>`if (o is int) {var i = (int)o; ... }`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_style_pattern_matching_over_is_with_cast_check = true:suggestion
```

### <a name="pattern_matching_as_null">"null" 검사를 포함하는 "as"(IDE0019)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_style_pattern_matching_over_as_with_null_check` | C# 7.0+ | true:suggestion | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | null 검사를 포함하는 `as` 식 대신 패턴 일치를 사용하여 항목이 특정 형식인지 확인하는 것이 좋습니다.| **C#:** <br>`if (o is string s) {...}`
| False | 패턴 일치 대신 null 검사를 포함하는 `as` 식을 사용하여 항목이 특정 형식인지 확인하는 것이 좋습니다.| **C#:** <br>`var s = o as string; if (s != null) {...}`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_style_pattern_matching_over_as_with_null_check = true:suggestion
```

### <a name="inlined_variable_declarations">인라인 변수 선언(IDE0018)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_style_inlined_variable_declaration` | C# 7.0+ | true:suggestion | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 가능한 경우 `out` 변수를 인라인으로 선언하는 것이 좋습니다. | **C#:** <br>`if (int.TryParse(value, out int i) {...}`
| False | 가능한 경우 `out` 변수를 명시적으로 선언하는 것이 좋습니다.| **C#:** <br>`int i; if (int.TryParse(value, out i) {...}`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_style_inlined_variable_declaration = true:suggestion
```
## <a name="expression_level_csharp">식 수준 기본 설정</a>
### <a name="expression_level_default">`default` 식 단순화(IDE0034)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_prefer_simple_default_expression` | C# 7.1+ | true:suggestion | Visual Studio 2017 v. 15.3 |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | `default(T)`보다 `default` 선호 | **C#:** <br>`void DoWork(CancellationToken cancellationToken = default){ ... }`
| False | 선호 | **C#:** <br>`void DoWork(CancellationToken cancellationToken = default(CancellationToken)){ ... }`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_prefer_simple_default_expression = true:suggestion
``` 

## <a name="null_checking">"Null" 검사 기본 설정</a>
### <a name="null_checking_throw_expressions">Throw 식(IDE0016)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_style_throw_expression`  | C# 7.0+ | true:suggestion | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | throw 문 대신 throw 식을 사용하는 것이 좋습니다. | **C#:** <br>`this.s = ss ?? throw new ArgumentNullException(nameof(s));`
| False | throw 식 대신 throw 문을 사용하는 것이 좋습니다.| **C#:** <br>`if (s==null) {throw new ArgumentNullException(nameof(s));} this.s = s;`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_style_throw_expression = true:suggestion
```

### <a name="null_checking_conditional_delegate_calls">조건부 대리자 호출 선호(IDE0041)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_style_conditional_delegate_call`  | C# 6.0+ | true:suggestion | Visual Studio 2017 RTW |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | null 검사를 수행하는 대신 람다 호출 시 조건부 병합 연산(`?.`)을 사용하는 것이 좋습니다. | **C#:** <br>`func?.Invoke(args);`
| False | 조건부 병합 연산자(`?.`)를 사용하는 대신 람다 호출 시 null 검사를 수행하는 것이 좋습니다.| **C#:** <br>`if (func!=null) { func(args); }`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_style_conditional_delegate_call = false:suggestion
```

## <a name="code_block">"코드 블록 기본 설정</a>
### <a name="prefer_braces">중괄호 기본 사용(IDE0011)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_prefer_braces`  | C#  | true:none | Visual Studio 2017 v. 15.3 |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 중괄호 기본 사용 | **C#:** <br>`if (test) { this.Display(); }`
| False | 가능하면 중괄호 없음 기본 사용 | **C#:** <br>`if (test) this.Display();`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp code style settings:
[*.cs]
csharp_prefer_braces = true:none
```

# <a name="formatting">서식 지정 규칙</a>
## <a name="overview"></a>개요
**규칙 형식:**
`options_name = false|true`

규칙을 적용하려는 조건을 대신 지정해야 하는 경우를 제외하고 서식 옵션에 **true**(이 옵션을 선호함) 또는 **false**(이 옵션을 선호하지 않음)를 지정해야 합니다.

## <a name="net-formatting-options"></a>.NET 서식 지정 옵션

- **[.NET 서식 지정 설정](#usings)**
    - [Using 구성](#usings)
        - [시스템 지시문 먼저 정렬](#usings_sort_system_first)
- **[C# 서식 지정 설정](#newline)**
    - [줄 바꿈 옵션](#newline)
        - [여는 중괄호 앞에서 줄 바꿈(`{`)](#newline_before_brace)
        - [앞에서 줄 바꿈`else`](#newline_before_else)
        - [앞에서 줄 바꿈`catch`](#newline_before_catch)
        - [앞에서 줄 바꿈`finally`](#newline_before_finally)
        - [개체 이니셜라이저의 멤버 앞에서 줄 바꿈](#newline_before_object)
        - [무명 형식의 멤버 앞에서 줄 바꿈](#newline_before_anonymous)
        - [쿼리 식 절의 멤버 앞에서 줄 바꿈](#newline_before_query)
    - [들여쓰기 옵션](#indent)
        - [`switch` 대/소문자 콘텐츠 들여쓰기](#indent_switch)
        - [`switch` 레이블 들여쓰기](#indent_switch_labels)
        - [레이블 위치 지정](#label)
    - [간격 옵션](#spacing)
        - [캐스트 뒤에 공백](#space_after_cast)
        - [제어 흐름 문의 키워드 뒤에 공백](#space_control_flow)
        - [메서드 선언 매개 변수 목록 괄호 간의 공백](#space_parameter_list)
        - [메서드 호출 인수 목록의 괄호 내 공백](#space_method_call)
        - [다른 옵션의 괄호 내 공백](#space_other)
    - [래핑 옵션](#wrapping)
        - [문과 멤버 선언을 동일한 줄에 유지](#wrapping_statement)
        - [블록을 한 줄에 유지](#wrapping_block)

## <a name="usings">Using 구성</a>
### <a name="usings_sort_system_first">시스템 지시문 먼저 정렬</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`dotnet_sort_system_directives_first`  |  C# 및 Visual Basic | true | Visual Studio 2017 v. 15.3  |


| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | System.* usings를 사전순으로 정렬하고 다른 using 앞에 배치합니다.| **C#:** <br>`using System.Collections.Generic;`<br> `using System.Threading.Tasks;`<br> `using Octokit;`
| False | Using의 순서가 필요하지 않습니다 | **C#:** <br>`using System.Collections.Generic;`<br> `using Octokit;` <br> `using System.Threading.Tasks;`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# .NET formatting settings:
[*.cs, *.vb]
dotnet_sort_system_directives_first = true
``` 

# <a name="csharp_formatting">C# 서식 지정 설정</a>
## <a name="newline">줄 바꿈 옵션</a>
### <a name="newline_before_brace">여는 중괄호 앞에서 줄 바꿈(`{`)</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_new_line_before_open_brace`  |  C#  | true | Visual Studio 2017 v. 15.3  |


| 값 | 설명 
| ------------- |:-------------|
| accessors, anonymous_methods, anonymous_types, control_blocks, events, indexers, lambdas, local_functions, methods, object_collection, properties, types. (여러 경우에 ','로 구분합니다.) | 지정된 식(Allman 스타일)의 새 줄에 중괄호 필요 |
| 모두 | 모든 식(Allman)의 새 줄에 중괄호 필요 |
| 없음 | 모든 식(K&R)의 동일한 줄에 중괄호 필요 |

#### <a name="applied"></a>적용됨:
```csharp
// csharp_new_line_before_open_brace = all
void MyMethod() 
{
    if (...) 
    {
        ...
    }
}
```

```csharp
// csharp_new_line_before_open_brace = none
void MyMethod() {
    if (...) {
        ...
    }
}
```

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_new_line_before_open_brace = methods, properties, control_blocks, types
``` 

### <a name="newline_before_else">앞에서 줄 바꿈`else`</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_new_line_before_else` |  C#  | true | Visual Studio 2017 v. 15.3  |


| 값 | 설명 
| ------------- |:-------------|
| True | 새 줄에 `else` 문을 배치합니다.  |
| False | 동일한 줄에 `else` 문을 배치합니다.  |

#### <a name="applied"></a>적용됨:
```csharp
// csharp_new_line_before_else = true
if (...) {
    ...
}
else {
    ...
}
```

```csharp
// csharp_new_line_before_else = false
if (...) {
    ...
} else {
    ...
}
```

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_new_line_before_else = true
``` 

### <a name="newline_before_catch">앞에서 줄 바꿈`catch`</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
| `csharp_new_line_before_catch`|  C#  | true | Visual Studio 2017 v. 15.3  |


| 값 | 설명 
| ------------- |:-------------|
| True | 새 줄에 `catch` 문을 배치합니다.  |
| False | 동일한 줄에 `catch` 문을 배치합니다. |

#### <a name="applied"></a>적용됨:
```csharp
// csharp_new_line_before_catch = true
try {
    ...
}
catch (Exception e) {
    ...
}
```

```csharp
// csharp_new_line_before_catch = false
try {
    ...
} catch (Exception e) {
    ...
}
```

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_new_line_before_catch = true
``` 

### <a name="newline_before_finally">앞에서 줄 바꿈`finally`</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
| `csharp_new_line_before_finally`|  C#  | true | Visual Studio 2017 v. 15.3  |


| 값 | 설명 
| ------------- |:-------------|
| True | `finally` 문을 닫는 괄호 뒤의 새 줄에 배치해야 합니다.  |
| False | `finally` 문을 닫는 괄호인 동일한 줄에 배치해야 합니다.  |

#### <a name="applied"></a>적용됨:
```csharp
// csharp_new_line_before_finally = true
try {
    ...
}
catch (Exception e) {
    ...
}
finally {
    ...
}
```

```csharp
// csharp_new_line_before_finally = false
try {
    ...
} catch (Exception e) {
    ...
} finally {
    ...
}
```

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_new_line_before_finally = true
``` 

### <a name="newline_before_object">개체 이니셜라이저의 멤버 앞에서 줄 바꿈</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
| `csharp_new_line_before_members_in_object_initializers`|  C#  | true | Visual Studio 2017 v. 15.3  |


| 값 | 설명 
| ------------- |:-------------|
| True | 개체 이니셜라이저의 멤버를 별도 줄에 배치해야 합니다.  |
| False | 개체 이니셜라이저의 멤버를 동일한 줄에 배치해야 합니다.  |

#### <a name="applied"></a>적용됨:
```csharp
// csharp_new_line_before_members_in_object_initializers = true
var z = new B()
{
    A = 3,
    B = 4
}
```

```csharp
// csharp_new_line_before_members_in_object_initializers = false
var z = new B()
{
    A = 3, B = 4
}
```

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_new_line_before_members_in_object_initializers = true
``` 

### <a name="newline_before_anonymous">무명 형식의 멤버 앞에서 줄 바꿈</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
| `csharp_new_line_before_members_in_anonymous_types` |  C#  | true | Visual Studio 2017 v. 15.3  |


| 값 | 설명 
| ------------- |:-------------|
| True | 무명 형식의 멤버를 별도 줄에 배치해야 합니다.  |
| False | 무명 형식의 멤버를 동일한 줄에 배치해야 합니다.  |

#### <a name="applied"></a>적용됨:
```csharp
// csharp_new_line_before_members_in_anonymous_types = true
var z = new
{
    A = 3,
    B = 4
}
```

```csharp
// csharp_new_line_before_members_in_anonymous_types = false
var z = new
{
    A = 3, B = 4
}
```

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_new_line_before_members_in_anonymous_types = true
``` 

### <a name="newline_before_query">쿼리 식 절의 멤버 앞에서 줄 바꿈</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_new_line_within_query_expression_clauses`  |  C#  | true | Visual Studio 2017 v. 15.3  |


| 값 | 설명 
| ------------- |:-------------|
| True | 쿼리 식 절의 요소를 별도 줄에 배치해야 합니다.  |
| False | 쿼리 식 절의 요소를 동일한 줄에 배치해야 합니다.  |

#### <a name="applied"></a>적용됨:
```csharp
// csharp_new_line_within_query_expression_clauses = true
var q = from a in e
        from b in e
        select a * b;
```

```csharp
// csharp_new_line_within_query_expression_clauses = false
var q = from a in e from b in e
        select a * b;
```

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_new_line_within_query_expression_clauses = true
``` 

## <a name="indent">들여쓰기 옵션</a>
### <a name="indent_switch">`switch` 대/소문자 콘텐츠 들여쓰기</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
| `csharp_indent_case_contents`  |  C#  | true | Visual Studio 2017 v. 15.3  |

| 값 | 설명 
| ------------- |:-------------|
| True | `switch` 대/소문자 콘텐츠 들여쓰기  |
| False | `switch` 대/소문자 콘텐츠 들여쓰지 않기 |

#### <a name="applied"></a>적용됨:
```csharp
// csharp_indent_case_contents = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}
```

```csharp
// csharp_indent_case_contents = false
switch(c) {
    case Color.Red:
    Console.WriteLine("The color is red");
    break;
    case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
    default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_indent_case_contents = true
``` 

### <a name="indent_switch_labels"> `switch` 레이블 들여쓰기 </a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
| `csharp_indent_switch_labels`  |  C#  | true | Visual Studio 2017 v. 15.3  |

| 값 | 설명 
| ------------- |:-------------|
| True | `switch` 레이블 들여쓰기  |
| False | `switch` 레이블 들여쓰지 않음 |

#### <a name="applied"></a>적용됨:
```csharp
// csharp_indent_switch_labels = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}
```

```csharp
// csharp_indent_switch_labels = false
switch(c) {
case Color.Red:
    Console.WriteLine("The color is red");
    break;
case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_indent_switch_labels = true
``` 

### <a name="label">레이블 위치 지정</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|`csharp_indent_labels`  |  C#  | one_less | Visual Studio 2017 v. 15.3  |


| 값 | 설명 
| ------------- |:-------------|
| one_less | 레이블은 현재 컨텍스트에 하나 적은 들여쓰기로 배치됩니다. |
| no_change | 레이블은 현재 컨텍스트와 동일한 들여쓰기로 배치됩니다. |

#### <a name="applied"></a>적용됨:
```csharp
// csharp_indent_labels = one_less
private string MyMethod(...) 
{
    if (...) {
        goto error;
    }
error:
    throw new Exception(...);
}

```

```csharp
// csharp_indent_labels= no_change
private string MyMethod(...) 
{
    if (...) {
        goto error;
    }
    error:
    throw new Exception(...);
}
```

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_indent_labels = one_less
``` 

## <a name="spacing">간격 옵션</a>
### <a name="space_after_cast">캐스트 뒤에 공백</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
| `csharp_space_after_cast` |  C#  | false | Visual Studio 2017 v. 15.3  |


| 값 | 설명 | 적용됨 |
| ------------- |:-------------|:-------------|
| True | 캐스트와 값 간의 공백 필요  | **C#:** <br>`int y = (int) x;`
| False | 캐스트와 값 간의 공백 필요 없음 | **C#:** <br>`int y = (int)x;`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_space_after_cast = true
``` 

### <a name="space_control_flow"> 제어 흐름 문의 키워드 뒤에 공백 </a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
| `csharp_space_after_keywords_in_control_flow_statements` |  C#  | true | Visual Studio 2017 v. 15.3  |


| 값 | 설명 | 적용됨 |
| ------------- |:-------------|:-------------|
| True | 키워드 뒤에 공백 필요 | **C#:** <br>`for (int i;i<x;i++) { ... }`
| False | 키워드 뒤에 공백 필요 없음 | **C#:** <br>`for(int i;i<x;i++) { ... }`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_space_after_keywords_in_control_flow_statements = true
``` 

### <a name="space_parameter_list">메서드 선언 인수 목록 괄호 간의 공백</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
| `csharp_space_between_method_declaration_parameter_list_parentheses` |  C#  | false | Visual Studio 2017 v. 15.3  |


| 값 | 설명 | 적용됨 |
| ------------- |:-------------|:-------------|
| True | 키워드 뒤에 공백 필요 | **C#:** <br>`void Bark( int x ) { ... }`
| False | 키워드 뒤에 공백 필요 없음 | **C#:** <br>`void Bark(int x) { ... }`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_space_between_method_declaration_parameter_list_parentheses = true
```

### <a name="space_method_call">메서드 호출 인수 목록의 괄호 내 공백</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|  `csharp_space_between_method_call_parameter_list_parentheses` |  C#  | false | Visual Studio 2017 v. 15.3  |


| 값 | 설명 | 적용됨 |
| ------------- |:-------------|:-------------|
| true | 제어 흐름 문의 괄호 간에 공백 배치 | **C#:** <br>`MyMethod( argument );`
| false | 식의 괄호 간에 공백 배치 | **C#:** <br>`MyMethod(argument);`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_space_between_method_call_parameter_list_parentheses = control_flow_statements, type_casts
```  

### <a name="space_other">다른 옵션의 괄호 내 공백</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|  `csharp_space_between_parentheses`  |  C#  | false | Visual Studio 2017 v. 15.3  |


| 값 | 설명 | 적용됨 |
| ------------- |:-------------|:-------------|
| control_flow_statements | 제어 흐름 문의 괄호 간에 공백 배치 | **C#:** <br>`for( int i;i<x;i++ ) { ... }`
| 식 | 식의 괄호 간에 공백 배치 | **C#:** <br>`var z = ( x * y ) - ( ( y - x ) * 3);`
| type_casts | 형식 캐스트의 괄호 간에 공백 배치 | **C#:**<br>`int y = ( int )x;`

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_space_between_parentheses = control_flow_statements, type_casts
``` 

## <a name="wrapping">래핑 옵션</a>
### <a name="wrapping_statement">문과 멤버 선언을 동일한 줄에 유지</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|  `csharp_preserve_single_line_statements`   |  C#  | true | Visual Studio 2017 v. 15.3  |


| 값 | 설명 |
| ------------- |:-------------|
| True | 문과 멤버 선언을 동일한 줄에 유지  | 
| False | 문과 멤버 선언을 다른 줄에 유지 | 

#### <a name="applied"></a>적용됨
```csharp
//csharp_preserve_single_line_statements = true
int i = 0; string name = "John";
```

```csharp
//csharp_preserve_single_line_statements = false
int i = 0; 
string name = "John";
```

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_preserve_single_line_statements = true
``` 

### <a name="wrapping_block">블록을 한 줄에 유지</a>
| **옵션 이름** | **해당 언어** | **Visual Studio 기본값** | **지원되는 버전** |
| ----------- | -------------------- | ----------------------| ----------------  |
|   `csharp_preserve_single_line_blocks`    |  C#  | true | Visual Studio 2017 v. 15.3  |


| 값 | 설명 |
| ------------- |:-------------|
| True | 블록을 한 줄에 유지 | 
| False | 블록을 별도 줄에 유지 | 

#### <a name="applied"></a>적용됨
```csharp
//csharp_preserve_single_line_blocks = true
public int Foo { get; set; }
```

```csharp
//csharp_preserve_single_line_blocks = false
public int MyProperty
{ 
    get; set;
}
```

#### <a name="example-editorconfig-file"></a>예제 editorconfig 파일:
```
# CSharp formatting settings:
[*.cs]
csharp_preserve_single_line_blocks = true
``` 

# <a name="naming">명명 규칙</a>
## <a name="overview"></a>개요
**규칙 형식:**<br>
namingRuleTitle:<br>
`dotnet_naming_rule.<namingRuleTitle>.symbols = <symbolTitle>`<br>
`dotnet_naming_rule.<namingRuleTitle>.style = <styleTitle>`<br>
`dotnet_naming_rule.<namingRuleTitle>.severity = none|suggestion|warning|error`<br>
<br>
symbolTitle:<br>
`dotnet_naming_symbols.<symbolTitle>.applicable_kinds = class, struct, interface, enum, property, method, field, event, namespace, delegate, type_parameter`<br>
`dotnet_naming_symbols.<symbolTitle>.applicable_accessibilities = public, internal, private, protected, protected_internal`<br>
`dotnet_naming_symbols.<symbolTitle>.required_modifiers = abstract, async, const, readonly, static`<br>
<br>
styleTitle:<br>
`dotnet_naming_style.<styleTitle>.capitalization = pascal_case|camel_case|first_word_upper|all_upper|all_lower`<br>
`dotnet_naming_style.<styleTitle>.required_prefix = string`<br>
`dotnet_naming_style.<styleTitle>.required_suffix = string`<br>
`dotnet_naming_style.<styleTitle>.word_separator = string`<br>

## <a name="writing-a-naming-convention"></a>명명 규칙 작성
명명 규칙의 경우 **기호**, **스타일** 및 **심각도**를 지정해야 합니다. 명명 규칙은 가장 구체적인 규칙부터 가장 덜 구체적인 규칙으로 정렬되어야 합니다. 적용할 수 있는 첫 번째 규칙은 적용되는 유일한 규칙이 됩니다. 

### <a name="severity"></a>심각도
다음은 명명 스타일 규칙의 심각도에 유효한 옵션입니다. `none`, `silent`, `suggestion`, `warning`, `error`

 `none` 및 `silent`는 동의어이며 사용자에게 표시되어야 한함을 의미하지 않습니다. 이 항목에는 이 규칙을 비활성화하는 효과가 있습니다.

 `suggestion`은 다음이 오류 목록에 표시되고 다음이 IDE에 표시됨을 의미합니다. `suggestion` 심각도는 명명 규칙을 허용하지만 빌드를 중단하지 않습니다.

심각도 | 효과
------------ | -------------
none/silent | 이 스타일을 따르지 않을 경우 사용자에게 아무 메시지도 표시되지 않지만 코드 생성 기능은 이 스타일로 생성됩니다. 
suggestion | 이 스타일을 따르지 않을 경우 사용자에게 제안으로 표시됩니다(처음 두 문자에 점선이 밑줄로 표시됨).
경고 | 이 스타일을 따르지 않을 경우 컴파일러 경고가 표시됩니다.
오류 | 이 스타일을 따르지 않을 경우 컴파일러 오류가 표시됩니다.

### <a name="symbol-specification"></a>기호 사양
_어떤_ 기호가 _어떤_ 한정자 및 _어떤_ 액세스 가능성 수준으로 명명 규칙을 적용해야 하는지 식별합니다.

|  옵션 이름 | `dotnet_naming_rule.<namingRuleTitle>.symbols` |
| ------------- |:-------------:|
|  | `dotnet_naming_symbols.<symbolTitle>.applicable_kinds`
|  | `dotnet_naming_symbols.<symbolTitle>.applicable_accessibilities`
|  | `dotnet_naming_symbols.<symbolTitle>.required_modifiers`

| 기호 | 액세스 가능성 | 한정자
| ------------- |------------- |------------- |
| `*` | `*` |  `abstract` | 
| `class` | `public` |  `must_inherit` | `async` | 
| `struct` | `internal`(C#) /  | `const` | 
| `interface` | `friend`(Visual Basic) | `readonly` | 
| `enum` | `private`  | `static` | 
| `property` | `protected` | `shared` |
| `method` |`protected_internal`(C#) | |
| `field` | `protected_friend`(Visual Basic) | |
| `event` | | |
| `delegate` | | |


### <a name="style-specification"></a>스타일 사양
기호에 적용할 명명 스타일을 식별합니다.

|  옵션 이름 | `dotnet_naming_rule.<namingRuleTitle>.style = <styleTitle>` |
| ------------- |:-------------:|
|  | `dotnet_naming_style.<styleTitle>.capitalization`|
|  | `dotnet_naming_style.<styleTitle>.required_prefix`|
|  | `dotnet_naming_style.<styleTitle>.required_suffix`|
|  | `dotnet_naming_style.<styleTitle>.word_separator`|


| 스타일 | 설명 |
| ------------- |:-------------:|
| 접두사 | 식별자 앞에 표시되어야 하는 필수 문자입니다. |
| 접미사 | 식별자 뒤에 표시되어야 하는 필수 문자입니다. |
| 단어 구분 기호 | 식별자에서 단어 간의 필수 구분 기호입니다. |
| 대문자 표시 |`pascal_case`, `camel_case`, `first_word_upper`, `all_upper`, `all_lower` | 


### <a name="example-naming-convention"></a>예제 명명 규칙
```
# CSharp formatting settings:
[*.cs]
dotnet_naming_rule.async_methods_end_in_async.symbols  = any_async_methods
dotnet_naming_rule.async_methods_end_in_async.style    = end_in_async
dotnet_naming_rule.async_methods_end_in_async.severity = suggestion

dotnet_naming_symbols.any_async_methods.applicable_kinds           = method
dotnet_naming_symbols.any_async_methods.applicable_accessibilities = *
dotnet_naming_symbols.any_async_methods.required_modifiers         = async

dotnet_naming_style.end_in_async.required_suffix = Async
dotnet_naming_style.end_in_async.capitalization  = pascal_case
``` 

