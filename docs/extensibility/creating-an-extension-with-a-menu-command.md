---
title: "메뉴 명령을 사용 하 여 확장을 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- write a vspackage
- vspackage
- tutorials
- visual studio package
ms.assetid: f97104c8-2bcb-45c7-a3c9-85abeda8df98
caps.latest.revision: "56"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3e9f72764d8fc87a9605f3bde20b7b2b93f44f39
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="creating-an-extension-with-a-menu-command"></a>메뉴 명령을 사용 하 여 확장 만들기
이 연습에서는 메모장을 실행 하는 메뉴 명령을 사용 하 여 확장을 만드는 방법을 보여 줍니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-a-menu-command"></a>메뉴 명령 만들기  
  
1.  라는 VSIX 프로젝트를 **FirstMenuCommand**합니다. VSIX 프로젝트 템플릿을 찾을 수 있습니다는 **새 프로젝트** 대화 상자의 **Visual C# / 확장성**합니다.  
  
2.  프로젝트를 열 때 명명 된 사용자 지정 명령 항목 템플릿을 추가 **FirstCommand**합니다. 에 **솔루션 탐색기**프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 / 새 항목**합니다. 에 **새 항목 추가** 대화 상자에서로 이동 **Visual C# / 확장성** 선택 **사용자 지정 명령**합니다. 에 **이름** 창의 맨 아래에 필드에서 명령 파일 이름을 변경한 **FirstCommand.cs**합니다.  
  
3.  프로젝트를 빌드하고 디버깅을 시작합니다.  
  
     Visual Studio의 실험적 인스턴스가 표시 됩니다. 실험적 인스턴스에 대 한 자세한 내용은 참조 [의 실험적 인스턴스](../extensibility/the-experimental-instance.md)합니다.  
  
4.  실험적 인스턴스를 열고는 **도구 / 확장명 및 업데이트** 창. 표시 됩니다는 **FirstMenuCommand** 여기 확장 합니다. (열면 **확장명 및 업데이트** Visual Studio에 해당 하는 작업 인스턴스를에 표시 되지 않습니다 **FirstMenuCommand**).  
  
     이제는 **도구** 실험적 인스턴스에서 메뉴. 표시 되어야 **호출 FirstCommand** 명령입니다. 이 시점에서 방금 나타납니다 "FirstCommandPackage 내 FirstMenuCommand.FirstCommand.MenuItemCallback()" 라고 표시 하는 메시지 상자. 실제로이 명령에는 다음 섹션에서 메모장을 시작 하는 방법을 살펴보겠습니다.  
  
## <a name="changing-the-menu-command-handler"></a>메뉴 명령 처리기를 변경합니다.  
 이제 메모장을 시작 하려면 명령 처리기를 업데이트 합니다.  
  
1.  디버깅을 중지 하 고 Visual Studio 인스턴스의 작업으로 돌아갑니다. FirstCommand.cs 파일을 열고 다음 추가 문을 사용 하 여:  
  
    ```csharp  
    using System.Diagnostics;  
    ```  
  
2.  개인 FirstCommand 생성자를 찾습니다. 여기서 명령 명령 서비스에 연결 되어와 명령 처리기 지정입니다. 다음과 같이 StartNotepad에 명령 처리기의 이름을 변경 합니다.  
  
    ```csharp  
    private FirstCommand(Package package)  
    {  
        if (package == null)  
        {  
            throw new ArgumentNullException(nameof(package));  
        }  
  
        this.package = package;  
  
         OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
        if (commandService != null)  
        {  
            CommandID menuCommandID = new CommandID(CommandSet, CommandId);  
            // Change to StartNotepad handler.  
            MenuCommand menuItem = new MenuCommand(this.StartNotepad, menuCommandID);  
            commandService.AddCommand(menuItem);  
        }  
    }  
    ```  
  
3.  MenuItemCallback 메서드를 제거 하 고 메모장을 방금 시작 StartNotepad 메서드 추가:  
  
    ```csharp  
    private void StartNotepad(object sender, EventArgs e)  
    {  
        Process proc = new Process();  
        proc.StartInfo.FileName = "notepad.exe";  
        proc.Start();  
    }  
    ```  
  
4.  이제 사용해 보세요. 프로젝트 디버깅을 시작 하 고 클릭 **도구 / 호출 FirstCommand**를 이루는 메모장의 인스턴스를 표시 됩니다.  
  
     인스턴스를 사용할 수는 <xref:System.Diagnostics.Process> 메모장 뿐 아니라 모든 실행 파일을 실행 하는 클래스입니다. 예를 들어, calc.exe로 시도 합니다.  
  
