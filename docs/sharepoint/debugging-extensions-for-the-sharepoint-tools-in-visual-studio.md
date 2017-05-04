---
title: "Debugging Extensions for the SharePoint Tools in Visual Studio | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "SharePoint development in Visual Studio, debugging extensions"
ms.assetid: 7cee8ce0-d07b-41f6-8ce1-b18e4be3b50c
caps.latest.revision: 26
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 22
---
# Debugging Extensions for the SharePoint Tools in Visual Studio
  Visual Studio의 실험적 인스턴스나 일반 인스턴스에서 SharePoint 도구 확장을 디버깅할 수 있습니다.  확장의 동작 문제를 해결해야 하는 경우 레지스트리 값을 수정하여 추가적인 오류 정보를 표시하고 Visual Studio에서 SharePoint 명령을 실행하는 방법을 구성할 수도 있습니다.  
  
## Visual Studio의 실험적 인스턴스에서 확장 디버깅  
 테스트되지 않은 확장에 의해 실수로 손상되지 않도록 Visual Studio 개발 환경을 보호하기 위해 Visual Studio SDK에서는 확장을 설치하고 테스트하는 데 사용할 수 있는 *실험적 인스턴스*라는 대체 Visual Studio 인스턴스를 제공합니다.  Visual Studio의 일반 인스턴스를 사용하여 새 확장을 개발하지만 실험적 인스턴스에서 이 확장을 디버깅하고 실행합니다.  자세한 내용은 [실험적 인스턴스](../extensibility/the-experimental-instance.md)을 참조하십시오.  
  
 VSIX 프로젝트를 사용하여 확장을 배포하는 경우 VSIX 프로젝트가 솔루션의 시작 프로젝트이면 Visual Studio에서는 솔루션을 디버깅할 때 자동으로 실험적 인스턴스에 확장을 설치하고 실행합니다.  시작 프로젝트는 여러 프로젝트가 포함된 솔루션을 디버깅할 때 시작되는 프로젝트입니다.  VSIX 프로젝트를 사용하여 확장을 배포하는 방법에 대한 자세한 내용은 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)를 참조하십시오.  시작 프로젝트에 대한 자세한 내용은 [방법: 시작 프로젝트 설정](http://msdn.microsoft.com/ko-kr/31465836-0911-48db-a5d9-e456b635e970)을 참조하십시오.  
  
 Visual Studio의 실험적 인스턴스에서 다양한 형식의 확장을 디버깅하는 방법을 보여 주는 예제는 다음 연습을 참조하십시오.  
  
-   [Walkthrough: Extending a SharePoint Project Item Type](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)  
  
-   [Walkthrough: Creating a Custom Action Project Item with an Item Template, Part 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)  
  
-   [Walkthrough: Creating a Custom Deployment Step for SharePoint Projects](../sharepoint/walkthrough-creating-a-custom-deployment-step-for-sharepoint-projects.md)  
  
-   [Walkthrough: Extending Server Explorer to Display Web Parts](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)  
  
-   [Walkthrough: Calling into the SharePoint Client Object Model in a Server Explorer Extension](../sharepoint/walkthrough-calling-into-the-sharepoint-client-object-model-in-a-server-explorer-extension.md)  
  
## Visual Studio의 일반 인스턴스에서 확장 디버깅  
 Visual Studio의 일반 인스턴스에서 확장 프로젝트를 디버깅하려면 먼저 일반 인스턴스에 확장을 설치한 다음  두 번째 Visual Studio 프로세스에 디버거를 연결합니다.  이 작업을 마친 후 개발 컴퓨터에 더 이상 로드되지 않도록 확장을 제거할 수 있습니다.  
  
#### 확장을 설치하려면  
  
1.  모든 Visual Studio 인스턴스를 닫습니다.  
  
2.  확장 프로젝트의 빌드 출력 폴더에서, .vsix파일을 두번 클릭 하거나 바로가기 메뉴를 열어서 **열기**를 선택합니다.  
  
3.  **Visual Studio Extension 설치 관리자** 대화 상자에서, 확장을 설치할 Visual Studio 버전을 선택한 다음, **설치** 버튼을 선택합니다.  
  
     Visual Studio는 확장 파일을 %UserProfile%\\AppData\\Local\\Microsoft\\VisualStudio\\11.0\\Extensions\\*author name*\\*extension name*\\*version*에 설치합니다.  이 경로의 마지막 세 폴더는 확장에 대한 extension.vsixmanifest 파일의 `Author`, `Name` 및 `Version` 요소에서 생성됩니다.  
  
4.  Visual Studio가 확장명을 설치하면, **닫기** 버튼을 선택합니다.  
  
#### 확장을 디버깅하려면  
  
1.  관리자 권한으로 Visual Studio를 시작하고 확장 프로젝트를 엽니다.  이후의 단계에서는 이 Visual Studio 인스턴스를 *첫 번째 인스턴스*라고 지칭합니다.  
  
2.  관리자 권한으로 또 다른 Visual Studio 인스턴스를 시작합니다.  이후의 단계에서는 이 Visual Studio 인스턴스를 *두 번째 인스턴스*라고 지칭합니다.  
  
3.  첫 번째 Visual Studio 인스턴스로 전환합니다.  
  
4.  메뉴 바에서, **디버그**, **프로세스에 연결**을 선택합니다.  
  
5.  **사용 가능한 프로세스** 목록에서, devenv.exe를 선택합니다.  이 항목은 두 번째 Visual Studio 인스턴스를 나타내며, 프로젝트 확장을 디버깅할 인스턴스입니다.  
  
6.  **첨부** 버튼을 선택합니다.  
  
     확장 프로젝트가 디버그 모드로 실행됩니다.  
  
7.  두 번째 Visual Studio 인스턴스로 전환합니다.  
  
8.  확장을 로드하는 새 SharePoint 프로젝트를 만듭니다.  예를 들어, 목록 정의 프로젝트 항목의 확장을 디버깅하는 경우 **목록 정의** 프로젝트를 만듭니다.  
  
9. 확장 코드를 테스트하는 데 필요한 모든 단계를 수행합니다.  
  
10. 확장 디버깅을 마치면 두 번째 Visual Studio 인스턴스를 닫습니다.  
  
#### 확장을 제거하려면  
  
1.  Visual Studio에서, 메뉴 모음에서, **도구**, **확장 및 업데이트**을 선택합니다.  
  
     **확장 및 업데이트** 대화 상자가 열립니다.  
  
2.  확장 목록에서, 확장의 이름을 선택하고 **제거**버튼을 선택합니다.  
  
3.  나타나는 대화 상자에서, **예** 단추를 선택하여 확장을 제거합니다.  
  
4.  **지금 다시 시작** 단추를 선택하여 제거를 완료합니다.  
  
## SharePoint 명령 디버깅  
 SharePoint 도구 확장의 일부인 SharePoint 명령을 디버깅하려면 디버거를 vssphost4.exe 프로세스에 연결해야 합니다.  이 프로세스는 SharePoint 명령을 실행하는 64비트 호스트 프로세스입니다.  SharePoint 명령 및 vssphost4.exe에 대한 자세한 내용은 [Calling into the SharePoint Object Models](../sharepoint/calling-into-the-sharepoint-object-models.md)을 참조하십시오.  
  
#### 디버거를 vssphost4.exe 프로세스에 연결하려면  
  
1.  실험 모드의 Visual Studio 인스턴스 또는 일반 모드의 Visual Studio 인스턴스에서 위에 언급된 지침에 따라 확장 디버깅을 시작합니다.  
  
2.  디버거를 실행 중인 Visual Studio 인스턴스에서, 메뉴 모음에서 **디버그** 메뉴의 **프로세스에 연결**을 선택합니다.  
  
3.  **사용 가능한 프로세스** 목록에서 vssphost.exe를 선택합니다.  
  
    > [!NOTE]  
    >  vssphost.exe가 목록에 나타나지 않으면 확장을 실행하고 있는 Visual Studio 인스턴스에서 vssphost4.exe 프로세스를 시작해야 합니다.  이렇게 하는 일반적인 방법은 개발 컴퓨터의 SharePoint 사이트에 Visual Studio가 연결하도록 하는 작업을 수행하는 것입니다.  예를 들어 Visual Studio에서는 **서버 탐색기** 창의 **SharePoint 연결** 노드 아래에 있는 사이트 연결 노드\(사이트 URL을 표시하는 노드\)를 확장하는 경우 또는 **목록 인스턴스**나 **이벤트 수신자** 항목 같은 특정 SharePoint 프로젝트 항목을 SharePoint 프로젝트에 추가하는 경우에 vssphost4.exe를 시작합니다.  
  
4.  **첨부** 버튼을 선택합니다.  
  
5.  디버깅되고 있는 Visual Studio 인스턴스에서 명령 실행에 필요한 단계를 수행합니다.  
  
## 레지스트리 값을 수정하여 SharePoint 도구 확장의 디버깅 지원  
 Visual Studio에서 SharePoint 도구의 확장을 디버깅하는 경우 레지스트리 값을 수정하여 확장과 관련된 문제 해결을 지원할 수 있습니다.  이러한 값은 HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\11.0\\SharePointTools 키 아래에 있습니다.  기본적으로 이러한 값은 존재하지 않습니다.  
  
 SharePoint 도구의 확장과 관련된 문제 해결을 지원하려면 EnableDiagnostics 값을 만들고 설정하면 됩니다.  다음 표에서는 이 값에 대해 설명합니다.  
  
|값|설명|  
|-------|--------|  
|EnableDiagnostics|진단 메시지가 **출력** 창에 표시되는지 여부를 지정하는 REG\_DWORD입니다.<br /><br /> 진단 메시지를 표시하려면 이 값을 1로 설정합니다.  메시지가 표시되지 않도록 하려면 이 값을 0으로 설정하거나 삭제합니다.<br /><br /> SharePoint 도구 확장에서 **출력** 창에 메시지를 작성하려면 SharePoint 프로젝트 서비스를 사용합니다.  자세한 내용은 [Using the SharePoint Project Service](../sharepoint/using-the-sharepoint-project-service.md)을 참조하십시오.|  
  
 확장에 SharePoint 명령이 포함되어 있으면 다른 값을 만들고 추가로 설정하여 명령 관련 문제 해결을 지원할 수 있습니다.  다음 표에서는 이러한 값에 대해 설명합니다.  
  
|값|설명|  
|-------|--------|  
|AttachDebuggerToHostProcess|vssphost4.exe가 시작하는 즉시 디버거와 연결할 수 있게 하는 대화 상자를 표시할지 여부를 지정하는 REG\_DWORD입니다.  이 값은 디버깅할 명령이 vssphost.exe 시작 직후에 vssphost.exe에 의해 실행되고 시간이 부족하여 명령 실행 전에 디버거를 수동으로 연결하지 못할 경우에 유용합니다.  대화 상자를 표시하기 위해 vssphost4.exe는 시작될 때 <xref:System.Diagnostics.Debugger.Break%2A> 메서드를 호출합니다.<br /><br /> 이 동작을 활성화하려면 이 값을 1로 설정합니다.  이 동작을 해제하려면 이 값을 0으로 설정하거나 삭제하십시오.<br /><br /> 이 값을 1로 설정한 경우 HostProcessStartupTimeout 값을 증가시키면 vssphost4.exe가 성공적으로 시작했음을 알리는 메시지를 보낼 것으로 Visual Studio에서 예상하기 전에 디버거를 연결할 수 있는 충분한 시간을 확보할 수 있습니다.|  
|ChannelOperationTimeout|Visual Studio에서 SharePoint 명령이 실행될 때까지 기다리는 시간\(초\)을 지정하는 REG\_DWORD입니다.  명령이 시간 안에 실행되지 않으면 <xref:Microsoft.VisualStudio.SharePoint.SharePointConnectionException>이 throw됩니다.<br /><br /> 기본값은 120초입니다.|  
|HostProcessStartupTimeout|Visual Studio에서 vssphost4.exe가 성공적으로 시작되었음을 알릴 때까지 기다리는 시간\(초\)을 지정하는 REG\_DWORD입니다.  vssphost4.exe에서 시간 안에 성공적인 시작을 알리지 않으면 <xref:Microsoft.VisualStudio.SharePoint.SharePointConnectionException>이 throw됩니다.<br /><br /> 기본값은 60초입니다.|  
|MaxReceivedMessageSize|Visual Studio와 vssphost4.exe 사이에 전달되는 WCF 메시지의 최대 허용 크기\(바이트\)를 지정하는 REG\_DWORD입니다.<br /><br /> 기본값은 1,048,576바이트\(1MB\)입니다.|  
|MaxStringContentLength|Visual Studio와 vssphost4.exe 사이에 전달되는 문자열의 최대 허용 크기\(바이트\)를 지정하는 REG\_DWORD입니다.<br /><br /> 기본값은 1,048,576바이트\(1MB\)입니다.|  
  
## 참고 항목  
 [Extending the SharePoint Tools in Visual Studio](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)   
 [Deploying Extensions for the SharePoint Tools in Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
  