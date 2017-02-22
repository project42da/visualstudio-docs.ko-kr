---
title: "방법: 소스 제어 플러그 인 설치 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 플러그 인 설치 [Visual Studio SDK]"
  - "소스 제어 플러그 인 설치"
ms.assetid: 9e2e01d9-7beb-42b2-99b2-86995578afda
caps.latest.revision: 32
caps.handback.revision: 32
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: 소스 제어 플러그 인 설치
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

소스 제어 플러그 인을 만드는 세 가지 단계가 포함 됩니다.  
  
1.  이 설명서의 소스 제어 플러그 인 API 참조 섹션에 정의 된 함수가 있는 DLL을 만듭니다.  
  
2.  소스 제어 플러그 인 API 정의 함수를 구현 합니다. 때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 에 대 한 호출 인터페이스 및 대화 상자에서 사용할 수 있도록 플러그 인입니다.  
  
3.  적절 한 레지스트리 항목을 만들어 DLL을 등록 합니다.  
  
## <a name="integration-with-visual-studio"></a>Visual Studio와의 통합  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 제어 플러그 인 소스 제어 플러그 인 API에 맞는 지원 합니다.  
  
### <a name="registering-the-source-control-plug-in"></a>소스 제어 플러그 인을 등록합니다.  
 먼저 소스를 소스 제어 시스템에 실행 중인 통합된 개발 환경 (IDE)을 호출 하려면 먼저 찾아야 API 내보내는 플러그 인 DLL을 제어 합니다.  
  
##### <a name="to-register-the-source-control-plug-in-dll"></a>등록 하는 소스 제어 플러그 인 DLL  
  
1.  사용자 제품 이름 하위 키 뒤에 회사 이름 하위 키를 지정 하는 소프트웨어 하위 키에 HKEY_LOCAL_MACHINE 키 아래 두 항목을 추가 합니다. 이 패턴은 HKEY_LOCAL_MACHINE\SOFTWARE\\*[회사 이름]*\\*[제품 이름]*\\*[항목]* = 값입니다. 두 항목은 항상 SCCServerName 및 SCCServerPath 호출 됩니다. 각 일반 문자열입니다.  
  
     예를 들어, 회사 이름은 Microsoft 및 소스 제어 제품 명명 됩니다 SourceSafe이 레지스트리 경로 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SourceSafe 됩니다. 이 하위 키 SCCServerName, 첫 번째 항목은 제품을 명명 하는 사용자가 읽을 수 있는 문자열은 두 번째 항목 SCCServerPath, IDE에 연결 해야 하는 플러그 인 DLL을 제어 하는 소스에 전체 경로입니다. 다음 샘플 레지스트리 항목을 제공합니다.  
  
    |예제 레지스트리 항목|예제 값|  
    |---------------------------|------------------|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SourceSafe\SCCServerName|Microsoft Visual SourceSafe|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SourceSafe\SCCServerPath|c:\vss\win32\ssscc.dll|  
  
    > [!NOTE]
    >  SCCServerPath는 전체 경로 SourceSafe 플러그 인입니다. 소스 제어 플러그 인 회사와 제품 이름은 다르지만 동일한 레지스트리 항목 경로 사용 합니다.  
  
