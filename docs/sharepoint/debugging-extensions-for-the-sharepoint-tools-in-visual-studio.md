---
title: Visual Studio에서 SharePoint 도구에 대 한 확장 디버깅 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, debugging extensions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a4e2e6f3858833be49caf59d4d53fc1f8a131f10
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765296"
---
# <a name="debug-extensions-for-the-sharepoint-tools-in-visual-studio"></a>Visual Studio에서 SharePoint 도구에 대 한 확장 디버깅
  실험적 인스턴스 또는 일반 인스턴스의 Visual Studio에서 SharePoint 도구 확장을 디버깅할 수 있습니다. 확장 동작 문제를 해결 해야 할 경우에 추가 오류 정보를 표시 하 고 Visual Studio에 SharePoint 명령이 실행 되는 방식을 구성 하는 레지스트리 값을 수정할 수 있습니다.  
  
## <a name="debug-extensions-in-the-experimental-instance-of-visual-studio"></a>Visual Studio의 실험적 인스턴스에서 확장을 디버그
 테스트 되지 않은 확장 프로그램에서 Visual Studio 개발 환경 실수로 손상 으로부터 보호, 하기 위해 Visual Studio SDK는 라는 대체 Visual Studio 인스턴스를 제공는 *실험적 인스턴스*를 사용할 수 있는 설치 하 고 확장을 테스트 합니다. Visual Studio의 일반 인스턴스를 사용 하 여 새로운 확장을 개발 하지만 디버그 하 고 실험적 인스턴스에서 실행 합니다. 자세한 내용은 참조 [의 실험적 인스턴스](/visualstudio/extensibility/the-experimental-instance)합니다.  
  
 확장 프로그램을 배포 하려면 VSIX 프로젝트를 사용 하 고 VSIX 프로젝트는 솔루션의 시작 프로젝트를 Visual Studio 자동으로 설치 하 고 솔루션을 디버깅할 때 실험적 인스턴스에서 확장을 실행 합니다. 시작 프로젝트는 여러 프로젝트를 포함 하는 솔루션을 디버깅할 때 시작 되는 프로젝트입니다. VSIX 프로젝트를 사용 하 여 확장 프로그램을 배포 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio에서 SharePoint 도구에 대 한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)합니다.  

 다양 한 형식의 Visual Studio의 실험적 인스턴스에서 확장을 디버그 하는 방법을 보여 주는 예제를 보려면 다음 연습을 참조 합니다.  
  
-   [연습: SharePoint 프로젝트 항목 형식 확장](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)  
  
-   [연습: 항목 템플릿을 사용하여 사용자 지정 작업 프로젝트 항목 만들기, 1부](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)  
  
-   [연습: SharePoint 프로젝트용 사용자 지정 배포 단계 만들기](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)  
  
-   [연습: 서버 탐색기를 확장하여 웹 파트 표시](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)  
  
-   [연습: 서버 탐색기 확장의 SharePoint 클라이언트 개체 모델 호출](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md)  
  
## <a name="debug-extensions-in-the-regular-instance-of-visual-studio"></a>Visual Studio의 일반 인스턴스에 대 한 확장 디버깅
 Visual Studio의 일반 인스턴스에 확장 프로젝트를 디버깅 하려는 경우 먼저 일반 인스턴스에 확장을 설치 합니다. 그런 다음 두 번째 Visual Studio 프로세스에 디버거를 연결 합니다. 작업을 마친 후 더 이상 개발 컴퓨터에서 로드 되도록 확장을 제거할 수 없습니다.  
  
#### <a name="to-install-the-extension"></a>확장을 설치하려면  
  
1.  Visual Studio의 모든 인스턴스를 닫습니다.  
  
2.  확장 프로젝트에 대 한 빌드 출력 폴더를 열고는 *.vsix* 파일 두 번 클릭 하거나 바로 가기 메뉴를 열고 선택 하 여 **열고**:  
  
3.  에 **Visual Studio 확장명 설치 관리자** 대화 상자에서 선택 하는 버전의 Visual Studio 확장을 설치 하 고 다음을 선택 하 시겠습니까는 **설치** 단추입니다.  
  
     Visual Studio는 확장 파일 %UserProfile%\AppData\Local\Microsoft\VisualStudio\11.0\Extensions를 설치\\*작성자 이름*\\*확장 이름* \\ *버전*합니다. 이 경로에 마지막 세 폴더에서 생성 되는 `Author`, `Name`, 및 `Version` 의 요소는 *extension.vsixmanifest* 파일에서 확장 합니다.  
  
