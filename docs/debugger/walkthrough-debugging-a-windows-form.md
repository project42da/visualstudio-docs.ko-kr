---
title: "연습: Windows Form 디버깅 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- debugging managed code, Windows Forms
- debugging [Visual Studio], Windows Forms
- Attach to Process dialog box
- debugger, attaching to programs
- Attach to Process dialog box, walkthroughs
- Windows Forms, debugging
- debugging Windows Forms, walkthroughs
ms.assetid: 529db1e2-d9ea-482a-b6a0-7c543d17f114
caps.latest.revision: "28"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 02db9a01286e65f371ab4d8388102a3db4c5602e
ms.sourcegitcommit: 1e08318a8a684b21609af7a5e48b56abcc3239e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/13/2017
---
# <a name="walkthrough-debugging-a-windows-form"></a>연습: Windows Form 디버깅
Windows Form에는 가장 일반적인 관리 되는 응용 프로그램 중 하나입니다. Windows Form Windows 표준 응용 프로그램을 만듭니다. Visual Basic, C# 또는 c + +를 사용 하 여이 연습을 완료할 수 있습니다.  
  
 먼저, 열려 있는 솔루션을 닫아야 합니다.  
  
### <a name="to-prepare-for-this-walkthrough"></a>이 연습을 준비하려면  
  
-   이미 열려 있는 솔루션이 있으면 닫습니다. (에 **파일** 메뉴 선택 **솔루션 닫기**.)  
  
## <a name="create-a-new-windows-form"></a>새 Windows Form 만들기  
 다음으로 새 Windows Form을 만들게 됩니다.  
  
#### <a name="to-create-the-windows-form-for-this-walkthrough"></a>이 연습에서는 Windows form을 만들려면  
  
1.  에 **파일** 메뉴 선택 **새로** 클릭 **프로젝트**합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  프로젝트 형식 창에서 열고는 **Visual Basic**, **Visual C#**, 또는 **Visual c + +** 노드를 다음  
  
    1.  Visual Basic 또는 Visual C#, 선택는 **Windows** 노드를 선택 합니다 **Windows Form 응용 프로그램** 에 **템플릿** 창.  
  
    2.  Visual c + +에 대 한 선택은 **CLR** 노드를 선택 합니다 **Windows Form 응용 프로그램** 에 **템플릿** 창...  
  
3.  에 **템플릿** 창 선택 **Windows 응용 프로그램**합니다.  
  
4.  에 **이름** 상자는 프로젝트 (예를 들어 Walkthrough_SimpleDebug) 고유한 이름을 지정 합니다.  
  