2.  소스 제어 플러그 인의 동작을 수정 하는 다음 선택적 레지스트리 항목을 사용할 수 있습니다. 이러한 항목 SccServerName SccServerPath과 같은 하위 키에서 이동합니다.  
  
    -   HideInVisualStudioregistry 항목을 사용 하 여 소스 제어 플러그 인에 플러그 인 선택 목록에 표시 하지 않을 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 이 항목의 소스 제어 플러그 인에 자동 전환 변경 됩니다. 경우에 소스 제어 플러그 인을 대체 하는 소스 제어 패키지를 제공 하지만 소스 제어 플러그 인에 소스 제어 패키지를 사용 하 여 마이그레이션할 사용자에 대해 쉽게 수행할 수 있도록 하려는 하는이 항목에 사용할 수 있습니다. 소스 제어 패키지를 설치 하는 경우 플러그 인을 숨기는이 레지스트리 항목을 설정 합니다.  
  
         HideInVisualStudio 값은 DWORD 값 하 고 플러그 인을 숨기려면 1 또는 플러그 인을 표시 하는 0으로 설정 됩니다. 레지스트리 항목이 표시 되지 않으면 기본 동작은 플러그 인을 표시 합니다.  
  
    -   비활성화 하거나 숨길 DisableSccManager 레지스트리 항목을 사용할 수는 **시작 \< 소스 제어 서버>** 일반적으로 아래에 표시 된 메뉴 옵션은 **파일** -> **소스 제어** 하위 메뉴입니다. 호출 옵션이 메뉴를 선택 하 고 [SccRunScc](../../extensibility/sccrunscc-function.md) 함수입니다. 소스 제어 플러그 인 외부 프로그램을 지원 되지 않을 수 있으며 따라서 수 있습니다를 비활성화 하거나 숨길도 **시작** 메뉴 옵션입니다.  
  
         DisableSccManager는 DWORD 값을 사용 하도록 설정 하려면 0으로 설정 됩니다는 **시작 \< 소스 제어 서버>** 메뉴 옵션을 메뉴 옵션을 사용 하지 않도록 설정 하려면 1로 설정 하 고 메뉴 옵션을 숨기려면 2로 설정 합니다. 이 레지스트리 항목이 표시 되지 않으면 기본 동작은 메뉴 옵션을 표시 합니다.  
  
    |예제 레지스트리 항목|예제 값|  
    |---------------------------|------------------|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SourceSafe\HideInVisualStudio|1|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\SourceSafe\DisableSccManager|1|  
  
3.  하위 키를 SourceCodeControlProvider, 소프트웨어 하위 키에서 HKEY_LOCAL_MACHINE 키 아래에 추가 합니다.  
  
     이 하위 키에서 레지스트리 항목 ProviderRegKey 설정은 1 단계에서 레지스트리에 저장 하는 하위 키를 나타내는 문자열입니다. 이 패턴은 HKEY_LOCAL_MACHINE\SOFTWARE\SourceCodeControlProvider\ProviderRegKey 소프트웨어 =\\*[회사 이름]*\\*[제품 이름]*합니다.  
  
     다음은이 하위 키에 대 한 샘플 콘텐츠입니다.  
  
    |레지스트리 항목|예제 값|  
    |--------------------|------------------|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\SourceCodeControlProvider\ProviderRegKey|SOFTWARE\Microsoft\SourceSafe|  
  
    > [!NOTE]
    >  동일한 하위 키 및 항목 이름에 소스 제어 플러그 인을 사용할 하지만 값은 다를 수 있습니다.  
  
4.  SourceCodeControlProvider 하위 키 아래 InstalledSCCProviders 라는 하위 키를 만들고 그런 다음 해당 하위 키 아래에서 하나의 항목을 배치 합니다.  
  
     이 항목의 이름 (동일 SCCServerName 항목에 대 한 지정 된 값), 공급자의 사용자가 읽을 수 있는 이름 이며 값을 다시 한 번 1 단계에서 만든 하위 키입니다. 이 패턴은 HKEY_LOCAL_MACHINE\SOFTWARE\SourceCodeControlProvider\InstalledSCCProviders\\*[표시 이름]* 소프트웨어 =\\*[회사 이름]*\\*[제품 이름]*합니다.  
  
     예:  
  
    |예제 레지스트리 항목|예제 값|  
    |---------------------------|------------------|  
    |HKEY_LOCAL_MACHINE\SOFTWARE\SourceCodeControlProvider\InstalledSCCProviders\Microsoft Visual SourceSafe|SOFTWARE\Microsoft\SourceSafe|  
  
    > [!NOTE]
    >  여러 소스 제어 플러그 인이 방식으로 등록 되어 있을 수 있습니다. 이 어떻게 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 제어 플러그 인 API 기반 플러그 인 설치 된 모든 찾습니다.  
  
## <a name="how-an-ide-locates-the-dll"></a>IDE는 DLL을 찾는 방법  
  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE에는 두 개의 소스 찾기 가지 플러그 인 DLL을 제어 합니다.  
  
-   기본 소스 제어 플러그 인 찾아 자동으로 연결 합니다.  
  
