---
title: Clickonce COM 구성 요소 배포 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- registration-free COM deployment
- ClickOnce deployment, COM components
- COM components, deploying
- deploying applications [ClickOnce], COM components
- components, deploying
ms.assetid: 1a4c7f4c-7a41-45f2-9af4-8b1666469b89
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ab25276596358f7c0a8c1f90bd38e89686e3196c
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815875"
---
# <a name="deploying-com-components-with-clickonce"></a>ClickOnce를 사용하여 COM 구성 요소 배포
일반적으로 레거시 COM 구성 요소 배포는 어려운 작업 이었습니다. 구성 요소는 전역으로 등록 해야 하 고 따라서 잘못 된 결과가 겹치는 응용 프로그램 간에 발생할 수 있습니다. 이 상황은 일반적으로.NET Framework 응용 프로그램에 문제가 구성 요소 응용 프로그램에 완전히 격리 되어 있거나-나란히 호환 가능 하기 때문입니다. Visual Studio를 사용 하면 Windows XP 또는 더 높은 운영 체제에서 격리 된 COM 구성 요소를 배포할 수 있습니다.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] .NET 응용 프로그램을 배포 하기 위한 쉽고 안전 하 게 보호 메커니즘을 제공 합니다. 그러나 레거시 COM 구성 요소를 사용 하는 응용 프로그램을 배포 하기 위한 추가 단계를 수행 해야 합니다. 이 항목에서는 독립 된 COM 구성 요소를 배포 하 고 (예를 들어 Visual Basic 6.0 또는 Visual c + +)에서 네이티브 구성 요소를 참조 하는 방법에 설명 합니다.  
  
 격리 된 COM 구성 요소를 배포 하는 방법에 대 한 자세한 내용은 참조 하십시오. "인 응용 프로그램 배포를 단순화 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 및 등록이 필요 없는 COM"에서 [ http://msdn.microsoft.com/msdnmag/issues/05/04/RegFreeCOM/default.aspx ](http://msdn.microsoft.com/msdnmag/issues/05/04/RegFreeCOM/default.aspx)합니다.  
  
## <a name="registration-free-com"></a>등록이 필요 없는 COM  
 등록이 필요 없는 COM는 배포 하 고 독립 된 COM 구성 요소를 활성화에 대 한 새 기술입니다. 모든 구성 요소의 형식 라이브러리와은 일반적으로 매니페스트 라는 XML 파일에 시스템 레지스트리에 등록 정보를 배치 하 여 작동 응용 프로그램과 같은 폴더에 저장 합니다.  
  
 COM 구성 요소 격리 클래스가 개발자의 컴퓨터에 등록 되어야 하는데 최종 사용자의 컴퓨터에 등록 하지 않아도입니다. COM 구성 요소를 격리 하려면 해당 참조 설정 하기만 하면 **격리 됨** 속성을 **True**합니다. 기본적으로이 속성 설정 **False**, 등록 된 COM 참조로 처리 되어야 함을 나타냅니다. 이 속성이 **True**를 빌드 시이 구성 요소에 대해 생성 되는 매니페스트를 수행 합니다. 에 해당 파일을 설치 하는 동안 응용 프로그램 폴더에 복사 됩니다.  
  
 매니페스트 생성기 격리 된 COM 참조를 발견 하면 모든 열거는 `CoClass` 각 항목의 해당 등록 데이터를 일치 하 고 생성 하는 구성 요소의 형식 라이브러리에 항목 매니페스트 모든 COM에 대 한 정의 형식 라이브러리 파일의 클래스를 제공 합니다.  
  
## <a name="deploying-registration-free-com-components-using-clickonce"></a>ClickOnce를 사용 하는 등록이 필요 없는 COM 구성 요소 배포  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 기술은 독립 된 COM 구성 요소를 배포 하는 데 적합 하기 때문에 둘 다 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 등록이 필요 없는 COM 구성 요소 배포 하려면 매니페스트를가 필요 합니다.  
  
 일반적으로 구성 요소의 작성자는 매니페스트를 제공 해야 합니다. 그러나 그렇지 않으면 Visual Studio는 COM 구성 요소에 대해 자동으로 매니페스트를 생성할 수 있습니다. 매니페스트 생성 중 수행 되는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 게시 프로세스; 자세한 내용은 참조 [ClickOnce 응용 프로그램 게시](../deployment/publishing-clickonce-applications.md)합니다. 또한이 기능을 통해 Visual Basic 6.0 같은 이전 개발 환경에서 제작 레거시 구성 요소를 활용할 수 있습니다.  
  
 두 가지는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] COM 구성 요소를 배포 합니다.  
  
