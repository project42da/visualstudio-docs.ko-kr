---
title: "격리 된 셸 확장 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Visual Studio shell 격리 모드"
ms.assetid: 9a641d8f-211e-4486-a1b1-4a89fafe7ee8
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# 격리 된 셸 확장
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

격리 된 셸 응용 프로그램에 VSPackage, 프레임 워크 MEF \(Managed Extensibility\) 구성 요소 부분 또는 일반 VSIX 프로젝트를 추가 하 여 Visual Studio isolated shell을 확장할 수 있습니다.  
  
> [!NOTE]
>  다음 단계는 Visual Studio Shell 격리 된 프로젝트 템플릿을 사용 하 여 기본 격리 된 셸 응용 프로그램을 만든 presuppose 합니다. 이 프로젝트 템플릿에 대 한 자세한 내용은 참조 [연습: 기본 격리 된 셸 응용 프로그램 만들기](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)합니다.  
  
## Visual Studio 패키지 프로젝트 템플릿의 위치  
 Visual Studio 패키지 프로젝트 템플릿은 **새 프로젝트** 대화 상자의 세 가지 서로 다른 위치에 있습니다.  
  
1.  아래에서 **Visual Basic**, **확장성**합니다. 프로젝트의 기본 언어는 Visual Basic입니다.  
  
2.  아래에서 **Visual C\#**, **확장성**합니다. 프로젝트의 기본 언어는 C\#입니다.  
  
3.  아래에서 **기타 프로젝트 형식**, **확장성**합니다. 프로젝트의 기본 언어는 C\+\+입니다.  
  
## VSPackage를 추가합니다.  
 VSPackage 격리 된 셸 응용 프로그램에 추가할 수 있습니다. 다음 단계에는 메뉴 명령을 추가 하는 하나를 만드는 방법을 보여 줍니다.  
  
#### 새 VSPackage를 추가 하려면  
  
1.  라는 Visual Studio 패키지 프로젝트를 추가 `MenuCommandsPackage`합니다.  
  
2.  에 **VSPackage 기본 정보** 마법사의 페이지 설정 **회사 이름** 를 `Fabrikam` 및 **VSPackage 이름** 를 `FabrikamMenuCommands`합니다.**다음** 단추를 선택합니다.  
  
3.  다음 페이지에서 선택 **메뉴 명령** 선택 **다음**합니다.  
  
4.  다음 페이지에서 설정 **명령 이름** 를 `Fabrikam Command` 및 **명령 ID** 를 `cmdidFabrikamCommand`, 를 선택한 다음 **다음**합니다.  
  
5.  에 **테스트 프로젝트 옵션을 선택** 페이지에서 테스트 옵션을 해제 한 다음 선택는 **마침** 단추입니다.  
  
6.  ShellExtensionsVSIX 프로젝트에서 source.extension.vsixmanifest 파일을 엽니다.  
  
     **자산** 섹션 VSShellStub.AboutBoxPackage 프로젝트에 대 한 항목이 포함 되어야 합니다.  
  
7.  **새로 만들기** 단추를 선택합니다.  
  
8.  에 **새 자산 추가** 창에는 **형식** 목록에서 **Microsoft.VisualStudio.VsPackage**합니다.  
  
9. 에 **소스** 나열 되어 있는지 확인 합니다 **현재 솔루션의 프로젝트** 을 선택 합니다. 에 **프로젝트** 목록 상자 **MenuCommandsPackage**합니다.  
  
10. 파일을 저장한 후 닫습니다.  
  
11. 솔루션을 빌드하고 격리 된 셸 디버깅을 시작 합니다.  
  
12. 메뉴 모음에서 **도구** 메뉴, **Fabrikam 명령**합니다.  
  
     메시지 상자가 표시 됩니다.  
  
13. 응용 프로그램 디버깅을 중지 합니다.  
  
## MEF 구성 요소 파트를 추가합니다.  
 다음 단계에는 격리 된 셸 응용 프로그램에 MEF 구성 요소 부분을 추가 하는 방법을 보여 줍니다.  
  
#### MEF 구성 요소를 추가 하려면  
  
1.  에 **새 프로젝트 추가** 대화 상자의 **Visual C\#**, **확장성**, 사용 하 여는 **편집기 여백을** 서식 파일을 프로젝트에 추가 합니다. 이 EventHandler의 이름을 `ShellEditorMargin`로 지정합니다.  
  
2.  ShellExtensionsVSIX 프로젝트에서 코드 뷰가 아니라 디자인 보기에서 Source.extension.vsixmanifest 파일을 엽니다.  
  
3.  에 `Asset` 섹션에서 선택 **콘텐츠 추가**합니다.  
  
4.  에 **새 자산 추가** 창에는 **형식** 목록에서 **Microsoft.VisualStudio.MefComponent**합니다.  
  
5.  에 **소스** 나열 되어 있는지 확인 합니다 **현재 솔루션의 프로젝트** 을 선택 합니다. 에 **프로젝트** 목록 상자 **ShellEditorMargin**합니다.  
  
6.  파일을 저장한 후 닫습니다.  
  
7.  솔루션을 빌드하고 격리 된 셸 디버깅을 시작 합니다.  
  
8.  텍스트 파일을 엽니다.  
  
     "Hello world\!" 단어가 포함 된 녹색 여백 텍스트 파일 창 맨 아래에 표시 되어야 합니다.  
  
9. 응용 프로그램 디버깅을 중지 합니다.  
  
## 일반 VSIX 프로젝트를 추가합니다.  
  
#### 일반 VSIX 프로젝트를 추가 하려면  
  
1.  에 **새 프로젝트 추가** 대화 상자의 **Visual C\#**, **확장성**, 사용 하 여는 **VSIXProject** 서식 파일을 프로젝트에 추가 합니다. 이 EventHandler의 이름을 `EmptyVSIX`로 지정합니다.  
  
2.  ShellExtensionsVSIX 프로젝트에서 코드 뷰가 아니라 디자인 뷰에서 Source.extensions.vsixmanifest 파일을 엽니다.  
  
3.  에 `Assets` 섹션에서 선택 **새로**합니다.  
  
4.  에 **새 자산 추가** 창에는 **형식** 목록에서 추가 하려는 콘텐츠의 종류를 선택 합니다.  
  
5.  **소스**, 다음 사항을 확인는 **현재 솔루션의 프로젝트** 옵션을 선택 합니다. 목록 상자에서 VSIX 프로젝트의 이름을 선택 합니다.  
  
6.  파일을 저장한 후 닫습니다.  
  
7.  이 프로젝트는 컴파일된 코드를 포함 하는 경우 해당 어셈블리는 출력에 포함 되도록 프로젝트를 편집 해야 합니다.  
  
    1.  VSIX 프로젝트를 언로드한 프로젝트 파일을 엽니다.  
  
    2.  첫 번째에서 `<PropertyGroup>` 차단의 값을 변경 `<CopyBuildOutputToOutputDirectory>` 를 `true`합니다.  
  
    3.  저장 하 고 프로젝트를 다시 로드 합니다.  
  
8.  솔루션을 빌드하고 실행합니다.  
  
## 참고 항목  
 [연습: 기본 격리 된 셸 응용 프로그램 만들기](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)