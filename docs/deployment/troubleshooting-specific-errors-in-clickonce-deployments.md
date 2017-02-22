---
title: "ClickOnce 배포 관련 오류 문제 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Microsoft.VisualStudio.Publish.ClickOnceProvider.ErrorPrompt.UncRequired"
  - "Microsoft.VisualStudio.Publish.ClickOnceProvider.ErrorPrompt.NoInstallUrl"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 배포, 문제 해결"
  - "응용 프로그램 배포, ClickOnce"
  - "ClickOnce 배포 문제 해결"
ms.assetid: 22dfe8f1-8271-4708-9c25-6bbb13920ac8
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ClickOnce 배포 관련 오류 문제 해결
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 배포할 때 발생할 수 있는 일반 오류들에 대해 살펴 보고 해당 오류를 해결하는 방법을 제시합니다.  
  
## 일반 오류  
  
#### .application 파일을 찾으려고 할 때 아무 것도 발생하지 않거나, Internet Explorer에 XML이 렌더링되거나, 실행 또는 다른 이름으로 저장 대화 상자가 표시됩니다.  
 이 오류는 주로 콘텐츠 형식\(MIME 형식이라고도 함\)이 서버나 클라이언트에 잘못 등록되었을 때 발생합니다.  
  
 우선, 서버가 .application 확장명을 콘텐츠 형식 "application\/x\-ms\-application"과 연결하도록 구성되었는지 확인합니다.  
  
 서버가 올바르게 구성되어 있으면 컴퓨터에 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]이 설치되어 있는지 확인합니다.  [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]이 설치되어 있는데도 이 문제가 계속되면 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]을 제거한 후 다시 설치하여 클라이언트에 콘텐츠 형식을 다시 등록해 봅니다.  
  
#### "응용 프로그램을 검색할 수 없습니다.배포할 때 파일이 누락되었습니다." 또는 "응용 프로그램 다운로드가 중단되었습니다. 네트워크 오류인지 확인하고 나중에 다시 실행해 보십시오."라는 메시지가 표시됩니다.  
 이 메시지는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 매니페스트가 참조하는 파일을 하나 이상 다운로드할 수 없음을 나타냅니다.  이 오류를 디버그하는 가장 손쉬운 방법은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]가 다운로드할 수 없다고 표시한 URL을 다운로드해 보는 것입니다.  이 문제는 다음과 같은 경우에 발생할 수 있습니다.  
  
-   로그 파일에 "\(403\) 사용할 수 없음" 또는 "\(404\) 찾을 수 없음"이 표시되는 경우 웹 서버가 이 파일의 다운로드를 차단하지 않도록 구성되었는지 확인합니다.  자세한 내용은 [ClickOnce 배포 시 서버 및 클라이언트 구성 문제](../deployment/server-and-client-configuration-issues-in-clickonce-deployments.md)를 참조하십시오.  
  
-   서버가 .config 파일을 차단하고 있으면 이 항목의 뒷부분에서 ".config 파일이 들어 있는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 설치하려고 하면 다운로드 오류가 발생합니다." 단원을 참조하십시오.  
  
-   배포 매니페스트의 `deploymentProvider` URL이 활성화에 사용된 URL과 다른 위치를 가리키므로 이 오류가 발생했는지 여부를 확인합니다.  
  
-   모든 파일이 서버에 있는지 확인합니다. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 로그에 찾을 수 없는 파일이 표시됩니다.  
  
-   네트워크 연결 문제가 있는지 여부를 확인합니다. 클라이언트 컴퓨터가 다운로드 중에 오프라인 상태가 되면 이러한 메시지가 나타날 수 있습니다.  
  
#### .config 파일이 들어 있는 ClickOnce 응용 프로그램을 설치하려고 하면 다운로드 오류가 발생합니다.  
 기본적으로 Visual Basic Windows 기반 응용 프로그램에는 App.config 파일이 포함되어 있습니다.  사용자가 Windows Server 2003을 사용하는 웹 서버에서 설치하려고 하면 이 운영 체제는 보안을 위해 .config 파일의 설치를 차단하므로 문제가 발생합니다.  .config 파일이 설치될 수 있도록 하려면 **게시 옵션** 대화 상자에서 **".deploy" 파일 확장명 사용**을 클릭합니다.  
  
 또한 콘텐츠 형식\(MIME 형식\)을 .application, .manifest 및 .deploy 파일에 적절하게 설정해야 합니다.  자세한 내용은 웹 서버 설명서를 참조하십시오.  
  
 자세한 내용은 [ClickOnce 배포 시 서버 및 클라이언트 구성 문제](../deployment/server-and-client-configuration-issues-in-clickonce-deployments.md)에서 "Windows Server 2003: 잠겨 있는 콘텐츠 형식"을 참조하십시오.  
  