-   부트스트래퍼를 사용 하 여; COM 구성 요소를 배포 하려면 이 지원 되는 모든 플랫폼에서 작동합니다.  
  
-   기본 구성 요소 격리 (라고도 등록이 필요 없는 COM) 배포를 사용 합니다. 그러나 Windows XP 또는 더 높은 운영 체제에서이 기능은 작동 하는 것은.  
  
### <a name="example-of-isolating-and-deploying-a-simple-com-component"></a>격리 및 간단한 COM 구성 요소 배포의 예  
 등록이 필요 없는 COM 구성 요소 배포를 보여 주기 위해이 예제는 Windows 기반 응용 프로그램 격리 된 네이티브 COM 구성 요소 참조 Visual Basic 6.0을 사용 하 여 만든 Visual Basic에서 만들고 사용 하 여 배포 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]합니다.  
  
 먼저 기본 COM 구성 요소 만들기 해야 합니다.  
  
##### <a name="to-create-a-native-com-component"></a>기본 COM 구성 요소를 만들려면  
  
1.  Visual Basic 6.0에서 사용 하 여는 **파일** 메뉴를 클릭 **새로**, 다음 **프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자는 **Visual Basic** 노드 선택한는 **ActiveX DLL** 프로젝트. **이름** 상자에 `VB6Hello`을 입력합니다.  
  
    > [!NOTE]
    >  등록이 필요 없는 com; ActiveX 컨트롤 및 ActiveX DLL 프로젝트 형식만 지원 됩니다. ActiveX EXE 및 ActiveX 문서 프로젝트 형식은 지원 되지 않습니다.  
  
3.  **솔루션 탐색기**를 두 번 클릭 **Class1.vb** 텍스트 편집기를 엽니다.  
  
4.  Class1.vb에서 생성된 된 코드에 대 한 뒤 다음 코드에 추가 `New` 메서드:  
  
    ```vb  
    Public Sub SayHello()  
       MsgBox "Message from the VB6Hello COM component"  
    End Sub  
    ```  
  
5.  구성 요소를 빌드하십시오. **빌드** 메뉴를 클릭 하 여 **솔루션 빌드**합니다.  
  
> [!NOTE]
>  COM 제어 프로젝트 형식 및 등록이 필요 없는 COM Dll만 지원 합니다. 등록이 필요 없는 com Exe를 사용할 수 없습니다.  
  
 이제는 Windows 기반 응용 프로그램을 만들고에 COM 구성 요소에 대 한 참조를 추가할 수 있습니다.  
  
##### <a name="to-create-a-windows-based-application-using-a-com-component"></a>COM 구성 요소를 사용 하 여 Windows 기반 응용 프로그램을 만들려면  
  
1.  Visual Basic에서 사용 하 여는 **파일** 메뉴를 클릭 **새로**, 다음 **프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자는 **Visual Basic** 노드 선택한 **Windows 응용 프로그램**합니다. **이름** 상자에 `RegFreeComDemo`을 입력합니다.  
  
3.  **솔루션 탐색기**, 클릭는 **모든 파일 표시** 단추 프로젝트 참조를 표시 합니다.  
  
4.  마우스 오른쪽 단추로 클릭는 **참조** 노드 선택한 **참조 추가** 상황에 맞는 메뉴입니다.  
  
5.  에 **참조 추가** 대화 상자를 클릭는 **찾아보기** 탭, 고 vb6hello.dll을 이동한 다음 선택 합니다.  
  
     A **VB6Hello** 참조가 참조 목록에 나타납니다.  
  
6.  가리킨는 **도구 상자**을 선택는 **단추** 컨트롤을 끌어는 **Form1** 폼입니다.  
  
7.  에 **속성** 창의 설정 단추의 **텍스트** 속성을 **Hello**합니다.  
  
