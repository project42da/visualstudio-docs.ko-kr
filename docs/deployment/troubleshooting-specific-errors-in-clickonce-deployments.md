---
title: ClickOnce 배포 관련 오류 문제 해결 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.ErrorPrompt.UncRequired
- Microsoft.VisualStudio.Publish.ClickOnceProvider.ErrorPrompt.NoInstallUrl
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications, ClickOnce
- troubleshooting ClickOnce deployments
- ClickOnce deployment, troubleshooting
ms.assetid: 22dfe8f1-8271-4708-9c25-6bbb13920ac8
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: b52caad3b6e4c98dd78e6c6be9835c11ac4d4175
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="troubleshooting-specific-errors-in-clickonce-deployments"></a>ClickOnce 배포 관련 오류 문제 해결
이 항목에서는 배포할 때 발생할 수 있는 다음과 같은 일반적인 오류는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 각 문제를 해결 하는 단계를 제공 합니다.  
  
## <a name="general-errors"></a>일반 오류  
  
#### <a name="when-you-try-to-locate-an-application-file-nothing-occurs-or-xml-renders-in-internet-explorer-or-you-receive-a-run-or-save-as-dialog-box"></a>때.application 파일을 찾으려고 아무 일도 발생 하거나 Internet Explorer에서 XML 렌더링 또는 실행 또는 다른 이름으로 저장 대화 상자가 나타나면  
 이 오류는 콘텐츠 형식 (MIME 유형이 라고도 함)는 서버 또는 클라이언트에 잘못 등록 되었을 원인일 가능성이 큽니다.  
  
 먼저, 콘텐츠 형식 "/ x ms-응용 프로그램".application 확장명을 연결 하려면 서버 구성 되어 있는지 확인 합니다.  
  
 서버가 올바르게 구성 하 고, 경우 되도록는 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] 컴퓨터에 설치 합니다. 경우는 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] 설치 된이 문제를 제거 하 고 다시 설치는 계속 표시 하 고는 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] 를 다시 클라이언트에 콘텐츠 형식을 등록 합니다.  
  
#### <a name="error-message-says-unable-to-retrieve-application-files-missing-in-deployment-or-application-download-has-been-interrupted-check-for-network-errors-and-try-again-later"></a>오류 메시지는 "응용 프로그램을 검색할 수 없습니다. 배포에서 누락 된 파일"또는"응용 프로그램 다운로드가 중단 되었습니다., 네트워크 오류를 확인 하 고 나중에 다시 시도 하십시오."  
 이 메시지는 하나 이상의 파일에서 참조 하 고 나타냅니다는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 매니페스트를 다운로드할 수 없습니다. 이 오류를 디버깅 하는 가장 쉬운 방법은 URL 다운로드를 시도 하는 하 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 라는 다운로드할 수 없습니다. 가능한 원인은 다음과 같습니다.  
  
-   로그 파일에 "(403) 사용할 수 없음" 라고 표시 하는 경우 또는 "(404) 찾을 수 없음"이이 파일의 다운로드를 차단 하지 않도록 웹 서버에 구성 되어 있는지 확인 합니다. 자세한 내용은 [ClickOnce 배포 시 서버 및 클라이언트 구성 문제](../deployment/server-and-client-configuration-issues-in-clickonce-deployments.md)를 참조하세요.  
  
-   .Config 파일 서버에 의해 차단 되 고 섹션을 참조 "다운로드를 설치 하려고 할 때 오류를 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] .config 파일이 들어 있는 응용 프로그램"이이 항목의 뒷부분에 나오는 합니다.  
  
-   이 때문에 발생 하는지 여부를 결정는 `deploymentProvider` 배포 매니페스트의 URL 활성화를 위해 사용 되는 URL과 다른 위치를 가리키고 있습니다.  
  
-   서버에 모든 파일이 있는지 확인 하십시오. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 로그 알려 주어 야 하는 파일을 찾을 수 없습니다.  
  
-   네트워크 연결 문제; 되었는지 확인 다운로드 하는 동안 클라이언트 컴퓨터가 오프 라인으로 전환한 경우이 메시지를 받을 수 있습니다.  
  