4.  Visual Studio 확장을 설치한 후 선택 된 **닫기** 단추입니다.  
  
#### <a name="to-debug-the-extension"></a>확장 프로그램을 디버깅 하려면  
  
1.  관리자 권한으로 Visual Studio를 시작 하 고 확장 프로젝트를 엽니다. 다음 단계를 참조로 Visual Studio의이 인스턴스는 *인스턴스 먼저*합니다.  
  
2.  관리자 권한으로 Visual Studio의 다른 인스턴스를 시작 합니다. 다음 단계를 참조로 Visual Studio의이 인스턴스는 *두 번째 인스턴스*합니다.  
  
3.  첫 번째 인스턴스의 Visual Studio로 전환 합니다.  
  
4.  메뉴 모음에서 **디버그**, **프로세스에 연결**합니다.  
  
5.  에 **사용 가능한 프로세스** 목록에서 선택 *devenv.exe*합니다. 이 항목의 Visual Studio; 두 번째 인스턴스를 참조 이 인스턴스가 확장 프로젝트를 디버깅 하려면입니다.  
  
6.  선택 된 **연결** 단추입니다.  
  
     Visual Studio 디버그 모드에서 확장 프로젝트를 실행합니다.  
  
7.  두 번째 인스턴스의 Visual Studio로 전환 합니다.  
  
8.  확장을 로드 하는 새 SharePoint 프로젝트를 만듭니다. 예를 들어 목록 정의 프로젝트 항목에 대 한 확장 디버깅 하는 경우 만들는 **목록 정의** 프로젝트.  
  
9. 확장 프로그램 코드를 테스트 하는 데 필요한 단계를 수행 합니다.  
  
10. 확장 디버깅 작업을 완료 하는 경우 Visual Studio의 두 번째 인스턴스를 닫습니다.  
  
#### <a name="to-remove-the-extension"></a>확장을 제거 하려면  
  
1.  Visual Studio 메뉴 모음에서 선택 **도구**, **확장명 및 업데이트**합니다.  
  
     **확장명 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장명 목록에는 확장의 이름을 선택한 다음 선택에서 **제거** 단추입니다.  
  
3.  표시 되는 대화 상자에서 선택 된 **예** 확장을 제거 하려면 확인 단추입니다.  
  
4.  선택 된 **지금 다시 시작** 단추 제거를 완료 합니다.  
  
## <a name="debug-sharepoint-commands"></a>SharePoint 명령 디버그
 SharePoint 명령은 SharePoint 도구 확장의 일부인를 디버깅 하려는 경우에 디버거를 첨부 해야는 *vssphost4.exe* 프로세스입니다. SharePoint 명령을 실행 하는 64 비트 호스트 프로세스입니다. SharePoint 명령에 대 한 자세한 내용은 및 *vssphost4.exe*, 참조 [SharePoint 개체 모델 호출](../sharepoint/calling-into-the-sharepoint-object-models.md)합니다.  
  
#### <a name="to-attach-the-debugger-to-the-vssphost4exe-process"></a>Vssphost4.exe 프로세스에 디버거를 연결 하려면  
  
1.  위의 지침에 따라 Visual Studio의 일반 인스턴스 또는 Visual Studio의 실험적 인스턴스에서 확장 프로그램을 디버깅을 시작 합니다.  
  
2.  Visual Studio 디버거를 메뉴 모음에서 실행 되는 인스턴스에서 선택 **디버그**, **프로세스에 연결**합니다.  
  
3.  에 **사용 가능한 프로세스** 목록에서 선택 *vssphost.exe*합니다.  
  
    > [!NOTE]  
    >  시작 해야 vssphost.exe 목록에 표시 되지 않습니다는 *vssphost4.exe* Visual Studio를 실행 하는 확장의 인스턴스에서 처리 합니다. 일반적으로 이렇게 하려면 Visual Studio는 개발 컴퓨터에 SharePoint 사이트에 연결 하는 동작을 수행 합니다. 예를 들어, Visual Studio 시작 *vssphost4.exe* 아래 (사이트 URL을 표시 하는 노드)는 사이트 연결 노드를 확장 하는 **SharePoint 연결** 의 노드는 **서버 탐색기**  창와 같은 특정 SharePoint 프로젝트 항목을 추가할 때 또는 **목록 인스턴스** 또는 **이벤트 수신기** SharePoint 프로젝트 항목입니다.  
  
4.  선택 된 **연결** 단추입니다.  
  
