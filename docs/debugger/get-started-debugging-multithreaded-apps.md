---
title: 다중 스레드 응용 프로그램 디버깅을 시작 하려면 | Microsoft Docs
ms.custom: H1HackMay2017
ms.date: 06/02/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- multithreaded debugging, tutorial
- tutorials, multithreaded debugging
ms.assetid: 62df746b-b0f6-4df4-83cf-b1d9d2e72833
caps.latest.revision: 38
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 48e912fdd04e25f9ad8f7babcf565afb5b739f05
ms.sourcegitcommit: 064f8678f4a918e1dce60285090a9803d37dc34b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/30/2018
---
# <a name="get-started-debugging-a-multithreaded-application-in-visual-studio"></a>Visual Studio에서 다중 스레드 응용 프로그램 디버깅을 시작.
Visual Studio는 여러 가지 도구와 다중 스레드 응용 프로그램을 디버그할 수 있도록 사용자 인터페이스 요소를 제공 합니다. 스레드 마커를 사용 하는 방법을 보여 주는이 자습서는 **병렬 스택** 창 고 **병렬 조사식** 창과 조건부 중단점, 중단점 필터입니다. 이 자습서에서는 몇 분 정도 걸리지만 완료에 익숙해질 수 다중 스레드 응용 프로그램 디버깅을 위한 기능입니다.

|         |         |
|---------|---------|
|  ![비디오에 대한 비디오 카메라 아이콘](../install/media/video-icon.png "비디오 보기")  |    [비디오 보기](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugging-Multi-threaded-Apps-in-Visual-Studio-2017-MoZPKMD6D_111787171) 유사한 단계를 보여 주는 다중 스레드 디버깅 합니다. |

다른 항목에 다른 다중 스레드 디버깅 도구를 사용 하 여 추가 정보를 제공 합니다.

- 사용 하는 방법을 보여 주는 유사한 항목에 대 한는 **디버그 위치** 도구 모음 및 **스레드** 창 참조 [연습: 다중 스레드 응용 프로그램을 디버깅](../debugger/how-to-use-the-threads-window.md)합니다.

- 사용 하는 샘플와 비슷한 항목에 대 한 <xref:System.Threading.Tasks.Task> (관리 코드) (c + +) 동시성 런타임 참조 및 [연습: 병렬 응용 프로그램 디버깅](../debugger/walkthrough-debugging-a-parallel-application.md)합니다. 가장 다중 스레드 응용 프로그램 형식에 적용 되 일반 디버깅 팁이 항목과 연결 된 항목을 참조 하세요.
  
이 자습서를 시작 하려면 다중 스레드 응용 프로그램 프로젝트를 해야 합니다. 여기에 나열된 단계에 따라 프로젝트를 만드십시오.  
  
#### <a name="to-create-the-multithreaded-app-project"></a>다중 스레드 응용 프로그램 프로젝트를 만들려면  
  
1.  에 **파일** 메뉴 선택 **새로** 클릭 하 고 **프로젝트**합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  에 **프로젝트 형식**s 상자에서 원하는 언어 클릭: **Visual C#**, **Visual c + +**, 또는 **Visual Basic**합니다.  
  
3.  에 **템플릿** 상자 **콘솔 응용 프로그램**합니다.  
  
4.  에 **이름** 상자에 mythreadwalkthroughapp 라는 이름을 입력 합니다.  
  
5.  **확인**을 클릭합니다.  
  
     새 콘솔 프로젝트가 나타납니다. 프로젝트가 만들어지면 소스 파일이 나타납니다. 선택한 언어에 따라 Program.cs, MyThreadWalkthroughApp.cpp, 또는 Module1.vb 소스 파일을 호출할 수 있습니다.  
  