#### <a name="download-error-when-you-try-to-install-a-clickonce-application-that-has-a-config-file"></a>다운로드는.config 파일을 포함 하는 ClickOnce 응용 프로그램을 설치 하려고 할 때 오류  
 기본적으로 Visual Basic Windows 기반 응용 프로그램 App.config 파일을 포함 합니다. 사용자가 해당 운영 체제 보안상의 이유로.config 파일의 설치를 차단 하기 때문에 Windows Server 2003을 사용 하는 웹 서버에서 설치 하려고 할 때 문제가 됩니다. 설치할.config 파일을 사용 하려면 **".deploy" 파일 확장명을 사용 하 여** 에 **게시 옵션** 대화 상자.  
  
 설정 해야 콘텐츠 형식 (MIME 유형이 라고도 함) 적절 하 게.application,.manifest 및.deploy 파일에 대 한 합니다. 자세한 내용은 웹 서버 설명서를 참조 하십시오.  
  
 자세한 내용은 "Windows Server 2003:: 선택 콘텐츠 형식"을 참조 [서버 및 클라이언트 구성 문제 ClickOnce 배포에서](../deployment/server-and-client-configuration-issues-in-clickonce-deployments.md)합니다.  
  
#### <a name="error-message-application-is-improperly-formatted-log-file-contains-xml-signature-is-invalid"></a>오류 메시지: "응용 프로그램의 형식이 잘못 되었습니다." 로그 파일에 "XML 서명이 잘못 되었습니다."  
 매니페스트 파일을 업데이트 하 고 다시 서명 확인 합니다. 사용 하 여 응용 프로그램을 다시 게시 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 하거나 마법사를 사용 하 여 응용 프로그램을 다시 서명 합니다.  
  
#### <a name="you-updated-your-application-on-the-server-but-the-client-does-not-download-the-update"></a>서버에서 응용 프로그램을 업데이트 하지만 클라이언트 업데이트를 다운로드 하지 않습니다.  
 다음 작업 중 하나를 완료 하 여이 문제를 해결할 수 있습니다.  
  
-   검사는 `deploymentProvider` 배포 매니페스트의 URL입니다. 같은 위치에서 비트를 업데이트 하 고 있는지 확인 하는 `deploymentProvider` 를 가리킵니다.  
  
-   배포 매니페스트의 업데이트 간격을 확인 합니다. 이 간격이, 예: 6 시간 마다 한 번 일정 한 간격으로 설정 되 면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 이 기간이 경과 될 때까지 업데이트에 대 한 검색 하지 것입니다. 응용 프로그램이 시작 될 때마다 업데이트를 검색 하도록 매니페스트를 변경할 수 있습니다. 업데이트 간격을 변경 하는 것은 업데이트를 설치 하 고 있지만 응용 프로그램 활성화를 낮추고 확인 하려면 개발 기간 동안 편리 합니다.  
  
-   시작 메뉴에서 응용 프로그램을 다시 시작 하십시오. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 백그라운드에서 업데이트를 발견 했을 수 있지만 다음 활성화에 대 한 비트를 설치 하 라는 메시지가 나타납니다.  
  
#### <a name="during-update-you-receive-an-error-that-has-the-following-log-entry-the-reference-in-the-deployment-does-not-match-the-identity-defined-in-the-application-manifest"></a>업데이트 하는 동안 오류가 발생 하는 다음 로그 항목을 가진: "배포의 참조가 응용 프로그램 매니페스트에 정의 된 id를 일치 하지 않습니다"  
 배포 및 응용 프로그램 매니페스트를 수동으로 편집한 서로 동기화 한 매니페스트에 어셈블리의 id에 대 한 설명을 발생할 수 있기 때문에이 오류가 발생할 수 있습니다. 어셈블리의 id의 이름, 버전, culture 및 공개 키 토큰으로 구성 됩니다. 매니페스트에서 id 설명을 확인 하 고 모든 차이점을 해결 하십시오.  
  
