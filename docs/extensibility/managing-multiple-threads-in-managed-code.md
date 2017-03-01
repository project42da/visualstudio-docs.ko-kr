---
title: "방법: 관리 코드에서 여러 스레드를 관리 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59730063-cc29-4dae-baff-2234ad8d0c8f
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: 477f57bbca9c49e7d7d13155fc1f6e55ee4667a8
ms.openlocfilehash: 417dc6e5285859424dfa3b482a90f1a141cff163
ms.lasthandoff: 02/22/2017

---
# <a name="how-to-managing-multiple-threads-in-managed-code"></a>방법: 관리 코드에서 여러 스레드를 관리 합니다.
비동기 메서드를 호출 하거나 Visual Studio UI 스레드가 아닌 스레드에서 실행 되는 작업을 관리 되는 VSPackage 확장을 사용 하는 경우 아래의 지침을 따라야 합니다. 완료 하려면 다른 스레드에서 작업에 대 한 대기 필요가 없기 때문에 UI 스레드를 응답 성능을 유지할 수 있습니다. 코드 보다 효율적으로 수행할 수 스택 공간을 차지 하는 추가 스레드가 없기 때문에 있고 더 안정적이 고 교착 상태 및 중지 문제를 방지 하기 때문에 디버깅을 쉽게 만들 수 있습니다.  
  
 일반적으로 전환할 수 있습니다 UI 스레드에서 다른 스레드로 또는 그 반대의 경우도 마찬가지입니다. 메서드가 반환 될 때 현재 스레드를 원래 호출한 스레드는 합니다.  
  
> [!IMPORTANT]
>  다음 지침은 Api를 사용 하 여 <xref:Microsoft.VisualStudio.Threading>네임 스페이스, 특히 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory>클래스</xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory> </xref:Microsoft.VisualStudio.Threading> 에 이 네임 스페이스의 Api에 새로 추가 된 [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)]합니다. 인스턴스를 가져올 수는 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory>에서 <xref:Microsoft.VisualStudio.Shell.ThreadHelper>속성 `ThreadHelper.JoinableTaskFactory`.</xref:Microsoft.VisualStudio.Shell.ThreadHelper> </xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory>  
  
## <a name="switching-from-the-ui-thread-to-a-background-thread"></a>UI 스레드에서 백그라운드 스레드로 전환  
  
1.  UI 스레드는 백그라운드 스레드에서 비동기 작업을 수행 하려는 경우 Task.Run()를 사용 합니다.  
  
    ```c#  
    await Task.Run(async delegate{  
        // Now you’re on a separate thread.  
    });  
    // Now you’re back on the UI thread.  
  
    ```  
  
2.  UI 스레드에서 사용 하 여 백그라운드 스레드에서 작업을 수행 하는 동안 동기적으로 차단 하려는 경우는 <xref:System.Threading.Tasks.TaskScheduler>속성 `TaskScheduler.Default` <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.Run%2A>::</xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.Run%2A> 내</xref:System.Threading.Tasks.TaskScheduler>  
  
    ```c#  
    // using Microsoft.VisualStudio.Threading;  
    ThreadHelper.JoinableTaskFactory.Run(async delegate {  
        await TaskScheduler.Default;  
        // You're now on a separate thread.  
        DoSomethingSynchronous();  
        await OrSomethingAsynchronous();  
    });  
    ```  
  
## <a name="switching-from-a-background-thread-to-the-ui-thread"></a>백그라운드 스레드에서 UI 스레드로 전환  
  
1.  백그라운드 스레드는 UI 스레드에서 작업을 수행 하려면 사용 하 여 해당 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A>::</xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A>  
  
    ```c#  
    // Switch to main thread  
    await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync();  
    ```  
  
     사용할 수는 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A>메서드를 UI 스레드로 전환 합니다.</xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A> 이 메서드는 메시지는 현재 비동기 메서드의 연속으로 UI 스레드를 게시 하 고 또한 올바른 우선 순위를 설정 하 고 교착 상태를 방지 하는 스레딩 프레임 워크의 나머지 부분과 통신.  
  
     백그라운드 스레드 메서드 비동기 없고 지킬 수 없을 때는 비동기 경우 계속 사용할 수 있습니다는 `await` 작업을 사용 하 여 UI 스레드로 전환 하려면 다음 구문을 사용 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.Run%2A>이 예제와 같이:</xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.Run%2A>  
  
    ```c#  
    ThreadHelper.JoinableTaskFactory.Run(async delegate {  
        // Switch to main thread  
        await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync();  
        // Do your work on the main thread here.  
    });  
    ```