5.  Visual Studio 디버깅 중인 인스턴스의에서 명령을 실행 하는 데 필요한 단계를 수행 합니다.  
  
## <a name="modify-registry-values-to-help-debug-sharepoint-tools-extensions"></a>SharePoint 도구 확장의 디버깅을 위해 레지스트리 값 수정
 Visual Studio에서 SharePoint 도구의 확장을 디버깅할 때 확장을 해결 하기 위해 레지스트리 값을 수정할 수 있습니다. 아래는 값이 존재는 **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\11.0\SharePointTools** 키입니다. 이러한 값은 기본적으로 존재 하지 않습니다.  
  
 SharePoint 도구 확장을 해결 하기 위해 수 만들고 EnableDiagnostics 값을 설정 합니다. 다음 표에서이 값을 설명합니다.  
  
|값|설명|  
|-----------|-----------------|  
|EnableDiagnostics|진단 메시지에 표시 되는지 여부를 지정 하는 REG_DWORD는 **출력** 창.<br /><br /> 진단 메시지를 표시 하려면이 값을 1로 설정 합니다. 메시지가 표시 되지 않도록 하려면이 값을 0으로 설정 하거나이 값을 삭제 합니다.<br /><br /> 메시지를 작성 하는 **출력** 창에서 SharePoint 도구 확장에서 SharePoint 프로젝트 서비스를 사용 합니다. 자세한 내용은 참조 [SharePoint 프로젝트 서비스를 사용 하 여](../sharepoint/using-the-sharepoint-project-service.md)합니다.|  
  
 SharePoint 명령 확장 프로그램의 경우, 만들고 명령을 해결 하기 위해 추가 값을 설정 하십시오. 다음 표에서 이러한 값에 설명 합니다.  
  
|값|설명|  
|-----------|-----------------|  
|AttachDebuggerToHostProcess|디버거를 연결할 수 있게 하는 대화 상자를 표시할지 여부를 지정 하는 REG_DWORD *vssphost4.exe* 으로 시작 합니다. 시작 후에 즉시 vssphost.exe 하 여 디버그 하는 명령을 실행 하는 경우에 유용 하 고 명령을 실행 하기 전에 디버거를 수동으로 연결 하려면 충분 한 시간 없는 합니다. 대화 상자를 표시 하려면 *vssphost4.exe* 호출은 <xref:System.Diagnostics.Debugger.Break%2A> 메서드 시작 될 때입니다.<br /><br /> 이 동작을 사용 하려면이 값을 1로 설정 합니다. 이 동작을 해제 하려면이 값을 0으로 설정 하거나이 값을 삭제 합니다.<br /><br /> 전에 Visual Studio에서는 디버거를 연결 하려면 충분 한 시간을 확보할 HostProcessStartupTimeout 값을 늘려야 할 수 있습니다이 값을 1로 설정 하면 *vssphost4.exe* 신호를 성공적으로 시작 합니다.|  
|ChannelOperationTimeout|Visual Studio가 SharePoint 명령이 실행 될 때까지 대기 하는 초 단위 시간을 지정 하는 REG_DWORD입니다. 이 명령은 시간 내에 실행 되지 않을 경우는 <xref:Microsoft.VisualStudio.SharePoint.SharePointConnectionException> throw 됩니다.<br /><br /> 기본값은 120 초입니다.|  
|HostProcessStartupTimeout|Visual Studio 대기 시간을 초 단위로 지정 하는 REG_DWORD *vssphost4.exe* 신호를 성공적으로 시작 합니다. 경우 *vssphost4.exe* 신호를 보내지 않는 성공적인 시작 시간 내에 <xref:Microsoft.VisualStudio.SharePoint.SharePointConnectionException> throw 됩니다.<br /><br /> 기본값은 60 초입니다.|  
|MaxReceivedMessageSize|최대 허용 크기, Visual Studio 간에 전달 되는 WCF 메시지를 바이트 단위로 지정 하는 REG_DWORD 및 *vssphost4.exe*합니다.<br /><br /> 기본값은 1048576 바이트 (1MB).|  
|MaxStringContentLength|최대 허용 크기, Visual Studio 간에 전달 되는 문자열의 바이트 단위로 지정 하는 REG_DWORD 및 *vssphost4.exe*합니다.<br /><br /> 기본값은 1048576 바이트 (1MB).|  
  
## <a name="see-also"></a>참고자료
 [Visual Studio에서 SharePoint 도구 확장](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)   
 [Visual Studio에서 SharePoint 도구에 대한 확장명 배포](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  