5.  **확인**을 클릭합니다.  
  
     Visual Studio 새 프로젝트를 만들고 Windows Forms 디자이너에서 새 폼을 표시 합니다. 자세한 내용은 참조 [Windows Forms 디자이너](http://msdn.microsoft.com/en-us/3c3d61f8-f36c-4d41-b9c3-398376fabb15)합니다.  
  
6.  에 **보기** 메뉴 선택 **도구 상자**합니다.  
  
     도구 상자가 열립니다. 자세한 내용은 참조 [도구 상자](../ide/reference/toolbox.md)합니다.  
  
7.  도구 상자에서에서 클릭 된 **단추** 제어 하 고 양식 디자인 화면에 컨트롤을 끌어 놓습니다. 폼에 단추를 놓습니다.  
  
8.  도구 상자에서에서 클릭는 **TextBox** 제어 하 고 양식 디자인 화면에 컨트롤을 끌어 놓습니다. 삭제는 **TextBox** 폼에 있습니다.  
  
9. 양식 디자인 화면에서 단추를 두 번 클릭 합니다.  
  
     이 코드 페이지로 이동합니다. 커서에 있어야 합니다. `button1_Click`합니다.  
  
10. 함수에서 `button1_Click`., 다음 코드를 추가 합니다.  
  
    ```  
    ' Visual Basic  
    textBox1.Text = "Button was clicked!"  
  
    // C#  
    textBox1.Text = "Button was clicked!";  
  
    // C++  
    textBox1->Text = "Button was clicked!";  
    ```  
  
11. 에 **빌드** 메뉴 선택 **솔루션 빌드**합니다.  
  
     프로젝트가 오류 없이 빌드되어야 합니다.  
  
## <a name="debug-your-form"></a>폼 디버깅  
 이제 디버깅을 시작할 준비가 되었습니다.  
  
#### <a name="to-debug-the-windows-form-created-for-this-walkthrough"></a>이 연습에 대해 생성 하는 Windows Form을 디버깅 하려면  
  
1.  소스 창에서 추가한 텍스트와 같은 줄의 왼쪽된 여백을 클릭 합니다.  
  
    ```  
    ' Visual Basic  
    textBox1.Text = "Button was clicked!"  
  
    // C#  
    textBox1.Text = "Button was clicked!";  
  
    // C++  
    textBox1->Text = "Button was clicked!";  
    ```  
  
     빨간 점이 나타나며 해당 줄의 텍스트가 빨간색으로 강조 표시됩니다. 빨간 점은 중단점을 나타냅니다. 자세한 내용은 참조 [중단점](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)합니다. 디버거에서 응용 프로그램을 실행하면 코드가 적중되는 위치에서 디버거가 실행을 중단합니다. 그런 다음 응용 프로그램의 상태를 보고 디버깅할 수 있습니다.  
  
    > [!NOTE]
    >  모든 줄을 마우스 오른쪽 단추로 클릭 가리킨 코드의 **중단점**, 클릭 하 고 **중단점 삽입** 같은 줄에 중단점을 추가 하려면.  
  
2.  ON은 **디버그** 메뉴 선택 **시작**합니다.  
  
     Windows Form 실행을 시작 합니다.  
  
3.  Windows Form에서 추가한 단추를 클릭 합니다.  
  
     Visual Studio에서이 줄으로 이동 된 코드 페이지에 중단점을 설정한 합니다. 이 줄은 노란색으로 강조 표시되어 있어야 합니다. 이제 응용 프로그램의 변수를 보고 해당 응용 프로그램의 실행을 제어할 수 있습니다. 응용 프로그램 실행, 사용자의 작업이 대기 중에 지금 중지 되었습니다.  
  
4.  에 **디버그** 메뉴 선택 **Windows**, 다음 **조사식**를 클릭 하 고 **조사식 1**합니다.  
  
5.  에 **조사식 1** 창에서 빈 행을 클릭 합니다. 에 **이름** 열, 형식 `textBox1.Text` (하는 경우 사용할 Visual Basic 또는 Visual C#) 또는 `textBox1->Text` (사용 중인 경우 c + +), 한 다음 ENTER 키를 누릅니다.  
  
     **조사식 1** 창으로 인용 부호 안에이 변수의 값을 표시 합니다.  
  
    ```  
    ""  
    ```  
  
6.  에 **디버그** 메뉴 선택 **한 단계씩 코드 실행**합니다.  
  
     값이 textBox1.Text 변경에는 **조사식 1** 창:  
  
    ```  
    Button was clicked!  
    ```  
  
7.  에 **디버그** 메뉴 선택 **계속** 프로그램 디버깅을 다시 시작 합니다.  
  
8.  Windows Form에서 단추를 다시 클릭 합니다.  
  
     Visual Studio는 다시 실행을 중단합니다.  
  
9. 중단점을 나타내는 빨간색 점을 클릭 합니다.  
  
     이 사용자 코드에서 중단점을 제거합니다.  
  
10. 에 **디버그** 메뉴 선택 **디버깅 중지**합니다.  
  
## <a name="attach-to-your-windows-form-application-for-debugging"></a>디버깅을 위해 Windows Form 응용 프로그램에 연결  
 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]에서는 실행 중인 프로세스에 디버거를 연결할 수 있습니다. Express Edition을 사용 하는 경우이 기능은 지원 되지 않습니다.  
  
#### <a name="to-attach-to-the-windows-form-application-for-debugging"></a>디버깅을 위해 Windows Form 응용 프로그램에 연결 하려면  
  
1.  위에서 만든 프로젝트에서 다시 한 번 추가한 줄에 중단점을 설정 하려면 왼쪽된 여백을 클릭 합니다.  
  
    ```  
    ' Visual Basic  
    textBox1.Text = "Button was clicked!"  
  
    // C#  
    textBox1.Text = "Button was clicked!"  
  
    // C++  
    textBox1->Text = "Button was clicked!";  
    ```  
  
2.  에 **디버그** 메뉴 선택 **디버깅 하지 않고 시작**합니다.  
  
     Windows Form는 경우 해당 실행 파일을 두 번 클릭 했습니다 처럼 windows에서 실행을 시작 합니다. 디버거가 연결 되지 않습니다.  
  
3.  에 **디버그** 메뉴 선택 **프로세스에 연결**합니다. (이 명령은에서 제공 됩니다.는 **도구** 메뉴.)  
  
     **프로세스에 연결** 대화 상자가 나타납니다.  
  
4.  에 **사용 가능한 프로세스** 창, 프로세스 이름 (Walkthrough_SimpleDebug.exe) 찾기는 **프로세스** 열 클릭 합니다.  
  
5.  클릭는 **연결** 단추입니다.  
  
6.  Windows Form을는 1과만 단추를 클릭 합니다.  
  
     디버거는 중단점에서 Windows Form의 실행을 중단 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Debugging Managed Code](../debugger/debugging-managed-code.md) (관리 코드 디버그)  
 [디버거 보안](../debugger/debugger-security.md)