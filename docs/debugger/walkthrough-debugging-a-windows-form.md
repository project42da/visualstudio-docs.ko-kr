---
title: "연습: Windows Form 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "프로세스에 연결 대화 상자"
  - "프로세스에 연결 대화 상자, 연습"
  - "디버거, 프로그램에 연결"
  - "디버깅[Visual Studio], 연습"
  - "디버깅[Visual Studio], Windows Forms"
  - "관리 코드 디버깅, Windows Forms"
  - "Windows Forms 디버깅, 연습"
  - "Windows Forms, 디버깅"
ms.assetid: 529db1e2-d9ea-482a-b6a0-7c543d17f114
caps.latest.revision: 28
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 28
---
# 연습: Windows Form 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Windows Form은 가장 일반적인 형태의 관리되는 응용 프로그램 중 하나입니다.  Windows Form은 표준 Windows 응용 프로그램을 만듭니다.  Visual Basic, C\# 또는 C\+\+를 사용하여 이 연습을 진행할 수 있습니다.  
  
 먼저 열려 있는 솔루션을 모두 닫아야 합니다.  
  
### 이 연습을 준비하려면  
  
-   열려 있는 솔루션이 있으면 닫습니다. **파일** 메뉴에서 **솔루션 닫기**를 선택합니다.  
  
## 새 Windows Form 만들기  
 그런 다음 새 Windows Form을 만듭니다.  
  
#### 이 연습에 사용할 Windows Form을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 선택한 다음 **프로젝트**를 클릭합니다.  
  
     **새 프로젝트** 대화 상자가 나타납니다.  
  
2.  프로젝트 형식 창에서 **Visual Basic**, **Visual C\#** 또는 **Visual C\+\+** 노드를 엽니다.  
  
    1.  Visual Basic 또는 Visual C\#의 경우 **Windows** 노드를 선택한 다음 **템플릿** 창에서 **Windows Form 응용 프로그램**을 선택합니다.  
  
    2.  Visual C\+\+의 경우 **CLR** 노드를 선택한 다음 **템플릿** 창에서 **Windows Form 응용 프로그램**을 선택합니다.  
  
3.  **템플릿** 창에서 **Windows 응용 프로그램**을 선택합니다.  
  
4.  **이름** 상자에 프로젝트의 고유 이름\(예: Walkthrough\_SimpleDebug\)을 입력합니다.  
  
