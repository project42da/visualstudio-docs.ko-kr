---
title: "연습: Web Form 디버깅 | Microsoft Docs"
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
- Web pages [.NET Framework], debugging
- Web sites [.NET Framework], debugging
- ASP.NET, debugging Web applications
- Web applications [.NET Framework], debugging
- ASP.NET Web sites, debugging
- ASP.NET Web pages, debugging
- debugging ASP.NET Web applications, Web Forms
- debugging [Visual Studio], Web Forms
ms.assetid: e2b4fa14-8f5b-444d-a903-54070b784bd4
caps.latest.revision: "31"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 842b52d063b5de701c74501410e3249da7358776
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-debugging-a-web-form"></a>연습: Web Form 디버깅
이 연습 과정에서는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램(Web Form)의 디버깅 방법을 보여 줍니다. 시작 및 실행을 중지 하 고, 중단점을 설정 하 고에서 변수를 검사 하는 방법을 보여는 **조사식** 창.  
  
> [!NOTE]
>  이 연습을 수행하려면 서버 컴퓨터에 대한 관리자 권한이 있어야 합니다. 기본적으로 aspnet_wp.exe나 w3wp.exe 같은 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 프로세스는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 프로세스로 실행됩니다. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]을 디버깅하려면 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]이 실행되는 컴퓨터에서 관리자 권한이 있어야 합니다. 자세한 내용은 참조 [시스템 요구 사항](../debugger/aspnet-debugging-system-requirements.md)합니다.  
  
 표시되는 대화 상자와 메뉴 명령은 실제 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
### <a name="to-create-the-web-form"></a>Web Form을 만들려면  
  
1.  열려 있는 솔루션이 있으면 닫습니다.  
  
2.  에 **파일** 메뉴를 클릭 **새로**, 클릭 하 고 **웹 사이트**합니다.  
  
     **새 웹 사이트** 대화 상자가 나타납니다.  
  
3.  에 **템플릿** 창에서 클릭 **ASP.NET 웹 사이트**합니다.  
  
4.  에 **위치** 줄, 클릭 **HTTP** 목록에서 하 고 텍스트 상자에 입력 **http://localhost/WebSite**합니다.  
  
5.  에 **언어** 목록에서 클릭 **Visual C#** 또는 **Visual Basic**합니다.  
  
6.  **확인**을 클릭합니다.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 새 프로젝트가 만들어지고 기본 HTML 소스 코드가 표시됩니다. 라는 새 가상 디렉터리도 만듭니다 **웹 사이트** 아래 **기본 웹 사이트** IIS에서 합니다.  
  
7.  클릭는 **디자인** 아래쪽 여백에 탭 합니다.  
  
8.  클릭는 **도구 상자** 왼쪽된 여백에 탭 또는에서 선택 된 **보기** 메뉴.  
  
     **도구 상자** 가 열립니다.  
  
9. 에 **도구 상자**, 클릭는 **단추** 제어 하 고 Default.aspx 기본 디자인 화면에 추가 합니다.  
  
10. 에 **도구 상자**, 클릭는 **Textbox** 컨트롤을 Default.aspx 기본 디자인 화면에 컨트롤을 끌어 놓습니다.  
  
