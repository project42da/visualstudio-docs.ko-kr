---
title: "사용자 설정에 대 한 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Custom Settings Points
- user settings [Visual Studio SDK], registering persistence support
- persistence, registering settings
ms.assetid: ad9beac3-4f8d-4093-ad0e-6fb00444a709
caps.latest.revision: "26"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8d25243c82cbb1facc4029e1a770113a7b1fca57
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="support-for-user-settings"></a>사용자 설정에 대 한 지원
VSPackage는 상태 변수를 사용자가 유지 되는 그룹인 하나 이상 설정 범주를 정의할 수는 **설정 가져오기/내보내기** 명령을 **도구** 메뉴. 이 지 속성을 설정 하려면 설정을 Api 사용에 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]합니다.  
  
 사용자 지정 설정 지점 및 GUID 라고 하는 레지스트리 항목 VSPackage의 설정 범주를 정의 합니다. VSPackage는 여러 설정 범주를 지원할 수 있습니다, 그리고 각각 사용자 지정 설정 지점으로 정의 된 합니다.  
  
-   Interop 어셈블리를 기반으로 하는 설정의 구현 (사용 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings> 인터페이스) 사용자 지정 설정 지점 레지스트리를 편집 하거나 등록자 스크립트 (.rgs 파일)를 사용 하 여 만들어야 합니다. 자세한 내용은 참조 [등록자 스크립트를 만드는](/cpp/atl/creating-registrar-scripts)합니다.  
  
-   관리 되는 패키지 프레임 워크 (MPF)를 사용 하는 코드를 연결 하 여 사용자 지정 설정 지점을 만들어야는 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 각 사용자 지정 설정 지점에 대 한 VSPackage를 합니다.  
  
     단일 VSPackage 지원 몇 가지 사용자 지정 설정 지점을, 각 사용자 지정 설정 지점 별도 클래스에서 구현 되 고 각각의 고유 인스턴스를 등록 하는 경우는 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 클래스입니다. 따라서 클래스를 구현 하는 설정이 여러 개 설정 범주를 지원할 수 있습니다.  
  
## <a name="custom-settings-point-registry-entry-details"></a>사용자 지정 설정 지점 레지스트리 항목 세부 정보  
 다음 위치에 레지스트리 항목에 사용자 지정 설정 지점을 생성 됩니다: HKLM\Software\Microsoft\VisualStudio\\*\<버전 >*\UserSettings\\`<CSPName>`여기서 `<CSPName>` 의 이름인 사용자 지정 설정 지점 VSPackage 지원 및  *\<버전 >* 의 버전이 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 예를 들어 8.0 합니다.  
  
> [!NOTE]
>  HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio의 루트 경로\\*\<버전 >* 대체로 재정의할 수 있습니다 때 루트는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE)가 초기화 합니다. 자세한 내용은 참조 [명령줄 스위치](../../extensibility/command-line-switches-visual-studio-sdk.md)합니다.  
  
 레지스트리 항목의 구조는 아래 표시 되어 있습니다.  
  
 HKLM\Software\Microsoft\VisualStudio\\*\<버전 >*\UserSettings\  
  
 `<CSPName`> = ' #12345 ' s  
  
 패키지 ' {XXXXXX XXXX XXXX XXXX XXXXXXXXX을 (를) ' =  
  
 범주 = ' {YYYYYY YYYY YYYY YYYY YYYYYYYYY}'  
  
 ResourcePackage = ' {ZZZZZZ ZZZZ ZZZZ ZZZZ ZZZZZZZZZ}'  
  
 AlternateParent CategoryName =  
  
|이름|형식|데이터|설명|  
|----------|----------|----------|-----------------|  
|(기본값)|REG_SZ|사용자 지정 설정 지점의 이름|키의 이름, `<CSPName`>, 사용자 지정 설정 지점의 지역화 되지 않은 이름입니다.<br /><br /> MPF 기반 구현에서는 키의 이름을 결합 하 여 가져온는 `categoryName` 및 `objectName` 의 인수는 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 생성자에 `categoryName_objectName`합니다.<br /><br /> 키는 비워 둘 수 있습니다 또는 위성 DLL에서에서 지역화 된 문자열에 참조 ID를 포함할 수 있습니다. 이 값에서 가져온는 `objectNameResourceID` 인수에는 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 생성자입니다.|  
|패키지|REG_SZ|GUID|사용자 지정 설정 지점을 구현 하는 VSPackage의 GUID입니다.<br /><br /> 구현 MPF를 사용 하 여 기반는 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 클래스, 생성자의를 사용 하 여 `objectType` VSPackage의 포함 하는 인수 <xref:System.Type> 및이 값을 얻는 리플렉션 합니다.|  
|범주|REG_SZ|GUID|설정 범주를 식별 하는 GUID입니다.<br /><br /> Interop 어셈블리에 따라 구현에 대 한이 값이 임의로 선택한 될 수 있습니다 GUID는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE에 전달 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ExportSettings%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ImportSettings%2A> 메서드. 이러한 두 가지 방법의 모든 구현이 해당 GUID 인수를 확인 해야 합니다.<br /><br /> MPF 기반 구현에서는이 GUID 여 가져온는 <xref:System.Type> 클래스 구현의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 설정 메커니즘입니다.|  
|ResourcePackage|REG_SZ|GUID|선택 사항입니다.<br /><br /> VSPackage 구현에서 제공 하지 않는 경우 지역화 된 문자열을 위성 포함 된 DLL에 대 한 경로입니다.<br /><br /> MPF 리플렉션을 사용 하 여 올바른 리소스 VSPackage를 가져올 하므로 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 클래스는이 인수를 설정 하지 않습니다.|  
|AlternateParent|REG_SZ|이 사용자 지정 설정 지점이 포함 된 도구 옵션 페이지 아래에 있는 폴더의 이름입니다.|선택 사항입니다.<br /><br /> 설정 구현을 지 원하는 경우에이 값을 설정 해야 **도구 옵션** 의 지 속성 메커니즘을 사용 하는 페이지는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 대신 자동화 모델 상태를 저장 하는 메커니즘입니다.<br /><br /> 이러한 경우 AlternateParent 키의 값은는 `topic` 의 섹션은 `topic.sub-topic` 문자열 특정을 식별 하는 데 **ToolsOptions** 페이지. 예를 들어는 **ToolsOptions** 페이지 `"TextEditor.Basic"` AlternateParent의 값 수 `"TextEditor"`합니다.<br /><br /> 때 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 사용자 지정 설정 지점에서는 발생 하는 범주 이름와 같습니다.|