#### "응용 프로그램 형식이 잘못 지정되었습니다."라는 오류 메시지가 나타나거나 로그 파일에 "XML 서명이 잘못되었습니다."라는 내용이 포함되어 있습니다.  
 매니페스트 파일을 업데이트하고 다시 서명했는지 확인합니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 사용하여 응용 프로그램을 다시 게시하거나 Mage를 사용하여 응용 프로그램에 다시 서명합니다.  
  
#### 서버의 응용 프로그램을 업데이트했지만 클라이언트가 업데이트를 다운로드하지 못합니다.  
 다음 작업 중 하나를 완료하여 이 문제를 해결할 수 있습니다.  
  
-   배포 매니페스트의 `deploymentProvider` URL을 확인합니다.  `deploymentProvider`가 가리키는 동일한 위치에서 비트를 업데이트하고 있는지 확인합니다.  
  
-   배포 매니페스트에서 업데이트 간격을 확인합니다.  이 간격이 일정한 간격으로 설정되어 있으면\(예: 6시간마다 한 번\) [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]는 이 간격이 지나기 전에는 업데이트를 검색하지 않습니다.  응용 프로그램이 시작될 때마다 업데이트를 검색하도록 매니페스트를 변경할 수도 있습니다.  업데이트 간격을 변경하면 개발할 때 업데이트가 설치되고 있는지 손쉽게 확인할 수 있지만 응용 프로그램의 활성화 속도는 떨어집니다.  
  
-   시작 메뉴에서 응용 프로그램을 다시 시작해 봅니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]가 백그라운드에서 업데이트를 발견했을 수 있지만 비트를 설치하라는 메시지는 다음에 활성화할 때 표시됩니다.  
  
#### 업데이트하는 동안 "배포의 참조가 응용 프로그램 매니페스트에 정의된 ID와 일치하지 않습니다."라는 로그 엔트리가 있는 오류 메시지가 표시됩니다.  
 이 오류는 배포 및 응용 프로그램 매니페스트를 수동으로 편집했고 한 매니페스트에 있는 어셈블리 ID의 설명이 다른 것과 동기화되지 않았기 때문에 발생할 수 있습니다.  어셈블리 ID는 이름, 버전, 문화권 및 공개 키 토큰으로 구성되어 있습니다.  매니페스트에서 ID 설명을 확인하고 다른 점을 모두 수정합니다.  
  
#### 로컬 디스크 또는 CD\-ROM에서 처음 활성화하는 데는 성공했지만 이후에 시작 메뉴에서 활성화할 수 없습니다.  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 Deployment Provider URL을 사용하여 응용 프로그램용 업데이트를 가져옵니다.  URL이 가리키는 위치가 맞는지 확인합니다.  
  
#### 오류: "응용 프로그램을 시작할 수 없습니다."  
 이 오류 메시지는 대개 해당 응용 프로그램을 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 저장소에 설치하는 과정에 문제가 있음을 나타냅니다.  즉, 응용 프로그램에 오류가 있거나 저장소가 손상되었습니다.  로그 파일에서 오류가 발생한 위치를 확인할 수 있습니다.  
  
 다음과 같은 작업을 수행해야 합니다.  
  
-   배포 매니페스트 ID, 응용 프로그램 매니페스트 ID 및 주 응용 프로그램 EXE의 ID가 모두 고유한지 확인합니다.  
  
-   파일 경로가 100자를 넘지 않는지 확인합니다.  응용 프로그램에 포함되어 있는 파일 경로가 매우 길 경우 저장할 수 있는 최대 경로 길이 제한을 초과했을 수 있습니다.  경로의 길이를 줄이고 다시 설치해 보십시오.  
  
#### 응용 프로그램 config 파일의 PrivatePath 설정이 적용되지 않습니다.  
 PrivatePath\(Fusion 검색 경로\)를 사용하려면 응용 프로그램에서 완전 신뢰 권한을 요청해야 합니다.  응용 프로그램 매니페스트를 변경하여 완전 신뢰를 요청한 다음 다시 시도하십시오.  
  
#### 응용 프로그램을 제거하는 동안 "응용 프로그램을 제거하지 못했습니다."라는 메시지가 나타납니다.  
 이 메시지는 대개 응용 프로그램이 이미 제거되었거나 저장소가 손상되었음을 나타냅니다.  **확인**을 클릭하면 **프로그램 추가\/제거** 항목이 제거됩니다.  
  