6.  소스 파일에 표시 되는 코드를 삭제 하 고 여기에 표시 된 예제 코드로 바꿉니다.

    ```csharp
    using System;
    using System.Threading;

    public class ServerClass
    {

        static int count = 0;
        // The method that will be called when the thread is started.
        public void InstanceMethod()
        {
            Console.WriteLine(
                "ServerClass.InstanceMethod is running on another thread.");

            int data = count++;
            // Pause for a moment to provide a delay to make
            // threads more apparent.
            Thread.Sleep(3000);
            Console.WriteLine(
                "The instance method called by the worker thread has ended.");
        }
    }

    public class Simple
    {
        public static void Main()
        {
            for (int i = 0; i < 10; i++)
            {
                CreateThreads();
            }
        }
        public static void CreateThreads()
        {
            ServerClass serverObject = new ServerClass();

            Thread InstanceCaller = new Thread(new ThreadStart(serverObject.InstanceMethod));
            // Start the thread.
            InstanceCaller.Start();

            Console.WriteLine("The Main() thread calls this after "
                + "starting the new InstanceCaller thread.");

        }
    }
    ```

    ```C++
    #include "stdafx.h"
    #include <thread>
    #include <iostream>
    #include <vector>

    int count = 0;

    void doSomeWork() {

        std::cout << "The doSomeWork function is running on another thread." << std::endl;
        int data = count++;
        // Pause for a moment to provide a delay to make
        // threads more apparent.
        std::this_thread::sleep_for(std::chrono::seconds(3));
        std::cout << "The function called by the worker thread has ended." << std::endl;
    }

    int main() {
        std::vector<std::thread> threads;

        for (int i = 0; i < 10; ++i) {

            threads.push_back(std::thread(doSomeWork));
            std::cout << "The Main() thread calls this after starting the new thread" << std::endl;
        }

        for (auto& thread : threads) {
            thread.join();
        }

        return 0;
    }
    ```

    ```VB
    Imports System.Threading

    Public Class ServerClass
        ' The method that will be called when the thread is started.
        Public count = 0
        Public Sub InstanceMethod()
            Console.WriteLine(
                    "ServerClass.InstanceMethod is running on another thread.")

            Dim data = count + 1
            ' Pause for a moment to provide a delay to make
            ' threads more apparent.
            Thread.Sleep(3000)
            Console.WriteLine(
                    "The instance method called by the worker thread has ended.")
        End Sub

    End Class

    Public Class Simple

        Public Shared Sub Main()

            Dim ts As New ThreadStarter
            For index = 1 To 10
                ts.CreateThreads()
            Next

        End Sub

    End Class
    Public Class ThreadStarter
        Public Sub CreateThreads()
            Dim serverObject As New ServerClass()

            ' Create the thread object, passing in the
            ' serverObject.InstanceMethod method using a
            ' ThreadStart delegate.
            Dim InstanceCaller As New Thread(AddressOf serverObject.InstanceMethod)

            ' Start the thread.
            InstanceCaller.Start()

            Console.WriteLine("The Main() thread calls this after " _
                        + "starting the new InstanceCaller thread.")

        End Sub
    End Class
    ```
  
7.  에 **파일** 메뉴를 클릭 하 여 **모두 저장**합니다.  
  
#### <a name="to-begin-the-tutorial"></a>자습서를 시작 하려면  
  
-   소스 코드 편집기에서 다음 코드를 찾습니다. 
  
    ```csharp  
    Thread.Sleep(3000);  
    Console.WriteLine();  
    ```  
  
    ```C++  
    Thread::Sleep(3000);  
    Console.WriteLine();  
    ```  
    ```VB
    Thread.Sleep(3000)
    Console.WriteLine()
    ```
  
#### <a name="to-start-debugging"></a>디버깅을 시작하려면  
  
1.  왼쪽된 여백에서 클릭는 `Thread.Sleep` 또는 `Thread::Sleep` 새 중단점을 삽입 하는 문입니다.  
  
     소스 코드 편집기의 왼쪽 여백에 빨간색 원이 나타납니다. 이 공은 이 위치에 중단점이 설정되었음을 나타냅니다. 
  
2.  에 **디버그** 메뉴를 클릭 하 여 **디버깅 시작** (**F5**).  
  
     Visual Studio 솔루션을 빌드합니다, 그리고 연결, 디버거에서 실행 되도록 응용 프로그램 시작 및 응용 프로그램 중단점에서 중지 하는 다음 합니다.  
  
    > [!NOTE]
    > 콘솔 창에 포커스를 전환 하는 경우 클릭는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 창에 포커스를 돌리는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
4.  소스 코드 편집기에서 중단점을 포함 하는 줄을 찾습니다.  
  
    ```csharp  
    Thread.Sleep(3000);  
    ```  
  
    ```C++  
    Thread::Sleep(3000);  
    ```

    ```VB
    Thread.Sleep(3000)
    ```    
  
