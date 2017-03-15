---
title: "ClickOnce를 사용하여 COM 구성 요소 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 배포, COM 구성 요소"
  - "COM 구성 요소, 배포"
  - "구성 요소, 배포"
  - "응용 프로그램 배포[ClickOnce], COM 구성 요소"
  - "등록이 필요 없는 COM 배포"
ms.assetid: 1a4c7f4c-7a41-45f2-9af4-8b1666469b89
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 12
---
# ClickOnce를 사용하여 COM 구성 요소 배포
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

레거시 COM 구성 요소 배포는 어려운 작업으로 여겨져 왔습니다.  구성 요소를 전역으로 등록해야 하므로 서로 중복되는 응용 프로그램 사이에 예기치 않은 결과가 발생할 수 있습니다.  구성 요소가 응용 프로그램에 완전히 격리되어 있거나 서로 병행하여 호환되는 .NET 응용 프로그램에서 이러한 상황은 일반적으로 문제가 되지 않습니다.  Visual Studio를 사용하면 Windows XP 이상의 운영 체제에 격리된 COM 구성 요소를 배포할 수 있습니다.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]를 사용하면 .NET 응용 프로그램을 쉽고 안전하게 배포할 수 있습니다.  그러나 응용 프로그램에서 레거시 COM 구성 요소를 사용하는 경우에는 추가 배포 단계를 수행해야 합니다.  이 항목에서는 격리된 COM 구성 요소 및 참조 기본 구성 요소\(예: Visual Basic 6.0 또는 Visual C\+\+의 구성 요소\)를 배포하는 방법을 설명합니다.  
  
 격리된 COM 구성 요소의 배포에 대한 자세한 내용은 [http:\/\/msdn.microsoft.com\/msdnmag\/issues\/05\/04\/RegFreeCOM\/default.aspx](http://msdn.microsoft.com/msdnmag/issues/05/04/RegFreeCOM/default.aspx)에 나오는 "Simplify App Deployment with [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] and Registration\-Free COM"을 참조하십시오.  
  
## 등록이 필요 없는 COM  
 등록이 필요 없는 COM은 격리된 COM 구성 요소를 배포하고 활성화하는 새로운 기술입니다.  이 기술은 일반적으로 시스템 레지스트리에 설치되는 모든 구성 요소의 형식 라이브러리와 등록 정보를 응용 프로그램과 같은 폴더에 저장되는 매니페스트라는 XML 파일에 넣는 작업입니다.  
  
 COM 구성 요소를 격리하려면 개발자의 컴퓨터에 COM 구성 요소를 등록해야 합니다. 그러나 최종 사용자의 컴퓨터에는 등록할 필요가 없습니다.  COM 구성 요소를 격리하기 위해서는 해당 참조의 **Isolated** 속성을 **True**로 설정하기만 하면 됩니다.  이 속성은 기본적으로 **False**로 설정되어 있으며, 이는 해당 COM 참조가 등록된 COM 참조처럼 처리되어야 함을 나타냅니다.  이 속성이 **True**인 경우에는 빌드할 때 이 구성 요소에 대해 매니페스트가 생성되며,  설치하는 동안 해당하는 파일이 응용 프로그램 폴더에 복사됩니다.  
  
 매니페스트 생성기에서 격리된 COM 참조를 발견하면 구성 요소의 형식 라이브러리에 모든 `CoClass` 엔트리를 열거하여, 각 엔트리와 해당하는 등록 데이터를 일치시키고 형식 라이브러리 파일의 모든 COM 클래스에 대해 매니페스트 정의를 생성합니다.  
  
## ClickOnce를 사용하여 등록이 필요 없는 COM 구성 요소 배포  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 기술은 격리된 COM 구성 요소의 배포에 매우 적합합니다. 왜냐하면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 및 등록이 필요 없는 COM 모두 구성 요소에 매니페스트가 있어야 배포할 수 있기 때문입니다.  
  
 일반적으로 매니페스트는 구성 요소를 만든 이가 제공합니다.  그러나 그렇지 않은 경우에는 Visual Studio에서 COM 구성 요소에 대해 매니페스트를 자동으로 생성할 수도 있습니다.  매니페스트 생성은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 게시 프로세스 동안 수행됩니다. 자세한 내용은 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)를 참조하십시오.  또한 이 기능을 사용하면 Visual Basic 6.0 같은 이전 개발 환경에서 만든 레거시 구성 요소를 활용할 수 있습니다.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서 COM 구성 요소를 배포하는 방법은 두 가지입니다.  
  