-   찾을 등록 된 모든 소스 제어 플러그 인을 사용자가 하나입니다.  
  
 첫 번째 방법은 해당 DLL을 찾을 IDE ProviderRegKey 항목에 대 한 HKEY_LOCAL_MACHINE\Software\SourceCodeControlProvider 하위 키 아래 표시 됩니다. 이 항목의 값은 다른 하위 키를 가리킵니다. IDE는 그런 다음 SccServerPath HKEY_LOCAL_MACHINE 아래 두 번째 하위 키 아래에 명명 된 항목에 대 한 찾아봅니다. 이 항목의 값은 DLL에 IDE를 가리킵니다.  
  
> [!NOTE]
>  IDE는 상대 경로 (예를 들어.\NewProvider.DLL)에서 Dll을 로드 하지 않습니다. DLL에 전체 경로 지정 해야 합니다 (예를 들어 c:\Providers\NewProvider.DLL). 이 않으면 무단 또는 가장 플러그 인 Dll의 로드를 방지 하 여 IDE의 보안을 강화 합니다.  
  
 두 번째 방법은 해당 DLL을 찾을 IDE 기능에서는 모든 항목에 대 한 HKEY_LOCAL_MACHINE\Software\SourceCodeControlProvider\InstalledSCCProviders 하위 키 아래*합니다.* 각 항목에는 이름 및 값입니다. 사용자에 게 이러한 이름 목록을 표시 하는 IDE*합니다.* 사용자 이름을 선택 하는 경우 IDE 하위 키를 가리키는 선택한 이름에 대 한 값을 찾습니다. IDE는 SccServerPath HKEY_LOCAL_MACHINE 아래 하위 키 아래에 명명 된 항목을 찾습니다. 해당 항목의 값은 올바른 DLL에 IDE를 가리킵니다.  
  
 소스 제어 플러그 인 DLL을 찾는 한 가지 방법을 모두 지원 하 고 따라서 한 이전 설정을 덮어씁니다 ProviderRegKey 설정으로 설정 해야 합니다. 무엇 보다도 추가 해야 자체 InstalledSccProviders 목록에는 사용자가 사용 하는 소스 제어 플러그 인의 선택 사용할 수 없도록 합니다.  
  
> [!NOTE]
>  그러나 HKEY_LOCAL_MACHINE 키 사용 되기 때문에 하나의 소스 제어 플러그 인 지정된 된 컴퓨터에서 플러그 인 기본 소스 제어로 등록할 수 있습니다 ( [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자가 어떤 소스 제어 플러그 인을 실제로 사용할 특정 솔루션에 대 한 것인지 확인할 수). 설치 과정 확인 하는 경우 소스 제어 플러그 인 이미 설정 되어 있습니다. 그럴 경우 사용자에 게 요청 하는 새 소스 제어 플러그 인을 기본적으로 설치 되 고 설정 여부입니다. 해제-설치 중에 모든 소스 제어 플러그 인 HKEY_LOCAL_MACHINE\SOFTWARE\SourceCodeControlProvider;에 공통 되는 다른 레지스트리 하위 키를 제거 하지 마십시오 사용자 특정 SCC 하위 키만 제거 합니다.  
  
## <a name="how-the-ide-detects-version-1213-support"></a>IDE에서 지원 되는 버전 1.2/1.3을 검색 하는 방법  
 어떻게 않습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 플러그인 지원 소스 제어 플러그 인 API 버전 1.2 및 1.3 기능 여부를 감지할? 고급 기능을 선언 하는 소스 제어 플러그 인 해당 함수를 구현 해야 합니다.  
  
 첫째, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 호출 하 여 반환 값을 확인 하는 [SccGetVersion](../../extensibility/sccgetversion-function.md)합니다. 보다 크거나 같은 1.2 이어야 합니다.  
  
 다음으로, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 검사 하 여 특정 새 기능이 지원 되는지 여부를 결정은 `lpSccCaps` 의 인수는 [SccInitialize](../../extensibility/sccinitialize-function.md)합니다.  
  
 이러한 조건을 모두 충족 되 면 버전 1.2 및 1.3에서에서 지원 되는 새 함수를 호출할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작 하기](../../extensibility/internals/getting-started-with-source-control-plug-ins.md)