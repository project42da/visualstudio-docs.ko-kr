---
title: Visual Studio에서 EditorConfig에 대한 .NET Coding 규칙 설정 | Microsoft Docs
ms.date: 02/28/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- coding conventions [EditorConfig]
- EditorConfig coding conventions
- language conventions [EditorConfig]
- formatting conventions [EditorConfig]
author: kuhlenh
ms.author: kaseyu
manager: douge
ms.technology: vs-ide-general
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b313271e29bba660af1aa48654bfdfefb81e39f1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="net-coding-convention-settings-for-editorconfig"></a>EditorConfig에 대한 .NET 코딩 규칙 설정

Visual Studio 2017에서는 [EditorConfig](../ide/create-portable-custom-editor-options.md) 파일을 사용하여 코드베이스에서 일관된 코드 스타일을 정의하고 유지 관리할 수 있습니다. EditorConfig에는 `indent_style` 및 `indent_size`와 같은 여러 가지 주요 서식 지정 속성이 포함됩니다. Visual Studio에서 EditorConfig 파일을 사용하여 .NET 코딩 규칙 설정을 구성할 수도 있습니다. EditorConfig 파일을 사용하면 개별 .NET 코딩 규칙을 활성화 또는 비활성화하고 (심각도 수준을 통해) 규칙을 적용하려는 수준을 구성할 수 있습니다. EditorConfig를 사용하여 코드 베이스에 일관성을 적용하는 방법에 대한 자세한 내용을 보려면 [휴대용, 사용자 지정 편집기 옵션 만들기](../ide/create-portable-custom-editor-options.md)를 참고하세요. 또한 [.NET 컴파일러 플랫폼의 .editorconfig 파일](https://github.com/dotnet/roslyn/blob/master/.editorconfig)을 예로 들 수 있습니다.

지원되는 .NET 코딩 규칙 범주에는 세 가지가 있습니다.

- [언어 규칙](#language-conventions)

   C# 또는 Visual Basic 언어에 관련된 규칙입니다. 예를 들어 변수를 정의하거나 식 본문 멤버를 사용하는 것이 좋은 경우 `var` 또는 명시적 형식을 사용하여 규칙을 지정할 수 있습니다.

- [서식 지정 규칙](#formatting-conventions)

   보다 쉽게 읽을 수 있기 위한 코드의 레이아웃 및 구조체와 관련된 규칙입니다. 예를 들어 제어 블록에서 Allman 중괄호 또는 공백을 사용하는 규칙을 지정할 수 있습니다.

- [명명 규칙](../ide/editorconfig-naming-conventions.md)

   코드 요소의 명명과 관련된 규칙입니다. 예를 들어 `async` 메서드가 "Async"로 끝나야 하는지를 지정할 수 있습니다.

## <a name="language-conventions"></a>언어 규칙

언어 규칙의 규칙에는 다음과 같은 형식이 있습니다.

`options_name = false|true : none|suggestion|warning|error`

각 언어 규칙 규칙의 경우 **true**(이 스타일 선호) 또는 **false**(이 스타일 선호하지 않음) 및 **심각도**를 지정해야 합니다. 심각도는 해당 스타일에 적용하는 수준을 지정합니다.

다음 표에서는 가능한 심각도 값 및 해당 효과를 나열합니다.

심각도 | 효과
:------- | ------
none or silent | 이 규칙을 위반하는 경우 사용자에게 아무 것도 표시되지 않습니다. 그러나 코드 생성 기능은 이 스타일의 코드를 생성합니다.
suggestion | 이 스타일 규칙을 위반하는 경우 이를 사용자에게 제안으로 표시합니다. 제안은 처음 두 개의 문자 아래에 세 개의 회색 점으로 표시됩니다.
경고 | 이 스타일 규칙을 위반하는 경우 컴파일러 경고가 표시됩니다.
오류 | 이 스타일 규칙을 위반하는 경우 컴파일러 오류가 표시됩니다.

다음 목록에서는 허용되는 언어 규칙을 보여줍니다.

- .NET 코드 스타일 설정
    - ["This." 및 "Me." 한정자](#this_and_me)
        - dotnet\_style\_qualification\_for_field
        - dotnet\_style\_qualification\_for_property
        - dotnet\_style\_qualification\_for_method
        - dotnet\_style\_qualification\_for_event
    - [형식 참조를 위한 프레임워크 형식 이름 대신 언어 키워드](#language_keywords)
        - dotnet\_style\_predefined\_type\_for\_locals\_parameters_members
        - dotnet\_style\_predefined\_type\_for\_member_access
    - [한정자 기본 설정](#normalize_modifiers)
        - dotnet\_style\_require\_accessibility_modifiers
        - csharp\_preferred\_modifier_order
        - visual\_basic\_preferred\_modifier_order
    - [식 수준 기본 설정](#expression_level)
        - dotnet\_style\_object_initializer
        - dotnet\_style\_collection_initializer
        - dotnet\_style\_explicit\_tuple_names
        - dotnet\_prefer\_inferred\_tuple_names
        - dotnet\_prefer\_inferred\_anonymous\_type\_member_names
    - ["Null" 검사 기본 설정](#null_checking)
        - dotnet\_style\_coalesce_expression
        - dotnet\_style\_null_propagation
- C# 코드 스타일 설정
    - [암시적 및 명시적 형식](#var)
        - csharp\_style\_var\_for\_built\_in_types
        - csharp\_style\_var\_when\_type\_is_apparent
        - csharp\_style\_var_elsewhere
    - [식 본문 멤버](#expression_bodied_members)
        - csharp\_style\_expression\_bodied_methods
        - csharp\_style\_expression\_bodied_constructors
        - csharp\_style\_expression\_bodied_operators
        - csharp\_style\_expression\_bodied_properties
        - csharp\_style\_expression\_bodied_indexers
        - csharp\_style\_expression\_bodied_accessors
    - [패턴 일치](#pattern_matching)
        - csharp\_style\_pattern\_matching\_over\_is\_with\_cast_check
        - csharp\_style\_pattern\_matching\_over\_as\_with\_null_check
    - [인라인 변수 선언](#inlined_variable_declarations)
        - csharp\_style\_inlined\_variable_declaration
    - [식 수준 기본 설정](#expression_level_csharp)
        - csharp\_prefer\_simple\_default_expression
        - csharp\_style\_deconstructed\_variable_declaration
        - csharp\_style\_pattern\_local\_over\_anonymous_function
    - ["Null" 검사 기본 설정](#null_checking_csharp)
        - csharp\_style\_throw_expression
        - csharp\_style\_conditional\_delegate_call
    - [코드 블록 기본 설정](#code_block)
        - csharp\_prefer_braces

### <a name="net-code-style-settings"></a>.NET 코드 스타일 설정

이 섹션의 스타일 규칙은 C# 및 Visual Basic 모두에 적용됩니다. 원하는 프로그래밍 언어의 코드 예제를 보려면 브라우저 창의 상단 오른쪽 모서리에 있는 **언어** 메뉴 드롭다운에서 선택합니다.

#### <a name="this_and_me"></a>"This." 그리고 "Me." 한정자

이 스타일 규칙(규칙 ID IDE0003 및 IDE0009)은 필드, 속성, 메서드 또는 이벤트에 적용할 수 있습니다. 값이 **true**이면 C#에서 `this.` 또는 Visual Basic에서 `Me.`를 코드 기호 앞에 추가하는 것이 좋습니다. 값이 **false**이면 `this.` 또는 `Me.`을 코드 요소 앞에 추가하지 _않는_ 것이 좋습니다.

다음 표에서는 규칙 이름, 적용 가능한 프로그래밍 언어 및 기본값을 보여줍니다.

| 규칙 이름 | 해당 언어 | Visual Studio 기본값 |
| ----------- | -------------------- | ----------------------|
| dotnet_style_qualification_for_field | C# 및 Visual Basic | false:none |
| dotnet_style_qualification_for_property | C# 및 Visual Basic | false:none |
| dotnet_style_qualification_for_method | C# 및 Visual Basic | false:none |
| dotnet_style_qualification_for_event | C# 및 Visual Basic | false:none |

**dotnet\_style\_qualification\_for_field**

- 이 규칙을 **true**로 설정하면 C#에서 `this.` 또는 Visual Basic에서 `Me.`를 필드 앞에 추가하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 `this.` 또는 `Me.`을 필드 앞에 추가하지 _않는_ 것이 좋습니다.

코드 예제:

```csharp
// dotnet_style_qualification_for_field = true
this.capacity = 0;

// dotnet_style_qualification_for_field = false
capacity = 0;
```

```vb
' dotnet_style_qualification_for_field = true
Me.capacity = 0

' dotnet_style_qualification_for_field = false
capacity = 0
```

**dotnet\_style\_qualification\_for_property**

- 이 규칙을 **true**로 설정하면 C#에서 `this.` 또는 Visual Basic에서 `Me.`를 속성 앞에 추가하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 `this.` 또는 `Me.`을 속성 앞에 추가하지 _않는_ 것이 좋습니다.

코드 예제:

```csharp
// dotnet_style_qualification_for_property = true
this.ID = 0;

// dotnet_style_qualification_for_property = false
ID = 0;
```

```vb
' dotnet_style_qualification_for_property = true
Me.ID = 0

' dotnet_style_qualification_for_property = false
ID = 0
```

**dotnet\_style\_qualification\_for_method**

- 이 규칙을 **true**로 설정하면 C#에서 `this.` 또는 Visual Basic에서 `Me.`를 메서드 앞에 추가하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 `this.` 또는 `Me.`을 메서드 앞에 추가하지 _않는_ 것이 좋습니다.

코드 예제:

```csharp
// dotnet_style_qualification_for_method = true
this.Display();

// dotnet_style_qualification_for_method = false
Display();
```

```vb
' dotnet_style_qualification_for_method = true
Me.Display()

' dotnet_style_qualification_for_method = false
Display()
```

**dotnet\_style\_qualification\_for_event**

- 이 규칙을 **true**로 설정하면 C#에서 `this.` 또는 Visual Basic에서 `Me.`를 이벤트 앞에 추가하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 `this.` 또는 `Me.`을 이벤트 앞에 추가하지 _않는_ 것이 좋습니다.

코드 예제:

```csharp
// dotnet_style_qualification_for_event = true
this.Elapsed += Handler;

// dotnet_style_qualification_for_event = false
Elapsed += Handler;
```

```vb
' dotnet_style_qualification_for_event = true
AddHandler Me.Elapsed, AddressOf Handler

' dotnet_style_qualification_for_event = false
AddHandler Elapsed, AddressOf Handler
```

이러한 규칙은 *.editorconfig* 파일에서 다음과 같이 표시될 수 있습니다.

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_qualification_for_field = false:suggestion
dotnet_style_qualification_for_property = false:suggestion
dotnet_style_qualification_for_method = false:suggestion
dotnet_style_qualification_for_event = false:suggestion
```

#### <a name="language_keywords"></a>형식 참조를 위한 프레임워크 형식 이름 대신 언어 키워드

지역 변수, 메서드 매개 변수 및 클래스 멤버 또는 멤버 액세스 식을 입력할 별도 규칙으로 이 스타일 규칙을 적용할 수 있습니다. 값이 **true**인 경우 자신을 나타내는 키워드를 가진 형식에 형식 이름(예: `Int32`) 대신 언어 키워드(예: `int` 또는 `Integer`)를 사용하는 것이 좋습니다. 값이 **false**인 경우 언어 키워드 대신 형식 이름을 사용하는 것이 좋습니다.

다음 표에서는 규칙 이름, 규칙 ID, 적용 가능한 프로그래밍 언어 및 기본값을 보여줍니다.

| 규칙 이름 | 규칙 ID | 해당 언어 | Visual Studio 기본값 |
| --------- | ------- | -------------------- | ----------------------|
| dotnet_style_predefined_type_for_locals_parameters_members | IDE0012 및 IDE0014 | C# 및 Visual Basic | true:none |
| dotnet_style_predefined_type_for_member_access | IDE0013 및 IDE0015 | C# 및 Visual Basic | true:none |

**dotnet\_style\_predefined\_type\_for\_locals\_parameters_members**

- 이 규칙을 **true**로 설정하면 자신을 나타내는 키워드를 포함한 형식에 형식 이름 대신 지역 변수의 언어 키워드, 메서드 매개 변수 및 클래스 멤버를 사용하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 언어 키워드 대신 지역 변수의 형식 이름, 메서드 매개 변수 및 클래스 멤버를 사용하는 것이 좋습니다.

코드 예제:

```csharp
// dotnet_style_predefined_type_for_locals_parameters_members = true
private int _member;

// dotnet_style_predefined_type_for_locals_parameters_members = false
private Int32 _member;
```

```vb
' dotnet_style_predefined_type_for_locals_parameters_members = true
Private _member As Integer

' dotnet_style_predefined_type_for_locals_parameters_members = false
Private _member As Int32
```

**dotnet\_style\_predefined\_type\_for\_member_access**

- 이 규칙을 **true**로 설정하면 자신을 나타내는 키워드를 포함한 형식에 형식 이름 대신 멤버 액세스 식에 대한 언어 키워드를 사용하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 언어 키워드 대신 멤버 액세스 식에 대한 형식 이름을 사용하는 것이 좋습니다.

코드 예제:

```csharp
// dotnet_style_predefined_type_for_member_access = true
var local = int.MaxValue;

// dotnet_style_predefined_type_for_member_access = false
var local = Int32.MaxValue;
```

```vb
' dotnet_style_predefined_type_for_member_access = true
Dim local = Integer.MaxValue

' dotnet_style_predefined_type_for_member_access = false
Dim local = Int32.MaxValue
```

이러한 규칙은 *.editorconfig* 파일에서 다음과 같이 표시될 수 있습니다.

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_predefined_type_for_locals_parameters_members = true:suggestion
dotnet_style_predefined_type_for_member_access = true:suggestion
```

#### <a name="normalize_modifiers"></a>한정자 기본 설정

이 섹션의 스타일 규칙은 액세스 가능성 한정자 요구 및 원하는 한정자 정렬 순서 지정을 비롯한 한정자 기본 설정과 관련이 있습니다.

다음 표에서는 규칙 이름, 규칙 ID, 적용 가능한 프로그래밍 언어, 기본값 및 먼저 지원되는 Visual Studio의 버전을 보여줍니다.

| 규칙 이름 | 규칙 ID | 해당 언어 | Visual Studio 기본값 | Visual Studio 2017 버전 |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| dotnet_style_require_accessibility_modifiers | IDE0040 | C# 및 Visual Basic | for_non_interface_members:none | 15.5 |
| csharp_preferred_modifier_order | IDE0036 | C# | 공용, 개인, 보호됨, 내부, 고정, 외부, 새로운, 가상, 추상, 봉인됨, 재정의, 읽기 전용, 안전하지 않음, 변동, 비동기: 없음 | 15.5 |
| visual_basic_preferred_modifier_order | IDE0036 | Visual Basic | 부분, 기본, 개인, 보호됨, 공용, 친구, NotOverridable, 재정의 가능, MustOverride, 오버로드, 재정의, MustInherit, NotInheritable, 고정, 공유, 그림자, 읽기 전용, 쓰기 전용, 차원, Const, WithEvents, 확대, 축소, 사용자 지정, 비동기: 없음 | 15.5 |

**dotnet\_style\_require\_accessibility_modifiers**

이 규칙은 **true** 또는 **false** 값을 허용하지 않습니다. 대신 다음 테이블의 값을 허용합니다.

| 값 | 설명 |
| ----- |:----------- |
| always | 액세스 가능성 한정자를 지정하는 것이 좋습니다. |
| for\_non\_interface_members | 공용 인터페이스 멤버를 제외하고 액세스 가능성 한정자를 선언하는 것을 선호합니다. 이것은 현재 **always**와 다르지 않으며 C#에서 기본 인터페이스 메서드를 추가할 경우 향후 교정으로 작동합니다. |
| never | 액세스 가능성 한정자를 지정하지 않는 것이 좋습니다. |

코드 예제:

```csharp
// dotnet_style_require_accessibility_modifiers = always
// dotnet_style_require_accessibility_modifiers = for_non_interface_members
class MyClass
{
    private const string thisFieldIsConst= "constant";
}

// dotnet_style_require_accessibility_modifiers = never
class MyClass
{
    const string thisFieldIsConst= "constant";
}
```

**csharp_preferred_modifier_order**

- 이 규칙이 한정자 목록으로 설정되면 지정된 순서를 선호합니다.
- 이 규칙이 파일에서 생략되면 한정자 순서를 선호하지 않습니다.

코드 예제:

```csharp
// csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async
class MyClass
{
    private static readonly int _daysInYear = 365;
}
```

**visual_basic_preferred_modifier_order**

- 이 규칙이 한정자 목록으로 설정되면 지정된 순서를 선호합니다.
- 이 규칙이 파일에서 생략되면 한정자 순서를 선호하지 않습니다.

코드 예제:

```vb
' visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async
Public Class MyClass
    Private Shared ReadOnly daysInYear As Int = 365
End Class
```

이러한 규칙은 *.editorconfig* 파일에서 다음과 같이 표시될 수 있습니다.

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_require_accessibility_modifiers = always:suggestion

# CSharp code style settings:
[*.cs]
csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async:suggestion

# Visual Basic code style settings:
[*.vb]
visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async:suggestion
```

#### <a name="expression_level"></a>식 수준 기본 설정

이 섹션의 스타일 규칙은 개체 이니셜라이저, 컬렉션 이니셜라이저, 명시적 또는 유추된 튜플 이름 및 유추된 익명의 형식을 사용하는 식 수준 기본 설정에 대해 다룹니다.

다음 표에서는 규칙 이름, 규칙 ID, 적용 가능한 프로그래밍 언어, 기본값 및 먼저 지원되는 Visual Studio의 버전을 보여줍니다.

| 규칙 이름 | 규칙 ID | 해당 언어 | Visual Studio 기본값 | Visual Studio 2017 버전 |
| --------- | ------- | -------------------- | ----------------------| ---- |
| dotnet_style_object_initializer | IDE0017 | C# 및 Visual Basic | true:suggestion | 첫 번째 릴리스 |
| dotnet_style_collection_initializer | IDE0028 | C# 및 Visual Basic | true:suggestion | 첫 번째 릴리스 |
| dotnet_style_explicit_tuple_names | IDE0033 | C# 7.0+ 및 Visual Basic 15+ | true:suggestion | 첫 번째 릴리스 |
| dotnet_style_prefer_inferred_tuple_names | IDE0037 | C# 7.1+ 및 Visual Basic 15+ | true:suggestion | 15.6 |
| dotnet_style_prefer_inferred_anonymous_type_member_names | IDE0037 | C# 및 Visual Basic | true:suggestion | 15.6 |

**dotnet\_style\_object_initializer**

- 이 규칙을 **true**로 설정한 경우 가능하면 개체 이니셜라이저를 사용하여 개체를 초기화하는 것이 좋습니다.
- 이 규칙을 **false**로 설정한 경우 가능하면 개체 이니셜라이저를 사용하여 개체를 초기화하지 *않는* 것이 좋습니다.

코드 예제:

```csharp
// dotnet_style_object_initializer = true
var c = new Customer() { Age = 21 };

// dotnet_style_object_initializer = false
var c = new Customer();
c.Age = 21;
```

```vb
' dotnet_style_object_initializer = true
Dim c = New Customer() With {.Age = 21}

' dotnet_style_object_initializer = false
Dim c = New Customer()
c.Age = 21
```

**dotnet\_style\_collection_initializer**

- 이 규칙을 **true**로 설정한 경우 가능하면 컬렉션 이니셜라이저를 사용하여 컬렉션을 초기화하는 것이 좋습니다.
- 이 규칙을 **false**로 설정한 경우 컬렉션 이니셜라이저를 사용하여 컬렉션을 초기화하지 *않는* 것이 좋습니다.

코드 예제:

```csharp
// dotnet_style_collection_initializer = true
var list = new List<int> { 1, 2, 3 };

// dotnet_style_collection_initializer = false
var list = new List<int>();
list.Add(1);
list.Add(2);
list.Add(3);
```

```vb
' dotnet_style_collection_initializer = true
Dim list = New List(Of Integer) From {1, 2, 3}

' dotnet_style_collection_initializer = false
Dim list = New List(Of Integer)
list.Add(1)
list.Add(2)
list.Add(3)
```

**dotnet\_style\_explicit\_tuple_names**

- 이 규칙을 **true**로 설정하면 ItemX 속성보다 튜플 이름을 사용하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 튜플 이름보다 ItemX 속성을 사용하는 것이 좋습니다.

코드 예제:

```csharp
// dotnet_style_explicit_tuple_names = true
(string name, int age) customer = GetCustomer();
var name = customer.name;

// dotnet_style_explicit_tuple_names = false
(string name, int age) customer = GetCustomer();
var name = customer.Item1;
```

```vb
 ' dotnet_style_explicit_tuple_names = true
Dim customer As (name As String, age As Integer) = GetCustomer()
Dim name = customer.name

' dotnet_style_explicit_tuple_names = false
Dim customer As (name As String, age As Integer) = GetCustomer()
Dim name = customer.Item1
```

**dotnet\_style\_prefer\_inferred\_tuple_names**

- 이 규칙이 **true**로 설정된 경우 추론된 튜플 요소 이름을 사용하는 것이 좋습니다.
- 이 규칙이 **false**로 설정된 경우 명시적 튜플 요소 이름을 사용하는 것이 좋습니다.

코드 예제:

```csharp
// dotnet_style_prefer_inferred_tuple_names = true
var tuple = (age, name);

// dotnet_style_prefer_inferred_tuple_names = false
var tuple = (age: age, name: name);
```

**dotnet\_style\_prefer\_inferred\_anonymous\_type\_member_names**

- 이 규칙이 **true**로 설정된 경우 추론된 무명 형식 멤버 이름을 사용하는 것이 좋습니다.
- 이 규칙이 **false**로 설정된 경우 명시적 무명 형식 멤버 이름을 사용하는 것이 좋습니다.

코드 예제:

```csharp
// dotnet_style_prefer_inferred_anonymous_type_member_names = true
var anon = new { age, name };

// dotnet_style_prefer_inferred_anonymous_type_member_names = false
var anon = new { age = age, name = name };

```

이러한 규칙은 *.editorconfig* 파일에서 다음과 같이 표시될 수 있습니다.

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_object_initializer = true:suggestion
dotnet_style_collection_initializer = true:suggestion
dotnet_style_explicit_tuple_names = true:suggestion
dotnet_style_prefer_inferred_tuple_names = true:suggestion
dotnet_style_prefer_inferred_anonymous_type_member_names = true:suggestion
```

#### <a name="null_checking"></a>Null 검사 기본 설정

이 섹션에서 스타일 규칙은 Null 검사 기본 설정과 관련이 있습니다.

다음 표에서는 규칙 이름, 규칙 ID, 적용 가능한 프로그래밍 언어, 기본값 및 먼저 지원되는 Visual Studio의 버전을 보여줍니다.

| 규칙 이름 | 규칙 ID | 해당 언어 | Visual Studio 기본값 | Visual Studio 2017 버전 |
| --------- | ------- | -------------------- | ----------------------| ---- |
| dotnet_style_coalesce_expression | IDE0029 | C# 및 Visual Basic | true:suggestion | 첫 번째 릴리스 |
| dotnet_style_null_propagation | IDE0031 | C# 6.0 이상 및 Visual Basic 14 이상 | true:suggestion | 첫 번째 릴리스 |

**dotnet\_style\_coalesce_expression**

- 이 규칙을 **true**로 설정하면 3개로 구성된 연산자 검사보다 null 결합 식을 사용하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 null 병합 식보다 3개로 구성된 연산자 검사를 사용하는 것이 좋습니다.

코드 예제:

```csharp
// dotnet_style_coalesce_expression = true
var v = x ?? y;

// dotnet_style_coalesce_expression = false
var v = x != null ? x : y; // or
var v = x == null ? y : x;
```

```vb
' dotnet_style_coalesce_expression = true
Dim v = If(x, y)

' dotnet_style_coalesce_expression = false
Dim v = If(x Is Nothing, y, x) ' or
Dim v = If(x IsNot Nothing, x, y)
```

**dotnet\_style\_null_propagation**

- 이 규칙을 **true**로 설정하면 가능한 경우 null 조건부 연산자를 사용하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 가능한 경우 3개로 구성된 null 검사를 사용하는 것이 좋습니다.

코드 예제:

```csharp
// dotnet_style_null_propagation = true
var v = o?.ToString();

// dotnet_style_null_propagation = false
var v = o == null ? null : o.ToString(); // or
var v = o != null ? o.String() : null;
```

```vb
' dotnet_style_null_propagation = true
Dim v = o?.ToString()

' dotnet_style_null_propagation = false
Dim v = If(o Is Nothing, Nothing, o.ToString()) ' or
Dim v = If(o IsNot Nothing, o.ToString(), Nothing)
```

이러한 규칙은 *.editorconfig* 파일에서 다음과 같이 표시될 수 있습니다.

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_coalesce_expression = true:suggestion
dotnet_style_null_propagation = true:suggestion
```

### <a name="c-code-style-settings"></a>C# 코드 스타일 설정

이 섹션의 스타일 규칙은 C#에만 적용됩니다.

#### <a name="var"></a>암시적 및 명시적 형식

이 섹션의 스타일 규칙(규칙 ID IDE0007 및 IDE0008)은 [var](/dotnet/csharp/language-reference/keywords/var) 키워드 및 변수 선언에서 명시적 형식을 사용하는 방법을 다룹니다. 이 규칙은 형식이 명확할 때 기본 제공 형식 및 다른 위치에 개별적으로 적용할 수 있습니다.

다음 표에서는 규칙 이름, 적용 가능한 프로그래밍 언어 및 기본값을 보여줍니다.

| 규칙 이름 | 해당 언어 | Visual Studio 기본값 |
| ----------- | -------------------- | ----------------------|
| csharp_style_var_for_built_in_types | C# | true:none |
| csharp_style_var_when_type_is_apparent | C# | true:none |
| csharp_style_var_elsewhere | C# | true:none |

**csharp\_style\_var\_for\_built\_in_types**

- 이 규칙을 **true**로 설정하면 `int`와 같은 기본 제공 시스템 형식으로 변수를 선언하는 데 `var`을 사용하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 `int`와 같은 기본 제공 시스템 형식으로 변수를 선언하는 데 `var`보다 명시적 형식을 사용하는 것이 좋습니다.

코드 예제:

```csharp
// csharp_style_var_for_built_in_types = true
var x = 5;

// csharp_style_var_for_built_in_types = false
int x = 5;
```

**csharp\_style\_var\_when\_type\_is_apparent**

- 이 규칙을 **true**로 설정하면 선언 식의 오른쪽에서 형식이 이미 언급된 경우 `var`을 사용하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 선언 식의 오른쪽에서 형식이 이미 언급된 경우 `var`보다 명시적 형식을 사용하는 것이 좋습니다.

코드 예제:

```csharp
// csharp_style_var_when_type_is_apparent = true
var obj = new Customer();

// csharp_style_var_when_type_is_apparent = false
Customer obj = new Customer();
```

**csharp\_style\_var_elsewhere**

- 이 규칙을 **true**로 설정하면 다른 코드 스타일 규칙에 의해 재정의되지 않는 모든 경우에 명시적 형식보다 `var`을 사용하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 다른 코드 스타일 규칙에 의해 재정의되지 않는 모든 경우에 `var`보다 명시적 형식을 사용하는 것이 좋습니다.

코드 예제:

```csharp
// csharp_style_var_elsewhere = true
var f = this.Init();

// csharp_style_var_elsewhere = false
bool f = this.Init();
```

예제 *.editorconfig* 파일:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_var_for_built_in_types = true:suggestion
csharp_style_var_when_type_is_apparent = true:suggestion
csharp_style_var_elsewhere = true:suggestion
```

#### <a name="expression_bodied_members"></a>식 본문 멤버

이 섹션의 스타일 규칙은 논리가 단일 식으로 구성되는 경우 [식 본문 멤버](/dotnet/csharp/programming-guide/statements-expressions-operators/expression-bodied-members)를 사용하는 방법을 다룹니다. 이 규칙은 메서드, 생성자, 연산자, 속성, 인덱서 및 접근자에 적용할 수 있습니다.

다음 표에서는 규칙 이름, 규칙 ID, 적용 가능한 언어 버전, 기본값 및 먼저 지원되는 Visual Studio의 버전을 보여줍니다.

| 규칙 이름 | 규칙 ID | 해당 언어 | Visual Studio 기본값 | Visual Studio 2017 버전 |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| csharp_style_expression_bodied_methods | IDE0022 | C# 6.0+ | false:none | 15.3 |
| csharp_style_expression_bodied_constructors | IDE0021 | C# 7.0+ | false:none | 15.3 |
| csharp_style_expression_bodied_operators | IDE0023 및 IDE0024 | C# 7.0+ | false:none | 15.3 |
| csharp_style_expression_bodied_properties | IDE0025 | C# 7.0+ | true:none | 15.3 |
| csharp_style_expression_bodied_indexers | IDE0026 | C# 7.0+ | true:none | 15.3 |
| csharp_style_expression_bodied_accessors | IDE0027 | C# 7.0+ | true:none | 15.3 |

**csharp\_style\_expression\_bodied_methods**

이 규칙은 다음 표의 값을 허용합니다.

| 값 | 설명 |
| ----- |:----------- |
| true | 메서드에 식 본문 멤버를 사용하는 것이 좋습니다. |
| when_on_single_line | 한 줄이 될 때 메서드에 식 본문 멤버를 사용하는 것이 좋습니다. |
| False | 메서드에 대한 블록 본문을 선호합니다. |

코드 예제:

```csharp
// csharp_style_expression_bodied_methods = true
public int GetAge() => this.Age;

// csharp_style_expression_bodied_methods = false
public int GetAge() { return this.Age; }
```

**csharp\_style\_expression\_bodied_constructors**

이 규칙은 다음 표의 값을 허용합니다.

| 값 | 설명 |
| ----- |:----------- |
| true | 생성자에 식 본문 멤버를 사용하는 것이 좋습니다. |
| when_on_single_line | 한 줄이 될 때 생성자에 식 본문 멤버를 사용하는 것이 좋습니다. |
| False | 생성자에 대한 본문을 선호합니다. |

코드 예제:

```csharp
// csharp_style_expression_bodied_constructors = true
public Customer(int age) => Age = age;

// csharp_style_expression_bodied_constructors = false
public Customer(int age) { Age = age; }
```

**csharp\_style\_expression\_bodied_operators**

이 규칙은 다음 표의 값을 허용합니다.

| 값 | 설명 |
| ----- |:----------- |
| true | 연산자에 식 본문 멤버를 사용하는 것이 좋습니다. |
| when_on_single_line | 한 줄이 될 때 연산자에 식 본문 멤버를 사용하는 것이 좋습니다. |
| False | 연산자에 대한 블록 본문을 선호합니다. |

코드 예제:

```csharp
// csharp_style_expression_bodied_operators = true
public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
    => new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary);

// csharp_style_expression_bodied_operators = false
public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
{ return new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary); }
```

**csharp\_style\_expression\_bodied_properties**

이 규칙은 다음 표의 값을 허용합니다.

| 값 | 설명 |
| ----- |:----------- |
| true | 속성에 식 본문 멤버를 사용하는 것이 좋습니다. |
| when_on_single_line | 한 줄이 될 때 속성에 식 본문 멤버를 사용하는 것이 좋습니다. |
| False | 속성에 대한 블록 본문을 선호합니다. |

코드 예제:

```csharp
// csharp_style_expression_bodied_properties = true
public int Age => _age;

// csharp_style_expression_bodied_properties = false
public int Age { get { return _age; }}
```

**csharp\_style\_expression\_bodied_indexers**

이 규칙은 다음 표의 값을 허용합니다.

| 값 | 설명 |
| ----- |:----------- |
| true | 인덱서에 식 본문 멤버를 사용하는 것이 좋습니다. |
| when_on_single_line | 한 줄이 될 때 인덱서에 식 본문 멤버를 사용하는 것이 좋습니다. |
| False | 인덱서에 대한 블록 본문을 선호합니다. |

코드 예제:

```csharp
// csharp_style_expression_bodied_indexers = true
public T this[int i] => _value[i];

// csharp_style_expression_bodied_indexers = false
public T this[int i] { get { return _values[i]; } }
```

**csharp\_style\_expression\_bodied_accessors**

이 규칙은 다음 표의 값을 허용합니다.

| 값 | 설명 |
| ----- |:----------- |
| true | 접근자에 식 본문 멤버를 사용하는 것이 좋습니다. |
| when_on_single_line | 한 줄이 될 때 접근자에 식 본문 멤버를 사용하는 것이 좋습니다. |
| False | 접근자에 대한 블록 본문을 선호합니다. |

코드 예제:

```csharp
// csharp_style_expression_bodied_accessors = true
public int Age { get => _age; set => _age = value; }

// csharp_style_expression_bodied_accessors = false
public int Age { get { return _age; } set { _age = value; } }
```

예제 *.editorconfig* 파일:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_methods = false:none
csharp_style_expression_bodied_constructors = false:none
csharp_style_expression_bodied_operators = false:none
csharp_style_expression_bodied_properties = true:suggestion
csharp_style_expression_bodied_indexers = true:suggestion
csharp_style_expression_bodied_accessors = true:suggestion
```

#### <a name="pattern_matching"></a>패턴 일치

이 섹션의 스타일 규칙은 C#에서 [패턴 일치](/dotnet/csharp/pattern-matching)를 사용하는 방법을 다룹니다.

다음 표에서는 규칙 이름, 규칙 ID, 적용 가능한 언어 버전 및 기본값을 보여줍니다.

| 규칙 이름 | 규칙 ID | 해당 언어 | Visual Studio 기본값 |
| --------- | ------- | -------------------- | ----------------------|
| csharp_style_pattern_matching_over_is_with_cast_check | IDE0020 | C# 7.0+ | true:suggestion |
| csharp_style_pattern_matching_over_as_with_null_check | IDE0019 | C# 7.0+ | true:suggestion |

**csharp\_style\_pattern\_matching\_over\_is\_with\_cast_check**

- 이 규칙을 **true**로 설정하면 캐스트를 포함하는 `is` 식보다 패턴 일치를 사용하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 패턴 일치보다 형식 캐스트를 포함하는 `is` 식을 사용하는 것이 좋습니다.

코드 예제:

```csharp
// csharp_style_pattern_matching_over_is_with_cast_check = true
if (o is int i) {...}

// csharp_style_pattern_matching_over_is_with_cast_check = false
if (o is int) {var i = (int)o; ... }
```

**csharp\_style\_pattern\_matching\_over\_as\_with\_null_check**

- 이 규칙을 **true**로 설정하면 null 검사를 포함하는 `as` 식 대신 패턴 일치를 사용하여 항목이 특정 형식인지 확인하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 패턴 일치 대신 null 검사를 포함하는 `as` 식을 사용하여 항목이 특정 형식인지 확인하는 것이 좋습니다.

코드 예제:

```csharp
// csharp_style_pattern_matching_over_as_with_null_check = true
if (o is string s) {...}

// csharp_style_pattern_matching_over_as_with_null_check = false
var s = o as string;
if (s != null) {...}
```

예제 *.editorconfig* 파일:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_pattern_matching_over_is_with_cast_check = true:suggestion
csharp_style_pattern_matching_over_as_with_null_check = true:suggestion
```

#### <a name="inlined_variable_declarations"></a>인라인 변수 선언

이 스타일 규칙은 `out` 변수가 인라인을 선언했는지 여부에 대해 다룹니다. C# 7부터 별도 변수 선언이 아니라 [메서드 호출의 인수 목록에서 out 변수를 선언](/dotnet/csharp/language-reference/keywords/out-parameter-modifier#calling-a-method-with-an-out-argument)할 수 있습니다.

다음 표에서는 규칙 이름, 규칙 ID, 적용 가능한 언어 버전 및 기본값을 보여줍니다.

| 규칙 이름 | 규칙 ID | 해당 언어 | Visual Studio 기본값 |
| --------- | -------- | -------------------- | ----------------------|
| csharp_style_inlined_variable_declaration | IDE0018 | C# 7.0+ | true:suggestion |

**csharp\_style\_inlined\_variable_declaration**

- 이 규칙을 **true**로 설정하면 가능한 경우 `out` 변수를 메서드 호출의 인수 목록에서 인라인으로 선언하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 `out` 변수를 메서드 호출 전에 선언하는 것이 좋습니다.

코드 예제:

```csharp
// csharp_style_inlined_variable_declaration = true
if (int.TryParse(value, out int i) {...}

// csharp_style_inlined_variable_declaration = false
int i;
if (int.TryParse(value, out i) {...}
```

예제 *.editorconfig* 파일:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_inlined_variable_declaration = true:suggestion
```

#### <a name="expression_level_csharp"></a>식 수준 기본 설정

이 섹션의 스타일 규칙은 [기본 식](/dotnet/csharp/programming-guide/statements-expressions-operators/default-value-expressions#default-literal-and-type-inference), 분해된 변수 및 익명 함수에 대한 로컬 함수의 사용을 비롯한 식 수준 기본 설정과 관련이 있습니다.

다음 표에서는 규칙 이름, 규칙 ID, 적용 가능한 언어 버전, 기본값 및 먼저 지원되는 Visual Studio의 버전을 보여줍니다.

| 규칙 이름 | 규칙 ID | 해당 언어 | Visual Studio 기본값 | Visual Studio 2017 버전 |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| csharp_prefer_simple_default_expression | IDE0034 | C# 7.1+ | true:suggestion | 15.3 |
| csharp_style_deconstructed_variable_declaration | IDE0042 | C# 7.0+ | true:suggestion | 15.5 |
| csharp_style_pattern_local_over_anonymous_function | IDE0039 | C# 7.0+ | true:suggestion | 15.5 |

**csharp\_prefer\_simple\_default_expression**

이 스타일 규칙을 사용 하 여 관련는 [ `default` 기본값 식에 대 한 리터럴](/dotnet/csharp/programming-guide/statements-expressions-operators/default-value-expressions#default-literal-and-type-inference) 때 컴파일러는 식의 형식을 유추할 수 있습니다.

- 이 규칙을 **true**로 설정하면 `default(T)`보다 `default`를 사용하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 `default`보다 `default(T)`를 사용하는 것이 좋습니다.

코드 예제:

```csharp
// csharp_prefer_simple_default_expression = true
void DoWork(CancellationToken cancellationToken = default) { ... }

// csharp_prefer_simple_default_expression = false
void DoWork(CancellationToken cancellationToken = default(CancellationToken)) { ... }
```

**csharp\_style\_deconstructed\_variable_declaration**

- 이 규칙이 **true**로 설정되면 분해된 변수 선언을 선호합니다.
- 이 규칙이 **false**로 설정되면 변수 선언에서 분해를 선호하지 않습니다.

코드 예제:

```csharp
// csharp_style_deconstructed_variable_declaration = true
var (name, age) = GetPersonTuple();
Console.WriteLine($"{name} {age}");

(int x, int y) = GetPointTuple();
Console.WriteLine($"{x} {y}");

// csharp_style_deconstructed_variable_declaration = false
var person = GetPersonTuple();
Console.WriteLine($"{person.name} {person.age}");

(int x, int y) point = GetPointTuple();
Console.WriteLine($"{point.x} {point.y}");
```

**csharp\_style\_pattern\_local\_over\_anonymous_function**

- 이 규칙이 **true**로 설정되면 익명 함수보다 로컬 함수를 선호합니다.
- 이 규칙이 **false**로 설정되면 로컬 함수보다 익명 함수를 선호합니다.

코드 예제:

```csharp
// csharp_style_pattern_local_over_anonymous_function = true
int fibonacci(int n)
{
    return n <= 1 ? 1 : fibonacci(n-1) + fibonacci(n-2);
}

// csharp_style_pattern_local_over_anonymous_function = false
Func<int, int> fibonacci = null;
fibonacci = (int n) =>
{
    return n <= 1 ? 1 : fibonacci(n - 1) + fibonacci(n - 2);
};
```

예제 *.editorconfig* 파일:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_prefer_simple_default_expression = true:suggestion
csharp_style_deconstructed_variable_declaration = true:suggestion
csharp_style_pattern_local_over_anonymous_function = true:suggestion
```

#### <a name="null_checking_csharp"></a>"Null" 검사 기본 설정

이러한 스타일 규칙은 `throw` 식 또는 `throw` 문 사용을 비롯한 `null` 검사 관련 구문 및 [람다 식](/dotnet/csharp/lambda-expressions)을 호출할 때를 null 검사를 수행하거나 조건부 병합 연산자(`?.`)를 사용할지에 대해 다룹니다.

다음 표에서는 규칙 이름, 규칙 ID, 적용 가능한 언어 버전 및 기본값을 보여줍니다.

| 규칙 이름 | 규칙 ID | 해당 언어 | Visual Studio 기본값 |
| --------- | ------- | -------------------- | ----------------------|
| csharp_style_throw_expression | IDE0016 | C# 7.0+ | true:suggestion |
| csharp_style_conditional_delegate_call | IDE0041 | C# 6.0+ | true:suggestion |

**csharp\_style\_throw_expression**

- 이 규칙을 **true**로 설정하면 `throw` 문 대신 `throw` 식을 사용하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 `throw` 식 대신 `throw` 문을 사용하는 것이 좋습니다.

코드 예제:

```csharp
// csharp_style_throw_expression = true
this.s = s ?? throw new ArgumentNullException(nameof(s));

// csharp_style_throw_expression = false
if (s == null) { throw new ArgumentNullException(nameof(s)); }
this.s = s;
```

**csharp\_style\_conditional\_delegate_call**

- 이 규칙을 **true**로 설정하면 람다 식을 호출할 때 null 검사를 수행하는 대신 조건부 병합 연산자(`?.`)를 사용하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 람다 식을 호출할 때 조건부 병합 연산자(`?.`)를 사용하는 대신 null 검사를 수행하는 것이 좋습니다.

코드 예제:

```csharp
// csharp_style_conditional_delegate_call = true
func?.Invoke(args);

// csharp_style_conditional_delegate_call = false
if (func != null) { func(args); }
```

예제 *.editorconfig* 파일:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_throw_expression = true:suggestion
csharp_style_conditional_delegate_call = false:suggestion
```

#### <a name="code_block"></a>코드 블록 기본 설정

이 스타일 규칙은 코드 블록을 묶는 데 중괄호 `{ }`를 사용하는 방법을 다룹니다.

다음 표에서는 규칙 이름, 규칙 ID, 적용 가능한 언어 버전, 기본값 및 먼저 지원되는 Visual Studio의 버전을 보여줍니다.

| 규칙 이름 | 규칙 ID | 해당 언어 | Visual Studio 기본값 | Visual Studio 2017 버전 |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| csharp_prefer_braces | IDE0011 | C# | true:none | 15.3 |

**csharp\_prefer\_braces**

- 이 규칙을 **true**로 설정하면 하나의 코드 줄에 대해서도 중괄호를 사용하는 것이 좋습니다.
- 이 규칙을 **false**로 설정하면 허용되는 경우 중괄호 를 사용하지 않는 것이 좋습니다.

코드 예제:

```csharp
// csharp_prefer_braces = true
if (test) { this.Display(); }

// csharp_prefer_braces = false
if (test) this.Display();
```

예제 *.editorconfig* 파일:

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_prefer_braces = true:none
```

## <a name="formatting-conventions"></a>서식 지정 규칙

서식 지정 규칙 대부분은 다음과 같은 형식입니다.

`rule_name = false|true`

**true**(이 스타일 선호) 또는 **false**(이 스타일 선호하지 않음)를 지정합니다. 심각도를 지정하지 않습니다. 몇 가지 규칙의 경우 true 또는 false 대신 규칙을 적용할 시기와 위치를 설명하는 다른 값을 지정합니다.

다음 목록은 Visual Studio에서 사용할 수 있는 서식 지정 규칙을 보여줍니다.

- .NET 서식 지정 설정
    - [using 구성](#usings)
        - dotnet_sort_system_directives_first
- C# 서식 지정 설정
    - [줄 바꿈 옵션](#newline)
        - csharp_new_line_before_open_brace
        - csharp_new_line_before_else
        - csharp_new_line_before_catch
        - csharp_new_line_before_finally
        - csharp_new_line_before_members_in_object_initializers
        - csharp_new_line_before_members_in_anonymous_types
        - csharp_new_line_between_query_expression_clauses
    - [들여쓰기 옵션](#indent)
        - csharp_indent_case_contents
        - csharp_indent_switch_labels
        - csharp_indent_labels
    - [간격 옵션](#spacing)
        - csharp_space_after_cast
        - csharp_space_after_keywords_in_control_flow_statements
        - csharp_space_between_method_declaration_parameter_list_parentheses
        - csharp_space_between_method_call_parameter_list_parentheses
        - csharp_space_between_parentheses
    - [래핑 옵션](#wrapping)
        - csharp_preserve_single_line_statements
        - csharp_preserve_single_line_blocks

### <a name="net-formatting-settings"></a>.NET 서식 지정 설정

이 섹션의 서식 설정 규칙은 C# 및 Visual Basic에 적용됩니다.

#### <a name="usings"></a>using 구성

이 서식 설정 규칙은 다른 using 지시문과 관련하여 System.* using 지시문의 배치를 다룹니다.

다음 표에서는 규칙 이름, 적용 가능한 언어, 기본값 및 먼저 지원되는 Visual Studio의 버전을 보여줍니다.

| 규칙 이름 | 해당 언어 | Visual Studio 기본값 | Visual Studio 2017 버전 |
| ----------- | -------------------- | ----------------------| ----------------  |
| dotnet_sort_system_directives_first |  C# 및 Visual Basic | true | 15.3  |

**dotnet\_sort\_system\_directives_first**

- 이 규칙이 **true**로 설정되면 System.* using 지시문을 사전순으로 정렬하고 다른 using 앞에 배치합니다.
- 이 규칙이 **false**로 설정되면 다른 using 지시문 앞에 System.* using 지시문을 배치하지 않습니다.

코드 예제:

```csharp
// dotnet_sort_system_directives_first = true
using System.Collections.Generic;
using System.Threading.Tasks;
using Octokit;

// dotnet_sort_system_directives_first = false
using System.Collections.Generic;
using Octokit;
using System.Threading.Tasks;
```

예제 *.editorconfig* 파일:

```EditorConfig
# .NET formatting settings:
[*.{cs,vb}]
dotnet_sort_system_directives_first = true
```

### <a name="c-formatting-settings"></a>C# 서식 지정 설정

이 섹션의 서식 설정 규칙은 C# 코드에만 적용됩니다.

#### <a name="newline"></a>줄 바꿈 옵션

이러한 서식 지정 규칙은 코드의 서식을 지정하기 위해 새 줄을 사용합니다.

다음 표에서는 "새 줄" 규칙 이름, 적용 가능한 언어, 기본값 및 먼저 지원되는 Visual Studio의 버전을 보여줍니다.

| 규칙 이름 | 해당 언어 | Visual Studio 기본값 | Visual Studio 2017 버전 |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_new_line_before_open_brace |  C# | 모두 | 15.3  |
| csharp_new_line_before_else |  C# | true | 15.3  |
| csharp_new_line_before_catch |  C# | true | 15.3  |
| csharp_new_line_before_finally |  C# | true | 15.3  |
| csharp_new_line_before_members_in_object_initializers |  C# | true | 15.3  |
| csharp_new_line_before_members_in_anonymous_types |  C# | true | 15.3  |
| csharp_new_line_between_query_expression_clauses |  C# | true | 15.3  |

**csharp\_new\_line\_before\_open_brace**

이 규칙은 중괄호 `{`가 앞의 코드와 동일한 줄 또는 새 줄에 배치되어야 하는지를 다룹니다. 이 규칙의 경우 **true** 또는 **false**를 지정하지 않습니다. 대신 **모두**, **없음** 또는 하나 이상의 코드 요소(예: **메서드** 또는 **속성**)를 지정하여 이 규칙을 적용할 시점을 정의합니다. 허용 가능한 값의 전체 목록은 다음 표에 나와 있습니다.

| 값 | 설명
| ------------- |:-------------|
| accessors, anonymous_methods, anonymous_types, control_blocks, events, indexers, lambdas, local_functions, methods, object_collection, properties, types.<br>(여러 경우에 ','로 구분합니다.) | 지정된 코드 요소("Allman" 스타일이라고도 함)의 경우 새 줄에 중괄호가 필요합니다. |
| 모두 | 모든 식("Allman" 스타일)의 경우 새 줄에 중괄호가 필요합니다. |
| 없음 | 모든 식("K&R")의 경우 동일한 줄에 중괄호가 필요합니다. |

코드 예제:

```csharp
// csharp_new_line_before_open_brace = all
void MyMethod()
{
    if (...)
    {
        ...
    }
}

// csharp_new_line_before_open_brace = none
void MyMethod() {
    if (...) {
        ...
    }
}
```

**csharp\_new\_line\_before_else**

- 이 규칙을 **true**로 설정하면 새 줄에 `else` 문을 배치합니다.
- 이 규칙을 **false**로 설정하면 동일한 줄에 `else` 문을 배치합니다.

코드 예제:

```csharp
// csharp_new_line_before_else = true
if (...) {
    ...
}
else {
    ...
}

// csharp_new_line_before_else = false
if (...) {
    ...
} else {
    ...
}
```

**csharp\_new\_line\_before_catch**

- 이 규칙을 **true**로 설정하면 새 줄에 `catch` 문을 배치합니다.
- 이 규칙을 **false**로 설정하면 동일한 줄에 `catch` 문을 배치합니다.

코드 예제:

```csharp
// csharp_new_line_before_catch = true
try {
    ...
}
catch (Exception e) {
    ...
}

// csharp_new_line_before_catch = false
try {
    ...
} catch (Exception e) {
    ...
}
```

**csharp\_new\_line\_before_finally**

- 이 규칙을 **true**로 설정하면 `finally` 문을 닫는 괄호 뒤의 새 줄에 배치해야 합니다.
- 이 규칙을 **false**로 설정하면 `finally` 문을 닫는 괄호와 동일한 줄에 배치해야 합니다.

코드 예제:

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

// csharp_new_line_before_finally = false
try {
    ...
} catch (Exception e) {
    ...
} finally {
    ...
}
```

**csharp\_new\_line\_before\_members\_in\_object_initializers**

- 이 규칙을 **true**로 설정하면 개체 이니셜라이저의 멤버를 별도 줄에 배치해야 합니다.
- 이 규칙을 **false**로 설정하면 개체 이니셜라이저의 멤버를 동일한 줄에 배치해야 합니다.

코드 예제:

```csharp
// csharp_new_line_before_members_in_object_initializers = true
var z = new B()
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_object_initializers = false
var z = new B()
{
    A = 3, B = 4
}
```

**csharp\_new\_line\_before\_members\_in\_anonymous_types**

- 이 규칙을 **true**로 설정하면 익명 형식의 멤버를 별도 줄에 배치해야 합니다.
- 이 규칙을 **false**로 설정하면 익명 형식의 멤버를 동일한 줄에 배치해야 합니다.

코드 예제:

```csharp
// csharp_new_line_before_members_in_anonymous_types = true
var z = new
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_anonymous_types = false
var z = new
{
    A = 3, B = 4
}
```

**csharp_new_line_between_query_expression_clauses**

- 이 규칙을 **true**로 설정하면 쿼리 식 절의 요소를 별도 줄에 배치해야 합니다.
- 이 규칙을 **false**로 설정하면 쿼리 식 절의 요소를 동일한 줄에 배치해야 합니다.

코드 예제:

```csharp
// csharp_new_line_between_query_expression_clauses = true
var q = from a in e
        from b in e
        select a * b;

// csharp_new_line_between_query_expression_clauses = false
var q = from a in e from b in e
        select a * b;
```

예제 *.editorconfig* 파일:

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_new_line_before_open_brace = methods, properties, control_blocks, types
csharp_new_line_before_else = true
csharp_new_line_before_catch = true
csharp_new_line_before_finally = true
csharp_new_line_before_members_in_object_initializers = true
csharp_new_line_before_members_in_anonymous_types = true
csharp_new_line_between_query_expression_clauses = true
```

#### <a name="indent"></a>들여쓰기 옵션

이러한 서식 지정 규칙은 코드의 서식을 지정하기 위해 들여쓰기를 사용합니다.

다음 표에서는 규칙 이름, 적용 가능한 언어, 기본값 및 먼저 지원되는 Visual Studio의 버전을 보여줍니다.

| 규칙 이름 | 해당 언어 | Visual Studio 기본값 | Visual Studio 2017 버전 |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_indent_case_contents |  C# | true | 15.3  |
| csharp_indent_switch_labels |  C# | true | 15.3  |
| csharp_indent_labels |  C# | no_change | 15.3  |

**csharp\_indent\_case_contents**

- 이 규칙을 **true**로 설정하면 `switch` 사례 콘텐츠를 들여씁니다.
- 이 규칙을 **false**로 설정하면 `switch` 사례 콘텐츠를 들여쓰지 않습니다.

코드 예제:

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

**csharp\_indent\_switch_labels**

- 이 규칙을 **true**로 설정하면 `switch` 레이블을 들여씁니다.
- 이 규칙을 **false**로 설정하면 `switch` 레이블을 들여쓰지 않습니다.

코드 예제:

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

**csharp\_indent_labels**

이 규칙은 **true** 또는 **false** 값을 허용하지 않습니다. 대신 다음 테이블의 값을 허용합니다.

| 값 | 설명 |
| ----- |:----------- |
| flush_left | 레이블은 가장 왼쪽 열에 배치됩니다. |
| one_less_than_current | 레이블은 현재 컨텍스트에 하나 적은 들여쓰기로 배치됩니다. |
| no_change | 레이블은 현재 컨텍스트와 동일한 들여쓰기로 배치됩니다. |

코드 예제:

```csharp
// csharp_indent_labels= flush_left
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
error:
        throw new Exception(...);
    }
}

// csharp_indent_labels = one_less_than_current
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
    error:
        throw new Exception(...);
    }
}

// csharp_indent_labels= no_change
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
        error:
        throw new Exception(...);
    }
}
```

예제 *.editorconfig* 파일:

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_indent_case_contents = true
csharp_indent_switch_labels = true
csharp_indent_labels = flush_left
```

#### <a name="spacing"></a>간격 옵션

이러한 서식 지정 규칙은 코드의 서식을 지정하기 위해 공백 문자를 사용합니다.

다음 표에서는 규칙 이름, 적용 가능한 언어, 기본값 및 먼저 지원되는 Visual Studio의 버전을 보여줍니다.

| 규칙 이름 | 해당 언어 | Visual Studio 기본값 | Visual Studio 2017 버전 |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_space_after_cast |  C# | False | 15.3  |
| csharp_space_after_keywords_in_control_flow_statements |  C# | true | 15.3  |
| csharp_space_between_method_declaration_parameter_list_parentheses |  C# | False | 15.3  |
| csharp_space_between_method_call_parameter_list_parentheses |  C# | False | 15.3  |
| csharp_space_between_parentheses |  C# | False | 15.3  |

**csharp\_space\_after_cast**

- 이 규칙을 **true**로 설정하면 캐스트와 값 사이에 공백이 필요합니다.
- 이 규칙을 **false**로 설정하면 캐스트와 값 사이에 공백이 필요하지 _않습니다_.

코드 예제:

```csharp
// csharp_space_after_cast = true
int y = (int) x;

// csharp_space_after_cast = false
int y = (int)x;
```

**csharp_space_after_keywords_in_control_flow_statements**

- 이 규칙을 **true**로 설정하면 `for` 루프와 같은 제어 흐름 문의 키워드 뒤에 공백이 필요합니다.
- 이 규칙을 **false**로 설정하면 `for` 루프와 같은 제어 흐름 문의 키워드 뒤에 공백이 필요하지 _않습니다_.

코드 예제:

```csharp
// csharp_space_after_keywords_in_control_flow_statements = true
for (int i;i<x;i++) { ... }

// csharp_space_after_keywords_in_control_flow_statements = false
for(int i;i<x;i++) { ... }
```

**csharp_space_between_method_declaration_parameter_list_parentheses**

- 이 규칙을 **true**로 설정하면 여는 괄호 뒤 및 메서드 선언 매개 변수 목록의 닫는 괄호 앞에 공백 문자를 배치합니다.
- 이 규칙을 **false**로 설정하면 여는 괄호 뒤 및 메서드 선언 매개 변수 목록의 닫는 괄호 앞에 공백 문자를 배치하지 않습니다.

코드 예제:

```csharp
// csharp_space_between_method_declaration_parameter_list_parentheses = true
void Bark( int x ) { ... }

// csharp_space_between_method_declaration_parameter_list_parentheses = false
void Bark(int x) { ... }
```

**csharp_space_between_method_call_parameter_list_parentheses**

- 이 규칙을 **true**로 설정하면 여는 괄호 뒤 및 메서드 호출의 닫는 괄호 앞에 공백 문자를 배치합니다.
- 이 규칙을 **false**로 설정하면 여는 괄호 뒤 및 메서드 호출의 닫는 괄호 앞에 공백 문자를 배치하지 않습니다.

코드 예제:

```csharp
// csharp_space_between_method_call_parameter_list_parentheses = true
MyMethod( argument );

// csharp_space_between_method_call_parameter_list_parentheses = false
MyMethod(argument);
```

**csharp_space_between_parentheses**

이 규칙은 다음 표에서 하나 이상의 값을 허용합니다.

| 값 | 설명 |
| ----- |:------------|
| control_flow_statements | 제어 흐름 문의 괄호 간에 공백 배치 |
| 식 | 식의 괄호 간에 공백 배치 |
| type_casts | 형식 캐스트의 괄호 간에 공백 배치 |

이 규칙을 생략하거나 `control_flow_statements`, `expressions` 또는 `type_casts` 이외의 값을 사용하는 경우 설정이 적용되지 않습니다.

코드 예제:

```csharp
// csharp_space_between_parentheses = control_flow_statements
for ( int i = 0; i < 10; i++ ) { }

// csharp_space_between_parentheses = expressions
var z = ( x * y ) - ( ( y - x ) * 3 );

// csharp_space_between_parentheses = type_casts
int y = ( int )x;
```

예제 *.editorconfig* 파일:

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_space_after_cast = true
csharp_space_after_keywords_in_control_flow_statements = true
csharp_space_between_method_declaration_parameter_list_parentheses = true
csharp_space_between_method_call_parameter_list_parentheses = true
csharp_space_between_parentheses = control_flow_statements, type_casts
```

#### <a name="wrapping"></a>래핑 옵션

이러한 서식 설정 규칙은 문 및 코드 블록에 단일 줄 및 별도 줄을 사용하는 것을 다룹니다.

다음 표에서는 규칙 이름, 적용 가능한 언어, 기본값 및 먼저 지원되는 Visual Studio의 버전을 보여줍니다.

| 규칙 이름 | 해당 언어 | Visual Studio 기본값 | Visual Studio 2017 버전 |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_preserve_single_line_statements |  C# | true | 15.3  |
| csharp_preserve_single_line_blocks |  C# | true | 15.3  |

**csharp_preserve_single_line_statements**

- 이 규칙이 **true**로 설정되면 문과 멤버 선언을 동일한 줄에 유지합니다.
- 이 규칙이 **false**로 설정되면 문과 멤버 선언을 다른 줄에 유지합니다.

코드 예제:

```csharp
//csharp_preserve_single_line_statements = true
int i = 0; string name = "John";

//csharp_preserve_single_line_statements = false
int i = 0;
string name = "John";
```

**csharp_preserve_single_line_blocks**

- 이 규칙을 **true**로 설정하면 코드 블록은 한 줄에 유지합니다.
- 이 규칙을 **false**로 설정하면 코드 블록은 별도 줄에 유지합니다.

코드 예제:

```csharp
//csharp_preserve_single_line_blocks = true
public int Foo { get; set; }

//csharp_preserve_single_line_blocks = false
public int MyProperty
{
    get; set;
}
```

예제 *.editorconfig* 파일:

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_preserve_single_line_statements = true
csharp_preserve_single_line_blocks = true
```

## <a name="see-also"></a>참고 항목

- [빠른 작업](../ide/quick-actions.md)
- [EditorConfig에 대한 .NET 명명 규칙](../ide/editorconfig-naming-conventions.md)
- [휴대용, 사용자 지정 편집기 옵션 만들기](../ide/create-portable-custom-editor-options.md)
- [.NET 컴파일러 플랫폼 .editorconfig 파일](https://github.com/dotnet/roslyn/blob/master/.editorconfig)
