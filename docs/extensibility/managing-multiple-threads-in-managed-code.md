---
title: "방법: 관리 코드에서 다중 스레드 관리 | Microsoft Docs"
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
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 21fcc9388b40baa9e003b4beb876ba2f0f23fbaf
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="how-to-managing-multiple-threads-in-managed-code"></a>방법: 관리 코드에서 다중 스레드 관리
비동기 메서드를 호출 하거나는 Visual Studio UI 스레드가 아닌 스레드에서 실행 하는 작업을 제공 하는 관리 되는 VSPackage 확장을 설정한 경우 다음 지침을 따라야 합니다. 완료 하려면 다른 스레드에서 작업을 기다릴 필요 하지 않습니다 때문에 UI 스레드를 응답 유지할 수 있습니다. 코드 보다 효율적으로 수행할 수 스택 공간을 차지 하는 추가 스레드가 없기 때문에 있고 더 안정적이 고 쉽게 교착 상태 및 중지 문제를 방지 하기 때문에 디버깅할 수 있도록 만들 수 있습니다.  
  
 일반적으로 전환할 수 있습니다 UI 스레드에서 다른 스레드로 또는 그 반대의 경우도 마찬가지입니다. 메서드가 반환 될 때 현재 스레드를 사용 했던 스레드가입니다.  
  
> [!IMPORTANT]
>  다음 지침에 Api를 사용 하는 <xref:Microsoft.VisualStudio.Threading> 네임 스페이스, 특히는 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory> 클래스입니다. 이 네임 스페이스에서 Api에 새로 추가 된 [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)]합니다. 인스턴스를 가져올 수는 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory> 에서 <xref:Microsoft.VisualStudio.Shell.ThreadHelper> 속성 `ThreadHelper.JoinableTaskFactory`합니다.  
  
## <a name="switching-from-the-ui-thread-to-a-background-thread"></a>UI 스레드 백그라운드 스레드로 전환  
  
1.  UI 스레드에서 백그라운드 스레드에서 비동기 작업을 수행 하려면 Task.Run()를 사용 하십시오.  
  
    ```csharp  
    await Task.Run(async delegate{  
        // Now you're on a separate thread.  
    });  
    // Now you're back on the UI thread.  
  
    ```  
  
2.  UI 스레드에서 동기적으로 사용 하 여 백그라운드 스레드에서 작업을 수행 하는 동안를 차단 하려는 경우는 <xref:System.Threading.Tasks.TaskScheduler> 속성 `TaskScheduler.Default` 내 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.Run%2A>:  
  
    ```csharp  
    // using Microsoft.VisualStudio.Threading;  
    ThreadHelper.JoinableTaskFactory.Run(async delegate {  
        await TaskScheduler.Default;  
        // You're now on a separate thread.  
        DoSomethingSynchronous();  
        await OrSomethingAsynchronous();  
    });  
    ```  
  
## <a name="switching-from-a-background-thread-to-the-ui-thread"></a>백그라운드 스레드에서 UI 스레드로 전환  
  
1.  백그라운드 스레드에 속해 있으며 사용 하 여 UI 스레드에서 작업을 수행 하려는 경우 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A>:  
  
    ```csharp  
    // Switch to main thread  
    await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync();  
    ```  
  
     사용할 수는 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A> UI 스레드로 전환 하는 메서드. 이 메서드는 메시지는 현재 비동기 메서드의 연속으로 UI 스레드를 게시 하 고 올바른 우선 순위를 설정 하 고 교착 상태를 방지 하기 위해 스레딩 프레임 워크의 나머지와도 통신.  
  
     백그라운드 스레드 메서드 비동기 없고 지킬 수 없을 때는 비동기 경우 계속 사용할 수 있습니다는 `await` 를 사용 하 여 래핑을 사용 하 여 UI 스레드로 전환 하는 구문을 <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.Run%2A>이 예제와 같이,:  
  
    ```csharp  
    ThreadHelper.JoinableTaskFactory.Run(async delegate {  
        // Switch to main thread  
        await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync();  
        // Do your work on the main thread here.  
    });  
    ```