#### <a name="first-time-activation-from-local-disk-or-cd-rom-succeeds-but-subsequent-activation-from-start-menu-does-not-succeed"></a>처음으로 로컬 디스크 또는 CD-ROM에서 정품 인증 성공 하지만 후속 활성화 시작 메뉴에서 실패  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 대 한 업데이트를 받을 배포 공급자 URL을 사용 합니다. URL이 가리키는 위치 올바른지 확인 합니다.  
  
#### <a name="error-cannot-start-the-application"></a>오류: "수 없는 응용 프로그램을 시작할"  
 이 오류 메시지는 일반적으로이 응용 프로그램을 설치 하는 문제 임을 나타냅니다는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 저장 합니다. 응용 프로그램에 오류 또는 저장소가 손상 되었습니다. 로그 파일 알려 오류가 발생 합니다.  
  
 다음을 수행 해야 합니다.  
  
-   배포 매니페스트 id, 응용 프로그램 매니페스트 id 및 주 응용 프로그램 EXE의 id를 모두 고유 있는지 확인 합니다.  
  
-   파일 경로 길이가 100 자 보다 긴 지 확인 합니다. 응용 프로그램에 너무 오래 된 파일 경로가 있으면 저장할 수는 최대 경로에 대 한 제한을 초과할 수 있습니다. 경로의 길이 줄이고 고 다시 설치 하십시오.  
  
#### <a name="privatepath-settings-in-application-config-file-are-not-honored"></a>응용 프로그램 구성 파일에서 PrivatePath 설정이 적용 되지 않습니다.  
 PrivatePath (Fusion 검색 경로)를 사용 하려면 응용 프로그램이 완전 신뢰 권한을 요청 해야 합니다. 완전 신뢰를 요청 하 한 후 다시 시도 하도록 응용 프로그램 매니페스트를 변경해 보십시오.  
  
#### <a name="during-uninstall-a-message-appears-saying-failed-to-uninstall-application"></a>제거 하는 동안 을 "응용 프로그램을 제거 하지 못했습니다."  
 이 메시지는 일반적으로 응용 프로그램이 이미 제거 또는 저장소가 손상 되었음을 나타냅니다. 클릭 한 후 **확인**, **프로그램 추가/제거** 항목이 제거 됩니다.  
  
#### <a name="during-installation-a-message-appears-that-says-that-the-platform-dependencies-are-not-installed"></a>플랫폼 종속성이 설치 되지 않았다 하는 메시지가 나타나면을 설치 하는 동안  
 GAC (전역 어셈블리 캐시)에서 응용 프로그램을 실행 하는 데 필요한 필수 구성 요소가 없습니다.  
  
## <a name="publishing-with-visual-studio"></a>Visual Studio와 함께 게시  
  
#### <a name="publishing-in-visual-studio-fails"></a>Visual Studio에서 게시 실패  
 있는지 서버에 게시할 수 있는 권한이 대상으로 하는 것을 확인 합니다. 예를 들어 터미널 서버 컴퓨터를 관리자가 일반 사용자로 로그인 한 경우 아마도 않아도 됩니다 로컬 웹 서버에 게시 하는 데 필요한 권한입니다.  
  
 url을 게시 하는 경우 대상 컴퓨터에 FrontPage Server Extensions를 사용할 수 있는지 확인 합니다.  
  
