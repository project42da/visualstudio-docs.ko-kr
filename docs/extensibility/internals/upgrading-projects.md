---
title: "프로젝트 업그레이드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- upgrading VSPackages
- upgrading applications, strategies
- VSPackages, upgrade support
ms.assetid: e01cb44a-8105-4cf4-8223-dfae65f8597a
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 060823a04127480ef8de387200425a34c6ef1178
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="upgrading-projects"></a>프로젝트 업그레이드
프로젝트 모델에의 한 버전에서 변경 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다음 해야 최신 버전에서 실행 될 수 있도록 프로젝트 및 솔루션 업그레이드할 수 있습니다. [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 사용자의 프로젝트에 업그레이드 지원을 구현 하는 데 사용할 수 있는 인터페이스를 제공 합니다.  
  
## <a name="upgrade-strategies"></a>업그레이드 전략  
 업그레이드를 지원 하기 위해 프로젝트 시스템 구현을 정의 하 고 업그레이드 전략을 구현 해야 합니다. 전략을 결정 하는 데,-side-by-side (SxS) 백업, 복사 백업 중 하나 또는 둘 다를 지원할 수 있습니다.  
  
-   SxS 백업 파일을 직접 업그레이드, 적합 한 파일 이름 접미사, 예를 들어 추가 ".old" 프로젝트에 복사 하는지 의미 합니다.  
  
-   사용자가 제공한 백업 위치에 프로젝트를 모든 프로젝트 항목 복사 하는지 백업 수단을 복사 합니다. 원래 프로젝트 위치에 있는 관련 파일은 업그레이드 됩니다.  
  
## <a name="how-upgrade-works"></a>작동을 업그레이드 하는 방법  
 이전 버전에서 만든 솔루션 때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 최신 버전으로 업그레이드 해야 하는지 결정 하는 솔루션 파일 IDE 검사에서 열립니다. 필요한 경우이 업그레이드는 **업그레이드 마법사** 업그레이드 프로세스를 통해 사용자가을 자동으로 실행 됩니다.  
  
 업그레이드를 요구 하는 솔루션을 업그레이드 하 여 새로운 전략에 대 한 각 프로젝트 팩터리를 쿼리 합니다. 전략은 복사 백업 또는 SxS 백업 프로젝트 팩터리 지원 하는지 여부를 결정 합니다. 정보는 전송 된 **업그레이드 마법사**, 백업에 필요한 정보를 수집 하 고 사용자에 게 사용 가능한 옵션을 제공 합니다.  
  
### <a name="multi-project-solutions"></a>다중 프로젝트 솔루션  
 솔루션에 여러 프로젝트가 포함 된 경우 업그레이드 전략을 협상 하는 c + + 프로젝트만 지 원하는 SxS 백업 및 복사 백업에만 지 웹 프로젝트, 프로젝트 팩터리와 같은 업그레이드 전략 달라 집니다.  
  
 솔루션에 대 한 각 프로젝트 팩터리를 쿼리하여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory>합니다. 그런 다음 연속 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject_CheckOnly%2A> 전역 프로젝트 파일 업그레이드 해야 하는 경우 확인 하 고 지원 되는 업그레이드 전략을 결정 하 합니다. **업그레이드 마법사** 그런 다음를 호출 합니다.  
  
 사용자는 마법사를 완료 한 후 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 실제 업그레이드를 수행 하려면 각 프로젝트 공장에서 호출 됩니다. 백업을 쉽게 하려면 IVsProjectUpgradeViaFactory 메서드를 제공는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUpgradeLogger> 서비스를 업그레이드 프로세스의 세부 정보를 기록 합니다. 이 서비스를 캐시할 수 없습니다.  
  
 모든 관련 전역 파일이 업데이트 한 후 각 프로젝트 팩터리를 인스턴스화하는 프로젝트 선택할 수 있습니다. 지원 하도록 프로젝트 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 모든 관련 프로젝트 항목 업그레이드 메서드가 호출 됩니다.  
  
> [!NOTE]
>  <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 방법은 SVsUpgradeLogger 서비스를 제공 하지 않습니다. 이 서비스를 호출 하 여 얻을 수 있습니다 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A>합니다.  
  
## <a name="best-practices"></a>모범 사례  
 사용 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave> 서비스를 편집 하기 전에 파일을 편집할 수 올바르며 저장 하기 전에 저장할 수 있는지 확인 합니다. 이렇게 하면 백업 및 업그레이드 구현 소스 제어에서 프로젝트 파일, 권한 부족 등을 사용 하 여 파일을 처리 합니다.  
  
 사용 된 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUpgradeLogger> 백업 서버로의 서비스 및 업그레이드에 성공 또는 실패는 업그레이드 프로세스의 정보를 제공 합니다.  
  
 백업 하 고 프로젝트를 업그레이드 하는 방법에 대 한 자세한 내용은 vsshell2.idl에 IVsProjectUpgrade에 대 한 주석을 참조 합니다.  
  
## <a name="upgrading-custom-projects"></a>사용자 지정 프로젝트 업그레이드
제품의 다른 Visual Studio 버전 간에 프로젝트 파일에 있는 정보를 변경하는 경우 이전 버전에서 새 버전으로의 프로젝트 파일 업그레이드를 지원해야 합니다. 에 참여할 수 있도록 업그레이드를 지원 하려면는 **Visual Studio 변환 마법사**, 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> 인터페이스입니다. 이 인터페이스에는 복사 업그레이드에 사용할 수 있는 메커니즘만 포함되어 있습니다. 프로젝트 업그레이드는 솔루션의 일부가 열릴 때 수행됩니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> 인터페이스 프로젝트 팩터리에서 구현 되거나 프로젝트 팩터리에서 얻을 수 이상 있어야 합니다.  
  
 사용 하는 이전 메커니즘은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> 인터페이스는 계속 지원 하지만 프로젝트를 열고의 일부로 프로젝트 시스템을 개념적으로 업그레이드 합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> 인터페이스 따라서 호출한는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 환경 경우라도는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> 인터페이스 또는 구현 합니다. 이 방법을 사용할 수 있습니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> 복사본을 구현 하 고 프로젝트 업그레이드의 전용 부분 위임할 수 (수 있는 새 위치)에서 전체를 수행 하는 작업의 나머지 부분에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> 인터페이스입니다.  
  
 샘플 구현을 보려면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>, 참조 [VSSDK 샘플](http://aka.ms/vs2015sdksamples)합니다.  
  
 프로젝트 업그레이드에서는 다음과 같은 시나리오가 발생합니다.  
  
-   파일이 프로젝트에서 지원할 수 있는 형식보다 최신 형식인 경우 이를 설명하는 오류를 반환해야 합니다. 이 제품의 이전 버전에는 버전을 확인 하는 코드를 가정 합니다.  
  
-   경우는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS> 플래그가 지정 된 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 메서드를 업그레이드 하려는 프로젝트를 열기 전에 현재 위치 업그레이드로 구현 합니다.  
  
-   경우는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS> 플래그가 지정 된 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 메서드에 복사 업그레이드로 구현 됩니다.  
  
-   경우는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS> 플래그가 지정 된 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 가 되었습니다 하 라는 메시지가 환경에서 프로젝트를 연 후 프로젝트 파일 업그레이드를로 업그레이드 한 다음 호출 합니다. 예를 들어 사용자가 이전 버전의 솔루션을 여는 경우 업그레이드하라는 메시지가 표시됩니다.  
  
-   경우는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS> 에 플래그를 지정 하지 않으면는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 호출 사용자에 게 프로젝트 파일 업그레이드를 물어야 합니다.  
  
     다음은 업그레이드 프롬프트 메시지의 예입니다.  
  
     "'%1' 프로젝트는 이전 버전의 Visual Studio에서 만들었습니다. 이 버전의 Visual Studio에서 이 프로젝트를 열면 이전 버전의 Visual Studio에서 이 프로젝트를 열 수 없습니다. 이 프로젝트를 계속 여시겠습니까?”  
  
### <a name="to-implement-ivsprojectupgradeviafactory"></a>IVsProjectUpgradeViaFactory를 구현하려면  
  
1.  메서드를 구현 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> 인터페이스, 특히는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 하거나 프로젝트 팩터리 구현에서 메서드 또는 구현 하거나 프로젝트 팩터리 구현에서 호출할 수 있도록 합니다.  
  
2.  솔루션 열기의 일부로 현재 위치 업그레이드를 수행 하려면 제공 플래그 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS> 로 `VSPUVF_FLAGS` 매개 변수에서 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 구현 합니다.  
  
3.  솔루션 열기의 일부로 현재 위치 업그레이드를 수행 하려면 제공 플래그 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS> 로 `VSPUVF_FLAGS` 매개 변수에서 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 구현 합니다.  
  
4.  실제 파일 업그레이드 단계를 사용 하 여 두는 2 단계와 3 단계를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>에 설명 된 대로 구현할 수는 "구현 `IVsProjectUpgade`" 아래 섹션 또는 실제 파일 업그레이드를 위임할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>합니다.  
  
5.  메서드를 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUpgradeLogger> 업그레이드를 게시 하려면 Visual Studio 마이그레이션 마법사를 사용 하 여 사용자에 대 한 메시지를 관련 됩니다.  
  
6.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsFileUpgrade>인터페이스는 모든 종류의 프로젝트 업그레이드의 일부로 발생 해야 하는 파일 업그레이드를 구현 하는 데 사용 됩니다. 이 인터페이스에서 호출 하지 않으면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory>, 프로젝트 시스템, 하지만 기본 프로젝트 시스템의 일부인 파일을 업그레이드 하는 메커니즘을 직접 미처 인식 하지 못할 때 제공 됩니다. 예를 들어 나머지 프로젝트 시스템을 처리하는 개발 팀이 컴파일러 관련 파일 및 속성을 처리하지 않는 경우 이러한 상황이 발생할 수 있습니다.  
  
### <a name="ivsprojectupgrade-implementation"></a>IVsProjectUpgrade 구현  
 프로젝트 시스템을 구현 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> 만에 참여 하지 수는 **Visual Studio 변환 마법사**합니다. 그러나 구현 하는 경우에는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> 인터페이스를 위임할 수 있습니다 여전히 파일 업그레이드를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> 구현 합니다.  
  
#### <a name="to-implement-ivsprojectupgrade"></a>IVsProjectUpgrade를 구현하려면  
  
1.  사용자가 프로젝트를 열면는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 메서드는 환경에서 프로젝트를 열 및 다른 사용자 하기 전에 작업을 프로젝트에서 수행할 수 있습니다. 사용자가 이미 되었습니다 하 라는 메시지가 나타나면 솔루션을 업그레이드 하면 <xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS> 플래그가에 전달 됩니다는 `grfUpgradeFlags` 매개 변수입니다. 사용자가 프로젝트를 직접 이러한를 열면를 사용 하 여 as는 **기존 프로젝트 추가** 명령을 하면 <xref:Microsoft.VisualStudio.Shell.Interop.__VSUPGRADEPROJFLAGS> 플래그가 전달 되지 않으며 프로젝트에 업그레이드 하 라는 메시지를 추가 해야 합니다.  
  
2.  에 대 한 응답은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 호출에서 프로젝트 프로젝트 파일을 업그레이드 여부를 평가 해야 합니다. 프로젝트는 프로젝트 형식을 새 버전으로 업그레이드 하지 않아도 경우 반환할 수 있습니다는 <xref:Microsoft.VisualStudio.VSConstants.S_OK> 플래그입니다.  
  
3.  프로젝트 형식을 새 버전으로 업그레이드 하는 프로젝트에 추가 해야 하는 경우 호출 하 여 프로젝트 파일을 수정할 수 있는지 여부를 확인 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 메서드 및 값을 전달 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags> 에 대 한는 `rgfQueryEdit` 매개 변수입니다. 그런 다음 프로젝트에서 다음을 수행해야 합니다.  
  
    -   경우는 `VSQueryEditResult` 에 반환 된 값의 `pfEditCanceled` 매개 변수는 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult>, 프로젝트 파일을 쓸 수 있으므로 업그레이드를 계속 합니다.  
  
    -   경우는 `VSQueryEditResult` 에 반환 된 값의 `pfEditCanceled` 매개 변수는 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult> 및 `VSQueryEditResult` 값에는 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags> 비트가 설정 다음 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 사용자 권한 문제를 직접 해결 해야 하기 때문에 오류를 반환 해야 합니다. 그런 다음 프로젝트에서 다음을 수행해야 합니다.  
  
         호출 하 여 사용자에 게 오류를 보고 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.ReportErrorInfo%2A> 다음 다시 돌아와 <xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes> 오류 코드를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>합니다.  
  
    -   경우는 `VSQueryEditResult` 값은 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult> 및 `VSQueryEditResultFlags` 값에는 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags> 호출 하 여 프로젝트 파일을 체크아웃할 수 해야 다음 비트가 설정 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> (<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags>, <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags>,...).  
  
4.  경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 프로젝트 파일에서 호출 하면 파일을 체크 아웃 되 고 최신 버전을 검색할 수는 프로젝트가 언로드 및 다시 로드 합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 프로젝트의 다른 인스턴스가 만들어지면 메서드가 다시 호출 됩니다. 이 두 번째 호출에서 프로젝트 파일을 디스크에 쓸 수 있습니다. 프로젝트에서 프로젝트 파일의 복사본을 .OLD 확장명을 사용하는 이전 형식으로 저장하고 필요한 업그레이드 변경을 수행한 다음 프로젝트 파일을 새 형식으로 저장하는 것이 좋습니다. 마찬가지로 업그레이드 프로세스의 일부가 실패 하면, 메서드를 지정 해야 실패를 반환 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes>합니다. 이로 인해 솔루션 탐색기에서 프로젝트가 언로드됩니다.  
  
     경우에 대 한 환경에서 발생 하는 전체 프로세스를 이해 하는에 대 한 호출에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 메서드 (reportonly 값 지정)를 반환는 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult> 및 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags> 플래그입니다.  
  
5.  사용자가 프로젝트 파일을 열려고 합니다.  
  
6.  환경에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CanCreateProject%2A> 구현 합니다.  
  
7.  경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CanCreateProject%2A> 반환 `true`, 다음 환경 호출 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CanCreateProject%2A> 구현 합니다.  
  
8.  환경에 <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat.Load%2A> Project1 파일을 열고 프로젝트 개체를 예를 들어 초기화를 구현 합니다.  
  
9. 환경에서 `IVsProjectUpgrade::UpgradeProject` 구현을 호출하여 프로젝트 파일을 업그레이드해야 하는지 여부를 확인합니다.  
  
10. 호출 하면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 의 값을 전달 하 고 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags> 에 대 한는 `rgfQueryEdit` 매개 변수입니다.  
  
11. 환경 반환 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult> 에 대 한 `VSQueryEditResult` 및 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResultFlags> 에 비트가 설정 `VSQueryEditResultFlags`합니다.  
  
12. 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade> 구현 호출 `IVsQueryEditQuerySave::QueryEditFiles` (<xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags>, <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags>).  
  
 이 호출로 인해 프로젝트 파일의 새 복사본이 체크 아웃되고 최신 버전이 검색될 수 있으며 프로젝트 파일을 다시 로드해야 합니다. 이때 다음 두 가지 중 하나가 발생합니다.  
  
-   프로젝트 다시 로드를 처리 하는 경우 다음 환경 호출 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> (VSITEMID_ROOT) 구현을 합니다. 이 호출을 받는 경우 프로젝트의 첫 번째 인스턴스(Project1)를 다시 로드하고 계속 프로젝트 파일을 업그레이드합니다. 환경 반환 하는 경우 프로젝트 다시 로드를 처리 한다고 인식 `true` 에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> (<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>).  
  
-   사용자 고유의 프로젝트 다시 로드를 처리 하지 않는 경우 돌아가면 `false` 에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> (<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID>). 이 경우 전에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A>(QEF_ForceEdit_NoPrompting, QEF_DisallowInMemoryEdits) 반환 환경 Project2 예를 들어 프로젝트의 다른 새 인스턴스를 다음과 같이 만듭니다.  
  
    1.  환경 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.Close%2A> 첫 번째 프로젝트 개체 Project1에 있으므로이 개체에에서 배치 비활성 상태입니다.  
  
    2.  환경에서 `IVsProjectFactory::CreateProject` 구현하여 프로젝트의 두 번째 인스턴스 Project2를 만듭니다.  
  
    3.  환경에서 `IPersistFileFormat::Load` 구현을 호출하여 파일을 열고 두 번째 프로젝트 개체 Project2를 초기화합니다.  
  
    4.  환경에서 `IVsProjectUpgrade::UpgradeProject` 를 두 번째로 호출하여 프로젝트 개체를 업그레이드해야 하는지 여부를 결정합니다. 그러나 이 호출은 프로젝트의 새로운 두 번째 인스턴스 Project2에 대해 수행됩니다. 이 프로젝트가 솔루션에 열려 있는 프로젝트입니다.  
  
        > [!NOTE]
        >  첫 번째 프로젝트를 Project1 비활성 상태로 배치 됩니다 반환 해야 합니다는 인스턴스의 <xref:Microsoft.VisualStudio.VSConstants.S_OK> 첫 번째 호출에서 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 구현 합니다.  
  
    5.  호출 하면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 의 값을 전달 하 고 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditFlags> 에 대 한는 `rgfQueryEdit` 매개 변수입니다.  
  
    6.  환경 반환 <xref:Microsoft.VisualStudio.Shell.Interop.tagVSQueryEditResult> 및 프로젝트 파일을 쓸 수 있으므로 업그레이드를 진행할 수 있습니다.  
  
 업그레이드 하지 않으면 반환 <xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes> 에서 `IVsProjectUpgrade::UpgradeProject`합니다. 업그레이드가 필요하지 않거나 업그레이드하지 않으려면 `IVsProjectUpgrade::UpgradeProject` 호출을 no-op으로 처리합니다. 반환 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.VSErrorCodes>, 자리 표시자 노드가 솔루션 프로젝트에 추가 됩니다.  
  
## <a name="upgrading-project-items"></a>프로젝트 항목 업그레이드
  
를 추가 하거나 구현 하지 않는 프로젝트 시스템 내의 항목을 관리 하는 경우 프로젝트 업그레이드 프로세스에 참여 하도록 해야 합니다. Crystal Reports은 프로젝트 시스템에 추가할 수 있는 항목의 예입니다.  
  
 일반적으로 프로젝트 항목 구현자 참조는 어떤 프로젝트와 다른 프로젝트 속성 있는 무엇이 업그레이드 방법을 결정할 수를 알 필요 하기 때문에 이미 완전히 인스턴스화된 및 업그레이드 된 프로젝트를 활용 하 게 합니다.  
  
### <a name="to-get-the-project-upgrade-notification"></a>프로젝트 업그레이드 알림을 가져올  
  
1.  설정의 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80.SolutionOrProjectUpgrading> 프로젝트 항목 구현에서 플래그 (vsshell80.idl에 정의 됨). 이렇게 하면 자동으로 VSPackage 프로젝트 항목 때 로드는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 셸으로 결정 하는 프로젝트 시스템의 업그레이드를 진행 합니다.  
  
2.  통지는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEventsProjectUpgrade> 통해 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution2.AdviseSolutionEvents%2A> 메서드.  
  
3.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEventsProjectUpgrade> 인터페이스는 프로젝트 시스템 구현에는 업그레이드 작업이 완료 되 고 새 업그레이드 된 프로젝트를 만들 후 발생 합니다. 시나리오에 따라는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEventsProjectUpgrade> 인터페이스 후 발생 합니다.는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenSolution%2A>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A>, 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject%2A> 메서드.  
  
### <a name="to-upgrade-the-project-item-files"></a>프로젝트 항목 파일을 업그레이드 하려면  
  
1.  프로젝트 항목 구현에서 파일 백업 프로세스를 신중 하 게 관리 해야 합니다. Side-by-side-백업에 대 한 특히 적용이 위치는 `fUpgradeFlag` 의 매개 변수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 방법은로 설정 되어 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS>".old"로 지정 된 클라이언트측 파일 따라를 백업한 파일 위치, 합니다. 오래 된 것은 프로젝트를 업그레이드 하는 경우 시스템 시간 보다 오래 된 백업된 파일을 지정할 수 있습니다. 또한 것이 방지 하기 위해 특정 단계를 수행 하지 않는 한 덮어쓸 수 있습니다.  
  
2.  프로젝트 항목의 프로젝트 업그레이드에 대 한 알림을 가져옵니다 시간에는 **Visual Studio 변환 마법사** 계속 표시 됩니다. 따라서의 메서드를 사용 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUpgradeLogger> 마법사 UI 업그레이드 하는 메시지를 제공 하는 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트](../../extensibility/internals/projects.md)   
