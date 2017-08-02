---
title: "예외 문제 해결: System.InvalidOperationException | Microsoft Docs"
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
  - "InvalidOperationException 클래스"
ms.assetid: db3400e5-62d7-4d65-897d-387e7edcb7cf
caps.latest.revision: 33
caps.handback.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.InvalidOperationException
개체의 상태가 메서드 호출을 지원할 수 없을 때 개체의 메서드를 호출하면 <xref:System.InvalidOperationException?displayProperty=fullName>이 throw됩니다. 또한 주 스레드나 UI 스레드가 아닌 스레드에서 메서드가 UI를 조작하려고 할 때도 예외가 throw됩니다.  
  
> [!IMPORTANT]
>  <xref:System.InvalidOperationException>은 다양한 상황에서 throw될 수 있으므로 예외 도우미에 표시되는 <xref:System.Exception.Message%2A>를 확인하고 이해해야 합니다.  
  
##  <a name="BKMK_In_this_article"></a> 이 문서의 내용  
 [UI가 아닌 스레드에서 실행되는 메서드가 UI를 업데이트함](#BKMK_A_method_running_on_a_non_UI_thread_updates_the_UI)  
  
 [foreach(Visual Basic에서는 For Each) 블록의 문이 자체적으로 반복하는 컬렉션을 변경함](#BKMK_A_statement_in_a_foreach_For_Each_in_Visual_Basic_block_changes_the_collection_it_is_iterating)  
  
 [null인 null 허용 &lt;T&gt;가 T로 캐스팅됨](#BKMK_A_Nullable_T_that_is_null_is_cast_to_T)  
  
 [빈 컬렉션에 대해 System.Linq.Enumerable 메서드가 호출됨](#BKMK_A_System_Linq_Enumerable_method_is_called_on_an_empty_collection)  
  
 [관련 문서](#BKMK_Related_articles)  
  
 이 문서의 코드 예제에서는 앱에서 일반적인 몇 가지 <xref:System.InvalidOperationException> 예외가 어떻게 발생하는지를 보여 줍니다. 문제를 처리하는 방법은 특정 상황에 따라 달라집니다. 치명적인 예외가 발생하여 앱 기능을 사용할 수 없는 경우에는 [try … catch](/dotnet/csharp/language-reference/keywords/exception-handling-statements)\(Visual Basic에서 [Try .. Catch](/dotnet/visual-basic/language-reference/statements/try-catch-finally-statement)\) 구문을 사용하여 예외를 캡처하고 앱을 종료하기 전에 상태를 정리할 수 있습니다. 그러나 미리 예상하여 방지할 수 있는 <xref:System.InvalidOperationException>도 있습니다. 수정된 메서드 예제에서는 이러한 몇 가지 기술을 보여 줍니다.  
  
##  <a name="BKMK_A_method_running_on_a_non_UI_thread_updates_the_UI"></a> UI가 아닌 스레드에서 실행되는 메서드가 UI를 업데이트함  
 [UI가 아닌 스레드에서 UI를 업데이트하면 InvalidOperationException이 발생함](#BKMK_Causing_an_InvalidOperationException_with_a_UI_update_from_a_non_UI_thread)  **&#124;**  [UI가 아닌 스레드에서 InvalidOperationExceptions 방지](#BKMK_Avoiding_InvalidOperationExceptions_on_non_UI_threads)  
  
 Windows Forms 및 WPF\(Windows Presentation Foundation\)와 같은 대부분의 .NET GUI\(그래픽 사용자 인터페이스\) 앱 프레임워크에서는 UI를 만들고 관리하는 스레드\(**주** 스레드 또는 **UI** 스레드\)에서만 GUI 개체에 액세스할 수 있습니다. UI 스레드가 아닌 스레드에서 UI 요소에 액세스하려고 하면 <xref:System.InvalidOperationException>이 throw됩니다.  
  
###  <a name="BKMK_Causing_an_InvalidOperationException_with_a_UI_update_from_a_non_UI_thread"></a> UI가 아닌 스레드에서 UI를 업데이트하면 InvalidOperationException이 발생함  
  
> [!NOTE]
>  다음 예제에서는 [Task\-based Asynchronous Pattern \(TAP\)](../Topic/Task-based%20Asynchronous%20Pattern%20\(TAP\).md)를 사용하여 UI가 아닌 스레드를 만듭니다. 그러나 이 예제는 모든 .NET [Asynchronous Programming Patterns](../Topic/Asynchronous%20Programming%20Patterns.md)과도 관련됩니다.  
  
 이러한 예제에서 `ThreadsExampleBtn_Click` 이벤트 처리기는 `DoSomeWork` 메서드를 두 번 호출합니다. 첫 번째 메서드 호출\(`DoSomeWork(20);`\)은 동기식으로 정상 실행됩니다. 하지만 두 번째 호출\(`Task.Run( () => { DoSomeWork(1000);});`\)은 앱의 [스레드 풀](http://msdn.microsoft.com/en-us/library/system.threading.threadpool.aspx)에 포함된 스레드에 대해 실행됩니다. 이 호출에서는 UI가 아닌 스레드에서 UI 업데이트를 시도하므로 문에서 <xref:System.InvalidOperationException>이 throw됩니다.  
  
 **WPF 및 스토어 앱**  
  
> [!NOTE]
>  Windows Phone 스토어 앱에서는 보다 구체적인 <xref:System.Exception>이 아닌 <xref:System.InvalidOperationException>이 throw됩니다.  
  
 **예외 메시지:**  
  
|||  
|-|-|  
|WPF 앱|추가 정보: 다른 스레드가 이 개체를 소유하고 있어 호출한 스레드가 해당 개체에 액세스할 수 없습니다.|  
|스토어 앱|추가 정보: 응용 프로그램이 다른 스레드를 위해 배열된 인터페이스를 호출했습니다. \(예외가 발생한 HRESULT: 0x8001010E\(RPC\_E\_WRONG\_THREAD\)\)|  
  
```c#  
private async void ThreadsExampleBtn_Click(object sender, RoutedEventArgs e) { TextBox1.Text = String.Empty; TextBox1.Text = "Simulating work on UI thread.\n"; DoSomeWork(20); TextBox1.Text += "Simulating work on non-UI thread.\n"; await Task.Run(() => DoSomeWork(1000)); TextBox1.Text += "ThreadsExampleBtn_Click completes. "; } private void DoSomeWork(int msOfWork) { // simulate work var endTime = DateTime.Now.AddMilliseconds(msOfWork); while (DateTime.Now < endTime) { // spin }; // report completion var msg = String.Format("Some work completed in {0} ms on UI thread. \n", msOfWork); TextBox1.Text += msg; }  
```  
  
 **Windows Forms 앱**  
  
 **예외 메시지:**  
  
-   추가 정보: 크로스 스레드 작업이 잘못되었습니다. 'TextBox1' 컨트롤이 자신이 만들어진 스레드가 아닌 스레드에서 액세스되었습니다.  
  
```c#  
private async void ThreadsExampleBtn_Click(object sender, EventArgs e) { TextBox1.Text = String.Empty; var tbLinesList = new List<string>() {"Simulating work on UI thread."}; TextBox1.Lines = tbLinesList.ToArray(); DoSomeWork(20, tbLinesList); tbLinesList.Add("Simulating work on non-UI thread."); TextBox1.Lines = tbLinesList.ToArray(); await Task.Run(() => DoSomeWork(1000, tbLinesList)); tbLinesList.Add("ThreadsExampleBtn_Click completes."); TextBox1.Lines = tbLinesList.ToArray(); } private void DoSomeWork(int msOfWork, List<string> tbLinesList) { // simulate work var endTime = DateTime.Now.AddMilliseconds(msOfWork); while (DateTime.Now < endTime) { }; { // spin }; // report completion var msg = String.Format("Some work completed in {0} ms on UI thread. \n", msOfWork); tbLinesList.Add(msg); TextBox1.Lines = tbLinesList.ToArray(); }  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 내용](#BKMK_In_this_article) ![In this section](../misc/media/pcs_backtotopmid.png "PCS\_BackToTopMid") [UI가 아닌 스레드에서 실행되는 메서드가 UI를 업데이트함](#BKMK_A_method_running_on_a_non_UI_thread_updates_the_UI)  
  
###  <a name="BKMK_Avoiding_InvalidOperationExceptions_on_non_UI_threads"></a> UI가 아닌 스레드에서 InvalidOperationExceptions 방지  
 Windows UI 프레임워크는 UI 요소의 멤버에 대한 호출이 UI 스레드에서 실행되는지를 확인하는 메서드와 UI 스레드에 대한 호출을 예약하는 기타 메서드가 포함된 *디스패처* 패턴을 구현합니다.  
  
 **WPF 앱**  
  
 WPF 앱에서는 <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=fullName> 메서드 중 하나를 사용하여 UI 스레드에 대해 대리자를 실행합니다. 필요한 경우 <xref:System.Windows.Threading.Dispatcher.CheckAccess%2A?displayProperty=fullName> 메서드를 사용하여 UI가 아닌 스레드에서 메서드를 실행 중인지 확인합니다.  
  
```c#  
private void DoSomeWork(int msOfWork) { var endTime = DateTime.Now.AddMilliseconds(msOfWork); while (DateTime.Now < endTime) { // spin }; // report completion var msgFormat = "Some work completed in {0} ms on {1}UI thread.\n"; var msg = String.Empty; if (TextBox1.Dispatcher.CheckAccess()) { msg = String.Format(msgFormat, msOfWork, String.Empty); TextBox1.Text += msg; } else { msg = String.Format(msgFormat, msOfWork, "non-"); Action act = ()=> {TextBox1.Text += msg;}; TextBox1.Dispatcher.Invoke(act); } }  
  
```  
  
 **Windows Forms 앱**  
  
 Windows Form 앱에서는 <xref:System.Windows.Forms.Control.Invoke%2A?displayProperty=fullName> 메서드를 사용하여 UI 스레드를 업데이트하는 대리자를 실행합니다. 필요한 경우 <xref:System.Windows.Forms.Control.InvokeRequired%2A?displayProperty=fullName> 속성을 사용하여 UI가 아닌 스레드에서 메서드를 실행 중인지 확인합니다.  
  
```c#  
private void DoSomeWork(int msOfWork, List<string> tbLinesList) { // simulate work var endTime = DateTime.Now.AddMilliseconds(msOfWork); while (DateTime.Now < endTime) { // spin }; // report completion var msgFormat = "Some work completed in {0} ms on {1}UI thread.\n"; var msg = String.Empty; if (TextBox1.InvokeRequired) { msg = String.Format(msgFormat, msOfWork, "non-"); tbLinesList.Add(msg); Action act = () => TextBox1.Lines = tbLinesList.ToArray(); TextBox1.Invoke( act ); } else { msg = String.Format(msgFormat, msOfWork, String.Empty); tbLinesList.Add(msg); TextBox1.Lines = tbLinesList.ToArray(); } }  
```  
  
 **스토어 앱**  
  
 스토어 앱에서는 <xref:Windows.UI.Core.CoreDispatcher.RunAsync%2A?displayProperty=fullName> 메서드를 사용하여 UI 스레드를 업데이트하는 대리자를 실행합니다. 필요한 경우 <xref:Windows.UI.Core.CoreDispatcher.HasThreadAccess%2A> 속성을 사용하여 UI가 아닌 스레드에서 메서드를 실행 중인지 확인합니다.  
  
```c#  
private void DoSomeWork(int msOfWork) { // simulate work var endTime = DateTime.Now.AddMilliseconds(msOfWork); while (DateTime.Now < endTime) { // spin }; // report completion var msgFormat = "Some work completed in {0} ms on {1}UI thread.\n"; var msg = String.Empty; if (TextBox1.Dispatcher.HasThreadAccess) { msg = String.Format(msgFormat, msOfWork, String.Empty); TextBox1.Text += msg; } else { msg = String.Format(msgFormat, msOfWork, "non-"); TextBox1.Dispatcher.RunAsync(Windows.UI.Core.CoreDispatcherPriority.Normal,()=> {TextBox1.Text += msg;}); } }  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 내용](#BKMK_In_this_article) ![In this section](../misc/media/pcs_backtotopmid.png "PCS\_BackToTopMid") [UI가 아닌 스레드에서 실행되는 메서드가 UI를 업데이트함](#BKMK_A_method_running_on_a_non_UI_thread_updates_the_UI)  
  
##  <a name="BKMK_A_statement_in_a_foreach_For_Each_in_Visual_Basic_block_changes_the_collection_it_is_iterating"></a> foreach\(Visual Basic에서는 For Each\) 블록의 문이 자체적으로 반복하는 컬렉션을 변경함  
 [foreach 사용 시 InvalidOperationException 발생](#BKMK_Causing_an_InvalidOperationException_with_foreach)  **&#124;**  [루프에서 InvalidOperationExceptions 방지](#BKMK_Avoiding_InvalidOperationExceptions_in_loops)  
  
 [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) 문\(Visual Basic에서는 [For Each](/dotnet/visual-basic/language-reference/statements/for-each-next-statement)\)은 <xref:System.Collections.IEnumerable?displayProperty=fullName> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 인터페이스를 구현하는 배열 또는 컬렉션의 각 요소에 대해 포함 문 그룹을 반복합니다.`foreach` 문은 컬렉션을 반복하여 요소를 읽고 수정하는 데 사용되지만 컬렉션에서 항목을 추가하거나 삭제하는 데 사용할 수는 없습니다. foreach 문의 소스 컬렉션에서 항목을 추가하거나 제거하면 <xref:System.InvalidOperationException>이 throw됩니다.  
  
###  <a name="BKMK_Causing_an_InvalidOperationException_with_foreach"></a> foreach 사용 시 InvalidOperationException 발생  
 이 예제에서는 <xref:System.InvalidOperationException> 문이 foreach 블록의 목록을 수정하려고 하면 `numList.Add(5);`이 throw됩니다.  
  
 **예외 메시지:**  
  
-   추가 정보: 컬렉션이 수정되었습니다. 열거 작업이 실행되지 않을 수도 있습니다.  
  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 내용](#BKMK_In_this_article) ![In this section](../misc/media/pcs_backtotopmid.png "PCS\_BackToTopMid") [foreach(Visual Basic에서는 For Each) 블록의 문이 자체적으로 반복하는 컬렉션을 변경함](#BKMK_A_statement_in_a_foreach_For_Each_in_Visual_Basic_block_changes_the_collection_it_is_iterating)  
  
###  <a name="BKMK_Avoiding_InvalidOperationExceptions_in_loops"></a> 루프에서 InvalidOperationExceptions 방지  
  
> [!IMPORTANT]
>  컬렉션을 반복하는 동안 요소를 목록에 추가하거나 목록에서 제거하면 예측하기 어려우며 의도하지 않은 부작용이 발생할 수 있습니다. 가능하면 반복 외부로 작업을 이동해야 합니다.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
 상황에 따라 컬렉션을 반복할 때 요소를 목록에 추가하거나 목록에서 제거해야 하는 경우에는 [for](/dotnet/csharp/language-reference/keywords/for)\(Visual Basic에서는 [For](/dotnet/visual-basic/language-reference/statements/for-next-statement)\) 루프를 사용합니다.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 내용](#BKMK_In_this_article) ![In this section](../misc/media/pcs_backtotopmid.png "PCS\_BackToTopMid") [foreach(Visual Basic에서는 For Each) 블록의 문이 자체적으로 반복하는 컬렉션을 변경함](#BKMK_A_statement_in_a_foreach_For_Each_in_Visual_Basic_block_changes_the_collection_it_is_iterating)  
  
##  <a name="BKMK_A_Nullable_T_that_is_null_is_cast_to_T"></a> null인 null 허용 \<T\>가 T로 캐스팅됨  
 [잘못된 캐스팅으로 인해 InvalidOperationException 발생](#BKMK_Causing_an_InvalidOperationException_with_an_invalid_cast)  **&#124;**  [잘못된 캐스팅에서 InvalidOperationException 방지](#BKMK_Avoiding_InvalidOperationException_from_a_bad_cast)  
  
 <xref:System.Nullable%601>\(Visual Basic에서는 `null`\)인 `Nothing` 구조체를 기본 형식으로 캐스팅하면 <xref:System.InvalidOperationException> 예외가 throw됩니다.  
  
###  <a name="BKMK_Causing_an_InvalidOperationException_with_an_invalid_cast"></a> 잘못된 캐스팅으로 인해 InvalidOperationException 발생  
 이 메서드에서는 Select 메서드가 dbQueryResults의 null 요소를 int로 캐스팅하면 <xref:System.InvalidOperationException>가 throw됩니다.  
  
 **예외 메시지:**  
  
-   추가 정보: Null 허용 개체에는 값이 있어야 합니다.  
  
```c#  
private void MapQueryResults() { var dbQueryResults = new int?[] { 1, 2, null, 4 }; var ormMap = dbQueryResults.Select(nullableInt => (int)nullableInt); //display map list foreach (var num in ormMap) { Console.Write("{0} ", num); } Console.WriteLine(); }  
  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 내용](#BKMK_In_this_article) ![In this section](../misc/media/pcs_backtotopmid.png "PCS\_BackToTopMid") [null인 null 허용 &lt;T&gt;가 T로 캐스팅됨](#BKMK_A_Nullable_T_that_is_null_is_cast_to_T)  
  
###  <a name="BKMK_Avoiding_InvalidOperationException_from_a_bad_cast"></a> 잘못된 캐스팅에서 InvalidOperationException 방지  
 <xref:System.InvalidOperationException>을 방지하려면 다음 방법을 사용합니다.  
  
-   <xref:System.Nullable%601.HasValue%2A?displayProperty=fullName> 속성을 사용하여 null이 아닌 요소만 선택합니다.  
  
-   오버로드된 <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=fullName> 메서드 중 하나를 사용하여 null 항목에 대해 기본값을 제공합니다.  
  
 **Nullable\<T\>.HasValue 예제**  
  
```c#  
private void MapQueryResults() { var dbQueryResults = new int?[] { 1, 2, null, 4 }; var ormMap = dbQueryResults .Where(nulllableInt => nulllableInt.HasValue) .Select(num => (int)num); //display map list foreach (var num in ormMap) { Console.Write("{0} ", num); } Console.WriteLine(); // handle nulls Console.WriteLine("{0} nulls encountered in dbQueryResults", dbQueryResults.Where(nullableInt => !nullableInt.HasValue).Count()); }  
```  
  
 **Nullable\<T\>.GetValueOrDefault 예제**  
  
 이 예제에서는 <xref:System.Nullable%601.GetValueOrDefault%28%600%29>를 사용하여 `dbQueryResults`에서 반환하는 예상 값 외부의 기본값을 지정합니다.  
  
```c#  
private void MapQueryResults() { var dbQueryResults = new int?[] { 1, 2, null, 4 }; var nullFlag = int.MinValue; var ormMap = dbQueryResults.Select(nullableInt => nullableInt.GetValueOrDefault(nullFlag)); // handle nulls Console.WriteLine("'{0}' indicates a null database value.", nullFlag); foreach (var num in ormMap) { Console.Write("{0} ", num); } Console.WriteLine(); }  
  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 내용](#BKMK_In_this_article) ![In this section](../misc/media/pcs_backtotopmid.png "PCS\_BackToTopMid") [null인 null 허용 &lt;T&gt;가 T로 캐스팅됨](#BKMK_A_Nullable_T_that_is_null_is_cast_to_T)  
  
##  <a name="BKMK_A_System_Linq_Enumerable_method_is_called_on_an_empty_collection"></a> 빈 컬렉션에 대해 System.Linq.Enumerable 메서드가 호출됨  
 <xref:System.Linq.Enumerable> 메서드 <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Last%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.First%2A>, <xref:System.Linq.Enumerable.Single%2A> 및 <xref:System.Linq.Enumerable.SingleOrDefault%2A>는 시퀀스에 대해 작업을 수행하여 단일 결과를 반환합니다.  
  
 그런데 시퀀스가 비어 있으면 이러한 메서드의 일부 오버로드가 <xref:System.InvalidOperationException> 예외를 throw합니다. `null`\(Visual Basic에서는 `Nothing`\)을 반환하는 오버로드도 있습니다. 또한 <xref:System.Linq.Enumerable.SingleOrDefault%2A>는 시퀀스에 둘 이상의 요소가 포함되어 있으면 <xref:System.InvalidOperationException>을 throw합니다.  
  
> [!TIP]
>  이 섹션에서 설명하는 대부분의 <xref:System.Linq.Enumerable> 메서드는 오버로드됩니다. 선택하는 오버로드의 동작을 명확하게 파악해야 합니다.  
  
 **예외 메시지:**  
  
 [Aggregate, Average, Last, Max, Min 메서드](#BKMK_Aggregate_Average_Last_Max_and_Min_methods)  **&#124;**  [First 및 FirstOrDefault 메서드](#BKMK_First_and_FirstOrDefault_methods)  **&#124;**  [Single 및 SingleOrDefault 메서드](#BKMK_Single_and_SingleOrDefault_methods)  
  
###  <a name="BKMK_Aggregate_Average_Last_Max_and_Min_methods"></a> Aggregate, Average, Last, Max, Min 메서드  
  
-   추가 정보: 시퀀스에 요소가 없습니다.  
  
 **Average로 인해 InvalidOperationException 발생**  
  
 이 예제에서 다음 메서드가 <xref:System.InvalidOperationException> 메서드를 호출하면 <xref:System.Linq.Enumerable.Average%2A>이 throw됩니다. Linq 식이 4보다 큰 요소를 포함하지 않는 시퀀스를 반환하기 때문입니다.  
  
```c#  
private void FindAverageOfNumbersGreaterThan4() { var dbQueryResults = new[] { 1, 2, 3, 4 }; var avg = dbQueryResults.Where(num => num > 4).Average(); Console.WriteLine("The average value numbers greater than 4 in the returned records is {0}", avg); }  
```  
  
 빈 시퀀스를 확인하지 않고 이러한 메서드 중 하나를 사용할 때는 해당 시퀀스가 비어 있지 않으며 빈 시퀀스는 원치 않는 항목임을 암시적으로 가정하게 됩니다. 시퀀스가 비어 있지 않다고 가정할 때는 예외가 catch 또는 throw되는 것이 정상입니다.  
  
 **빈 시퀀스로 인해 발생하는 InvalidOperationException 방지**  
  
 <xref:System.Linq.Enumerable.Any%2A?displayProperty=fullName> 메서드 중 하나를 사용하여 시퀀스가 비어 있는지 확인합니다.  
  
> [!TIP]
>  평균을 구할 시퀀스에 요소가 많이 포함되어 있거나 시퀀스를 생성하는 작업의 부담이 큰 경우 <xref:System.Linq.Enumerable.Any%2A>를 사용하면 확인 성능을 개선할 수 있습니다.  
  
```c#  
private void FindAverageOfNumbersGreaterThan4() { var dbQueryResults = new[] { 1, 2, 3, 4 }; var moreThan4 = dbQueryResults.Where(num => num > 4); if(moreThan4.Any()) { var msgFormat = "The average value numbers greater than 4 in the returned records is {0}"; Console.WriteLine(msgFormat, moreThan4.Average()); } else { // handle empty collection Console.WriteLine("There are no values greater than 4 in the ecords."); } }  
  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 내용](#BKMK_In_this_article) ![In this section](../misc/media/pcs_backtotopmid.png "PCS\_BackToTopMid") [빈 컬렉션에 대해 System.Linq.Enumerable 메서드가 호출됨](#BKMK_A_System_Linq_Enumerable_method_is_called_on_an_empty_collection)  
  
###  <a name="BKMK_First_and_FirstOrDefault_methods"></a> First 및 FirstOrDefault 메서드  
 <xref:System.Linq.Enumerable.First%2A>는 시퀀스의 첫 번째 항목을 반환하거나, 시퀀스가 비어 있으면 <xref:System.InvalidOperationException>을 throw합니다.<xref:System.Linq.Enumerable.FirstOrDefault%2A> 대신 <xref:System.Linq.Enumerable.First%2A> 메서드를 호출하면 예외를 throw하지 않고 지정된 값이나 기본값을 반환할 수 있습니다.  
  
> [!NOTE]
>  .NET Framework에서는 형식에 기본값의 개념을 사용합니다. 예를 들어 참조 형식의 기본값은 null이고 정수 형식의 기본값은 0입니다.[기본값 표](/dotnet/csharp/language-reference/keywords/default-values-table)을 참조하세요.  
  
 **First로 인해 InvalidOperationException 발생**  
  
 <xref:System.Linq.Enumerable.First%2A>는 지정된 조건을 충족하는 시퀀스의 첫 번째 요소를 반환하는 최적화 메서드입니다. 조건을 충족하는 요소가 없으면 메서드는 <xref:System.InvalidOperationException> 예외를 throw합니다.  
  
 이 예제에서는 `First`에 4보다 큰 요소가 없으므로 `dbQueryResults` 메서드가 예외를 throw합니다.  
  
 **예외 메시지:**  
  
-   추가 정보: 시퀀스에 일치하는 요소가 없습니다.  
  
```c#  
private void FindANumbersGreaterThan4() { var dbQueryResults = new[] { 1, 2, 3, 4 }; var firstNum = dbQueryResults.First(n=> n > 4); var msgFormat = "{0} is an element of dbQueryResults that is greater than 4"; Console.WriteLine(msgFormat, firstNum); }  
  
```  
  
 **FirstOrDefault를 사용하여 예외 방지**  
  
 <xref:System.Linq.Enumerable.FirstOrDefault%2A> 대신 <xref:System.Linq.Enumerable.First%2A> 메서드 중 하나를 사용하여 `firstNum` 시퀀스에 요소가 하나 이상 포함되어 있는지를 확인할 수 있습니다. 쿼리는 조건을 충족하는 요소를 찾지 못하면 지정된 값이나 기본값을 반환합니다. 반환된 값을 확인하여 요소가 발견되었는지를 파악할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Linq.Enumerable.FirstOrDefault%2A> 사용 시 형식의 기본값이 시퀀스의 유효한 요소이면 구현이 다소 복잡해질 수 있습니다.  
  
```c#  
private void FindANumbersGreaterThan4() { var dbQueryResults = new[] { 1, 2, 3, 4 }; // default(object) == null var firstNum = dbQueryResults.FirstOrDefault(n => n > 4); if (firstNum != 0) { var msgFormat = "{0} is an element of dbQueryResults that is greater than 4"; Console.WriteLine(msgFormat, firstNum); } else { // handle default case Console.WriteLine("No element of dbQueryResults is greater than 4."); } }  
  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 내용](#BKMK_In_this_article) ![In this section](../misc/media/pcs_backtotopmid.png "PCS\_BackToTopMid") [빈 컬렉션에 대해 System.Linq.Enumerable 메서드가 호출됨](#BKMK_A_System_Linq_Enumerable_method_is_called_on_an_empty_collection)  
  
###  <a name="BKMK_Single_and_SingleOrDefault_methods"></a> Single 및 SingleOrDefault 메서드  
 <xref:System.Linq.Enumerable.Single%2A?displayProperty=fullName> 메서드는 시퀀스의 유일한 요소 또는 지정한 테스트를 충족하는 시퀀스의 유일한 요소를 반환합니다.  
  
 시퀀스에 요소가 없거나 둘 이상 있으면 메서드는 <xref:System.InvalidOperationException> 예외를 throw합니다.  
  
 <xref:System.Linq.Enumerable.SingleOrDefault%2A>를 사용하면 시퀀스에 요소가 없을 때 예외를 throw하는 대신 지정한 값이나 기본값을 반환할 수 있습니다. 그러나 시퀀스에 선택 조건자와 일치하는 요소가 둘 이상 포함되어 있으면 <xref:System.Linq.Enumerable.SingleOrDefault%2A>는 계속 <xref:System.InvalidOperationException>을 throw합니다.  
  
> [!NOTE]
>  .NET Framework에서는 형식에 기본값의 개념을 사용합니다. 예를 들어 참조 형식의 기본값은 null이고 정수 형식의 기본값은 0입니다.[기본값 표](/dotnet/csharp/language-reference/keywords/default-values-table)을 참조하세요.  
  
 **Single로 인해 InvalidOperationExceptions 발생**  
  
 이 예제에서는 `singleObject`에 4보다 큰 요소가 없으므로 <xref:System.InvalidOperationException>에서 `dbQueryResults`을 throw합니다.  
  
 **예외 메시지:**  
  
-   추가 정보: 시퀀스에 일치하는 요소가 없습니다.  
  
```c#  
private void FindTheOnlyNumberGreaterThan4() { var dbQueryResults = new[] { (object)1, (object)2, (object)3, (object)4 }; var singleObject = dbQueryResults.Single(obj => (int)obj > 4); // display results var msgFormat = "{0} is the only element of dbQueryResults that is greater than 4"; Console.WriteLine(msgFormat, singleObject); }  
  
```  
  
 **Single 또는 SingleOrDefault로 인해 InvalidOperationExceptions 발생**  
  
 이 예제에서는 `singleObject`에 2보다 큰 요소가 둘 이상 포함되어 있으므로 <xref:System.InvalidOperationException>에서 `dbQueryResults`을 throw합니다.  
  
 **예외 메시지:**  
  
-   추가 정보: 시퀀스에 둘 이상의 일치하는 요소가 있습니다.  
  
```c#  
private void FindTheOnlyNumberGreaterThan2() { var dbQueryResults = new[] { (object)1, (object)2, (object)3, (object)4 }; var singleObject = dbQueryResults.SingleOrDefault(obj => (int)obj > 2); if (singleObject != null) { var msgFormat = "{0} is the only element of dbQueryResults that is greater than 2"; Console.WriteLine(msgFormat, singleObject); } else { // handle empty collection Console.WriteLine("No element of dbQueryResults is greater than 2."); } }  
  
```  
  
 **Single을 통해 InvalidOperationExceptions 방지**  
  
 <xref:System.Linq.Enumerable.Single%2A> 및 <xref:System.Linq.Enumerable.SingleOrDefault%2A>를 사용하는 경우에는 사용 의도도 표시할 수 있습니다.<xref:System.Linq.Enumerable.Single%2A>은 조건에서 결과를 하나만 반환할 것임을 명확하게 나타냅니다.<xref:System.Linq.Enumerable.SingleOrDefault%2A>는 결과를 반환하지 않거나 하나만 반환하도록 선언합니다. 이러한 조건이 유효하지 않을 때는 <xref:System.InvalidOperationException>이 throw되거나 catch되는 것이 정상입니다. 그러나 무효 상황이 일정 빈도로 발생할 것으로 예상되는 경우에는 <xref:System.Linq.Enumerable>, <xref:System.Linq.Enumerable.First%2A> 등의 다른 <xref:System.Linq.Enumerable.Where%2A> 메서드를 사용하여 결과를 생성해야 합니다.  
  
 개발 중에는 <xref:System.Diagnostics.Debug.Assert%2A> 메서드 중 하나를 사용하여 가정 내용을 확인할 수 있습니다. 이 예제에서는 강조 표시된 코드로 인해 디버거가 중단되며 개발 중에 어설션 대화 상자가 표시됩니다. 릴리스 코드에서는 어셜션이 제거되며 결과가 잘못된 경우 <xref:System.Linq.Enumerable.Single%2A>이 throw됩니다.  
  
> [!NOTE]
>  <xref:System.Linq.Enumerable.Take%2A>을 사용하고 해당 `count` 매개 변수를 2로 설정하면 반환되는 시퀀스가 최대 2개 요소로 제한됩니다. 이 시퀀스는 확인해야 하는 모든 사례\(요소 0개, 1개, 2개 이상\)가 포함되며, 시퀀스에 요소가 많이 포함되어 있거나 시퀀스를 생성하는 작업의 부담이 큰 경우 확인 성능을 개선할 수 있습니다.  
  
```c#  
private void FindTheOnlyNumberGreaterThan4() { var dbQueryResults = new[] { (object)1, (object)2, (object)3, (object)4 }; var moreThan4 = dbQueryResults.Where(obj => (int)obj > 4).Take(2); System.Diagnostics.Debug.Assert(moreThan4.Count() == 1,String.Format("moreThan4.Count() == 1; Actual count: {0}", moreThan4.Count())); // do not handle exceptions in release code Console.WriteLine("{0} is the only element of dbQueryResults that is greater than 4", moreThan4.Single()); }  
  
```  
  
 예외는 방지하되 릴리스 코드에서 무효 상태를 계속 처리하려는 경우에는 위에서 설명한 기술을 수정할 수 있습니다. 아래 예제의 switch 문에서는 메서드가 `moreThan2`에서 반환하는 요소 수에 응답합니다.  
  
```c#  
private void FindTheOnlyNumberGreaterThan2() { var dbQueryResults = new[] { (object)1, (object)2, (object)3, (object)4 }; var moreThan2 = dbQueryResults.TakeWhile(obj => (int)obj > 2).Take(2); switch(moreThan2.Count()) { case 1: // success var msgFormat = "{0} is the only element of dbQueryResults that is greater than 2"; Console.WriteLine(msgFormat, moreThan2.Single()); break; case 0: // handle empty collection Console.WriteLine("No element of the dbQueryResults are greater than 4."); break; default: // count > 1 // handle more than one element Console.WriteLine("More than one element of dbQueryResults is greater than 4"); break; } }  
  
```  
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 내용](#BKMK_In_this_article) ![In this section](../misc/media/pcs_backtotopmid.png "PCS\_BackToTopMid") [빈 컬렉션에 대해 System.Linq.Enumerable 메서드가 호출됨](#BKMK_A_System_Linq_Enumerable_method_is_called_on_an_empty_collection)  
  
##  <a name="BKMK_Related_articles"></a> 관련 문서  
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
  
 ![맨 위로 이동](~/debugger/media/pcs_backtotop.png "PCS\_BackToTop") [이 문서의 내용](#BKMK_In_this_article)