#### <a name="error-message-unable-to-create-the-web-site-site-the-components-for-communicating-with-frontpage-server-extensions-are-not-installed"></a>오류 메시지: 웹 사이트를 만들 수 없습니다. '\<사이트 >'입니다. FrontPage Server Extensions와 통신 하기 위한 구성 요소 설치 되지 않습니다.  
 Microsoft Visual Studio 웹 제작 구성 요소에서 게시 하려고 하는 컴퓨터에 설치 되어 있는지 확인 합니다. Express 사용자에 대 한이 구성 요소는 기본적으로 설치 되지 않았습니다. 자세한 내용은 [http://go.microsoft.com/fwlink/?LinkId=102310](http://go.microsoft.com/fwlink/?LinkId=102310)를 참조하세요.  
  
#### <a name="error-message-could-not-find-file-microsoftwindowscommon-controls-version6000-culture-publickeytoken6595b64144ccf1df-processorarchitecture-typewin32"></a>오류 메시지: 파일을 찾을 수 없습니다 ' Microsoft.Windows.Common-컨트롤, 버전 = 6.0.0.0, Culture = *, PublicKeyToken 6595b64144ccf1df, ProcessorArchitecture = =\*, 유형 = win32'  
 비주얼 스타일을 사용를 사용 하 여 WPF 응용 프로그램을 게시 하려고 하면이 오류 메시지가 나타납니다. 이 문제를 해결 하려면 참조 [하는 방법: WPF 응용 프로그램 비주얼 스타일이 활성화 된 게시](../deployment/how-to-publish-a-wpf-application-with-visual-styles-enabled.md)합니다.  
  
## <a name="using-mage"></a>마법사를 사용 하 여  
  
#### <a name="you-tried-to-sign-with-a-certificate-in-your-certificate-store-and-a-received-blank-message-box"></a>인증서 저장소와 수신된 된 빈 메시지 상자에 있는 인증서로 서명 하 려 했습니다.  
 에 **서명** 해야 대화 상자:  
  
-   선택 **저장 된 인증서로 서명**, 및  
  
-   목록에서 인증서를 선택 합니다. 첫 번째 인증서가 기본적으로 선택 합니다.  
  
#### <a name="clicking-the-dont-sign-button-causes-an-exception"></a>"서명 하지 않음" 단추를 클릭 하면 예외가 발생  
 이 문제는 알려진된 버그가 있습니다. 모든 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 매니페스트는 서명 되어야 합니다. 서명 옵션 중 하나를 선택 하 고 클릭 **확인**합니다.  
  
## <a name="additional-errors"></a>추가 오류  
 다음 표에 클라이언트 컴퓨터 사용자는 사용자가을 설치할 때 발생할 수 있는 몇 가지 일반적인 오류 메시지는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다. 오류에 대 한 가장 큰 원인은의 설명 옆에 있는 각 오류 메시지가 나열 됩니다.  
  
|오류 메시지|설명|  
|-------------------|-----------------|  
|응용 프로그램을 시작할 수 없습니다. 응용 프로그램 게시자를 게 문의 하십시오.<br /><br /> 응용 프로그램을 시작할 수 없습니다. 응용 프로그램 공급 업체에 문의.|이들은 응용 프로그램을 시작할 수 없는 및 다른 특정 한 이유를 찾을 수 있습니다 때 발생 하는 일반 오류 메시지입니다. 자주 하는 응용 프로그램이 손상,이 즉 또는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 저장소가 손상 되었습니다.|  
|계속할 수 없습니다. 응용 프로그램 형식이 잘못 되었습니다. 응용 프로그램 게시자에 게 문의 합니다.<br /><br /> 응용 프로그램 유효성 검사에 실패 했습니다. 계속할 수 없습니다.<br /><br /> 응용 프로그램 파일을 검색할 수 없습니다. 배포의 파일이 손상 되었습니다.|배포에서 매니페스트 파일 중 하나가 유효 구문상 하지 않거나 해당 파일과 조정할 수 없는 해시를 포함 합니다. 이 오류는 어셈블리 내에 포함 된 매니페스트가 손상 되었음을 나타낼 수도 있습니다. 다시 배포 하 고 응용 프로그램이 다시 컴파일해야 또는 찾기 만들고 매니페스트에서 오류를 수동으로 수정.|  
|응용 프로그램을 검색할 수 없습니다. 인증 오류입니다.<br /><br /> 응용 프로그램을 설치 하지 못했습니다. 서버에서 응용 프로그램 파일을 찾을 수 없습니다. 응용 프로그램 공급 업체나 관리자에 문의 하십시오.|배포에 있는 하나 이상의 파일에 액세스할 수 없기 때문에 다운로드할 수 없습니다. 이 배포 파일 중 하나 보호 된 파일으로 처리 하는 웹 서버에 수행 하는 확장명으로 끝나는 경우에 발생할 수 있는 웹 서버에 의해 반환 되는 403 사용할 수 없음 오류가 발생할 수 있습니다. 또한 응용 프로그램의 파일 중 하나 이상이 포함 된 디렉터리에 액세스 하기 위해 사용자 이름 및 암호가 필요할 수 있습니다.|  
|응용 프로그램을 다운로드할 수 없습니다. 응용 프로그램에 필요한 파일이 없습니다. 시스템 관리자 또는 응용 프로그램 공급 업체에 문의 하십시오.|서버에서 하나 이상의 응용 프로그램 매니페스트에 나열 된 파일을 찾을 수 없습니다. 배포의 모든 종속 파일을 업로드 하 고 다시 시도 확인 합니다.|  
|응용 프로그램을 다운로드 하지 못했습니다. 네트워크 연결을 확인 하거나 시스템 관리자 또는 네트워크 서비스 공급자에 게 문의 하십시오.|[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 서버에 네트워크 연결을 설정할 수 없습니다. 서버의 사용 가능성 및 네트워크의 상태를 검사 합니다.|  
|URLDownloadToCacheFile 실패 했습니다 HRESULT '\<번호 >'입니다. 다운로드 하는 동안 오류가 발생 '\<파일 >'입니다.|사용자가 설정한 Internet Explorer 고급 보안 옵션 "사이 전환할 때 경고 및 비보안 모드" 배포 대상 컴퓨터와 보안 사이트를 설치 하는 ClickOnce 응용 프로그램의 설치 URL 안전 하지 않은에서 리디렉션된 경우 (또는 반대로)를 중단 하는 Internet Explorer 경고 때문에 설치가 실패 합니다.<br /><br /> 이 해결 하려면 다음 중 하나를 수행할 수 있습니다.<br /><br /> -보안 옵션의 선택을 취소 합니다.<br />-지정한 있는지 설정 URL이 보안 모드를 변경 하는 방식으로 리디렉션되지 않습니다.<br />-리디렉션을 완전히 제거 하 고 실제 설치 URL을 가리킵니다.|  
|오류가 하드 디스크에 쓰는 발생 했습니다. 사용할 수 없는 공간이 부족 하 여 디스크에 있습니다. 시스템 관리자 또는 응용 프로그램 공급 업체에 문의 하십시오.|이 응용 프로그램을 저장 하기 위한 충분 한 디스크 공간을 나타낼 수 있습니다 하지만 응용 프로그램 파일 드라이브에 저장 하려고 시도할 때 보다 일반적인 I/O 오류를 나타낼 수도 있습니다.|  
|응용 프로그램을 시작할 수 없습니다. 디스크에 사용 가능한 공간이 충분 하지 않습니다.|하드 디스크가 가득 찼습니다. 공간을 지우고 응용 프로그램을 다시 실행 하려고 합니다.|  
|너무 많은 배포 된 정품 인증을 한 번에 로드 하려고 합니다.|[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 동시에 시작할 수 있는 다른 응용 프로그램의 수를 제한 합니다. 로컬에 대 한 서비스 거부 공격을 사용 하면 악의적인 시도 방지 하기 위해 주로 이것이 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 서비스; 빠르게 연속적으로 반복 해 서 동일한 응용 프로그램을 시작 하려고만 결국의 단일 인스턴스를 사용 하는 사용자는 응용 프로그램입니다.|  
|네트워크를 통해 바로 가기 키를 활성화할 수 없습니다.|바로 가기는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 로컬 하드 디스크에만 응용 프로그램을 시작할 수 있습니다. 원격 서버에 바로 가기 파일을 가리키는 URL을 열어 시작할 수는 없습니다.|  
|응용 프로그램은 너무 커서 부분 신뢰에서 온라인으로 실행 합니다. 시스템 관리자 또는 응용 프로그램 공급 업체에 문의 하십시오.|부분 신뢰에서 실행 되는 응용 프로그램은 기본적으로이 250MB 온라인 응용 프로그램 할당의 크기의 절반 보다 클 수 없습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce 배포 문제 해결](../deployment/troubleshooting-clickonce-deployments.md)