#### <a name="ShowThreadsInSource"></a>스레드 마커를 검색 하려면  

1.  디버그 도구 모음에서을 클릭는 **소스의 스레드 표시** 단추 ![소스의 스레드 표시](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker")합니다.

2. 키를 눌러 **F11** 이동 하는 코드의 디버거 한 줄에 한 번입니다.
  
3.  창 왼쪽의 여백을 확인합니다. 이 줄에 표시 됩니다는 *스레드 마커* 아이콘 ![스레드 마커](../debugger/media/dbg-thread-marker.png "ThreadMarker") 두 가닥의 실 유사한 합니다. 스레드 마커는 이 위치에서 스레드가 중지되었음을 나타냅니다.

    스레드 마커 중단점에서 부분적으로 숨겨진 수를 확인 합니다. 
  
4.  스레드 마커에 포인터를 올려 놓습니다. DataTips가 나타납니다. DataTip을 통해 중지된 각 스레드의 이름과 스레드 ID 번호를 알 수 있습니다. 이 경우 이름이 되었을 `<noname>`합니다. 
  
5.  바로 가기 메뉴에서 사용할 수 있는 옵션을 보려면 스레드 마커를 마우스 오른쪽 단추로 클릭 합니다.
    
## <a name="ParallelStacks"></a>스레드 위치를 확인 합니다.

에 **병렬 스택** 전환할 수 창 작업 보기 하 고 있습니다 (프로그래밍에 대 한 작업 기반)와 스레드 뷰 간에 각 스레드에 대 한 호출 스택 정보 볼 수 있습니다. 이 응용 프로그램에서 스레드 뷰를 사용할 수 있습니다.

1. 열기는 **병렬 스택** 창을 선택 하 여 **디버그 > Windows > 병렬 스택**합니다. 다음과 같이 표시 됩니다 (정보만 각 스레드, 하드웨어 및 프로그래밍 언어의 현재 위치에 따라 다를 수 됩니다).

    ![병렬 스택 창](../debugger/media/dbg-multithreaded-parallel-stacks.png "ParallelStacksWindow")

    이 예제에서는 왼쪽에서 오른쪽 구했습니다이 정보를:
    
    - 주 스레드 (왼쪽)에서 중지 되었습니다. `Thread.Start` (중지 지점을 스레드 마커 아이콘으로 표시 됩니다 ![스레드 마커](../debugger/media/dbg-thread-marker.png "ThreadMarker")).
    - 입력 한 두 개의 스레드는 `ServerClass.InstanceMethod`, 그 중 하나는 현재 스레드 (노란색 화살표)에 다른 스레드가 중지 하는 동안 `Thread.Sleep`합니다.
    - (오른쪽)에 새 스레드를 시작 됩니다 (에서 중지 `ThreadHelper.ThreadStart`).

2.  항목을 마우스 오른쪽 단추로 클릭는 **병렬 스택** 창 바로 가기 메뉴에서 사용할 수 있는 옵션을 확인 합니다.

    이러한 오른쪽 클릭 메뉴에서 다양 한 작업을 수행할 수 있습니다 하지만이 자습서에서 이러한 세부 정보 중에서 **병렬 조사식** 창 (다음 섹션).

    > [!NOTE]
    > 각 스레드에 대 한 정보 보기에서 사용 하 여 목록 보기에 더 관심이 있는 경우는 **스레드** 창 대신 합니다. 참조 [연습: 다중 스레드 응용 프로그램을 디버깅](../debugger/how-to-use-the-threads-window.md)합니다.

## <a name="set-a-watch-on-a-variable"></a>조사식 변수에 설정

1. 열기는 **병렬 조사식** 창을 선택 하 여 **디버그 > Windows > 병렬 조사식 > 병렬 조사식 1**합니다.

2. 나타나는 셀을 클릭는 `<Add Watch>` 텍스트 (또는 4 번째 열에서 빈 머리글 셀) 형식 `data`, Enter 키를 누릅니다.

    각 스레드에 대 한 데이터 변수에 대 한 값 창에 나타납니다.

3. 표시 되는 셀을 다시 클릭는 `<Add Watch>` 텍스트 (또는 5 번째 열에서 빈 머리글 셀) 형식 `count`, Enter 키를 누릅니다.

    각 스레드에 대해 count 변수에 대 한 값 창에 나타납니다. (이 많은 정보를 아직 표시 되지 않으면, 시도 f11를 몇 번 더 디버거에서 스레드 실행 합니다.)

    ![병렬 조사식 창](../debugger/media/dbg-multithreaded-parallel-watch.png "ParallelWatchWindow")

4. 사용 가능한 옵션을 보려면 창에 행 중 하나를 마우스 오른쪽 단추로 클릭 합니다.

## <a name="flagging-and-unflagging-threads"></a>스레드에 플래그 지정 및 해제  
특별 한 주의가 스레드에 플래그를 설정할 수 있습니다. 스레드에 플래그를 지정 하는 것이 중요 한 스레드를 추적 하 고에 대 한 중요 하지 않은 스레드를 무시 하도록 좋습니다.  
  
#### <a name="to-flag-threads"></a>스레드에 플래그를 지정하려면  

1. 에 **병렬 조사식** 창 SHIFT 키를 누른 채 여러 행을 선택 합니다.

2. 마우스 오른쪽 단추로 클릭 하 고 선택 **플래그**합니다.

    이제 선택한 모든 스레드가 플래그가 지정 됩니다. 이제 플래그가 지정 된 스레드만 표시 하도록 필터링 할 수 있습니다.
  
3.  에 **병렬 조사식** 창 찾기는 **플래그가 지정 된 스레드만 표시** 단추 ![플래그가 지정 된 스레드 표시](../debugger/media/dbg-threads-show-flagged.png "ThreadMarker")합니다.  
  
4.  클릭는 **플래그가 지정 된 스레드만 표시** 단추입니다.  
  
    플래그가 지정된 스레드만 목록에 나타납니다.

    > [!TIP]
    > 일부 스레드 플래그 때 코드 편집기에서 코드의 줄을 마우스 오른쪽 단추로 클릭 하 고 선택할 수 **실행 플래그가 지정 된 스레드를 커서까지** (스레드를 플래그 지정 하는 코드에 도달 하면 선택 하 고 있는지 확인). 이것은 선택된 된 실행 순서 대로 제어를 더욱 쉽게 코드 줄에 있는 스레드를 일시 중지 [스레드 중지 및 재개](#bkmk_freeze)합니다.

5.  클릭는 **플래그가 지정 된 스레드만 표시** 다시 전환 하려면 단추 **모든 스레드 표시** 모드입니다.
    
#### <a name="to-unflag-threads"></a>스레드의 플래그를 해제하려면

스레드 플래그를 해제 하려면 하나 이상의 플래그가 지정 된 스레드 단추로 **병렬 조사식** 창을 선택 하 고 **플래그 해제**합니다.

## <a name="bkmk_freeze"></a> 중지 및 재개 스레드 실행 

> [!TIP]
> 고정 및 고정 해제 수 (일시 중단 및 다시 시작) 스레드 작업을 수행 하는 순서를 제어 하는 스레드입니다. 이 교착 상태 같은 동시성 문제를 해결 하 고 경합 조건을 수 있습니다.
  
#### <a name="to-freeze-and-unfreeze-threads"></a>스레드를 중지 및 해제하려면  
  
1.  에 **병렬 조사식** 선택 된 모든 행을 마우스 오른쪽 단추로 클릭 하 고 선택 창 **고정**합니다.

    두 번째 열에서 일시 중지 아이콘 이제 각 행에 대해 나타납니다. 일시 중지 아이콘은 스레드가 중지 되었음을 나타냅니다.

2.  하나의 행을 클릭 하 여 행을 선택 취소 합니다.

3.  행을 마우스 오른쪽 단추로 클릭 하 고 선택 **재개**합니다.

    일시 중지 아이콘은 스레드가 더 이상 중지 되었음을 나타내는이 행에서 사라집니다.

4.  코드 편집기로 전환 하 고 클릭 **F11**합니다. 고정 되지 않은 스레드만 실행 됩니다.

    앱에서 몇 가지 새 스레드를 인스턴스화할 수도 수 있습니다. 모든 새 스레드를 플래그 지정 된 않으며 고정 되지 않은 확인 합니다.

## <a name="bkmk_follow_a_thread"></a> 조건부 중단점을 사용 하 여 단일 스레드를 수행 합니다.

경우에 따라 디버거에서 단일 스레드로 실행을 추적 하 유용할 수 있습니다. 관심 않은 스레드를 고정 하 여 수행할 수 있는 한 가지 방법은 이지만 일부 시나리오는 단일 스레드 하지 않고를 따르는 고정 하는 다른 스레드 (예를 들어 특정 버그 재현)를 만들 수 있습니다. 스레드가 다른 스레드에서 고정 하지 않고를 수행 하려면에 관심이 있는 스레드에서 제외 하 고 코드를 중단 하면 하면 안 됩니다. 설정 하 여이 수행할 수는 [조건부 중단점](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)합니다.

스레드 이름이 나 스레드 id입니다. 예: 서로 다른 조건에 중단점을 설정할 수 있습니다. 유용할 수 있는 다른 방법은 각 스레드에 고유 된다고 생각 하는 데이터에 조건을 설정 하는 것입니다. 중인 특정 스레드에의 보다 일부 특정 데이터 값에 더 많은 관심 일반적인 디버깅 시나리오입니다.

#### <a name="to-follow-a-single-thread"></a>단일 스레드를 수행 하려면

1. 이전에 만든 중단점을 마우스 오른쪽 단추로 클릭 하 고 선택 **조건**합니다.

2. 에 **중단점 설정** 창, 형식 `data == 5` 조건 식에 대 한 합니다.

    ![조건부 중단점](../debugger/media/dbg-multithreaded-conditional-breakpoint.png "ConditionalBreakpoint")

    > [!TIP]
    > 특정 스레드에 더 관심이 인 경우 스레드 이름이 나 스레드 ID 조건에 사용 합니다. 이 작업을 수행 하는 **중단점 설정** 창에서 **필터** 대신 **조건식**, 필터 팁을 따릅니다. 앱 코드에서 스레드 이름 지정 (스레드 Id는 디버거를 다시 시작 하면 변경) 이후 수도 있습니다.

3. 닫기는 **중단점 설정** 창.

4. 다시 시작을 클릭 ![응용 프로그램 다시 시작](../debugger/media/dbg-tour-restart.png "RestartApp") 디버깅 세션을 다시 시작 하는 단추입니다.

    데이터 변수는 5 스레드에서 코드로 중단 됩니다. 노란색 화살표 (현재 디버거 컨텍스트)에서 찾을 **병렬 조사식** 되었는지 확인 하는 창입니다.

5. 이제 실행 (F10) 코드 및 코드 (F11)를 한 단계씩 하 고 단일 스레드로 실행을 추적 합니다.

    중단점 조건은 스레드를 고유 하 고 디버거 (사용 하지 않도록 해야 할 수 있습니다) 다른 스레드에서 다른 중단점이 적중 되지 않습니다, 코드 실행 하 고 다른 스레드를 전환 하지 않으면 코드를 한 단계씩 합니다.

    > [!NOTE]
    > 디버거를 진행 하면 모든 스레드가 실행 됩니다. 그러나 다른 스레드 중 하나는 중단점에 도달 하지 않는 한 다른 스레드에서 코드로 디버거가 중단 되지 않습니다. 
  
## <a name="more-about-the-multithreaded-debugging-windows"></a>다중 스레드 디버깅 창에 대 한 자세한 정보 

#### <a name="to-switch-to-another-thread"></a>다른 스레드로 전환 하려면 

- 다른 스레드로 전환 하려면 참조 [하는 방법: 다른 스레드가 디버그 하는 동안로 전환](../debugger/how-to-switch-to-another-thread-while-debugging.md) 

#### <a name="to-learn-more-about-the-parallel-stack-and-parallel-watch-windows"></a>병렬 스택 및 병렬 조사식 창에 대 한 자세한 내용을 보려면  
  
- 참조 [하는 방법: 병렬 스택 창 사용](../debugger/using-the-parallel-stacks-window.md) 

- 참조 [하는 방법: 병렬 조사식 창 사용](../debugger/how-to-use-the-parallel-watch-window.md) 
  
## <a name="see-also"></a>참고 항목  
 [다중 스레드 응용 프로그램 디버그](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [방법: 디버그 중 다른 스레드로 전환](../debugger/how-to-switch-to-another-thread-while-debugging.md)