-   부트스트래퍼를 사용하여 COM 구성 요소를 배포합니다. 이 방법은 지원되는 모든 플랫폼에서 사용할 수 있습니다.  
  
-   등록이 필요 없는 COM이라고 하는 네이티브 구성 요소 격리 배포를 사용합니다.  그러나 이 방법은 Windows XP 이상의 운영 체제에서만 사용할 수 있습니다.  
  
### 간단한 COM 구성 요소의 격리 및 배포에 대한 예제  
 등록이 필요 없는 COM 구성 요소 배포를 보여 주기 위해, 이 예제에서는 Visual Basic 6.0을 사용하여 만든 격리된 네이티브 COM 구성 요소를 참조하는 Windows 기반 응용 프로그램을 Visual Basic으로 만든 다음 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]를 사용하여 이를 배포합니다.  
  
 먼저 네이티브 COM 구성 요소를 만들어야 합니다.  
  
##### 네이티브 COM 구성 요소를 만들려면  
  
1.  Visual Basic 6.0의 **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자에서 **Visual Basic** 노드를 선택하고 **ActiveX DLL** 프로젝트를 선택합니다.  **이름** 상자에 `VB6Hello`를 입력합니다.  
  
    > [!NOTE]
    >  등록이 필요 없는 COM에는 ActiveX DLL 및 ActiveX 컨트롤 프로젝트 형식만 지원됩니다. ActiveX EXE 및 ActiveX 문서 프로젝트 형식은 지원되지 않습니다.  
  
3.  **솔루션 탐색기**에서 **Class1.vb**를 두 번 클릭하여 텍스트 편집기를 엽니다.  
  
4.  Class1.vb에서 `New` 메서드에 대해 생성된 코드 뒤에 다음 코드를 추가합니다.  
  
    ```  
    Public Sub SayHello()  
       MsgBox "Message from the VB6Hello COM component"  
    End Sub  
    ```  
  
5.  구성 요소를 빌드합니다.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
> [!NOTE]
>  등록이 필요 없는 COM은 DLL 및 COM 컨트롤 프로젝트 형식만 지원합니다.  EXE 형식은 등록이 필요 없는 COM과 함께 사용할 수 없습니다.  
  
 이제 Windows 기반 응용 프로그램을 만들고 여기에 COM 구성 요소에 대한 참조를 추가할 수 있습니다.  
  
##### COM 구성 요소를 사용하여 Windows 기반 응용 프로그램을 만들려면  
  
1.  Visual Basic의 **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자에서 **Visual Basic** 노드를 선택하고 **Windows 응용 프로그램**을 선택합니다.  **이름** 상자에 `RegFreeComDemo`를 입력합니다.  
  
3.  **솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭하여 프로젝트 참조를 표시합니다.  
  
4.  **참조** 노드를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **참조 추가**를 선택합니다.  
  
5.  **참조 추가** 대화 상자에서 **찾아보기** 탭을 클릭하고 VB6Hello.dll을 찾아서 선택합니다.  
  
     **VB6Hello** 참조가 참조 목록에 나타납니다.  
  
6.  **도구 상자**를 가리키고 **단추** 컨트롤을 선택한 다음 **Form1** 폼으로 끌어서 놓습니다.  
  
7.  **속성** 창에서 단추의 **Text** 속성을 Hello로 설정합니다.  
  
8.  단추를 두 번 클릭하여 처리기 코드를 추가하고, 코드 파일에서 코드를 추가하여 처리기가 다음과 같이 표시되도록 합니다.  
  
    ```  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
        Dim VbObj As New VB6Hello.Class1  
        VbObj.SayHello()  
    End Sub  
    ```  
  
9. 응용 프로그램을 실행합니다.  **디버그** 메뉴에서 **디버깅 시작**을 클릭합니다.  
  
 그 다음에는 컨트롤을 격리시켜야 합니다.  응용 프로그램에서 사용하는 각 COM 구성 요소는 프로젝트에 COM 참조로 나타납니다.  이러한 참조는 **솔루션 탐색기** 창의 **참조** 노드 아래에 표시됩니다.  참조는 **프로젝트** 메뉴에서 **참조 추가** 명령을 사용하여 직접 추가하거나 ActiveX 컨트롤을 폼으로 끌어서 놓아 간접적으로 추가할 수 있습니다.  
  
 다음 단계에서는 COM 구성 요소를 격리시키는 방법과 격리된 컨트롤이 들어 있는 업데이트된 응용 프로그램을 게시하는 방법을 보여 줍니다.  
  