5.  **확인**을 클릭합니다.  
  
     새 프로젝트가 만들어지고 Windows Forms 디자이너에 새 폼이 표시됩니다.  자세한 내용은 [Windows Forms 디자이너](http://msdn.microsoft.com/ko-kr/3c3d61f8-f36c-4d41-b9c3-398376fabb15)를 참조하십시오.  
  
6.  **보기** 메뉴에서 **도구 상자**를 선택합니다.  
  
     도구 상자가 열립니다.  자세한 내용은 [도구 상자](../ide/reference/toolbox.md)를 참조하십시오.  
  
7.  도구 상자에서 **Button** 컨트롤을 클릭한 다음 폼 디자인 표면으로 끕니다.  단추를 폼 위에 놓습니다.  
  
8.  도구 상자에서 **TextBox** 컨트롤을 클릭한 다음 폼 디자인 표면으로 끕니다.  **TextBox**를 폼 위에 놓습니다.  
  
9. 폼 디자인 표면에서 단추를 두 번 클릭합니다.  
  
     그러면 코드 페이지로 이동합니다.  커서는 `button1_Click`에 있어야 합니다.  
  
10. `button1_Click` 함수에 다음 코드를 추가합니다.  
  
    ```  
    ' Visual Basic  
    textBox1.Text = "Button was clicked!"  
  
    // C#  
    textBox1.Text = "Button was clicked!";  
  
    // C++  
    textBox1->Text = "Button was clicked!";  
    ```  
  
11. **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.  
  
     프로젝트가 오류 없이 빌드되어야 합니다.  
  
## 폼 디버깅  
 이제 디버깅을 시작할 수 있습니다.  
  
#### 이 연습에 사용하기 위해 만든 Windows Form을 디버깅하려면  
  
1.  소스 창에서, 텍스트를 추가한 줄의 왼쪽 여백을 클릭합니다.  
  
    ```  
    ' Visual Basic  
    textBox1.Text = "Button was clicked!"  
  
    // C#  
    textBox1.Text = "Button was clicked!";  
  
    // C++  
    textBox1->Text = "Button was clicked!";  
    ```  
  
     빨간 점이 나타나며 해당 줄의 텍스트가 빨간색으로 강조 표시됩니다.  빨간 점은 중단점을 나타냅니다.  자세한 내용은 [중단점](http://msdn.microsoft.com/ko-kr/fe4eedc1-71aa-4928-962f-0912c334d583)을 참조하십시오.  디버거에서 응용 프로그램을 실행하면 코드가 적중되는 위치에서 디버거가 실행을 중단합니다.  그런 다음 응용 프로그램의 상태를 보고 디버깅할 수 있습니다.  
  
    > [!NOTE]
    >  코드 줄을 마우스 오른쪽 단추로 클릭하고 **중단점**을 가리킨 다음 **중단점 삽입**을 클릭하여 해당 줄에 중단점을 추가합니다.  
  
2.  **디버그** 메뉴에서 **시작**을 선택합니다.  
  
     Windows Form이 실행되기 시작합니다.  
  
3.  Windows Form에서, 추가한 단추를 클릭합니다.  
  
     Visual Studio의 경우, 코드 페이지에서 중단점을 설정한 줄로 이동합니다.  이 줄은 노란색으로 강조 표시되어 있어야 합니다.  이제 응용 프로그램의 변수를 보고 해당 응용 프로그램의 실행을 제어할 수 있습니다.  응용 프로그램이 실행을 중지하고 사용자의 동작을 기다립니다.  
  
4.  **디버그** 메뉴에서 **창**, **조사식**, **조사식1**을 차례로 선택합니다.  
  
5.  **조사식1** 창에서 빈 행을 클릭합니다.  **이름** 열에 `textBox1.Text`\(Visual Basic, Visual C\# 또는 J\#을 사용하는 경우\) 또는 `textBox1->Text`\(C\+\+를 사용하는 경우\)를 입력한 다음 Enter 키를 누릅니다.  
  
     **조사식1** 창에 다음과 같이 이 변수의 값이 인용 부호 안에 표시됩니다.  
  
    ```  
    ""  
    ```  
  
6.  **디버그** 메뉴에서 **한 단계씩 코드 실행**을 선택합니다.  
  
     **조사식1** 창에서 textBox1.Text 값이 다음과 같이 변경됩니다.  
  
    ```  
    Button was clicked!  
    ```  
  
7.  **디버그** 메뉴에서 **계속**을 선택하여 프로그램 디버깅을 다시 시작합니다.  
  
8.  Windows Form에서 단추를 다시 클릭합니다.  
  
     Visual Studio가 다시 실행을 중단합니다.  
  
9. 중단점을 나타내는 빨간색 점을 클릭합니다.  
  
     그러면 코드에서 중단점이 제거됩니다.  
  
10. **디버그** 메뉴에서 **디버깅 중지**를 선택합니다.  
  
## Windows Form 응용 프로그램에 연결하여 디버깅 수행  
 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]에서는 실행 중인 프로세스에 디버거를 연결할 수 있습니다.  Express 버전을 사용하는 경우에는 이 기능이 지원되지 않습니다.  
  
#### Windows Form 응용 프로그램에 연결하여 디버깅을 수행하려면  
  
1.  위에서 만든 프로젝트에서 왼쪽 여백을 클릭하여 다음 코드가 추가된 줄에서 중단점을 다시 한 번 설정합니다.  
  
    ```  
    ' Visual Basic  
    textBox1.Text = "Button was clicked!"  
  
    // C#  
    textBox1.Text = "Button was clicked!"  
  
    // C++  
    textBox1->Text = "Button was clicked!";  
    ```  
  
2.  **디버그** 메뉴에서 **디버깅하지 않고 시작**을 선택합니다.  
  
     실행 파일을 두 번 클릭했을 때처럼 Windows Form이 Windows에서 실행되기 시작합니다.  디버거는 연결되지 않습니다.  
  
3.  **디버그** 메뉴에서 **프로세스에 연결**을 선택합니다. 이 명령은 **도구** 메뉴에서도 사용할 수 있습니다.  
  
     **프로세스에 연결** 대화 상자가 나타납니다.  
  
4.  **사용 가능한 프로세스** 창의 **프로세스** 열에서 프로세스 이름\(Walkthrough\_SimpleDebug.exe\)을 찾아 클릭합니다.  
  
5.  **연결** 단추를 클릭합니다.  
  
6.  Windows Form에서 한 단추만 클릭합니다.  
  
     디버거가 중단점에서 Windows Form의 실행을 중단합니다.  
  
## 참고 항목  
 [관리 코드 디버깅](../debugger/debugging-managed-code.md)   
 [디버거 보안](../debugger/debugger-security.md)