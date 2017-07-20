---
title: "EditorConfig에 대한 .NET 코드 스타일 설정 | Microsoft 문서"
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
caps.latest.revision: 01
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 8ce85525f6af336682f6f8547c2f6c13dde73c8c
ms.openlocfilehash: 288595f50555bd8314d0ad60cd2e1ce8121a8ab0
ms.contentlocale: ko-kr
ms.lasthandoff: 06/23/2017

---

# EditorConfig에 대한 .NET 코드 스타일 설정
<a id="net-code-style-settings-for-editorconfig" class="xliff"></a>

## 가능한 값
<a id="possible-values" class="xliff"></a>

`options_name = false|true : none|suggestion|warning|error`

코드 스타일 옵션에 대해 **true**(이 옵션 선호) 또는 **false**(이 옵션 선호 안 함), 콜론(`:`) 및 심각도(`none`, `suggestion`, `warning` 또는 `error`)를 지정해야 합니다. 심각도는 코드 베이스에서 원하는 스타일의 적용 수준을 의미합니다.

심각도 | 효과
------------ | -------------
없음 | 이 스타일을 따르지 않을 경우 사용자에게 아무 메시지도 표시되지 않지만 코드 생성 기능은 이 스타일로 생성됩니다. 
suggestion | 이 스타일을 따르지 않을 경우 사용자에게 제안으로 표시됩니다(처음 두 문자에 점선이 밑줄로 표시됨).
경고 | 이 스타일을 따르지 않을 경우 컴파일러 경고가 표시됩니다.
오류 | 이 스타일을 따르지 않을 경우 컴파일러 오류가 표시됩니다.

## .NET 코드 스타일 옵션
<a id="net-code-style-options" class="xliff"></a>