##### COM 구성 요소를 격리시키려면  
  
1.  **솔루션 탐색기**의 **참조** 노드에서 **VB6Hello** 참조를 선택합니다.  
  
2.  **속성** 창에서 **Isolated** 속성의 값을 **False**에서 **True**로 변경합니다.  
  
3.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
 F5 키를 누르면 응용 프로그램이 예상대로 작동되는데, 이제는 등록이 필요 없는 COM으로 실행됩니다.  이를 확인하려면 VB6Hello.dll 구성 요소의 등록을 해제하고 Visual Studio IDE 외부에서 RegFreeComDemo1.exe를 실행해 보십시오.  이제 단추를 클릭해도 계속 작동될 것입니다.  임시로 응용 프로그램 매니페스트 이름을 바꾸면 다시 실패하게 됩니다.  
  
> [!NOTE]
>  COM 구성 요소의 등록을 임시로 해제하면 이 구성 요소가 없는 상태를 시뮬레이션할 수 있습니다.  명령 프롬프트를 열고 `cd /d %windir%\system32`를 입력하여 시스템 폴더로 이동한 다음 `regsvr32 /u VB6Hello.dll`을 입력하여 구성 요소의 등록을 해제합니다.  `regsvr32 VB6Hello.dll`을 입력하면 구성 요소를 다시 등록할 수 있습니다.  
  
 마지막 단계는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]를 사용하여 응용 프로그램을 게시하는 작업입니다.  
  
##### 격리된 COM 구성 요소를 사용하여 응용 프로그램 업데이트를 게시하려면  
  
1.  **빌드** 메뉴에서 **RegFreeComDemo 게시**를 클릭합니다.  
  
     게시 마법사가 나타납니다.  
  
2.  게시 마법사에서 게시된 파일을 액세스하고 검사할 수 있는 로컬 컴퓨터 디스크의 위치를 지정합니다.  
  
3.  **마침**을 클릭하여 응용 프로그램을 게시합니다.  
  
 게시된 파일을 검사해 보면 sysmon.ocx 파일이 포함되어 있는 것을 알 수 있습니다.  컨트롤은 이 응용 프로그램에 완전히 격리되어 있습니다. 즉, 최종 사용자의 컴퓨터에 해당 컨트롤의 다른 버전을 사용한 다른 응용 프로그램이 있더라도 이 응용 프로그램과 충돌하지 않습니다.  
  
## 네이티브 어셈블리 참조  
 Visual Studio에서는 네이티브 Visual Basic 6.0 또는 C\+\+ 어셈블리에 대한 참조를 지원합니다. 이러한 참조를 네이티브 참조라고 합니다.  **파일 형식** 속성이 **Native**로 설정되어 있는지 또는 **ActiveX**로 설정되어 있는지 확인하여 참조가 네이티브인지 구별할 수 있습니다.  
  
 네이티브 참조를 추가하려면 **참조 추가** 명령을 사용한 다음 매니페스트를 찾습니다.  일부 구성 요소는 매니페스트가 DLL 내에 있습니다.  이러한 경우 DLL을 선택하기만 하면 Visual Studio에서 구성 요소에 매니페스트가 포함되어 있음이 감지되어 해당 구성 요소가 네이티브 참조로 추가됩니다.  또한 Visual Studio에서는 매니페스트에 나열된 독립 파일 또는 어셈블리가 참조된 구성 요소와 같은 폴더에 있는 경우 자동으로 포함시킵니다.  
  
 COM 컨트롤 격리를 사용하면 매니페스트가 없는 COM 구성 요소를 배포하기가 쉬워집니다.  그러나 구성 요소가 매니페스트와 함께 제공되면 매니페스트를 직접 참조할 수 있습니다.  실제로 **Isolated** 속성을 사용하는 것보다 가능하면 구성 요소를 만든 이가 제공하는 매니페스트를 사용하는 것이 가장 좋습니다.  
  
## 등록이 필요 없는 COM 구성 요소 배포의 제한 사항  
 등록이 필요 없는 COM은 일반적인 배포 방법에 비해 확실한 이점을 갖고 있습니다.  그러나 여기에도 몇 가지 제한 사항 및 주의 사항이 있습니다.  가장 큰 제한은 Windows XP 이상에서만 사용 가능하다는 점입니다.  등록이 필요 없는 COM을 구현하려면 핵심 운영 체제에 구성 요소를 로드하는 방법을 변경해야 합니다.  그러나 등록이 필요 없는 COM에 대해서는 하위 수준의 지원 계층이 없습니다.  
  
 모든 구성 요소가 등록이 필요 없는 COM를 구현하는 데 적합한 것은 아닙니다.  다음과 같은 경우에 해당하면 적합한 구성 요소가 아닙니다.  
  
