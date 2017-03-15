---
title: "Vspackage 문제 해결 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, troubleshooting
- debugging, VSPackages
ms.assetid: 274673e7-72e7-476f-a263-3411b5b874be
caps.latest.revision: 22
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: 933b0177e3287717b2cfb900996b947db7034ee5
ms.lasthandoff: 02/22/2017

---
# <a name="troubleshooting-vspackages"></a>Vspackage 문제 해결
다음은 일반적인 문제를 VSPackage 있을 수 있으며 문제를 해결 하기 위한 팁.  
  
### <a name="to-troubleshoot-a-vspackage-that-keeps-visual-studio-from-starting"></a>Visual Studio가 시작 유지 하는 VSPackage의 문제를 해결 하려면  
  
-   시작 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 안전 모드에서.  
  
     시작 하려면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 명령 프롬프트에서 안전 모드에서는 입력 **devenv.exe /safemode**합니다.  
  
     이 프로세스 중 없는 Vspackage에 포함 된 Vspackage를 제외 하 고 로드 된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
### <a name="to-troubleshoot-a-vspackage-that-does-not-load"></a>VSPackage를 로드 하지 않는 문제를 해결 하려면  
  
1.  일반적으로 실험 레지스트리 루트를 실행 하려면 VSPackage 등록 되어 있는 레지스트리 루트를 사용 하 고 있는지 확인 합니다.  
  
     자세한 내용은 참조 [의 실험적 인스턴스에서](../extensibility/the-experimental-instance.md)합니다.  
  
2.  VSPackage는 실험적 레지스트리 루트에서 실행을 위한, 하는 경우의 실험적 버전 실행 되 고 있는지 확인 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
     실험적 버전을 실행 하려면 명령 창에서 다음을 입력: **devenv /rootsuffix exp**합니다.  
  
3.  VSPackage 레지스트리 항목을 확인 합니다.  
  
     자세한 내용은 참조 [등록 Vspackage](http://msdn.microsoft.com/en-us/31e6050f-1457-4849-944a-a3c36b76f3dd) 및 [관리 Vspackage](../extensibility/managing-vspackages.md)합니다.  
  
4.  열기는 **출력** 인스턴스의 창 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackage 로드에 실패 하는 합니다. 이유는 VSPackage 로드에 실패 하는 방법에 대 한 정보는 해당 창에 표시 될 수 있습니다.  
  
    > [!NOTE]
    >  실험적 버전을 시작 하는 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE) 검사는 **출력** 두 버전의 창.  
  
5.  작업 로그를 검사 합니다.  
  
     자세한 내용은 참조 [하는 방법: 작업 로그를 사용 하 여](../extensibility/how-to-use-the-activity-log.md)합니다.  
  
6.  IDE에 의해 throw 된 예외에 대 한 자세한 내용은 **예외** 에 **디버그** 메뉴에 예외를 사용 합니다. 에 **예외** 대화 상자에 대 한 자세한 내용을 보려는 예외 유형을 선택 합니다.  
  
### <a name="to-troubleshoot-a-vspackage-that-does-not-register"></a>VSPackage를 등록 하지 않는 문제를 해결 하려면  
  
1.  VSPackage 어셈블리가 신뢰할 수 있는 위치에 있는지 확인 합니다. RegPkg 기본.net 보안 구성에 네트워크 공유와 같은 신뢰할 수 없는 또는 부분적으로 신뢰할 수 있는 위치에 어셈블리를 등록할 수 없습니다. 사용자가 신뢰할 수 없는 위치에 프로젝트를 만들 때마다 경고가 나타나더라도 "이이 메시지를 다시 표시 안 함" 확인란을 다시에서이 경고를 방지할 수 있습니다.  
  
### <a name="to-troubleshoot-a-command-that-is-not-visible-or-that-generates-an-error-when-you-click-a-command"></a>명령을 표시 되지 않는 또는 명령을 클릭할 때 오류를 생성 하는 문제를 해결 하려면  
  