- [Dotnet 코드 스타일 설정](#this_and_me)
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
- [CSharp 코드 스타일 설정](#csharp_codestyle)
    - ["var"](#var)
        - [기본 제공 형식에 "var" 사용](#var_built_in)
        - [형식이 명확한 경우 "var" 사용](#var_apparent)
        - [다른 곳에서 "var" 사용](#var_elsewhere)
    - [식 본문 멤버](#expression_bodied_members)
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
    - ["Null" 검사 기본 설정](#null_checking)
        - [Throw 식](#null_checking_throw_expressions)
        - [조건부 대리자 호출](#null_checking_conditional_delegate_calls)

## <a name="this_and_me">"This." 및 "Me." 한정</a>

### <a name="this_and_me_fields">필드</a>

|  옵션 이름 | `dotnet_style_qualification_for_field` |
| ------------- |:-------------:|
| **해당 언어** | C# 및 Visual Basic

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 비정적 메서드에서 사용되는 모든 비정적 필드 앞에 `this.`(C#) 또는 `Me.`(Visual Basic)를 추가하는 것이 좋습니다. | **C#:** <br>`this.capacity = 0;` <br><br> **Visual Basic:** `Me.capacity = 0`
| False | 비정적 메서드에서 사용되는 모든 비정적 필드 앞에 `this.`(C#) 또는 `Me.`(Visual Basic)를 추가하지 않는 것이 좋습니다. | **C#:** <br>`capacity = 0;` <br><br> **Visual Basic:** `capacity = 0`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp and VisualBasic code style settings:
[*.cs,*.vb]
dotnet_style_qualification_for_field = false:suggestion
```

### <a name="this_and_me_properties">속성</a>

|  옵션 이름 | `dotnet_style_qualification_for_property` |
| ------------- |:-------------:|
| **해당 언어** | C# 및 Visual Basic

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 비정적 메서드에서 사용되는 모든 비정적 속성 앞에 `this.`(C#) 또는 `Me.`(Visual Basic)를 추가하는 것이 좋습니다.| **C#:** <br>`this.ID = 0;` <br><br> **Visual Basic:** `Me.ID = 0`
| False | 비정적 메서드에서 사용되는 모든 비정적 속성 앞에 `this.`(C#) 또는 `Me.`(Visual Basic)를 추가하지 *않는* 것이 좋습니다. | **C#:** <br>`ID = 0;` <br><br> **Visual Basic:** `ID = 0`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp and VisualBasic code style settings:
[*.cs,*.vb]
dotnet_style_qualification_for_property = false:suggestion
```


### <a name="this_and_me_methods">메서드</a>
|  옵션 이름 | `dotnet_style_qualification_for_method` |
| ------------- |:-------------:|
| **해당 언어** | C# 및 Visual Basic

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 비정적 메서드 내에서 호출되는 모든 비정적 메서드 앞에 `this.`(C#) 또는 `Me.`(VB)를 추가하는 것이 좋습니다.| **C#:** <br>`this.Display();` <br><br> **Visual Basic:** `Me.Display()`
| False | 비정적 메서드 내에서 호출되는 모든 비정적 메서드 앞에 `this.`(C#) 또는 `Me.`(VB)를 추가하지 *않는* 것이 좋습니다. | **C#:** <br>`Display();` <br><br> **Visual Basic:** `Display()`


#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_qualification_for_method = false:suggestion
```

### <a name="this_and_me_events">이벤트</a>
|  옵션 이름 | `dotnet_style_qualification_for_event` |
| ------------- |:-------------:|
| **해당 언어** | C# 및 Visual Basic

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 비정적 메서드 내에서 참조되는 모든 비정적 이벤트 앞에 `this.`(C#) 또는 `Me.`(VB)를 추가하는 것이 좋습니다.| **C#:** <br>`this.Elapsed += Handler;` <br><br> **Visual Basic:** `AddHandler Me.Elapsed, AddressOf Handler`
| False | 비정적 메서드 내에서 참조되는 모든 비정적 이벤트 앞에 `this.`(C#) 또는 `Me.`(VB)를 추가하지 *않는* 것이 좋습니다. | **C#:** <br>`Elapsed += Handler;` <br><br> **Visual Basic:** `AddHandler Elapsed, AddressOf Handler`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_qualification_for_event = false:suggestion
```

## <a name="language_keywords">형식 참조를 위한 언어 키워드(int, string 등) 및 프레임워크 형식 이름</a>
### <a name="language_keywords_variables">로컬 항목, 매개 변수 및 멤버</a>
|  옵션 이름 | `dotnet_style_predefined_type_for_locals_parameters_members` |
| ------------- |:-------------:|
| **해당 언어** | C# 및 Visual Basic

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 로컬 항목, 매개 변수 및 형식 멤버의 경우 언어 키워드로 형식을 나타내는 형식(`int`, `double`, `float`, `short`, `long`, `decimal`, `string`)에서 형식 이름(`Int32`, `Int64` 등) 대신 키워드를 사용하는 것이 좋습니다.| **C#:** <br>`private int _member;` <br><br> **Visual Basic:** `Private _member As Integer`
| False | 로컬 항목, 매개 변수 및 형식 멤버의 경우 언어 키워드로 형식을 나타내는 형식(`int`, `double`, `float`, `short`, `long`, `decimal`, `string`)에서 키워드 대신 형식 이름(`Int32`, `Int64` 등)을 사용하는 것이 좋습니다.  | **C#:** <br>`private Int32 _member;` <br><br> **Visual Basic:** `Private _member As Int32`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_predefined_type_for_locals_parameters_members = true:suggestion
``` 

### <a name="language_keywords_member_access">멤버 액세스 식</a>
|  옵션 이름 | `dotnet_style_predefined_type_for_member_access` |
| ------------- |:-------------:|
| **해당 언어** | C# 및 Visual Basic

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 멤버 액세스 식이 키워드 표현(`int`, `double`, `float`, `short`, `long`, `decimal`, `string`)과 함께 형식에 사용될 때마다 키워드를 사용하는 것이 좋습니다.| **C#:** <br>`var local = int.MaxValue;` <br><br> **Visual Basic:** `Dim local = Integer.MaxValue`
| False | 멤버 액세스 식이 키워드 표현(`int`, `double`, `float`, `short`, `long`, `decimal`, `string`)과 함께 형식에 사용될 때마다 형식 이름을 사용하는 것이 좋습니다. | **C#:** <br>`var local = Int32.MaxValue;` <br><br> **Visual Basic:** `Dim local = Int32.MaxValue`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_predefined_type_for_member_access = true:suggestion
``` 

## <a name="expression_level">식 수준 기본 설정</a>
### <a name="expression_level_object_initializers">개체 이니셜라이저</a>
|  옵션 이름 | `dotnet_style_object_initializer` |
| ------------- |:-------------:|
| **해당 언어** | C# 및 Visual Basic

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 가능한 경우 개체 이니셜라이저를 사용하여 개체를 초기화하는 것이 좋습니다.| **C#:** <br>`var c = new Customer(){ Age = 21 };` <br><br> **Visual Basic:** `Dim c = New Customer() With { .Age = 21 }`
| False | 개체 이니셜라이저를 사용하여 개체를 초기화하지 *않는* 것이 좋습니다. | **C#:** <br>`var c = new Customer();`<br>`c.Age = 21;` <br><br> **Visual Basic:** <br>`Dim c = new Customer() `<br>`c.Age = 21`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_object_initializer = true:suggestion
``` 

### <a name="expression_level_collection_initializers">컬렉션 이니셜라이저</a>
|  옵션 이름 | `dotnet_style_collection_initializer` |
| ------------- |:-------------:|
| **해당 언어** | C# 및 Visual Basic

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 가능한 경우 컬렉션 이니셜라이저를 사용하여 컬렉션을 초기화하는 것이 좋습니다.| **C#:** <br>`var list = new List<int>{ 1, 2, 3 };` <br><br> **Visual Basic:** <br> `Dim list = new List(Of Integer) From { 1, 2, 3}`
| False | 컬렉션 이니셜라이저를 사용하여 컬렉션을 초기화하지 *않는* 것이 좋습니다. | **C#:** <br>`var list = new List<int>();`<br>`list.Add(1);`<br>`list.Add(2);`<br>`list.Add(3);` <br><br> **Visual Basic:** <br>`Dim list = new List(Of Integer)`<br>`list.Add(1)`<br>`list.Add(2)`<br>`list.Add(3)`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_collection_initializer = true:suggestion
```

### <a name="expression_level_tuple_names">명시적 튜플 이름</a>
|  옵션 이름 | `dotnet_style_explicit_tuple_names` |
| ------------- |:-------------:|
| **해당 언어** | C# 및 Visual Basic

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | ItemX 속성보다 튜플 이름을 사용하는 것이 좋습니다.| **C#:** <br>`(string name, int age) customer = GetCustomer();`<br>`var name = customer.name;` <br><br> **Visual Basic:** <br> `Dim customer As (name As String, age As Integer) = GetCustomer()`<br>`Dim name = customer.name`
| False | 튜플 이름보다 ItemX 속성을 사용하는 것이 좋습니다. | **C#:** <br>`(string name, int age) customer = GetCustomer();`<br>`var name = customer.Item1;` <br><br> **Visual Basic:** <br>`Dim customer As (name As String, age As Integer) = GetCustomer()`<br> `Dim name = customer.Item1`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_explicit_tuple_names = true:suggestion
``` 

### <a name="expression_level_null_checking">"null" 검사에 식 병합</a>
|  옵션 이름 | `dotnet_style_coalesce_expression` |
| ------------- |:-------------:|
| **해당 언어** | C# 및 Visual Basic

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 3개로 구성된 연산자 검사보다 null 병합 식을 사용하는 것이 좋습니다.| **C#:** <br>`var v = x ?? y;` <br><br> **Visual Basic:** <br> `Dim v = If(x, y)`
| False | null 병합 식보다 3개로 구성된 연산자 검사를 사용하는 것이 좋습니다. | **C#:** <br>`var v = x != null ? x : y; // or`<br>`var v = x == null ? y : x;` <br><br> **Visual Basic:** <br>`Dim v = If(x Is Nothing, y, x) ' or`<br> `Dim v = If(x IsNot Nothing, x, y)`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_coalesce_expression = true:suggestion
``` 

### <a name="expression_level_null_propogation">"null" 검사의 Null 전파</a>
|  옵션 이름 | `dotnet_style_null_propagation` |
| ------------- |:-------------:|
| **해당 언어** | C# 및 Visual Basic

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 가능한 경우 null 조건부 연산자를 사용하는 것이 좋습니다.| **C#:** <br>`var v = o?.ToString();` <br><br> **Visual Basic:** <br> `Dim v = o?.ToString()`
| False | 가능한 경우 3개로 구성된 null 검사를 사용하는 것이 좋습니다. | **C#:** <br>`var v = o == null ? null : o.ToString(); // or`<br>`var v = o != null ? o.String() : null;` <br><br> **Visual Basic:** <br>`Dim v = If(o Is Nothing, Nothing, o.ToString()) ' or`<br> `Dim v = If(o IsNot Nothing, o.ToString(), Nothing)`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp and VisualBasic code style settings:
[*.cs, *.vb]
dotnet_style_null_propagation = true:suggestion
``` 

# <a name="csharp_codestyle">CSharp 코드 스타일 설정</a>
## <a name="var">"var"</a>
### <a name="var_built_in">기본 제공 형식에 "var" 사용</a>
|  옵션 이름 | `csharp_style_var_for_built_in_types` |
| ------------- |:-------------:|
| **해당 언어** | C#

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | `int` 등의 기본 제공 시스템 형식에 `var`을 사용하는 것이 좋습니다.| **C#:** <br>`var x = 5;`
| False | `int` 등의 기본 제공 시스템 형식에 `var`을 사용하지 않는 것이 좋습니다. | **C#:** <br>`int x = 5;`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp code style settings:
[*.cs]
csharp_style_var_for_built_in_types = true:suggestion
``` 

### <a name="var_apparent">형식이 명확한 경우 "var" 사용</a>
|  옵션 이름 | `csharp_style_var_when_type_is_apparent` |
| ------------- |:-------------:|
| **해당 언어** | C#

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 선언 식의 오른쪽에서 형식이 이미 언급된 경우 `var`을 사용하는 것이 좋습니다.| **C#:** <br>`var obj = new C();`
| False | 선언 식의 오른쪽에서 형식이 이미 언급된 경우 `var`을 사용하지 않는 것이 좋습니다. | **C#:** <br>`C obj = new C();`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp code style settings:
[*.cs]
csharp_style_var_when_type_is_apparent = true:suggestion
``` 

### <a name="var_elsewhere">다른 곳에서 "var" 사용</a>
|  옵션 이름 | `csharp_style_var_elsewhere` |
| ------------- |:-------------:|
| **해당 언어** | C#

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 다른 코드 스타일 규칙에 의해 재정의되지 않는 경우 항상 `var`을 사용하는 것이 좋습니다.| **C#:** <br>`var f = this.Init();`
| False | 다른 코드 스타일 규칙에 의해 재정의되지 않는 경우 항상 var을 사용하지 않는 것이 좋습니다.| **C#:** <br>`bool f = this.Init();`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp code style settings:
[*.cs]
csharp_style_var_elsewhere = true:suggestion
``` 

### <a name="expression_bodied_members">메서드</a>
|  옵션 이름 | `csharp_style_expression_bodied_methods` |
| ------------- |:-------------:|
| **해당 언어** | C#

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 메서드에 식 본문 멤버를 사용하는 것이 좋습니다.| **C#:** <br>`public int GetAge() => this.Age;`
| False | 메서드에 식 본문 멤버를 사용하지 않는 것이 좋습니다.| **C#:** <br>`public int GetAge() { return this.Age; }`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_methods = false:none
``` 

### <a name="expression_bodied_members_constructors">생성자</a>
|  옵션 이름 | `csharp_style_expression_bodied_constructors` |
| ------------- |:-------------:|
| **해당 언어** | C#

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 생성자에 식 본문 멤버를 사용하는 것이 좋습니다.| **C#:** <br>`public Customer(int age) => Age = age;`
| False | 생성자에 식 본문 멤버를 사용하지 않는 것이 좋습니다.| **C#:** <br>`public Customer(int age) { Age = age; }`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_constructors = false:none
``` 

### <a name="expression_bodied_members_operators">연산자</a>
|  옵션 이름 | `csharp_style_expression_bodied_operators` |
| ------------- |:-------------:|
| **해당 언어** | C#

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 연산자에 식 본문 멤버를 사용하는 것이 좋습니다.| **C#:** <br>`public static ComplexNumber operator +(ComplexNumber c1, ComplexNumber c2)`<br>`=> new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary);`
| False | 연산자에 식 본문 멤버를 사용하지 않는 것이 좋습니다.| **C#:** <br>`public static ComplexNumber operator +(ComplexNumber c1, ComplexNumber c2)`<br>`{ return new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary); }`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_operators = false:none
``` 

### <a name="expression_bodied_members_properties">속성</a>
|  옵션 이름 | `csharp_style_expression_bodied_properties` |
| ------------- |:-------------:|
| **해당 언어** | C#

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 속성에 식 본문 멤버를 사용하는 것이 좋습니다.| **C#:** <br>`public int Age => _age;`
| False | 속성에 식 본문 멤버를 사용하지 않는 것이 좋습니다.| **C#:** <br>`public int Age { get { return _age; }}`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_properties = false:none
``` 

### <a name="expression_bodied_members_indexers">인덱서</a>
|  옵션 이름 | `csharp_style_expression_bodied_indexers` |
| ------------- |:-------------:|
| **해당 언어** | C#

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 인덱서에 식 본문 멤버를 사용하는 것이 좋습니다.| **C#:** <br>`public T this[int i] => _value[i];`
| False | 인덱서에 식 본문 멤버를 사용하지 않는 것이 좋습니다.| **C#:** <br>`public T this[int i] { get { return _values[i]; } }`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_indexers = false:none
``` 

### <a name="expression_bodied_members_accessors">접근자</a>
|  옵션 이름 | `csharp_style_expression_bodied_accessors` |
| ------------- |:-------------:|
| **해당 언어** | C#

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 접근자에 식 본문 멤버를 사용하는 것이 좋습니다.| **C#:** <br>`public int Age { get => _age; set => _age = value; }`
| False | 접근자에 식 본문 멤버를 사용하지 않는 것이 좋습니다.| **C#:** <br>`public int Age { get { return _age; } set { _age = value; } }`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_accessors = false:none
``` 

## <a name="pattern_matching">패턴 일치</a>
### <a name="pattern_matching_is_cast">"캐스트" 검사를 포함하는 "is"</a>
|  옵션 이름 | `csharp_style_pattern_matching_over_is_with_cast_check` |
| ------------- |:-------------:|
| **해당 언어** | C#

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 캐스트를 포함하는 `is` 식보다 패턴 일치를 사용하는 것이 좋습니다.| **C#:** <br>`if (o is int i) {...}`
| False | 패턴 일치보다 형식 캐스트를 포함하는 `is` 식을 사용하는 것이 좋습니다.| **C#:** <br>`if (o is int) {var i = (int)o; ... }`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp code style settings:
[*.cs]
csharp_style_pattern_matching_over_is_with_cast_check = true:suggestion
```

### <a name="pattern_matching_as_null">"null" 검사를 포함하는 "as"</a>
|  옵션 이름 | `csharp_style_pattern_matching_over_as_with_null_check` |
| ------------- |:-------------:|
| **해당 언어** | C#

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | null 검사를 포함하는 `as` 식 대신 패턴 일치를 사용하여 항목이 특정 형식인지 확인하는 것이 좋습니다.| **C#:** <br>`if (o is string s) {...}`
| False | 패턴 일치 대신 null 검사를 포함하는 `as` 식을 사용하여 항목이 특정 형식인지 확인하는 것이 좋습니다.| **C#:** <br>`var s = o as string; if (s != null) {...}`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp code style settings:
[*.cs]
csharp_style_pattern_matching_over_as_with_null_check = true:suggestion
```

### <a name="inlined_variable_declarations">인라인 변수 선언</a>
|  옵션 이름 | `csharp_style_inlined_variable_declaration` |
| ------------- |:-------------:|
| **해당 언어** | C#

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | 가능한 경우 `out` 변수를 인라인으로 선언하는 것이 좋습니다. | **C#:** <br>`if (int.TryParse(value, out int i) {...}`
| False | 가능한 경우 `out` 변수를 명시적으로 선언하는 것이 좋습니다.| **C#:** <br>`int i; if (int.TryParse(value, out i) {...}`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp code style settings:
[*.cs]
csharp_style_inlined_variable_declaration = true:suggestion
```

## <a name="null_checking">"Null" 검사 기본 설정</a>
### <a name="null_checking_throw_expressions">Throw 식</a>
|  옵션 이름 | `csharp_style_throw_expression` |
| ------------- |:-------------:|
| **해당 언어** | C#

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | throw 문 대신 throw 식을 사용하는 것이 좋습니다. | **C#:** <br>`this.s = ss ?? throw new ArgumentNullException(nameof(s));`
| False | throw 식 대신 throw 문을 사용하는 것이 좋습니다.| **C#:** <br>`if (s==null) {throw new ArgumentNullException(nameof(s));} this.s = s;`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp code style settings:
[*.cs]
csharp_style_throw_expression = true:suggestion
```

### <a name="null_checking_conditional_delegate_calls">조건부 대리자 호출 선호</a>
|  옵션 이름 | `csharp_style_conditional_delegate_call` |
| ------------- |:-------------:|
| **해당 언어** | C#

| 값 | 설명 | 적용됨 
| ------------- |:-------------|:-------------|
| True | null 검사를 수행하는 대신 람다 호출 시 조건부 병합 연산(`?.`)을 사용하는 것이 좋습니다. | **C#:** <br>`func?.Invoke(args);`
| False | 조건부 병합 연산자(`?.`)를 사용하는 대신 람다 호출 시 null 검사를 수행하는 것이 좋습니다.| **C#:** <br>`if (func!=null) { func(args); }`

#### 예제 editorconfig 파일:
<a id="example-editorconfig-file" class="xliff"></a>
```
# CSharp code style settings:
[*.cs]
csharp_style_conditional_delegate_call = false:suggestion
```