8.  처리기 코드를 추가 하려면 단추를 두 번 클릭 하 고 처리기는 다음과 같이 읽을 수 있도록 코드 파일에서 코드를 추가 합니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
        Dim VbObj As New VB6Hello.Class1  
        VbObj.SayHello()  
    End Sub  
    ```  
  
9. 응용 프로그램을 실행합니다. **디버그** 메뉴를 클릭 하 여 **디버깅 시작**합니다.  
  
 다음 컨트롤을 격리 해야 합니다. 응용 프로그램이 사용 하는 각 COM 구성 요소는 프로젝트에 대 한 COM 참조로 표시 됩니다. 이러한 참조는 아래에 표시 됩니다는 **참조** 에서 노드는 **솔루션 탐색기** 창. (직접 사용 하거나 추가할 수 있는 알림 참조는 **참조 추가** 명령을 **프로젝트** 메뉴 또는 ActiveX 컨트롤을 폼으로 끌기가 직접.)  
  
 다음 단계에는 COM 구성 요소를 격리 하 고 격리 된 컨트롤을 포함 하는 업데이트 된 응용 프로그램을 게시 하는 방법을 보여 줍니다.  
  
##### <a name="to-isolate-a-com-component"></a>COM 구성 요소를 격리 하려면  
  
1.  **솔루션 탐색기**에 **참조** 노드를 선택는 **VB6Hello** 참조 합니다.  
  
2.  에 **속성** 창의 값을 변경는 **격리 됨** 속성 **False** 를 **True**합니다.  
  
3.  **빌드** 메뉴를 클릭 하 여 **솔루션 빌드**합니다.  
  
 이제 f5 키를 예상 대로 응용 프로그램 작동 하지만 경우 등록이 필요 없는 COM. 이제 실행 이 증명 하려면 고 VB6Hello.dll 구성 요소를 등록 취소 한 RegFreeComDemo1.exe Visual Studio IDE 외부에서 실행 합니다. 단추를 클릭할 때이 시간 여전히 작동 합니다. 응용 프로그램 매니페스트를 일시적으로 바꾸면 다시 실패 합니다.  
  
> [!NOTE]
>  COM 구성 요소가 없는 경우 일시적으로 등록을 취소 하 여 시뮬레이션할 수 있습니다. 명령 프롬프트를 열고, 폴더로 이동 하 여 시스템을 입력 하 여 `cd /d %windir%\system32`, 다음을 입력 하 여 구성 요소 등록을 취소 `regsvr32 /u VB6Hello.dll`합니다. 입력 하 여 다시 등록할 수 있습니다 `regsvr32 VB6Hello.dll`합니다.  
  
 마지막 단계를 사용 하 여 응용 프로그램을 게시 하는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]:  
  
##### <a name="to-publish-an-application-update-with-an-isolated-com-component"></a>격리 된 COM 구성 요소와 응용 프로그램 업데이트를 게시 하려면  
  
1.  **빌드** 메뉴를 클릭 하 여 **게시 RegFreeComDemo**합니다.  
  
     게시 마법사가 나타납니다.  
  
2.  게시 마법사에서 로컬 컴퓨터의 디스크에 액세스 하 고 게시 된 파일을 검사할 수 있는 위치를 지정 합니다.  
  
3.  클릭 **마침** 는 응용 프로그램을 게시 합니다.  
  
 게시 된 파일을 검사 하면 sysmon.ocx 파일이 포함 되어 있는지를 언급 합니다. 컨트롤이 최종 사용자의 컴퓨터에 다른 버전의 컨트롤을 사용 하 여 다른 응용 프로그램을이 응용 프로그램으로 방해 없습니다 것을 의미 합니다.이 응용 프로그램에 완전히 격리 됩니다.  
  
## <a name="referencing-native-assemblies"></a>네이티브 어셈블리 참조  
 Visual Studio 네이티브 Visual Basic 6.0 또는 c + + 어셈블리;에 대 한 참조를 지원합니다. 이러한 참조를 네이티브 참조 라고 합니다. 참조가 있는지 확인 하 여 네이티브 인지 알 수 있습니다는 **파일 형식을** 속성이로 설정 되어 **네이티브** 또는 **ActiveX**합니다.  
  
 네이티브 참조를 추가 하려면 사용 된 **참조 추가** 명령을 한 후 매니페스트를 찾습니다. 일부 구성 요소는 DLL에 매니페스트를 배치합니다. 이 경우 DLL 자체를 선택 하기만 하면 하 고 Visual Studio로 추가 됩니다 네이티브 참조는 구성 요소에 포함된 된 매니페스트 포함 되어 있는지 검색 하는 경우. Visual Studio는 종속 파일이 나 참조 된 구성 요소와 같은 폴더에 있는 경우에 매니페스트에 나와 있는 어셈블리에도 자동으로 포함 됩니다.  
  
 COM 제어 격리를 사용 하면 쉽게 이미 매니페스트를 갖지 않는 COM 구성 요소를 배포할 수 있습니다. 그러나 구성 요소 매니페스트와 함께 제공 되는 경우 매니페스트를 직접 참조할 수 있습니다. 사용 하는 것 보다 가능 구성 요소의 작성자가 제공 하는 매니페스트를 항상 사용 해야 실제로 **격리 됨** 속성입니다.  
  
## <a name="limitations-of-registration-free-com-component-deployment"></a>등록이 필요 없는 COM 구성 요소 배포의 제한 사항  
 등록이 필요 없는 COM 일반적인 배포 방법에 비해 지우기 이점을 제공합니다. 그러나 몇 가지 제한 사항 및 지적도 해야 주의. 가장 큰 제한은 에서만 사용할 Windows XP 이상입니다. 등록이 필요 없는 COM의 구현에는 핵심 운영 체제에서 구성 요소 로드 되는 방법에는 변경 해야 합니다. 그러나는 등록이 필요 없는 com 없는 하위 수준 지원을 계층  
  
 모든 구성 요소는 등록이 필요 없는 com 적합 한 후보 다음 중 하나에 해당할 경우 구성 요소는 적합 하지 않습니다.  
  
-   구성 요소가-out-of-process 서버입니다. EXE 서버가 지원 되지 않습니다. Dll만 지원 됩니다.  
  
-   구성 요소가 운영 체제의 일부 이거나 XML, Internet Explorer 또는 Microsoft 데이터 액세스 Components (MDAC)와 같은 시스템 구성 요소입니다. 구성 요소를 만든;의 재배포 정책을 따라야 합니다. 공급 업체에 문의 하십시오.  
  
-   구성 요소에는 Microsoft Office와 같은 응용 프로그램의 일부입니다. 예를 들어 해서는 Microsoft Excel 개체 모델을 격리할 수 있습니다. Office의 일부분 이므로 사용 하 여 컴퓨터에 설치 된 전체 Office 제품.  
  
-   구성 요소 추가 기능에서 또는 스냅인에서 예를 들어 Office 추가 기능에서 또는 웹 브라우저에서 제어로 사용 하기 위한 합니다. 이러한 구성 요소에는 일반적으로 일종의 매니페스트 자체의 범위를 벗어납니다 호스팅 환경에 따라 정의 된 등록 구성표 필요 합니다.  
  
-   구성 요소는 시스템에서 인쇄 스풀러에 대 한 예를 들어 장치 드라이버에 대 한 실제 또는 가상 장치를 관리합니다.  
  
-   구성 요소가 재배포 가능 패키지는 데이터 액세스입니다. 데이터 응용 프로그램에는 일반적으로 별도 데이터 액세스 재배포 가능 패키지를 실행 하기 전에 설치 해야 합니다. Microsoft ADO 데이터 컨트롤, Microsoft OLE DB 또는 MDAC Microsoft Data Access Components ()와 같은 구성 요소를 격리 하지 않아야 합니다. 대신, 응용 프로그램 MDAC 또는 SQL Server Express를 사용 하는 경우로 설정 해야 이러한 필수 구성 요소입니다. 참조 [하는 방법: ClickOnce 응용 프로그램에 필수 구성 요소 설치](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)합니다.  
  
 경우에 따라 구성 요소 개발자는 등록이 필요 없는 com 다시 디자인할 수 있습니다. 없는 경우 작성 하 고 수 있습니다에 의존 하는 부트스트래퍼를 사용 하 여 표준 등록 체계를 통해 응용 프로그램을 게시 합니다. 자세한 내용은 참조 [부트스트래퍼 패키지 만들기](../deployment/creating-bootstrapper-packages.md)합니다.  
  
 COM 구성 요소는 응용 프로그램 마다 한 번 격리 수만 있습니다. 예를 들어 서로 다른 두에서 동일한 COM 구성 요소를 격리할 수 없습니다 **클래스 라이브러리** 동일한 응용 프로그램의 일부인 프로젝트입니다. 빌드 경고, 그렇게 하면 및 응용 프로그램 실행 시 로드 되지 것입니다. 이 문제를 방지 하기 위해 단일 클래스 라이브러리의 COM 구성 요소를 캡슐화 하는 것이 좋습니다.  
  
 응용 프로그램의 배포 등록을 요구 하지 않는 경우에 개발자의 컴퓨터에는 COM 등록은 필요 하는 몇 가지 시나리오가 있습니다. `Isolated` 속성 자동으로 생성 된 매니페스트 빌드하는 동안 COM 구성 요소 개발자의 컴퓨터에 등록 해야 해야 합니다. 빌드하는 동안 자체 등록을 호출 하는 등록 캡처 기능이 없으며 있습니다. 또한 형식 라이브러리에 명시적으로 정의 된 모든 클래스는 매니페스트에 반영 되지 않습니다. 네이티브 참조와 같은 기존 매니페스트가 COM 구성 요소를 사용 하는 경우 구성 요소 개발 시 등록 않아도 됩니다. 그러나 등록은 구성 요소는 ActiveX 컨트롤 및에 포함 하려는 경우 필요는 **도구 상자** 및 Windows Forms 디자이너입니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)