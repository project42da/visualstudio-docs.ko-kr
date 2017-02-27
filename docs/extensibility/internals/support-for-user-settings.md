---
title: "사용자 설정에 대 한 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "사용자 지정 설정 포인트"
  - "지 속성 지원을 등록 사용자 설정 [Visual Studio SDK]"
  - "지 속성, 등록 설정"
ms.assetid: ad9beac3-4f8d-4093-ad0e-6fb00444a709
caps.latest.revision: 26
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 26
---
# 사용자 설정에 대 한 지원
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

VSPackage 한 상태 변수를 사용자가 보관 하는 그룹 하나 이상의 설정 범주를 정의할 수는 **설정 가져오기 및 내보내기** 명령에 **도구** 메뉴. 설정을 Api를 사용 하면이 지 속성을 사용 하려면에 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]합니다.  
  
 사용자 지정 설정을 점 및 GUID 라고 하는 레지스트리 항목 VSPackage의 설정 범주를 정의 합니다. VSPackage 여러 설정 범주를 지원할 수 있는, 각각 사용자 지정 설정 지점에서 정의 합니다.  
  
-   Interop 어셈블리를 기반으로 하는 설정의 구현 \(사용 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings> 인터페이스\) 레지스트리를 편집 하거나 등록자 스크립트 \(.rgs 파일\)를 사용 하 여 사용자 지정 설정을 점을 만들어야 합니다. 자세한 내용은 [Creating Registrar Scripts](/visual-cpp/atl/creating-registrar-scripts)을 참조하십시오.  
  
-   관리 되는 패키지 프레임 워크 \(MPF\)를 사용 하는 코드를 연결 하 여 사용자 지정 설정을 포인트 만들어야는 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 각 사용자 지정 설정 지점에 대 한 VSPackage에 있습니다.  
  
     단일 VSPackage 몇 가지 사용자 지정 설정을 포인트를 지원, 각 사용자 지정 설정 점 별도 클래스에서 구현 되 고 각각의 고유 인스턴스 등록 하는 경우는 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 클래스입니다. 따라서 클래스를 구현 하는 설정을 여러 개 설정 범주를 지원할 수 있습니다.  
  
## 사용자 지정 설정 지점 레지스트리 항목 세부 정보  
 다음 위치에 레지스트리 항목에서 사용자 지정 설정을 지점이 만들어지는: HKLM\\Software\\Microsoft\\VisualStudio\\*\< 버전 \>*\\UserSettings\\`<CSPName>`, 여기서 `<CSPName>` 는 VSPackage에서 지 원하는 사용자 지정 설정을 지점의 이름을 및 *\< 버전 \>* 의 버전 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 예를 들어 8.0.  
  
> [!NOTE]
>  HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\의 루트 경로*\< 버전 \>* 대체도 재정의할 수 때 루트는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\) 초기화 됩니다. 자세한 내용은 [명령줄 스위치](../../extensibility/command-line-switches-visual-studio-sdk.md)을 참조하십시오.  
  
 레지스트리 항목의 구조는 다음과 같습니다.  
  
 HKLM\\Software\\Microsoft\\VisualStudio\\*\< 버전 \>*\\UserSettings\\  
  
 `<CSPName`\> \= ' \#12345 ' s  
  
 패키지 \= ' {XXXXXX XXXX XXXX XXXX XXXXXXXXX}'  
  
 범주 \= ' {YYYYYY YYYY YYYY YYYY YYYYYYYYY}'  
  
 ResourcePackage \= ' {ZZZZZZ ZZZZ ZZZZ ZZZZ ZZZZZZZZZ}'  
  
 AlternateParent CategoryName \=  
  
|이름|형식|데이터|설명|  
|--------|--------|---------|--------|  
|\(기본값\)|REG\_SZ|사용자 지정 설정을 포인트의 이름|키의 이름, `<CSPName`\>을 사용자 지정 설정 포인트의 지역화 되지 않은 이름입니다.<br /><br /> MPF에 따라 구현에 대 한 키의 이름을 결합 하 여 가져옵니다는 `categoryName` 및 `objectName` 의 인수는 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 생성자에 `categoryName_objectName`합니다.<br /><br /> 키 수 비어 있거나 참조 ID가 있으면 위성 DLL의 지역화 된 문자열을 포함할 수 있습니다. 이 값에서 가져온는 `objectNameResourceID` 에 대 한 인수는 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 생성자입니다.|  
|Package|REG\_SZ|GUID|사용자 지정 설정 지점을 구현 하는 VSPackage의 GUID입니다.<br /><br /> 구현을 사용 하 여 MPF 기반는 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 클래스, 생성자의 사용 `objectType` 는 VSPackage를 포함 하는 인수 <xref:System.Type> 및이 값을 얻는 리플렉션.|  
|범주|REG\_SZ|GUID|설정 범주를 식별 하는 GUID입니다.<br /><br /> Interop 어셈블리에 따라 구현에 대 한이 값이 임의로 선택한 될 수 있습니다 GUID는는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE 전달는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ExportSettings%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ImportSettings%2A> 메서드. 이러한 두 가지 방법의 모든 구현이 해당 GUID 인수를 확인 해야 합니다.<br /><br /> MPF에 따라 구현에 대 한이 GUID 여 가져온는 <xref:System.Type> 구현 하는 클래스의는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 설정 메커니즘입니다.|  
|ResourcePackage|REG\_SZ|GUID|선택적 요소.<br /><br /> 경로를 위성 DLL에 포함 된 지역화 된 문자열 구현 VSPackage에서 제공 하지 않는 경우.<br /><br /> MPF 리플렉션을 사용 하 여 올바른 리소스 VSPackage 가져올 않으므로 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 클래스는이 인수를 설정 하지 않습니다.|  
|AlternateParent|REG\_SZ|이 사용자 지정 설정 지점이 포함 된 도구 옵션 페이지 아래에 있는 폴더의 이름입니다.|선택적 요소.<br /><br /> 설정을 구현에서 지 원하는 경우에이 값을 설정 해야 **도구 옵션** 에 지 속성 메커니즘을 사용 하는 페이지는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 상태를 저장 하는 자동화 모델의 메커니즘은 대신 합니다.<br /><br /> AlternateParent 키의 값은 이러한 경우에는 `topic` 의 섹션은 `topic.sub-topic` 문자열 특정을 식별 하는 데 **도구옵션** 페이지입니다. 예를 들어는 **도구옵션** 페이지 `"TextEditor.Basic"` AlternateParent의 값은 `"TextEditor"`합니다.<br /><br /> 때 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 생성 사용자 지정 설정 점 범주 이름을와 같습니다.|