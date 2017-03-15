---
title: "연습: Async 메서드에 디버거 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "async 기능, 디버거 사용"
  - "await 연산자, 디버거 사용"
  - "한 단계씩 코드 실행 명령, await 연산자에서"
  - "프로시저 나가기 명령, async 메서드 내부"
  - "프로시저 단위 실행 명령, await 연산자에서"
ms.assetid: 5adb2531-3f09-4b7e-8baa-29de80abee6e
caps.latest.revision: 23
caps.handback.revision: 23
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
---
# 연습: Async 메서드에 디버거 사용
비동기 기능을 사용하면 콜백을 사용하거나 여러 메서드 또는 람다 식에 코드를 분할하지 않고도 비동기 메서드를 호출할 수 있습니다.  동기 코드를 비동기로 만들려면 동기 메서드 대신 비동기 메서드를 호출하고 몇 가지 키워드를 코드에 추가해야 합니다.  자세한 내용은 [Async 및 Await를 사용한 비동기 프로그래밍](../Topic/Asynchronous%20Programming%20with%20Async%20and%20Await%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
 Visual Studio 디버거에서 `Async` 기능과 함께 **한 단계씩 코드 실행**, **프로시저 단위 실행** 및 **프로시저 나가기** 명령을 사용할 수 있습니다.  또한 특히 await 연산자가 포함된 문에서 제어 흐름을 보기 위해 중단점을 계속 사용할 수 있습니다.  이 연습에서 완료하는 작업은 다음과 같으며, 이러한 작업은 순서에 관계없이 실행할 수 있습니다.  
  
-   중단점을 사용하여 await 문에서 제어 흐름을 보여 줍니다.  
  
-   await 연산자가 포함된 문에서 **한 단계씩 코드 실행** 및 **프로시저 단위 실행** 명령의 동작을 이해합니다.  
  
-   비동기 메서드 내에서 사용할 때 **프로시저 나가기** 명령의 동작을 이해합니다.  
  
## 제어 흐름을 표시하기 위한 중단점  
 [Async](/dotnet/visual-basic/language-reference/modifiers/async)\(Visual Basic\) 또는 [async](/dotnet/csharp/language-reference/keywords/async)\(C\#\) 한정자로 메서드를 표시하는 경우 [Await](/dotnet/visual-basic/language-reference/modifiers/async)\(Visual Basic\) 또는 [await](/dotnet/csharp/language-reference/keywords/await)\(C\#\) 연산자를 메서드에서 사용할 수 있습니다.  await 식을 만들려면 await 연산자를 작업과 연결해야 합니다.  await 식이 작업에 대해 호출되면 현재 메서드가 즉시 종료되고 다른 작업을 반환합니다.  await 연산자와 연결된 작업이 완료되면 동일한 메서드에서 실행이 다시 시작됩니다.  자세한 내용은 [비동기 프로그램의 제어 흐름](../Topic/Control%20Flow%20in%20Async%20Programs%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
> [!NOTE]
>  비동기 메서드는 아직 완료되지 않은 첫 번째 대기된 개체를 검색할 때나 비동기 메서드의 끝에 도달할 때 중에서 먼저 발생하는 시점에 호출자에게 반환됩니다.  
  
> [!NOTE]
>  다음 예제의 콘솔 응용 프로그램은 <xref:System.Threading.Tasks.Task.Wait%2A> 메서드를 사용하여 응용 프로그램이 `Main`에서 종료되는 것을 방지합니다.  교착 상태 상황이 발생할 수 있으므로 콘솔 응용 프로그램 외부에서 <xref:System.Threading.Tasks.Task.Wait%2A> 메서드를 사용하면 안 됩니다.  
  
 다음 절차에서는 중단점을 설정하여 응용 프로그램이 await 문에 도달할 때 발생하는 상황을 보여 줍니다.  `Debug.WriteLine` 문을 추가하여 제어 흐름을 보여 줄 수도 있습니다.  
  
1.  콘솔 응용 프로그램을 만든 후 다음 코드를 붙여 넣습니다.  
  
     [!code-cs[csAsyncDebugging#1](../misc/codesnippet/CSharp/walkthrough-using-the-debugger-with-async-methods_1.cs)]
     [!code-vb[csAsyncDebugging#1](../misc/codesnippet/VisualBasic/walkthrough-using-the-debugger-with-async-methods_1.vb)]  
  
2.  "set breakpoint" 주석으로 끝나는 세 줄에서 디버깅 중단점을 설정합니다.  
  
3.  F5 키를 선택하거나 메뉴 모음에서 **디버그**, **디버깅 시작**을 선택하여 응용 프로그램을 실행합니다.  
  
     응용 프로그램이 `ProcessAsync` 메서드에 진입하고 await 연산자가 포함된 줄에서 중단됩니다.  
  
4.  F5 키를 다시 선택합니다.  
  
     응용 프로그램이 await 연산자가 포함된 문에서 중지되었기 때문에 응용 프로그램은 즉시 비동기 메서드를 종료하고 작업을 반환합니다.  따라서 응용 프로그램은 `ProcessAsync` 메서드를 종료하고 호출하는 메서드\(`Main`\)의 중단점에서 중단됩니다.  
  
5.  F5 키를 다시 선택합니다.  
  
     `DoSomethingAsync` 메서드가 완료되면 호출하는 메서드의 await 문 뒤에서 코드가 다시 시작됩니다.  따라서 응용 프로그램이 `ProcessAsync` 메서드의 중단점에서 중단됩니다.  
  
     `DoSomethingAsync`가 처음에 대기되었을 때 `ProcessAsync` 메서드는 종료되고 작업을 반환했습니다.  그런 다음 대기된 `DoSomethingAsync` 메서드가 완료되었을 때 await 문의 평가를 통해 `DoSomethingAsync`의 반환 값이 생성되었습니다.  `DoSomethingAsync` 메서드는 Visual Basic에서 `Task (Of Integer)`를 반환하거나 C\#에서 `Task<int>`를 반환하도록 정의되므로 return 문의 값은 정수입니다.  자세한 내용은 [비동기 반환 형식](../Topic/Async%20Return%20Types%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
### 작업을 가져온 다음 대기  
 `ProcessAsync` 메서드에서 `Dim result = Await DoSomethingAsync()`\(Visual Basic\) 또는 `var result = await DoSomethingAsync();`\(C\#\) 문은 다음 두 문이 축약된 것입니다.  
  
 [!code-cs[csAsyncDebugging#2](../misc/codesnippet/CSharp/walkthrough-using-the-debugger-with-async-methods_2.cs)]
 [!code-vb[csAsyncDebugging#2](../misc/codesnippet/VisualBasic/walkthrough-using-the-debugger-with-async-methods_2.vb)]  
  
 코드의 첫 번째 줄은 비동기 메서드를 호출하고 작업을 반환합니다.  이 작업은 코드의 다음 줄에서 await 연산자와 연결됩니다.  await 문은 메서드\(`ProcessAsync`\)를 종료하고 다른 작업을 반환합니다.  await 연산자와 연결된 작업이 완료되면 메서드\(`ProcessAsync`\)의 await 문 뒤에서 코드가 다시 시작됩니다.  
  
 await 문이 즉시 다른 작업을 반환하는 경우 해당 작업은 await 연산자가 포함된 비동기 메서드\(`ProcessAsync`\)의 반환된 인수입니다.  await에서 반환하는 작업에는 동일한 메서드의 await 뒤에 발생하는 코드 실행이 포함되어 있으며, 이 때문에 해당 작업은 await와 연결된 작업과 다릅니다.  
  
## 한 단계씩 코드 실행 및 프로시저 단위 실행  
 **한 단계씩 코드 실행** 명령은 메서드를 한 단계씩 실행하지만 **프로시저 단위 실행** 명령은 메서드 호출을 실행한 다음 호출하는 메서드의 다음 줄에서 중단됩니다.  자세한 내용은 [한 단계씩 코드 실행, 프로시저 단위 실행 또는 프로시저 나가기](../debugger/navigating-through-code-with-the-debugger.md#BKMK_Step_into__over__or_out_of_the_code)를 참조하십시오.  
  
 다음 절차에서는 await 문에서 **한 단계씩 코드 실행** 또는 **프로시저 단위 실행** 명령을 선택할 때 발생하는 상황을 보여 줍니다.  
  
1.  콘솔 응용 프로그램의 코드를 다음 코드로 바꿉니다.  
  
     [!code-cs[csAsyncDebugging#3](../misc/codesnippet/CSharp/walkthrough-using-the-debugger-with-async-methods_3.cs)]
     [!code-vb[csAsyncDebugging#3](../misc/codesnippet/VisualBasic/walkthrough-using-the-debugger-with-async-methods_3.vb)]  
  
2.  F11 키를 선택하거나 메뉴 모음에서 **디버그**, **한 단계씩 코드 실행**을 선택하여 await 연산자가 포함된 문에서 `Step Into` 명령을 보여주기 시작합니다.  
  
     응용 프로그램이 시작되고 첫 번째 줄에서 중단됩니다. 첫 번째 줄은 Visual Basic에서 `Sub Main()`이고, C\#에서 `Main` 메서드의 여는 중괄호입니다.  
  
3.  F11 키를 세 번 더 선택합니다.  
  
     응용 프로그램이 이제 `ProcessAsync` 메서드의 await 문에 있습니다.  
  
4.  F11 키를 선택합니다.  
  
     응용 프로그램이 `DoSomethingAsync` 메서드에 진입하고 첫 번째 줄에서 중단됩니다.  이 동작은 `await` 문에서 응용 프로그램이 즉시 호출하는 메서드\(`Main`\)로 반환되는 경우에도 발생합니다.  
  
5.  응용 프로그램이 `ProcessAsync` 메서드의 await 문으로 반환될 때까지 F11 키를 계속 선택합니다.  
  
6.  F11 키를 선택합니다.  
  
     await 문 다음에 오는 줄에서 응용 프로그램이 중단됩니다.  
  
7.  메뉴 모음에서 **디버그**, **디버깅 중지**를 선택하여 응용 프로그램의 실행을 중지합니다.  
  
     다음 단계에서는 await 문에서 **프로시저 단위 실행** 명령을 보여 줍니다.  
  
8.  F11 키를 4번 선택하거나 메뉴 모음에서 **디버그**, **한 단계씩 코드 실행**을 4번 선택합니다.  
  
     응용 프로그램이 이제 `ProcessAsync` 메서드의 await 문에 있습니다.  
  
9. F10 키를 선택하거나 메뉴 모음에서 **디버그**, **프로시저 단위 실행**을 선택합니다.  
  
     await 문 다음에 오는 줄에서 실행이 중단됩니다.  이 동작은 응용 프로그램이 await 문에서 호출하는 메서드\(`Main`\)로 즉시 반환되는 경우에도 발생합니다.  `Step Over` 명령은 `DoSomethingAsync` 메서드의 실행도 예상대로 프로시저 단위로 실행합니다.  
  
10. 메뉴 모음에서 **디버그**, **디버깅 중지**를 선택하여 응용 프로그램의 실행을 중지합니다.  
  
     다음 단계에서 보여주듯이 **한 단계씩 코드 실행** 및 **프로시저 단위 실행** 명령의 동작은 await 연산자가 비동기 메서드 호출과 다른 줄에 있는 경우 약간 다릅니다.  
  
11. `ProcessAsync` 메서드에서 await 문을 다음 코드로 바꿉니다.  원래 await 문은 다음 두 문이 축약된 것입니다.  
  
     [!code-cs[csAsyncDebugging#2](../misc/codesnippet/CSharp/walkthrough-using-the-debugger-with-async-methods_2.cs)]
     [!code-vb[csAsyncDebugging#2](../misc/codesnippet/VisualBasic/walkthrough-using-the-debugger-with-async-methods_2.vb)]  
  
12. F11 키를 선택하거나 메뉴 모음에서 **디버그**, **한 단계씩 코드 실행**을 여러 번 선택하여 실행을 시작하고 코드를 단계별로 실행합니다.  
  
     `DoSomethingAsync` 호출에서 **한 단계씩 코드 실행** 명령은 `DoSomethingAsync` 메서드에서 중단되지만 **프로시저 단위 실행** 명령은 예상대로 다음 문으로 이동합니다.  await 문에서 두 명령은 await 뒤에 오는 문에서 중단됩니다.  
  
## 프로시저 나가기  
 비동기가 아닌 메서드에서 **프로시저 나가기** 명령은 메서드 호출 다음에 오는 코드의 호출하는 메서드에서 중단됩니다.  비동기 메서드의 경우 호출하는 메서드에서 실행이 중단되는 논리가 보다 복잡하며, 해당 논리는 **프로시저 나가기** 명령이 비동기 메서드의 첫 번째 줄에 있는지 여부에 따라 달라집니다.  
  
1.  콘솔 응용 프로그램의 코드를 다음 코드로 바꿉니다.  
  
     [!code-cs[csAsyncDebugging#4](../misc/codesnippet/CSharp/walkthrough-using-the-debugger-with-async-methods_4.cs)]
     [!code-vb[csAsyncDebugging#4](../misc/codesnippet/VisualBasic/walkthrough-using-the-debugger-with-async-methods_4.vb)]  
  
2.  `DoSomethingAsync` 메서드의 `Debug.WriteLine("before")` 줄에 중단점을 설정합니다.  
  
     이는 첫 번째 줄이 아닌 비동기 메서드의 줄에서 **프로시저 나가기** 명령의 동작을 보여주기 위한 것입니다.  
  
3.  F5 키를 선택하거나 메뉴 모음에서 **디버그**, **디버깅 시작**을 선택하여 응용 프로그램을 시작합니다.  
  
     `DoSomethingAsync` 메서드의 `Debug.WriteLine("before")`에서 코드가 중단됩니다.  
  
4.  Shift\+F11 키를 선택하거나 메뉴 모음에서 **디버그**, **프로시저 나가기**를 선택합니다.  
  
     호출하는 메서드에서 현재 메서드와 연결된 작업에 대한 await 문에서 응용 프로그램이 중단됩니다.  따라서 응용 프로그램이 `ProcessAsync` 메서드의 await 문에서 중단됩니다.  응용 프로그램은 `DoSomethingAsync` 메서드 호출 뒤에 오는 코드인 `Dim z = 0`\(Visual Basic\) 또는 `int z = 0;`\(C\#\)에서 중단되지 않습니다.  
  
5.  메뉴 모음에서 **디버그**, **디버깅 중지**를 선택하여 응용 프로그램의 실행을 중지합니다.  
  
     다음 단계에서는 비동기 메서드의 첫 번째 줄에서 **프로시저 나가기**를 실행할 때 발생하는 상황을 보여 줍니다.  
  
6.  기존 중단점을 제거하고 `DoSomethingAsync` 메서드의 첫 번째 줄에 중단점을 추가합니다.  
  
     C\#에서는 `DoSomethingAsync` 메서드의 여는 중괄호에 중단점을 추가하고,  Visual Basic에서는 `Async Function DoSomethingAsync() As Task(Of Integer)`가 포함된 줄에 중단점을 추가합니다.  
  
7.  F5 키를 선택하여 응용 프로그램을 시작합니다.  
  
     `DoSomethingAsync` 메서드의 첫 번째 줄에서 코드가 중단됩니다.  
  
8.  메뉴 모음에서 **디버그**, **창**, **출력**을 선택합니다.  
  
     **출력** 창이 열립니다.  
  
9. Shift\+F11 키를 선택하거나 메뉴 모음에서 **디버그**, **프로시저 나가기**를 선택합니다.  
  
     비동기 메서드가 첫 번째 await에 도달할 때까지 응용 프로그램이 다시 시작되었다가 호출하는 문에서 중단됩니다.  따라서 응용 프로그램이 `Dim the Task = DoSomethingAsync()`\(Visual Basic\) 또는 `var theTask = DoSomethingAsync();`\(C\#\)에서 중단됩니다.  "before" 메시지가 출력 창에 표시되지만 "after" 메시지는 아직 표시되지 않습니다.  
  
10. F5 키를 선택하여 응용 프로그램을 계속 실행합니다.  
  
     응용 프로그램이 호출된 비동기 함수\(`DoSomethingAsync`\)의 await 문 뒤에 오는 문에서 계속 실행됩니다.  "after" 메시지가 출력 창에 나타납니다.  
  
## 참고 항목  
 [디버거로 코드 탐색](../debugger/navigating-through-code-with-the-debugger.md)