#### 설치하는 동안 플랫폼 종속성이 설치되지 않았다는 메시지가 나타납니다.  
 GAC\(전역 어셈블리 캐시\)에 응용 프로그램을 실행하는 데 필요한 필수 구성 요소가 없습니다.  
  
## Visual Studio를 통한 게시  
  
#### Visual Studio에서 게시할 수 없습니다.  
 대상 서버에 대한 게시 권한이 있는지 확인합니다.  예를 들어, 터미널 서버 컴퓨터에 관리자가 아닌 일반 사용자로 로그인한 경우에는 로컬 웹 서버에 게시하는 데 필요한 권한을 가지고 있지 않을 수 있습니다.  
  
 URL을 사용하여 게시하는 경우에는 대상 컴퓨터에서 FrontPage Server Extensions를 사용할 수 있는지 확인합니다.  
  
#### "'\<site\>' 웹 사이트를 만들 수 없습니다.FrontPage Server Extensions와 통신하는 데 필요한 구성 요소가 설치되어 있지 않습니다."라는 오류 메시지가 나타납니다.  
 게시 작업을 시작하는 컴퓨터에 Microsoft Visual Studio 웹 제작 도구 구성 요소가 설치되어 있는지 확인하십시오.  Express 사용자의 경우 이 구성 요소는 기본적으로 설치되어 있지 않습니다.  자세한 내용은 [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=102310](http://go.microsoft.com/fwlink/?LinkId=102310) 페이지를 참조하십시오.  
  
#### 오류 메시지: 파일을 찾을 수 없습니다 ' Microsoft.Windows.Common\-컨트롤, 버전 6.0.0.0, Culture \= \= \*, 예와 6595b64144ccf1df, ProcessorArchitecture \= \= \*, 형식이 win32 \='  
 사용 하는 비주얼 스타일을 사용 하는 WPF 응용 프로그램을 게시 하려고 하면이 오류 메시지가 나타납니다.  이 문제를 해결 하려면를 참조 하십시오 [방법: 비주얼 스타일을 사용하여 WPF 응용 프로그램 게시](../deployment/how-to-publish-a-wpf-application-with-visual-styles-enabled.md).  
  
## Mage 사용  
  
#### 인증서 저장소에 있는 인증서로 서명하려고 했으나 빈 메시지 상자가 나타났습니다.  
 **서명** 대화 상자에서 다음을 수행해야 합니다.  
  
-   **저장된 인증서로 서명**을 선택하고  
  
-   목록에서 인증서를 선택합니다. 첫 번째 인증서는 기본 선택이 아닙니다.  
  
#### "서명하지 않음" 단추를 클릭하면 예외가 발생합니다.  
 이 문제는 알려진 버그입니다.  모든 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 매니페스트에는 서명이 필요합니다.  서명 옵션 중 하나를 선택하고 **확인**을 클릭합니다.  
  
## 기타 오류  
 다음 표에서는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 설치할 때 클라이언트 컴퓨터 사용자에게 표시될 수 있는 몇 가지 일반적인 오류 메시지를 보여 줍니다.  각 오류 메시지는 오류의 주요 원인에 대한 설명 옆에 나열됩니다.  
  
|오류 메시지|설명|  
|------------|--------|  
|응용 프로그램을 시작할 수 없습니다.  응용 프로그램 게시자에게 문의하십시오.<br /><br /> 응용 프로그램을 시작할 수 없습니다.  도움이 필요하면 응용 프로그램 공급업체에 문의하십시오.|응용 프로그램을 시작할 수 없고 다른 특정한 이유를 찾을 수 없을 때 발생하는 일반적인 오류 메시지입니다.  주로 응용 프로그램이 손상되었거나 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 저장소가 손상된 경우입니다.|  
|계속할 수 없습니다.  응용 프로그램 형식이 잘못 지정되었습니다.  도움이 필요하면 응용 프로그램 게시자에게 문의하십시오.<br /><br /> 응용 프로그램의 유효성을 검사하지 못했습니다.  계속할 수 없습니다.<br /><br /> 응용 프로그램 파일을 검색할 수 없습니다.  배포할 때 응용 프로그램의 파일이 손상되었습니다.|배포 매니페스트 파일 중 하나에 잘못된 구문이 있거나 해당 파일로 조정할 수 없는 해시가 포함되어 있습니다.  이 오류는 어셈블리에 포함된 매니페스트가 손상되었음을 의미할 수도 있습니다.  배포를 다시 만들어 응용 프로그램을 다시 컴파일하거나, 매니페스트에서 수동으로 오류를 찾아서 수정합니다.|  
|응용 프로그램을 검색할 수 없습니다.  인증 오류입니다.<br /><br /> 응용 프로그램을 설치하지 못했습니다.  서버에서 응용 프로그램 파일을 찾을 수 없습니다.  도움이 필요하면 응용 프로그램 공급업체나 관리자에게 문의하십시오.|하나 이상의 배포 파일에 대한 액세스 권한이 없으므로 해당 파일을 다운로드할 수 없습니다.  이 오류는 웹 서버에서 '403 사용할 수 없음' 오류를 반환할 경우에 발생할 수 있습니다. '403 사용할 수 없음 오류'는 배포 파일 중 하나가 웹 서버에서 보호 파일로 취급되는 확장명으로 끝나는 경우에 발생할 수 있습니다.  또한 하나 이상의 응용 프로그램 파일이 들어 있는 디렉터리에 액세스하려면 사용자 이름과 암호가 필요할 수 있습니다.|  
|응용 프로그램을 다운로드할 수 없습니다.  응용 프로그램에 필요한 파일이 없습니다.  도움이 필요하면 응용 프로그램 공급업체나 시스템 관리자에게 문의하십시오.|응용 프로그램 매니페스트에 나열된 하나 이상의 파일이 서버에 없습니다.  모든 배포 종속 파일을 업로드했는지 확인하고 다시 시도하십시오.|  
|응용 프로그램을 다운로드하지 못했습니다.  네트워크 연결을 확인하거나 시스템 관리자 또는 네트워크 서비스 공급자에게 문의하십시오.|[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서 서버에 대한 네트워크 연결을 설정할 수 없습니다.  서버의 사용 가능성과 네트워크 상태를 확인하십시오.|  
|HRESULT '\<number\>'와 함께 URLDownloadToCacheFile이 실패했습니다.  '\<file\>'을\(를\) 다운로드하는 동안 오류가 발생했습니다.|배포 대상 컴퓨터에서 Internet Explorer 고급 보안 옵션 "보안과 비보안 모드 사이를 전환할 때 경고"가 설정되어 있고 설치하려는 ClickOnce 응용 프로그램의 설치 URL이 비보안 사이트에서 보안 사이트로 또는 그 반대로 리디렉션된 경우 Internet Explorer 경고의 방해 때문에 설치가 실패합니다.<br /><br /> 이 문제를 해결하려면 다음 중 하나를 수행하십시오.<br /><br /> -   보안 옵션을 지웁니다.<br />-   설치 URL이 보안 모드를 변경하는 방식으로 리디렉션되지 않도록 합니다.<br />-   리디렉션을 완전히 제거하고 실제 설치 URL을 가리킵니다.|  
|하드 디스크에 쓰는 동안 오류가 발생했습니다.  디스크에 사용 가능한 공간이 충분한지 확인하십시오.  도움이 필요하면 응용 프로그램 공급업체나 시스템 관리자에게 문의하십시오.|이 오류는 응용 프로그램을 저장할 디스크 공간이 부족함을 나타내거나 응용 프로그램 파일을 드라이브에 저장할 때 발생하는 일반적인 I\/O 오류를 나타낼 수도 있습니다.|  
|응용 프로그램을 시작할 수 없습니다.  디스크에 사용 가능한 공간이 부족합니다.|하드 디스크가 꽉 찼습니다.  공간을 지우고 응용 프로그램을 다시 실행해 보십시오.|  
|배포된 활성화를 한 번에 너무 많이 로드하려고 했습니다.|[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]는 동시에 시작할 수 있는 응용 프로그램 수를 제한합니다.  이 제한을 사용하면 로컬 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 서비스를 악의적인 서비스 거부 공격 시도로부터 보호할 수 있습니다. 사용자가 동일한 응용 프로그램을 시작하려고 연속해서 빠르게 시도할 경우 해당 응용 프로그램의 단일 인스턴스만 표시됩니다.|  
|네트워크상에서 바로 가기를 활성화할 수 없습니다.|[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 대한 바로 가기는 로컬 하드 디스크에서만 시작될 수 있습니다.  원격 서버에서 바로 가기 파일을 가리키는 URL을 열어 시작할 수는 없습니다.|  
|이 응용 프로그램의 크기가 너무 커서 부분적 트러스트로 온라인에서 실행할 수 없습니다.  도움이 필요하면 응용 프로그램 공급업체나 시스템 관리자에게 문의하십시오.|부분 신뢰 수준으로 실행되는 응용 프로그램은 온라인 응용 프로그램 할당량 크기의 절반보다 크지 않아야 합니다. 이 크기는 기본적으로 250MB입니다.|  
  
## 참고 항목  
 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce 배포 문제 해결](../deployment/troubleshooting-clickonce-deployments.md)