## <a name="cleaning-up-the-experimental-environment"></a>실험적 환경 정리  
 여러 확장을 개발 하는 경우에 확장 프로그램 코드의 다른 버전으로 결과 탐색, 실험 환경 예상 대로 작동 하지 않을 수 있습니다. 이 경우 원래 대로 스크립트를 실행 해야 합니다. 호출 될 **Visual Studio 2015 실험적 인스턴스 다시 설정**, 하며 Visual Studio SDK의 일부분으로 포함 합니다. 이 스크립트는 처음부터 다시 시작할 수 있도록 실험 환경에서 확장 프로그램에 대 한 모든 참조를 제거 합니다.  
  
 두 가지 방법 중 하나에이 스크립트를 얻을 수 있습니다.  
  
1.  바탕 화면에서 찾을 **Visual Studio 2015 실험적 인스턴스 다시 설정**합니다.  
  
2.  명령줄에서 다음을 실행 합니다.  
  
    ```  
    <VSSDK installation>\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe /Reset /VSInstance=14.0 /RootSuffix=Exp && PAUSE  
  
    ```  
  
## <a name="deploying-your-extension"></a>확장 배포  
 이제 도구 확장을 실행 하는 원하는 방식으로 사용자가 동료 및 친구와 공유에 대해 생각 하는 시간입니다. 쉽습니다, Visual Studio 2015가 설치를 보유 합니다. 빌드한.vsix 파일을 보내거나 하면 됩니다. (있어야 릴리스 모드에서 빌드할 수 있습니다.)  
  
 FirstMenuCommand bin 디렉터리에이 확장에 대 한.vsix 파일을 찾을 수 있습니다. 특히, 릴리스 구성 구축한 라고 가정할 경우 됩니다.  
  
 **\<코드 디렉터리 > \FirstMenuCommand\FirstMenuCommand\bin\Release\ FirstMenuCommand.vsix**  
  
 친구 필요한 확장을 설치 하려면 Visual Studio의 열려 있는 모든 인스턴스를 닫고 다음을 표시 하는.vsix 파일을 두 번 클릭 하 고 **VSIX 설치 관리자**합니다. 파일에 복사 되 고 **%LocalAppData%\Microsoft\VisualStudio\14.0\Extensions** 디렉터리입니다.  
  
 친구 Visual Studio를 다시 제공 하는 경우에에서 FirstMenuCommand 확장을 찾을 수 그 **도구 / 확장명 및 업데이트**합니다. 으로 이동할 수는 그 **확장명 및 업데이트** 를 제거 하거나 너무 확장명을 사용 하지 않도록 설정 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 연습에서는 Visual Studio 확장으로 수행할 수 있는의 작은 부분만을 살펴보았습니다. 다른 (상당히 쉽게) 수행할 수 있는 Visual Studio 확장과 짧은 목록을 다음과 같습니다.  
  
1.  더 많은 작업이 간단한 메뉴 명령 사용 하 여 수행할 수 있습니다.  
  
    1.  추가 사용자 고유의 아이콘: [메뉴 명령에 아이콘 추가](../extensibility/adding-icons-to-menu-commands.md)  
  
    2.  메뉴 명령의 텍스트 변경: [메뉴 명령의 텍스트를 변경 합니다.](../extensibility/changing-the-text-of-a-menu-command.md)  
  
    3.  메뉴 바로 가기 명령에 추가: [메뉴 항목에 바로 가기 키 바인딩](../extensibility/binding-keyboard-shortcuts-to-menu-items.md)  
  
2.  다른 종류의 명령, 메뉴 및 도구 모음 추가: [확장 메뉴 및 명령](../extensibility/extending-menus-and-commands.md)  
  
3.  도구 창을 추가 하 고 기본 제공 Visual Studio 도구 창 확장: [확장 및 사용자 지정 도구 창](../extensibility/extending-and-customizing-tool-windows.md)  
  
4.  IntelliSense, 코드 제안 사항을 추가 하 고 다른 기능을 기존 코드 편집기: [편집기와 언어 서비스를 확장 합니다.](../extensibility/extending-the-editor-and-language-services.md)  
  
5.  확장 프로그램에 옵션 및 속성 페이지 및 사용자 설정 추가: [확장 속성 및 속성 창](../extensibility/extending-properties-and-the-property-window.md) 및 [확장 사용자 설정 및 옵션](../extensibility/extending-user-settings-and-options.md)  
  
 다른 종류의 확장은 새로운 유형의 프로젝트를 만들 때 처럼 좀 더 많은 작업이 필요한 지 ([확장 프로젝트](../extensibility/extending-projects.md)), 새 유형의 편집기 만들기 ([만드는 사용자 지정 편집기 및 디자이너](../extensibility/creating-custom-editors-and-designers.md)), 또는 격리 셸에서 확장 프로그램 구현: [Visual Studio 격리 셸](../extensibility/visual-studio-isolated-shell.md)