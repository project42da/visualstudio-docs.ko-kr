---
title: "방법: 빌드 이벤트 지정(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "빌드 이벤트[Visual Studio]"
  - "빌드[Visual Studio], 이벤트"
  - "이벤트[Visual Studio], 빌드"
  - "빌드 후 이벤트"
  - "빌드 전 이벤트"
ms.assetid: 40dc83bf-a7c5-4a14-816a-fa0980b6e4c3
caps.latest.revision: 26
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 26
---
# 방법: 빌드 이벤트 지정(Visual Basic)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Basic의 빌드 이벤트를 사용하면 스크립트, 매크로 또는 기타 작업을 컴파일 프로세스의 일부로 실행할 수 있습니다.  컴파일 전에는 빌드 전 이벤트가 발생하고, 컴파일 후에는 빌드 후 이벤트가 발생합니다.  
  
 빌드 이벤트는 **프로젝트 디자이너**의 **컴파일** 페이지에서 액세스할 수 있는 **빌드 이벤트** 대화 상자에서 지정됩니다.  
  
> [!NOTE]
>  Visual Basic Express 항목의 빌드 이벤트를 지원 하지 않습니다.  이러한 디버깅은 전체 Visual Studio 제품에서만 지원됩니다.  
  
## 빌드 전 이벤트 및 빌드 후 이벤트 지정 방법  
  
#### 빌드 이벤트를 지정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **컴파일** 탭을 클릭합니다.  
  
3.  **빌드 이벤트** 단추를 클릭하여 **빌드 이벤트** 대화 상자를 엽니다.  
  
4.  빌드 전 작업이나 빌드 후 작업의 명령줄 인수를 입력한 다음 **확인**을 클릭합니다.  
  
    > [!NOTE]
    >  .bat 파일을 실행하는 모든 빌드 후 명령 앞에 `call` 문을 추가하십시오.  예를 들면 `call C:\MyFile.bat` 또는 `call C:\MyFile.bat call C:\MyFile2.bat`를 사용할 수 있습니다.  
  
    > [!NOTE]
    >  빌드 전 또는 빌드 후 이벤트가 성공적으로 완료되지 않은 경우 성공적인 동작을 나타내는 0 이외의 코드로 이벤트 동작이 종료되도록 하여 빌드를 종료할 수 있습니다.  
  
## 예제: 빌드 후 이벤트를 사용하여 매니페스트 정보를 변경하는 방법  
 다음 절차에서는 빌드 후 이벤트에서 호출되는 .exe 명령을 사용하여 응용 프로그램 매니페스트\(프로젝트 디렉터리의 .exe.manifest 파일\)에서 최소 운영 체제 버전을 설정하는 방법을 보여 줍니다.  최소 운영 체제 버전은 4.10.0.0과 같이 네 부분으로 구성된 번호입니다.  이를 위해 명령에서 매니페스트의 `<dependentOS>` 섹션을 변경합니다.  
  
```  
<dependentOS>  
   <osVersionInfo>  
      <os majorVersion="4" minorVersion="10" buildNumber="0" servicePackMajor="0" />  
   </osVersionInfo>  
</dependentOS>  
```  
  
#### 응용 프로그램 매니페스트를 변경하기 위해 .exe 명령을 만들려면  
  
1.  명령에 대한 콘솔 응용 프로그램을 만듭니다.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자의 **Visual Basic** 노드에서 **Windows**와 **콘솔 응용 프로그램** 템플릿을 차례로 선택합니다.  프로젝트 이름을 `ChangeOSVersionVB`로 지정합니다.  
  
3.  Module1.vb에서 파일의 맨 위에 있는 다른 `Imports` 문에 다음 줄을 추가합니다.  
  
    ```  
    Imports System.Xml  
    ```  
  
4.  `Sub Main`에서 다음 코드를 추가합니다.  
  
    ```  
    Sub Main()  
       Dim applicationManifestPath As String  
       applicationManifestPath = My.Application.CommandLineArgs(0)  
       Console.WriteLine("Application Manifest Path: " & applicationManifestPath.ToString)  
  
       'Get version name  
       Dim osVersion As Version  
       If My.Application.CommandLineArgs.Count >= 2 Then  
          osVersion = New Version(My.Application.CommandLineArgs(1).ToString)  
       Else  
          Throw New ArgumentException("OS Version not specified.")  
       End If  
       Console.WriteLine("Desired OS Version: " & osVersion.ToString())  
  
       Dim document As XmlDocument  
       Dim namespaceManager As XmlNamespaceManager  
       namespaceManager = New XmlNamespaceManager(New NameTable())  
       With namespaceManager  
          .AddNamespace("asmv1", "urn:schemas-microsoft-com:asm.v1")  
          .AddNamespace("asmv2", "urn:schemas-microsoft-com:asm.v2")  
       End With  
  
       document = New XmlDocument()  
       document.Load(applicationManifestPath)  
  
       Dim baseXPath As String  
       baseXPath = "/asmv1:assembly/asmv2:dependency/asmv2:dependentOS/asmv2:osVersionInfo/asmv2:os"  
  
       'Change minimum required OS Version.  
       Dim node As XmlNode  
       node = document.SelectSingleNode(baseXPath, namespaceManager)  
       node.Attributes("majorVersion").Value = osVersion.Major.ToString()  
       node.Attributes("minorVersion").Value = osVersion.Minor.ToString()  
       node.Attributes("buildNumber").Value = osVersion.Build.ToString()  
       node.Attributes("servicePackMajor").Value = osVersion.Revision.ToString()  
  
       document.Save(applicationManifestPath)  
    End Sub  
    ```  
  
     이 명령은 두 개의 인수를 사용합니다.  그 중 하나는 응용 프로그램 매니페스트의 경로, 즉 빌드 프로세스에서 매니페스트가 생성되는 폴더로서 대개 Projectname.publish이고  나머지 하나는 새 운영 체제 버전입니다.  
  