11. 끌어 놓은 단추 컨트롤을 두 번 클릭합니다.  
  
     이렇게 하면 코드 페이지(C#의 경우 Default.aspx.cs, [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 경우 Default.aspx.vb)가 표시됩니다. 커서는 `Button1_Click` 함수에 있어야 합니다.  
  
12. `Button1_Click` 함수에 다음 코드를 추가합니다.  
  
    ```  
    ' Visual Basic  
    TextBox1.Text = "Button was clicked!"  
  
    // C#  
    TextBox1.Text = "Button was clicked!";  
    ```  
  
13. **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     프로젝트가 오류 없이 빌드되어야 합니다.  
  
     이제 디버깅을 시작할 수 있습니다.  
  
### <a name="to-debug-the-web-form"></a>Web Form을 디버깅하려면  
  
1.  Default.aspx.cs 또는 Default.aspx.vb 창에서 추가한 텍스트와 같은 줄의 왼쪽 여백을 클릭합니다.  
  
    ```  
    ' Visual Basic  
    TextBox1.Text = "Button was clicked!"  
  
    // C#  
    textBox1.Text = "Button was clicked!";  
    ```  
  
     빨간 점이 나타나며 해당 줄의 텍스트가 빨간색으로 강조 표시됩니다. 빨간 점은 중단점을 나타냅니다. 디버거에서 응용 프로그램을 실행하면 코드가 적중되는 위치에서 디버거가 실행을 중단합니다. 그런 다음 응용 프로그램의 상태를 보고 디버깅할 수 있습니다. 자세한 내용은 참조 [중단점](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)합니다.  
  
2.  **디버그** 메뉴에서 **디버깅 시작**을 클릭합니다.  
  
3.  **디버깅 사용 안 함** 대화 상자가 나타납니다. 선택 **디버깅할 수 있도록 Web.config 파일을 수정** 옵션을 클릭 하 여 **확인**합니다.  
  
     Internet Explorer가 시작되어 방금 디자인한 페이지를 표시합니다.  
  
4.  Internet Explorer에서 단추를 클릭합니다.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 경우 이 작업을 수행하면 코드 페이지(Default.aspx.cs 또는 Default.aspx.vb)에서 중단점을 설정한 줄로 이동합니다. 이 줄은 노란색으로 강조 표시되어 있어야 합니다. 이제 응용 프로그램의 변수를 보고 해당 응용 프로그램의 실행을 제어할 수 있습니다. 응용 프로그램 실행이 중지되고 사용자가 명령을 입력할 때까지 대기합니다.  
  
5.  에 **디버그** 메뉴를 클릭 **Windows**, 클릭 **조사식**, 클릭 하 고 **조사식 1**합니다.  
  
6.  에 **조사식** 창, 형식 **TextBox1.Text**합니다.  
  
     **조사식** 창에 변수 값 표시 `TextBox1.Text`:  
  
    ```  
    ""  
    ```  
  
7.  에 **디버그** 메뉴를 클릭 하 여 **프로시저 단위 실행**합니다.  
  
     값 `TextBox1.Text` 에서 변경 된 **조사식** 창:  
  
    ```  
    "Button was clicked!"  
    ```  
  
8.  에 **디버그** 메뉴를 클릭 하 여 **계속**합니다.  
  
9. Internet Explorer에서 단추를 다시 클릭합니다.  
  
     중단점에서 다시 실행이 중지됩니다.  
  
10. Default.aspx.cs 또는 Default.aspx.vb 창의 왼쪽 여백에서 빨간 점을 클릭합니다.  
  
     중단점이 제거됩니다.  
  
11. 에 **디버그** 메뉴를 클릭 하 여 **디버깅 중지**합니다.  
  
### <a name="to-attach-to-the-web-form-for-debugging"></a>디버깅하기 위해 Web Form에 연결하려면  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 실행 중인 프로세스에 디버거를 연결할 수 있습니다. 디버깅을 효율적으로 수행하려면 기호 파일(PDB)을 사용하여 실행 파일을 디버그 버전으로 컴파일합니다.  
  
2.  Default.aspx.cs 또는 Default.aspx.vb 창에서 왼쪽 여백을 클릭하여 추가한 줄에 중단점을 한 번 더 설정합니다.  
  
    ```  
    ' Visual Basic  
    TextBox1.Text = "Button was clicked!"  
  
    // C#  
    textBox1.Text = "Button was clicked!";  
    ```  
  
3.  에 **디버그** 메뉴를 클릭 하 여 **디버깅 하지 않고 시작**합니다.  
  
     Web Form이 Internet Explorer에서 실행되지만 디버거가 연결되지는 않습니다.  
  
4.  [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 프로세스에 연결합니다. 자세한 내용은 참조 [배포 된 웹 응용 프로그램 디버깅](../debugger/debugging-deployed-web-applications.md)합니다.  
  
5.  Internet Explorer에서 폼의 단추를 클릭합니다.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 Default.aspx.cs, Default.aspx.vb 또는 Default.aspx의 중단점이 적중되어야 합니다.  
  
6.  완료 되 면 디버깅에 **디버그** 메뉴를 클릭 하 여 **디버깅 중지**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ASP.NET 응용 프로그램 디버그](../debugger/how-to-enable-debugging-for-aspnet-applications.md)