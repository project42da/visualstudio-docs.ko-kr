---
title: "예외 문제 해결: System.NullReferenceException | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "NullReferenceException 클래스"
ms.assetid: 4822b0b4-8105-43fb-887a-3cc51ff02899
caps.latest.revision: 29
caps.handback.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.NullReferenceException
<xref:System.NullReferenceException>은 `null` 값을 갖는 *참조 형식*\([C\#](/dotnet/csharp/language-reference/keywords/reference-types), [Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types)\)의 속성이나 메서드를 사용하려고 할 때 발생합니다. 예를 들어 [new](/dotnet/csharp/language-reference/keywords/new)\(Visual Basic의 경우 [New](/dotnet/visual-basic/language-reference/operators/new-operator)\) 키워드를 먼저 사용하지 않고 개체를 사용하려고 했거나 값이 [null](/dotnet/csharp/language-reference/keywords/null)\(Visual Basic의 경우 [Nothing](/dotnet/visual-basic/language-reference/nothing)\)로 설정된 개체를 사용하려고 했을 수 있습니다.  
  
##  <a name="BKMK_Contents"></a> 이 문서의 섹션  
 [이 문서에서 사용되는 클래스](#BKMK_Classes_used_in_the_examples)  
  
 [NullReferenceException이 발생하는 일반적인 원인](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 [개발 시 null 참조 예외 소스 찾기](#BKMK_Find_the_source_of_a_null_reference_exception_during_development)  
  
 [NullReferenceException 방지](#BKMK_Avoid_NullReferenceExceptions)  
  
 [릴리스 코드에서 발생된 NullReferenceException 처리](#BKMK_Handle_NullReferenceExceptions_in_release_code)  
  
##  <a name="BKMK_Classes_used_in_the_examples"></a> 이 문서에서 사용되는 클래스  
 이 문서에 포함된 대부분의 예제에서는 다음 클래스 중 하나 또는 둘 다가 사용됩니다.  
  
```c#  
public class Automobile { public EngineInfo Engine {get; set;} } public class EngineInfo { public EngineInfo() { } public EngineInfo(string powerSrc, double engineSize) { Power = powerSrc; Size = engineSize; } public double Size { get; set; } public string Power = null; }  
  
```  
  
```vb  
Public Class Automobile Public Property Engine As EngineInfo End Class Public Class EngineInfo Public Sub New() End Sub Public Sub New(powerSrc As String, engineSize As Double) Power = powerSrc Size = engineSize End Sub Public Property Size() As Double Public Power As String = Nothing End Class  
  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)  
  
##  <a name="BKMK_Common_causes_of_NullReferenceExceptions"></a> NullReferenceException이 발생하는 일반적인 원인  
 임의의 참조 형식 변수는 null일 수 있습니다. 지역 변수, 클래스 속성, 메서드 매개 변수 및 메서드 반환 값에는 모두 null 참조가 포함될 수 있습니다. 이러한 변수의 속성이나 메서드가 null일 때 이를 호출하면 NullReferenceException이 발생합니다. 구체적인 사례는 다음과 같습니다.  
  
 [지역 변수 또는 멤버 필드가 선언되었지만 초기화되어 있지 않음](#BKMK_A_local_variable_or_member_field_is_declared_but_not_initialized)  
  
 [속성이나 필드가 null임](#BKMK_A_property_or_field_is_null)  
  
 [메서드 매개 변수가 null임](#BKMK_A_method_parameter_is_null)  
  
 [메서드 반환 값이 null임](#BKMK_The_return_value_of_a_method_is_null)  
  
 [컬렉션이나 배열의 개체가 null임](#BKMK_An_object_in_a_collection_or_array_is_null)  
  
 [조건으로 인해 개체가 만들어지지 않음](#BKMK_An_object_is_not_created_because_of_a_condition)  
  
 [참조를 통해 메서드에 전달된 개체가 null로 설정됨](#BKMK_An_object_passed_by_reference_to_a_method_is_set_to_null)  
  
###  <a name="BKMK_A_local_variable_or_member_field_is_declared_but_not_initialized"></a> 지역 변수 또는 멤버 필드가 선언되었지만 초기화되어 있지 않음  
 이 단순 오류는 Visual Basic 코드에서 주로 발생합니다. 변수를 out 매개 변수로 전달하도록 선언하는 경우를 제외하고 C\# 컴파일러에서는 초기화되지 않은 지역 참조 변수를 사용할 수 없습니다. 변수를 이와 같이 사용하면 Visual Basic 컴파일러가 경고를 생성합니다.  
  
-   다음 C\# 코드에서는 강조 표시된 줄에서 이 컴파일러 오류가 생성됩니다.  
  
 **할당되지 않은 'engine' 지역 변수를 사용했습니다.**  
  
-   Visual Basic 코드에서는 강조 표시된 줄이 컴파일러 경고 BC42104를 생성합니다.  
  
 **값이 할당되기 전에 'engine' 변수를 사용했습니다. 런타임에 null 참조 예외가 발생할 수 있습니다.**     코드가 실행될 때 이 줄에서 NullReferenceException을 throw합니다.  
  
```c#  
public void NullReferencFromUninitializedLocalVariable() { EngineInfo engine; Console.WriteLine(engine.ToString()); }  
```  
  
```vb  
Public Sub NullReferencFromUninitializedLocalVariable() Dim engine As EngineInfo Console.WriteLine(engine.ToString()) End Sub  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [NullReferenceException이 발생하는 일반적인 원인](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)  
  
###  <a name="BKMK_A_property_or_field_is_null"></a> 속성이나 필드가 null임  
 클래스의 필드 및 속성은 클래스가 만들어질 때 해당 [기본값](../Topic/Data%20Member%20Default%20Values.md)으로 자동으로 초기화됩니다. 참조 형식의 기본값은 `null`\(Visual Basic의 경우 `Nothing`\)입니다. 필드나 속성의 값이 null일 때 부모 클래스의 필드나 속성에서 멤버 메서드를 호출하면 NullReferenceException이 발생합니다.  
  
 다음 예제에서 `Engine`의 `car` 속성이 null로 자동 초기화되므로 강조 표시된 줄이 NullReferenceException을 throw합니다.  
  
```c#  
public void NullReferenceFromProperty() { var car = new Automobile(); Console.WriteLine(car.Engine.ToString()); }  
```  
  
```vb  
Public Sub NullReferenceFromProperty() Dim car = New Automobile() Console.WriteLine(car.Engine.ToString()) End Sub  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [NullReferenceException이 발생하는 일반적인 원인](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)  
  
###  <a name="BKMK_A_method_parameter_is_null"></a> 메서드 매개 변수가 null임  
 참조 형식인 메서드 매개 변수는 `null`\(Visual Basic의 경우 `Nothing`\)일 수 있습니다. null인 매개 변수 값에 대한 멤버 메서드나 속성을 호출하면 NullReferenceException이 발생합니다.  
  
 다음 예제에서는 `BadEngineInfoPassedToMethod`에서 매개 변수가 null인 `NullReferenceFromMethodParameter`를 호출하므로, 강조 표시된 줄이 NullReferenceException을 throw합니다.  
  
```c  
public void BadEngineInfoPassedToMethod() { EngineInfo eng = null; NullReferenceFromMethodParameter(eng); } public void NullReferenceFromMethodParameter(EngineInfo engine) { Console.WriteLine(engine.ToString()); }  
  
```  
  
```vb  
Public Sub BadParameterPassedToMethod() As EngineInfo Dim eng As EngineInfo = Nothing NullReferenceFromMethodParameter(eng) End Sub Public Sub NullReferenceFromMethodParameter(engine As EngineInfo) Console.WriteLine(engine.ToString()) End Sub  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [NullReferenceException이 발생하는 일반적인 원인](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)  
  
###  <a name="BKMK_The_return_value_of_a_method_is_null"></a> 메서드 반환 값이 null임  
 참조 형식을 반환하는 메서드가 `null`\(Visual Basic의 경우 `Nothing`\)을 반환할 수 있습니다. 반환된 참조 형식의 속성이나 메서드를 호출할 경우 참조가 null이면 NullReferenceException이 발생합니다.  
  
 다음 예제에서는 `BadGetEngineInfo`에 대한 호출이 `NullReferenceFromMethodParameter` 메서드의 null 참조를 반환하므로, 강조 표시된 줄이 NullReferenceException을 throw합니다.  
  
```c#  
public EngineInfo BadGetEngineInfo() { EngineInfo engine = null; return engine; } public void NullReferenceFromMethodReturnValue() { var engine = BadGetEngineInfo(); Console.WriteLine(engine.ToString()); }  
```  
  
```vb  
Public Function BadGetEngineInfo() As EngineInfo Dim engine As EngineInfo = Nothing Return engine End Function Public Sub NullReferenceFromMethodReturnValue() Dim engine = BadGetEngineInfo() Console.WriteLine(engine.ToString()) End Sub  
  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [NullReferenceException이 발생하는 일반적인 원인](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)  
  
###  <a name="BKMK_An_object_in_a_collection_or_array_is_null"></a> 컬렉션이나 배열의 개체가 null임  
 참조 형식의 목록이나 배열에는 null 항목이 포함될 수 있습니다. null인 목록 항목에 대한 메서드나 속성을 호출하면 NullReferenceException이 발생합니다.  
  
 다음 예제에서는 `NullReferenceFromListItem()`에 대한 호출이 null 항목을 반환하므로, `BadGetCarList`의 강조 표시된 줄이 NullReferenceException을 throw합니다.  
  
```c#  
public Automobile[] BadGetCarList() { var autos = new Automobile[10]; for (int i = 0; i autos.Length; i++) { if (i != 6) { autos[i] = new Automobile(); } } return autos; } public void NullReferenceFromListItem() { var cars = BadGetCarList(); foreach (Automobile car in cars) { Console.WriteLine(car.ToString()); } }  
```  
  
```vb  
Public Function BadGetCarList() As Automobile() Dim autos = New Automobile(10) {} For i As Integer = 0 To 9 If i <> 6 Then autos(i) = New Automobile() End If Next Return autos End Function Public Sub NullReferenceFromListItem() Dim cars = BadGetCarList() For Each car As Automobile In cars Console.WriteLine(car.ToString()) Next End Sub  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [NullReferenceException이 발생하는 일반적인 원인](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)  
  
###  <a name="BKMK_An_object_is_not_created_because_of_a_condition"></a> 조건으로 인해 개체가 만들어지지 않음  
 참조 형식이 조건부 블록에서 초기화되는 경우 조건이 false이면 개체가 만들어지지 않습니다.  
  
 다음 예제에서는 `NullReferenceFromConditionalCreation` 메서드가 `engine`를 반환하는 경우에만 `DetermineTheCondition()`의 강조 표시된 줄이 `true` 변수를 초기화하므로, 해당 강조 표시된 줄이 NullReferenceException을 throw합니다.  
  
```c#  
public bool DetermineTheCondition() { return false; } public void NullReferenceFromConditionalCreation() { EngineInfo engine = null; var condition = DetermineTheCondition(); if (condition) { engine = new EngineInfo(); engine.Power = "Diesel"; engine.Size = 2.4; } Console.WriteLine(engine.Size); }  
```  
  
```vb  
Public Function DetermineTheCondition() As Boolean Return False End Function Public Sub NullReferenceFromConditionalCreation() Dim engine As EngineInfo = Nothing Dim condition = DetermineTheCondition() If condition Then engine = New EngineInfo() engine.Power = "Diesel" engine.Size = 2.4 End If Console.WriteLine(engine.Size) End Sub  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [NullReferenceException이 발생하는 일반적인 원인](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)  
  
### 메서드에 전달된 개체의 속성이 null로 설정됨  
 C\#의 `ref` 또는 `out` 키워드를 사용하거나 Visual Basic의 `ByRef` 키워드를 사용하지 않고, 값을 통해 개체를 메서드에 매개 변수로 전달하는 경우 메서드는 매개 변수의 메모리 위치\(매개 변수가 가리키는 위치\)를 변경할 수 없지만 개체의 속성을 변경할 수는 있습니다.  
  
 다음 예제에서는 `NullPropertyReferenceFromPassToMethod` 메서드가 `Automobile` 개체를 만들고 `Engine` 속성을 초기화합니다. 그런 다음 `BadSwapCarEngine`을 호출하여 새 개체를 매개 변수로 전달합니다.`BadSwapCarEngine`이 Engine 속성을 null로 설정하므로 `NullPropertyReferenceFromPassToMethod`의 강조 표시된 줄에서 NullReferenceException이 throw됩니다.  
  
```c#  
public void BadSwapCarEngine(Automobile car) { car.Engine = null; } public void (Automobile car) { car.Engine = new EngineInfo("GAS", 1.5); BadSwapCarEngine(car); Console.WriteLine(car.Engine.ToString()); }  
  
```  
  
```vb  
Public Sub BadSwapCarEngine(car As Automobile) car.Engine = Nothing End Sub Public Sub NullPropertyReferenceFromPassToMethod() Dim car As New Automobile() car.Engine = New EngineInfo("GAS", 1.5) BadSwapCarEngine(car) Console.WriteLine(car.Engine.ToString()) End Sub  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [NullReferenceException이 발생하는 일반적인 원인](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)  
  
###  <a name="BKMK_An_object_passed_by_reference_to_a_method_is_set_to_null"></a> 참조를 통해 메서드에 전달된 개체가 null로 설정됨  
 C\#의 `ref` 또는 `out` 키워드를 사용하거나 Visual Basic의 `ByRef` 키워드를 사용하여, 참조를 통해 참조 형식을 메서드에 매개 변수로 전달하는 경우 매개 변수가 가리키는 메모리 위치를 변경할 수 있습니다.  
  
 참조를 통해 참조 형식을 메서드에 전달하는 경우 메서드는 참조된 형식을 `null`\(Visual Basic의 경우 `Nothing`\)로 설정할 수 있습니다.  
  
 다음 예제에서는 `NullReferenceFromPassToMethodByRef` 메서드에 대한 호출이 `BadEngineSwapByRef` 변수를 null로 설정하므로, `stockEngine`의 강조 표시된 줄이 NullReferenceException을 throw합니다.  
  
```c#  
public void BadEngineSwapByRef(ref EngineInfo engine) { engine = null; } public void NullReferenceFromPassToMethodByRef() { var stockEngine = new EngineInfo(); stockEngine.Power = "Gas"; stockEngine.Size = 7.0; BadSwapEngineByRef(ref stockEngine); Console.WriteLine(stockEngine.ToString()); }  
```  
  
```vb  
Public Sub BadSwapEngineByRef(ByRef engine As EngineInfo) engine = Nothing End Sub Public Sub NullReferenceFromPassToMethodByRef() Dim formatStr = "The stock engine has been replaced by a {0} liter {} engine" Dim stockEngine = New EngineInfo() stockEngine.Power = "Gas" stockEngine.Size = 7.0 BadSwapEngineByRef(stockEngine) Console.WriteLine(stockEngine.ToString()) End Sub  
  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [NullReferenceException이 발생하는 일반적인 원인](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)  
  
##  <a name="BKMK_Find_the_source_of_a_null_reference_exception_during_development"></a> 개발 시 null 참조 예외 소스 찾기  
 [데이터 팁, 지역 창 및 조사식 창을 사용하여 변수 값 확인](#BKMK_Use_data_tips_the_Locals_window_and_watch_windows_to_see_variables_values)  
  
 [호출 스택을 검색하여 참조 변수가 초기화되지 않았거나 null로 설정된 위치 찾기](#BKMK_Walk_the_call_stack_to_find_where_a_type_reference_is_not_initialized_or_set_to_null_)  
  
 [개체가 null(Visual Basic의 경우 Nothing)이면 디버깅을 중지하도록 조건부 중단점 설정](#BKMK_Set_conditional_breakpoints_to_stop_debugging_when_an_object_is_null_Nothing_in_Visual_Basic_)  
  
###  <a name="BKMK_Use_data_tips_the_Locals_window_and_watch_windows_to_see_variables_values"></a> 데이터 팁, 지역 창 및 조사식 창을 사용하여 변수 값 확인  
  
-   포인터를 변수 이름 위에 놓으면 [데이터 팁](../debugger/view-data-values-in-data-tips-in-the-code-editor.md)에 해당 값이 표시됩니다. 변수가 개체나 컬렉션을 참조하는 경우에는 데이터 형식을 확장하여 해당 속성이나 요소를 검사할 수 있습니다.  
  
-   **지역** 창을 열어 현재 컨텍스트에서 활성인 변수를 확인할 수 있습니다.  
  
-   [조사식 창](../debugger/watch-and-quickwatch-windows.md)을 사용하면 코드를 단계별로 실행함에 따라 변수가 어떻게 변경되는지 확인할 수 있습니다.  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [개발 시 null 참조 예외 소스 찾기](#BKMK_Find_the_source_of_a_null_reference_exception_during_development)  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)  
  
###  <a name="BKMK_Walk_the_call_stack_to_find_where_a_type_reference_is_not_initialized_or_set_to_null_"></a> 호출 스택을 검색하여 참조 변수가 초기화되지 않았거나 null로 설정된 위치 찾기  
 Visual Studio [호출 스택 창](../debugger/how-to-use-the-call-stack-window.md)에는 디버거가 예외나 중단점에서 중지되었을 때 완료되지 않은 메서드의 이름이 나열됩니다.**호출 스택** 창에서 이름을 선택한 다음 **프레임으로 전환**을 선택하여 메서드의 실행 컨텍스트를 변경하고 해당 변수를 검사할 수 있습니다.  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [개발 시 null 참조 예외 소스 찾기](#BKMK_Find_the_source_of_a_null_reference_exception_during_development)  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)  
  
###  <a name="BKMK_Set_conditional_breakpoints_to_stop_debugging_when_an_object_is_null_Nothing_in_Visual_Basic_"></a> 개체가 null\(Visual Basic의 경우 Nothing\)이면 디버깅을 중지하도록 조건부 중단점 설정  
 [조건부 중단점](http://msdn.microsoft.com/library/5557y8b4.aspx#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)을 설정하여 변수가 null이면 중단할 수 있습니다. 조건부 중단점은 컬렉션의 항목이 간헐적으로만 null인 경우와 같이 null 참조가 자주 발생하지 않는 경우에 유용합니다. 조건부 중단점의 또 다른 이점으로는 특정 처리 루틴에 대한 커밋 전에 문제를 디버깅할 수 있다는 점입니다.  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [개발 시 null 참조 예외 소스 찾기](#BKMK_Find_the_source_of_a_null_reference_exception_during_development)  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)  
  
##  <a name="BKMK_Avoid_NullReferenceExceptions"></a> NullReferenceException 방지  
 [Debug.Assert를 사용하여 고정 확인](#BKMK_Use_Debug_Assert_to_confirm_an_invariant)  
  
 [참조 형식을 완전히 초기화](#BKMK_Fully_initialize_reference_types)  
  
###  <a name="BKMK_Use_Debug_Assert_to_confirm_an_invariant"></a> Debug.Assert를 사용하여 고정 확인  
 *고정*은 true임을 확정하는 조건입니다.[Debug.Assert\(System.Diagnostics\)](http://msdn.microsoft.com/library/system.diagnostics.debug.assert.aspx) 문은 앱의 디버그 빌드에서만 호출되며 릴리스 코드에서는 호출되지 않습니다. 고정 조건이 true가 아닐 경우 디버거는 Assert 문에서 중단되며 대화 상자를 표시합니다.`Debug.Assert`에서는 앱 개발 중에 조건이 변경되지 않았다는 확인을 제공합니다. 어설션은 코드를 읽는 다른 사용자를 위해 조건이 항상 true여야 한다는 점도 설명합니다.  
  
 예를 들어 `MakeEngineFaster` 메서드는 유일한 호출자 메서드\(`engine`\)가 `TheOnlyCallerOfMakeEngineFaster`를 완전히 초기화하는 것으로 알려졌으므로 `EngineInfo` 매개 변수가 null이 아닌 것으로 가정합니다.`MakeEngineFaster`의 어설션은 이 가정을 입증하며 이 가정이 true라는 확인을 제공합니다.  
  
 매개 변수를 초기화하지 않는 새로운 호출자 메서드\(`BadNewCallerOfMakeEngineFaster`\)를 추가할 경우 어설션이 트리거됩니다.  
  
```c#  
private void TheOnlyCallerOfMakeEngineFaster() { var engine = new EngineInfo(); engine.Power = "GAS"; engine.Size = 1.5; MakeEngineFaster(engine); } private void MakeEngineFaster(EngineInfo engine) { System.Diagnostics.Debug.Assert(engine != null, "Assert: engine != null"); engine.Size *= 2; Console.WriteLine("The engine is twice as fast"); } private void BadNewCallerOfMakeEngineFaster() { EngineInfo engine = null; MakeEngineFaster(engine); }  
```  
  
```vb  
Public Sub TheOnlyCallerOfMakeEngineFaster() Dim engine As New EngineInfo engine.Power = "GAS" engine.Size = 1.5 MakeEngineFaster(engine) End Sub Private Sub MakeEngineFaster(engine As EngineInfo) System.Diagnostics.Debug.Assert(engine IsNot Nothing, "Assert: engine IsNot Nothing") engine.Size = engine.Size * 2 Console.WriteLine("The engine is twice as fast") End Sub Public Sub BadNewCallerOfMakeEngineFaster() Dim engine As EngineInfo = Nothing MakeEngineFaster(engine) End Sub  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [NullReferenceException 방지](#BKMK_Avoid_NullReferenceExceptions)  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)  
  
###  <a name="BKMK_Fully_initialize_reference_types"></a> 참조 형식을 완전히 초기화  
 참조 형식을 가능한 만들자마자 완전히 초기화하여 대부분의 NullReferenceException을 방지할 수 있습니다.  
  
 **자체 클래스에 전체 초기화 추가**  
  
 NullReferenceException을 throw한 클래스를 제어하는 경우 형식의 생성자에 있는 개체를 완전히 초기화해봅니다. 예를 들어 다음은 전체 초기화를 보장하는 예제 클래스의 수정된 버전입니다.  
  
```c#  
public class Automobile { public EngineInfo Engine { get; set; } public Automobile(){this.Engine = new EngineInfo();} public Automobile(string powerSrc, double engineSize) { this.Engine = new EngineInfo(powerSrc, engineSize); } } public class EngineInfo { public double Size {get; set;} public string Power {get; set;} public EngineInfo(){// the base enginethis.Power = "GAS";this.Size = 1.5;} public EngineInfo(string powerSrc, double engineSize) { this.Power = powerSrc; this.Size = engineSize; } }  
  
```  
  
```vb  
Public Class Automobile Public Property Engine As EngineInfo     Public Sub New()Me.Engine = New EngineInfo()End SubPublic Sub New(powerSrc As String, engineSize As Double)Me.Engine = New EngineInfo(powerSrc, engineSize)End Sub End Class Public Class BaseEngineInfo Public Sub New()' the base engineMe.Power = "GAS"Me.Size = 1.5End Sub Public Sub New(powerSrc As String, engineSize As Double) Power = powerSrc Size = engineSize End Sub Public Property Size() As Double Public Power As String = String.Empty End Class  
```  
  
> [!NOTE]
>  **대형 속성이나 간헐적으로 사용되는 속성에 초기화 지연 사용**  
>   
>  클래스의 메모리 공간을 줄이고 성능을 향상시키려면 참조 형식 속성에 대해 초기화 지연을 사용해봅니다.[초기화 지연](../Topic/Lazy%20Initialization.md)을 참조하세요.  
  
##  <a name="BKMK_Handle_NullReferenceExceptions_in_release_code"></a> 릴리스 코드에서 발생된 NullReferenceException 처리  
 [참조 형식을 사용하기 전에 null(Visual Basic의 경우 Nothing) 검사](#BKMK_Check_for_null_Nothing_in_Visual_Basic_before_using_a_reference_type)  
  
 [try–catch–finally(Visual Basic의 경우 Try–Catch–Finally)를 사용하여 예외 처리](#BKMK_Use_try_catch_finally_Try_Catch_Finally_in_Visual_Basic_to_handle_the_exception)  
  
 NullReferenceException이 발생된 후 이를 처리하는 것 보다는 이를 예방하는 것이 더 좋습니다. 예외 처리로 인해 코드는 유지 관리하고 이해하기가 더 어려워지며 때로는 다른 버그가 발생할 수도 있습니다. NullReferenceException은 대개 복구할 수 없는 오류입니다. 이러한 경우 예외로 인해 앱이 중지되도록 하는 것이 최상의 방법일 수 있습니다.  
  
 하지만 오류 처리가 유용한 경우도 많이 있습니다.  
  
-   앱에서 null 개체를 무시할 수 있습니다. 예를 들어 앱에서 데이터베이스의 레코드를 검색하고 처리하는 경우 null 개체를 발생시키는 잘못된 레코드를 무시할 수 있습니다. 로그 파일이나 응용 프로그램 UI에 있는 잘못된 데이터를 기록하기만 하면 됩니다.  
  
-   예외에서 복구할 수 있습니다. 예를 들어 참조 형식을 반환하는 웹 서비스에 대한 호출은 연결이 끊어졌거나 연결 시간이 초과된 경우 null을 반환할 수 있습니다. 연결을 다시 설정한 다음 다시 호출할 수 있습니다.  
  
-   앱 상태를 올바른 상태로 복원할 수 있습니다. 예를 들어 NullReferenceException을 throw하는 메서드를 호출하기 전에 정보를 데이터 저장소에 저장하도록 하는 다단계 작업을 수행할 수 있습니다. 초기화되지 않은 개체로 인해 데이터 레코드가 손상될 경우 앱을 종료하기 전에 이전 데이터를 제거할 수 있습니다.  
  
-   그리고 예외 보고를 원할 수 있습니다. 예를 들어 앱 사용자의 실수로 오류가 발생한 경우 사용자가 올바른 정보를 제공할 수 있도록 도와 주는 메시지를 생성할 수 있습니다. 문제를 해결할 수 있도록 오류에 대한 정보를 기록할 수도 있습니다. ASP.NET과 같은 일부 프레임워크에는 앱이 충돌하지 않도록 모든 오류를 캡처하는 수준 높은 예외 처리기가 포함되어 있습니다. 이러한 경우 예외 발생 여부를 확인할 수 있는 방법은 예외를 로깅하는 것뿐입니다.  
  
 다음은 릴리스 코드에서 NullReferenceException을 처리하는 두 가지 방법입니다.  
  
###  <a name="BKMK_Check_for_null_Nothing_in_Visual_Basic_before_using_a_reference_type"></a> 참조 형식을 사용하기 전에 null\(Visual Basic의 경우 Nothing\) 검사  
 개체를 사용하기 전에 null에 대한 명시적 테스트를 사용하여 try\-catch\-finally 구문의 성능 저하를 방지합니다. 하지만 여전히 초기화되지 않은 개체에 대한 응답으로 수행할 작업을 결정하고 구현해야 합니다.  
  
 이 예제에서 `CheckForNullReferenceFromMethodReturnValue`는 `BadGetEngineInfo` 메서드의 반환 값을 테스트합니다. 개체는 null이 아니면 사용되며 그렇지 않을 경우 메서드가 오류를 보고합니다.  
  
```c#  
public EngineInfo BadGetEngineInfo() { EngineInfo engine = null; return engine; } public void CheckForNullReferenceFromMethodReturnValue() { var engine = BadGetEngineInfo(); if(engine != null) { // modify the info engine.Power = "DIESEL"; engine.Size = 2.4; } else { // report the error Console.WriteLine("BadGetEngine returned null") } }  
  
```  
  
```vb  
public EngineInfo BadGetEngineInfo() { EngineInfo engine = null; return engine; } Public Sub CheckForNullReferenceFromMethodReturnValue() Dim engine = BadGetEngineInfo() If (engine IsNot Nothing) Then ' modify the info engine.Power = "DIESEL" engine.Size = 2.4 Else ' report the error Console.WriteLine("BadGetEngineInfo returned Nothing") End If End Sub  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [릴리스 코드에서 발생된 NullReferenceException 처리](#BKMK_Handle_NullReferenceExceptions_in_release_code)  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)  
  
###  <a name="BKMK_Use_try_catch_finally_Try_Catch_Finally_in_Visual_Basic_to_handle_the_exception"></a> try–catch–finally\(Visual Basic의 경우 Try–Catch–Finally\)를 사용하여 예외 처리  
 기본 제공 예외 처리 구문\(C\#의 경우 [try, catch, finally](/dotnet/csharp/language-reference/keywords/exception-handling-statements), Visual Basic의 경우 [Try, Catch, Finally](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)\)을 사용할 경우, 개체가 null이 아님을 검사하는 방법에 비해 NullReferenceExceptions를 처리하기 위한 더 많은 옵션이 제공됩니다.  
  
 다음 예제에서 `CatchNullReferenceFromMethodCall`은 두 개의 어설션을 사용하여 해당 매개 변수에 엔진을 비롯한 완전한 자동차가 포함되어 있다는 가정을 확인합니다.`try` 블록에서는 `RarelyBadEngineSwap`에 대한 호출이 자동차의 `Engine` 속성을 제거할 수 있으므로 강조 표시된 줄이 NullReferenceException을 throw합니다.`catch` 블록에서는 예외를 캡처하고, 예외 정보를 파일에 기록하고, 오류를 사용자에게 보고합니다.`finally` 블록에서 메서드는 메서드가 시작되었을 때보다 자동차의 상태가 더 나아졌음을 보장합니다.  
  
```c#  
public void RarelyBadSwapCarEngine(Automobile car) { if ((new Random()).Next() == 42) { car.Engine = null; } else { car.Engine = new EngineInfo("DIESEL", 2.4); } } public void CatchNullReferenceFromMethodCall(Automobile car) { System.Diagnostics.Debug.Assert(car != null, "Assert: car != null"); System.Diagnostics.Debug.Assert(car.Engine != null, "Assert: car.Engine != null"); // save current engine properties in case they're needed var enginePowerBefore = car.Engine.Power; var engineSizeBefore = car.Engine.Size; try { RarelyBadSwapCarEngine(car); var msg = "Swap succeeded. New engine power source: {0} size {1}"; Console.WriteLine(msg, car.Engine.Power, car.Engine.Size); } catch(NullReferenceException nullRefEx) { // write exception info to log file LogException(nullRefEx); // notify the user Console.WriteLine("Engine swap failed. Please call your customer rep."); } finally { if(car.Engine == null) { car.Engine = new EngineInfo(enginePowerBefore, engineSizeBefore); } } }  
  
```  
  
```vb  
Public Sub RarelyBadSwapCarEngine(car As Automobile) If (New Random()).Next = 42 Then car.Engine = Nothing Else car.Engine = New EngineInfo("DIESEL", 2.4) End If End Sub Public Sub CatchNullReferenceFromMethodCall(car As Automobile) System.Diagnostics.Debug.Assert(car IsNot Nothing) System.Diagnostics.Debug.Assert(car.Engine IsNot Nothing) ' save current engine properties in case they're needed Dim powerBefore = car.Engine.Power Dim sizeBefore = car.Engine.Size Try RarelyBadSwapCarEngine(car) Dim msg = "Swap succeeded. New engine power source: {0} size {1}" Console.WriteLine(msg, car.Engine.Power, car.Engine.Size) Catch nullRefEx As NullReferenceException ' write exception info to log file LogException(nullRefEx) ' notify user Console.WriteLine("Engine swap failed. Please call your customer rep.") Finally If car.Engine Is Nothing Then car.Engine = New EngineInfo(powerBefore, sizeBefore) End Try End Sub  
  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [릴리스 코드에서 발생된 NullReferenceException 처리](#BKMK_Handle_NullReferenceExceptions_in_release_code)  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)  
  
## 관련 문서  
 [예외 디자인 지침\(.NET Framework 디자인 지침\)](http://msdn.microsoft.com/library/ms229014)  
  
 [예외 처리 및 Throw\(.NET Framework 응용 프로그램 필수 항목\)](http://msdn.microsoft.com/library/5b2yeyab)  
  
 [방법: 첫째 예외 알림 받기\(.NET Framework 개발 가이드\)](http://msdn.microsoft.com/library/Dd997368)  
  
 [방법: PLINQ 쿼리에서 발생된 예외 처리\(.NET Framework 개발 가이드\)](http://msdn.microsoft.com/library/Dd460712)  
  
 [관리되는 스레드에서 발생된 예외\(.NET Framework 개발 가이드\)](http://msdn.microsoft.com/library/ms228965)  
  
 [예외 및 예외 처리\(C\# 프로그래밍 가이드\)](http://msdn.microsoft.com/library/ms173160)  
  
 [예외 처리문\(C\# 참조\)](http://msdn.microsoft.com/library/s7fekhdy)  
  
 [Try...Catch...Finally 문\(Visual Basic\)](http://msdn.microsoft.com/library/fk6t46tz)  
  
 [예외 처리\(F\#\)](http://msdn.microsoft.com/library/Dd233223)  
  
 [C\+\+\/CLI의 예외](http://msdn.microsoft.com/library/Hh875008)  
  
 [예외 처리\(작업 병렬 라이브러리\)](http://msdn.microsoft.com/library/Dd997415)  
  
 [예외 처리\(디버깅\)](http://msdn.microsoft.com/library/x85tt0dd)  
  
 [연습: 동시성 예외 처리\(Visual Studio의 데이터 액세스\)](http://msdn.microsoft.com/library/ms171936)  
  
 [방법: 데이터 바인딩에서 발생하는 오류 및 예외 처리\(Windows Forms\)](http://msdn.microsoft.com/library/k26k86tb)  
  
 [네트워크 앱\(XAML\)\(Windows\)에서 발생된 예외 처리](http://msdn.microsoft.com/library/Dn263240)  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 섹션](#BKMK_Contents)