5.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
6.  `C:\TEMP\ChangeOSVersionVB.exe`와 같이 디렉터리에 .exe 파일을 복사합니다.  
  
 다음으로는 빌드 후 이벤트에서 이 명령을 호출하여 응용 프로그램 매니페스트를 변경합니다.  
  
#### 빌드 후 이벤트를 호출하여 응용 프로그램 매니페스트를 변경하려면  
  
1.  게시할 프로젝트에 대한 Windows 응용 프로그램을 만듭니다.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자의 **Visual Basic** 노드에서 **Windows**와 **Windows 응용 프로그램** 템플릿을 차례로 선택합니다.  프로젝트 이름을 `VBWinApp`로 지정합니다.  
  
3.  **솔루션 탐색기**에서 프로젝트를 선택하고 **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
4.  프로젝트 디자이너에서 **게시** 페이지로 이동하고 **게시 위치**를 `C:\TEMP\`로 설정합니다.  
  
5.  **지금 게시**를 클릭하여 프로젝트를 게시합니다.  
  
     매니페스트 파일이 빌드되어 `C:\TEMP\VBWinApp_1_0_0_0\VBWinApp.exe.manifest`로 배치됩니다.  매니페스트 파일을 보려면 파일을 마우스 오른쪽 단추로 클릭하고 **연결 프로그램**, **목록에서 프로그램 선택**, **Notepad**를 차례로 클릭합니다.  
  
     파일에서 `<osVersionInfo>` 요소를 검색합니다.  예를 들면 버전은 다음과 같습니다.  
  
    ```  
    <os majorVersion="4" minorVersion="10" buildNumber="0" servicePackMajor="0" />  
    ```  
  
6.  프로젝트 디자이너에서 **컴파일** 탭으로 이동하고 **빌드 이벤트** 단추를 클릭하여 **빌드 이벤트** 대화 상자를 엽니다.  
  
7.  **빌드 후 이벤트 명령줄** 상자에 다음 명령을 입력합니다.  
  
     `C:\TEMP\ChangeOSVersionVB.exe "$(TargetPath).manifest" 5.1.2600.0`  
  
     프로젝트를 빌드하면 이 명령이 응용 프로그램 매니페스트의 최소 운영 체제 버전을 5.1.2600.0으로 변경합니다.  
  
     `$(TargetPath)` 매크로는 작성 중인 실행 파일의 전체 경로를 나타냅니다.  그러므로 $\(TargetPath\).manifest는 bin 디렉터리에 만들어지는 응용 프로그램 매니페스트를 지정합니다.  게시하면 위에서 설정한 게시 위치에 이 매니페스트가 복사됩니다.  
  
8.  프로젝트를 다시 게시합니다.  **게시** 페이지로 이동하고 **지금 게시**를 클릭합니다.  
  
     매니페스트를 다시 봅니다.  매니페스트 파일을 보려면 게시 디렉터리로 이동하여 파일을 마우스 오른쪽 단추로 클릭한 다음 **연결 프로그램**, **목록에서 프로그램 선택**, **Notepad**를 차례로 클릭합니다.  
  
     버전은 다음과 같아야 합니다.  
  
    ```  
    <os majorVersion="5" minorVersion="1" buildNumber="2600" servicePackMajor="0" />  
    ```  
  
## 참고 항목  
 [Managing Compilation Properties](http://msdn.microsoft.com/ko-kr/94308881-f10f-4caf-a729-f1028e596a2c)   
 [프로젝트 디자이너, 컴파일 페이지\(Visual Basic\)](../ide/reference/compile-page-project-designer-visual-basic.md)   
 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)   
 [빌드 전 이벤트\/빌드 후 이벤트 명령줄 대화 상자](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)   
 [방법: 빌드 이벤트 지정\(C\#\)](../ide/how-to-specify-build-events-csharp.md)