1.  다음을 입력 하 여 새롭거나 변경 된 메뉴 명령 및 IDE에 이미 병합는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 명령 프롬프트: **devenv /rootsuffix Exp /setup**합니다.  
  
2.  다음 사항을 확인 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackage에 대 한 UI.dll를 찾을 수 있습니다.  
  
    1.  레지스트리의 패키지 섹션에서 VSPackage의 CLSID를 찾습니다.  
  
         HKLM\Software\Microsoft\Visual Studio\\*\<버전 >*\Packages  
  
    2.  SatelliteDll 하위 키를 제공한 경로가 정확한 지 확인 합니다.  
  
### <a name="to-troubleshoot-a-vspackage-that-behaves-unexpectedly"></a>VSPackage 예기치 않게 동작 하는 문제를 해결 하려면  
  
1.  코드에 중단점을 설정합니다.  
  
     디버깅을 위한 좋은 출발점은 생성자 및 초기화 메서드입니다. 메뉴 명령 등 평가 하려는 영역에 중단점을 설정할 수도 있습니다. 중단점을 설정 하려면 디버거에서 실행 해야 합니다.  
  
    1.  에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.  
  
    2.  에 **속성 페이지** 대화 상자는 **디버그** 탭 합니다.  
  
    3.  **명령줄 인수** 상자, 개발 환경의 루트 접미사를 입력 하는 VSPackage 대상입니다. 예를 들어 실험 빌드를 선택 하려면 입력: **RootSuffix Exp**합니다.  
  
    4.  에 **디버그** 메뉴 클릭 **디버깅 시작** 하거나 F5 키를 누릅니다.  
  
        > [!NOTE]
        >  프로젝트를 디버깅 하는 경우 만들거나 이제 프로젝트의 기존 인스턴스를 로드 합니다.  
  
2.  작업 로그를 사용 합니다.  
  
     주요 지점에서 작업 로그에 정보를 기록 하 여 VSPackage 동작을 추적 합니다. 이 기술은 소매 환경에서 VSPackage를 실행 하는 경우에 특히 유용 합니다. 자세한 내용은 참조 [하는 방법: 작업 로그를 사용 하 여](../extensibility/how-to-use-the-activity-log.md)합니다.  
  
3.  공용 기호를 사용 합니다.  
  
     디버깅 하는 동안 가독성을 높이기 기호 디버거를 연결할 수 있습니다.  
  
    1.  **도구/옵션** 메뉴를 탐색 하는 **디버깅/기호** 대화 상자입니다.  
  
    2.  이 추가 **기호 파일 (.pdb) 위치**:  
  
         [http://msdl.microsoft.com/download/symbols](http://msdl.microsoft.com/download/symbols)  
  
    3.  성능 향상을 위해 예를 들어 기호 캐시 폴더를 지정 합니다.  
  
        ```  
        C:\symbols  
        ```  
  
### <a name="to-troubleshoot-a-missing-vspackage-or-one-of-its-dependencies"></a>누락 된 VSPackage 또는 해당 종속성 중 하나를 해결 하려면  
  
1.  관리 코드에 대 한 참조 경로 정확한 지 확인 합니다.  
  
    1.  에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.  
  
    2.  선택은 **참조** 탭에 **속성 페이지** 모든 경로가 올바른지 대화 상자와 있는지 확인 합니다. 사용할 수 있습니다는 **개체 브라우저** 참조 된 개체를 찾아볼 수 있습니다.  
  
         관리 코드에 대해 사용할 수는 [Fuslogvw.exe (어셈블리 바인딩 로그 뷰어)](http://msdn.microsoft.com/Library/e32fa443-0778-4cc3-bf36-5c8ea297d296) 실패 한 어셈블리 로드의 세부 정보를 표시 합니다.  
  
2.  비관리 코드에 대 한 찾기에 VSPackage의 CLSID는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] CLSID 레지스트리 노드:  
  
     HKLM\Software\Microsoft\Visual Studio\\*\<버전 >*\CLSID  
  
 InprocServer32 항목 VSPackage dll의 올바른 경로 있는지 확인 하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [Vspackage](../extensibility/internals/vspackages.md)