-   구성 요소가 out\-of\-process 서버입니다.  EXE 서버는 지원되지 않으며 DLL만 지원됩니다.  
  
-   구성 요소가 운영 체제의 일부이거나, XML, Internet Explorer 또는 MDAC\(Microsoft Data Access Components\)와 같은 시스템 구성 요소입니다.  구성 요소를 만든 이의 재배포 정책을 따르는 것이 좋습니다. 공급업체에 문의하십시오.  
  
-   구성 요소가 Microsoft Office와 같은 응용 프로그램의 일부입니다.  예를 들어, Microsoft Excel 개체 모델은 격리시키면 안 됩니다.  이것은 Office의 일부로, 전체 Office 제품을 컴퓨터에 설치해야만 사용할 수 있기 때문입니다.  
  
-   구성 요소가 Office 추가 기능이나 웹 브라우저의 컨트롤과 같은 추가 기능이나 스냅인으로 사용됩니다.  이러한 구성 요소를 사용하려면 대개 매니페스트의 범위를 벗어나는 호스팅 환경에 의해 정의되는 몇 가지 등록 체계가 필요합니다.  
  
-   구성 요소가 인쇄 스풀러의 장치 드라이버와 같은 시스템의 실제 또는 가상 장치를 관리합니다.  
  
-   구성 요소가 데이터 액세스 재배포 가능 요소입니다.  일반적으로 데이터 응용 프로그램은 별도의 데이터 액세스 재배포 가능 요소를 설치해야 실행될 수 있습니다.  Microsoft ADO Data Control, Microsoft OLE DB 또는 MDAC\(Microsoft Data Access Components\)와 같은 구성 요소는 격리시키지 않는 것이 좋습니다.  대신 응용 프로그램에서 MDAC 또는 SQL Server Express를 사용하는 경우 이를 필수 구성 요소로 설정하는 것이 좋습니다. [방법: ClickOnce 응용 프로그램을 사용하여 필수 구성 요소 설치](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)를 참조하십시오.  
  
 경우에 따라 구성 요소의 개발자는 등록이 필요 없는 COM을 위해 구성 요소를 다시 디자인할 수 있습니다.  다시 디자인할 수 없더라도 부트스트래퍼를 사용하여 표준 등록 체계를 통해 구성 요소를 사용하는 응용 프로그램을 빌드하고 게시할 수 있습니다.  자세한 내용은 [부트스트래퍼 패키지 만들기](../deployment/creating-bootstrapper-packages.md)를 참조하십시오.  
  
 COM 구성 요소는 응용 프로그램별로 한 번만 격리시킬 수 있습니다.  예를 들어, 같은 응용 프로그램의 일부인 두 개의 서로 다른 **클래스 라이브러리** 프로젝트에서 같은 COM 구성 요소를 격리할 수 없습니다.  이렇게 하면 빌드 경고가 발생하고 런타임에 응용 프로그램이 로드되지 않습니다.  이 문제를 해결하기 위해 Microsoft에서는 COM 구성 요소를 단일 클래스 라이브러리에 캡슐화할 것을 권장합니다.  
  
 응용 프로그램의 배포에는 등록이 필요하지 않지만 개발자의 컴퓨터에서 COM 등록을 수행해야 하는 경우도 있습니다.  `Isolated` 속성을 사용하려면 개발자의 컴퓨터에 COM 구성 요소를 등록해야 빌드하는 동안 매니페스트가 자동으로 생성됩니다.  빌드하는 동안 자동 등록을 호출하는 등록 캡처 기능은 없습니다.  또한 형식 라이브러리에 명시적으로 정의되지 않은 클래스는 매니페스트에 반영되지 않습니다.  네이티브 참조와 같이 기존 매니페스트가 있는 COM 구성 요소를 사용하는 경우 개발할 때 구성 요소를 등록하지 않을 수 있습니다.  그러나 구성 요소가 ActiveX 컨트롤이고 이 구성 요소를 **도구 상자** 및 Windows Forms 디자이너에 포함하려는 경우는 반드시 등록해야 합니다.  
  
## 참고 항목  
 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)