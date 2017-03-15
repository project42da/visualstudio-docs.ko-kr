---
title: "사용자 지정 옵션 페이지 등록 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "등록, 사용자 지정 도구 옵션 페이지"
  - "도구 옵션 페이지[Visual Studio SDK], 등록"
ms.assetid: 0ac6377d-a679-4f7d-be80-451c829b56f2
caps.latest.revision: 28
caps.handback.revision: 28
manager: "douge"
---
# 사용자 지정 옵션 페이지 등록
에  **도구 옵션** 사용자와 지원 자동화에 사용할 수 있도록 페이지에서 함께 제대로 등록 되어 있어야 해당 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\).  
  
 **도구 옵션** 패키지를 관리 되는 프레임 워크를 기반으로 페이지의 인스턴스를 적용 하 여 등록 됩니다 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 있는 VSPackage 페이지를 제공 합니다.  설정 하 여 자동화 지원을 나타냅니다의 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute.SupportsAutomation%2A> 속성을 `true`.  
  
## 도구 옵션 페이지 등록  
 사용자 지정 통합  **도구 옵션** 페이지를 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 다음 위치에서 레지스트리 항목을 만들어야: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\*\<Version\>*\\ToolsOptionsPages, 어디  *\<Version\>* 의 버전이 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 예를 들어 8.0.  
  
 항목에 범주는 기본 키가 \(`<PageCategory>`\)의  **도구 옵션** 페이지 및 페이지의 하위 범주 이름을 포함 하는 하위 키 \(`<PageSubCategory>`\).  
  
 예를 들어,는  **도구 옵션** 는 문자열로 식별 페이지  **TextEditor.Basic**, 레지스트리 키가 `<PageCategory>`의 하위 키와 textEditor \= `<PageSubCategory>`\= 기본.  
  
 레지스트리 항목은 다음과 같습니다.  
  
 HKLM\\Software\\Microsoft\\VisualStudio\\*\<Version\>*\\ToolsOptionsPages\\  
  
 `<PageCategory>` \= '\#12345'  
  
 패키지 ' {0} XXXXXX XXXX XXXX XXXX XXXXXXXXX}' \=  
  
 ResourcePackage \= ' {YYYYYY YYYY YYYY YYYY YYYYYYYYY}'  
  
 HKLM\\Software\\Microsoft\\VisualStudio\\*\<Version\>*\\ToolsOptionsPages\\`<PageCategory>`  
  
 `<PageSubCategory>>` \= '\#67890'  
  
 페이지 ' {ZZZZZZ ZZZZ ZZZZ ZZZZ ZZZZZZZZZ}' \=  
  
 패키지 ' {0} AAAAAA AAAA AAAA AAAA AAAAAAAAA}' \=  
  
 ResourcePackage \= ' {0} BBBBBB BBBB BBBB BBBB BBBBBBBBB}'  
  
 NoShowAllView \= 0\/1  
  
 다음 표에서 값에서 HKLM\\Software\\Microsoft\\VisualStudio\\*\<Version\>*\\ToolsOptionsPages\\`<PageCategory>`.  
  
|Name|형식|데이터|설명|  
|----------|--------|---------|--------|  
|\(기본값\)|REG\_SZ|정식 범주 이름을 사용자 지정  **도구 옵션** 페이지|키의 이름, `<PageCategory>`, 정식 지역화 되지 않은 범주 이름입니다 있는  **도구 옵션** 페이지입니다. **Note:**  자동화를 지 원하는 경우, 정식 지역화 되지 않은 범주와 하위 범주 이름을 얻으려면 사용 됩니다 있는  **도구 옵션** 페이지의 <xref:EnvDTE.Properties> 컬렉션입니다.  자세한 내용은 [옵션 페이지 사용](../misc/using-options-pages.md)를 참조하십시오. <br /><br /> 패키지를 관리 되는 프레임 워크를 기반으로 구현을 위한 `<PageCategory`\> 가져온는 `categoryName` 인수는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 생성자입니다.<br /><br /> 키 비워둘 수 또는 참조 ID는 구현 위성 DLL의에서 지역화 된 문자열을 포함할 수 있습니다.<br /><br /> 이 값이 가져온 패키지를 관리 되는 프레임 워크를 기반으로 구현 되는 `categoryResourceID` 인수에는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 생성자입니다.|  
|패키지|REG\_SZ|GUID|사용자 지정을 구현 하는 Vspackage의 GUID  **도구 옵션** 페이지입니다.<br /><br /> 구현을 기반으로 관리 되는 패키지 프레임 워크 사용에 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 리플렉션을 사용 하 여이 값을 얻을 수 있습니다.|  
|ResourcePackage|REG\_SZ|GUID|선택적 요소.<br /><br /> 포함 하는 위성 DLL 구현 Vspackage를 제공 하지 않을 경우 문자열 지역화 된.<br /><br /> 패키지를 관리 되는 프레임 워크에서 리플렉션을 사용 하 여 올바른 리소스 패키지를 얻을 수 있도록 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 이 인수를 설정 하지 않습니다.|  
  
 다음 표에서 값에서 HKLM\\Software\\Microsoft\\VisualStudio\\*\<Version\>*\\ToolsOptionsPages\\`<PageCategory>`\\`<PageSubCategory>`.  
  
|Name|형식|데이터|설명|  
|----------|--------|---------|--------|  
|\(기본값\)|REG\_SZ|사용자 지정의 정식 하위 범주 이름  **도구 옵션** 페이지|키의 이름, `<PageSubCategory`\>, 정식 지역화 되지 않은 이름입니다 있는  **도구 옵션** 페이지 하위 범주. **Note:**  자동화를 지 원하는 경우, 정식 지역화 되지 않은 범주와 하위 범주 이름을 얻으려면 사용 됩니다 있는  **도구 옵션** 페이지의 <xref:EnvDTE.Properties> 컬렉션입니다.  자세한 내용은 [옵션 페이지 사용](../misc/using-options-pages.md)를 참조하십시오. <br /><br /> 패키지를 관리 되는 프레임 워크를 기반으로 구현을 위한 `<PageSubegory`\> 가져온는 `pageName` 인수는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 생성자입니다.<br /><br /> 키를 비어 있을 수 있습니다 또는 지역화 된 위성 DLL의 구현에서에서 문자열 참조 ID를 포함할 수 있습니다.<br /><br /> 이 값이 가져온 패키지를 관리 되는 프레임 워크를 기반으로 구현 되는 `pageNameResourceID` 인수에는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 생성자입니다.|  
|페이징|REG\_SZ|GUID|사용자 지정을 구현 하는 개체의 GUID를  **도구 옵션** 페이지입니다.<br /><br /> 구현을 기반으로 관리 되는 패키지 프레임 워크 사용에 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 생성자의 사용 `pageType` 인수가 들어 있는 VSPackage <xref:System.Type> 및이 값을 얻기 위해 반사.|  
|패키지|REG\_SZ|GUID|구현을 기반으로 관리 되는 패키지 프레임 워크 사용에 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 리플렉션을 사용 하 여이 값을 얻을 수 있습니다.|  
|ResourcePackage|REG\_SZ|GUID|선택적 요소.<br /><br /> 포함 하는 위성 DLL 구현 Vspackage를 제공 하지 않을 경우 문자열 지역화 된.<br /><br /> 패키지를 관리 되는 프레임 워크에서 리플렉션을 사용 하 여 올바른 리소스 DLL을 얻을 수 있도록 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 이 인수를 설정 하지 않습니다.|  
|NoShowAllView|REG\_DWORD|0 또는 1|선택적 요소.<br /><br /> 나타냅니다 여부는 지정 된  **도구 옵션** 페이지의 복잡 한 \(기본\) 보기에서 표시 해야  **도구 옵션** 페이지입니다.  어떤 특별 한 프로그래밍 환경, Visual Basic, 등을 지 원하는  **도구 옵션** 사용자 옵션 전문된 간단한 뷰를 제공 하는 집계 일반 설정 페이지입니다.<br /><br /> REG\_DWORD 항목을 0이 아닌 경우는  **도구 옵션** 페이지 복잡 한 보기에 나타나지 않습니다.<br /><br /> 자세한 내용은 [옵션 대화 상자](../ide/reference/options-dialog-box-visual-studio.md)를 참조하십시오.<br /><br /> 구현에서 패키지를 관리 되는 프레임 워크를 기반으로 설정할 수 있습니다이 값을 설정 하 여는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute.NoShowAllView%2A> 속성에 `true` 에 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 생성자입니다.|  
  
 VSPackage 또는 단일 interop 어셈블리를 기준으로 개체를 두 개 이상 구현할 수 있습니다  **도구 옵션** 페이지입니다.  새 항목에 HKLM\\Software\\Microsoft\\VisualStudio\\ 각 구현 되어야*\<Version\>*\\ToolsOptionsPages.  
  
 제공 하는 개체와 관리 되는 패키지 프레임 워크 인스턴스화하는  **도구 옵션** 페이지에서 각 페이지가 있어야 있는 VSPackage 구현에서 독립적인 자체 구현을 개체 <xref:Microsoft.VisualStudio.Shell.Package>.  
  
## 자동화 지원  
 자동화 지원을 구현에 사용 되는 경우는  **도구 옵션** 페이지 해야 등록 자체를 자동화 공급자입니다.  재산 관리의 자동화를 사용 하는 지 속성 메커니즘을 사용 하 여 저장 하는  **도구 옵션** 상태 페이지에서 스스로 등록 해야는 `AutomationProperty` 공급자입니다.  
  
### 있는 VSPackage \(Interop 어셈블리를 기준으로 도구 옵션 페이지에 대 한\) 자동화 공급자로 등록  
 **도구 옵션** 는 interop 어셈블리를 기준으로 페이지는 VSPackage 구현 클래스의 일부로 구현 됩니다.  
  
 이런 경우는  **도구 옵션** 페이지인 Vspackage는 자동화 공급자로 등록 해야 하는 interop assembly–based 자동화를 지원 합니다.  
  
> [!NOTE]
>  자동화 지원 패키지를 관리 되는 프레임 워크의 개체는 Vspackage의 구현과 독립적으로 제공 됩니다.  자동화 개체를 지 원하는 경우이 통해 등록 된는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute.SupportsAutomation%2A> 속성에는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 생성자.  
  
 자동화 공급자는 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\ 형식으로 그대로 있는 VSPackage 등록에 대 한 항목*\<Version\>*\\Packages\\*\<PackageGUID\>*\\Automation, 어디  *\<Version\>* 의 버전이 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] \(8.0\) 및  *\<PackageGUID\>* VSPackage 자동화 개체 구현에서의 GUID입니다.  
  
> [!NOTE]
>  루트 경로를 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\*\<Version\>* Visual Studio 셸 초기화 될 때 대체 루트를 재정의할 수 있습니다.  자세한 내용은 [명령줄 스위치](../extensibility/command-line-switches-visual-studio-sdk.md)를 참조하십시오.  
  
 레지스트리 항목의 구조는 다음과 같습니다.  
  
 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\*\<Version\>*\\Packages\\*\<PackageGUID\>*\\Automation  
  
 `<AutomationObjectName>`  
  
|Name|형식|데이터|설명|  
|----------|--------|---------|--------|  
|자동화|REG\_SZ|정의 되지 않음|정의되어 있지 않습니다.<br /><br /> 이 키가 있는지를 나타내는 Vspackage를 참조 하도록  *\<PackageGUID\>* 자동화를 지원 합니다.<br /><br /> 문서를 저장 하는 필드를 사용할 수 있습니다.<br /><br /> <xref:Microsoft.VisualStudio.Shell.ProvideAutomationObjectAttribute>이 키 패키지를 관리 되는 프레임 워크를 기반으로 하는 응용 프로그램에 대해 자동으로 만들어집니다.|  
|`<AutomationObjectName>`|REG\_SZ|제공 되는 자동화 개체의 정식 이름|키 이름 에서만 관련입니다.  이 자동화 작업에 사용 됩니다.<br /><br /> 문서를 저장 하는 필드를 사용할 수 있습니다.<br /><br /> 이 키의 이름을 결정 됩니다 패키지를 관리 되는 프레임 워크를 기반으로 구현에는 `name` 인수에는 <xref:Microsoft.VisualStudio.Shell.ProvideAutomationObjectAttribute> 생성자.<br /><br /> 경우는 <xref:Microsoft.VisualStudio.Shell.ProvideAutomationObjectAttribute> 생성자가 제공 하는 유효한 문자열의 <xref:Microsoft.VisualStudio.Shell.ProvideAutomationObjectAttribute.Description%2A> 속성이 값이 여기 삽입 합니다.|  
  
### 자동화 지원 도구 옵션 페이지 등록  
 Interop와 관리 패키지 Framework– assembly–based 구현은  **도구 옵션** 해야 페이지 등록 자동화 액세스를 허용 하는  **도구 옵션** 페이지.  여기는 자동화 속성 지 속성 메커니즘 및 페이지를 통해 액세스 권한을 <xref:EnvDTE>.  이 등록을 자동화 서비스 공급자로 VSPackage 자체 독립적입니다.  
  
 와 마찬가지로  **도구 옵션** 페이지 등록 언급 위의 항목이 있는 범주와 기본 키 \(`<PageCategory>`\)의  **도구 옵션** 페이지 및 페이지의 하위 범주 이름을 포함 하는 하위 키 \(`<PageSubcategory>`\).  
  
 패키지를 관리 되는 프레임 워크를 사용 하는 경우 사용 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 제공 하는 클래스를 등록 하는  **도구 옵션** 설정 하 고 페이지의 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute.SupportsAutomation%2A> 속성을 `true` 페이지에서 자동화를 지원함을 나타냅니다.  
  
 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\ 레지스트리 항목을 찾을 수*\<Version\>*\\AutomationProperties, 어디  *\<Version\>* 의 버전이 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 예를 들어 8.0입니다.  
  
> [!NOTE]
>  루트 경로를 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\*\<Version\>* Visual Studio 셸을 자세한 내용은 초기화 될 때 대체 루트를 재정의할 수 있습니다 [명령줄 스위치](../extensibility/command-line-switches-visual-studio-sdk.md).  
  
 레지스트리 항목은 다음과 같습니다.  
  
 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\*\<Version\> \\*AutomationProperties  
  
 `<PageCategory>` \= ‘\#456’  
  
 ResourcePackage \= ' {0} XXXXXX XXXX XXXX XXXX XXXXXXXXX}'  
  
 `<PageSubCategory>` \= ‘\#789’  
  
 패키지 ' {YYYYYY YYYY YYYY YYYY YYYYYYYYY}' \=  
  
 Name \= '`<PageCategory>` .`<PageSubcategory>`'  
  
 'ProfileSave' \= 1\/0  
  
 다음 표에서 값에서 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\*\<Version\>*\\AutomationProperties\\`<PageCategory>`.  
  
|Name|형식|데이터|설명|  
|----------|--------|---------|--------|  
|\(기본값\)|REG\_SZ|정식 범주 이름을 사용자 지정  **도구 옵션** 페이지|키의 이름, `<PageCategory`\>, 정식 지역화 되지 않은 이름입니다 있는  **도구 옵션** 페이지 범주입니다. **Note:**  자동화를 지 원하는 경우, 정식 지역화 되지 않은 범주와 하위 범주 이름을 얻으려면 사용 됩니다 있는  **도구 옵션** 페이지의 <xref:EnvDTE.Properties> 컬렉션입니다.  자세한 내용은 [옵션 페이지 사용](../misc/using-options-pages.md)를 참조하십시오. <br /><br /> 키 비워둘 수 또는 참조 ID는 구현 위성 DLL의에서 지역화 된 문자열을 포함할 수 있습니다.<br /><br /> 패키지를 관리 되는 프레임 워크를 기반으로 구현을 위한 `<PageCategory`\> 가져온는 `categoryName` 인수는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 생성자입니다.|  
|ResourcePackage|REG\_SZ|GUID|선택적 요소.<br /><br /> 포함 하는 위성 DLL 구현 Vspackage를 제공 하지 않을 경우 문자열 지역화 된.<br /><br /> 패키지를 관리 되는 프레임 워크에서 리플렉션을 사용 하 여 올바른 리소스 Vspackage를 얻을 수 있도록 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 이 인수를 설정 하지 않습니다.|  
  
 다음 표에서 값에서 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\*\<Version\>*\\AutomationProperties\\`<PageCategory>\<PageSubCategory>`.  
  
|Name|형식|데이터|설명|  
|----------|--------|---------|--------|  
|\(기본값\)|REG\_SZ|사용자 지정 하위 범주 이름  **도구 옵션** 페이지|키의 이름, `<PageSubCategory`\>, 정식 지역화 되지 않은 이름입니다 있는  **도구 옵션** 페이지 하위 범주. **Note:**  자동화를 지 원하는 경우, 정식 지역화 되지 않은 범주와 하위 범주 이름을 얻으려면 사용 됩니다 있는  **도구 옵션** 페이지의 <xref:EnvDTE.Properties> 컬렉션입니다.  자세한 내용은 [옵션 페이지 사용](../misc/using-options-pages.md)를 참조하십시오. <br /><br /> 키 비워둘 수 또는 참조 ID는 구현 위성 DLL의에서 지역화 된 문자열을 포함할 수 있습니다.<br /><br /> 패키지를 관리 되는 프레임 워크를 기반으로 하는 구현을 위한 `<PageSubCategory>` 에서 가져온는 `pageName` 인수에는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 생성자입니다.|  
|패키지|REG\_SZ|GUID|사용자 지정을 구현 하는 Vspackage의 GUID  **도구 옵션** 페이지입니다.<br /><br /> 구현을 기반으로 관리 되는 패키지 프레임 워크 사용에 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 리플렉션을 사용 하 여이 값을 얻을 수 있습니다.|  
|Name|REG\_SZ|이름에는  **도구 옵션** 컬렉션 속성 페이지|`<PageCategory>.<PageSubCategory>` 를 참조 하는 데 사용 되는 문자열은  **도구 옵션** 페이지.  자세한 내용은 [옵션 페이지 사용](../misc/using-options-pages.md)를 참조하십시오.<br /><br /> 구현에서 패키지를 관리 되는 프레임 워크를 기반으로 이름 인수를 가져옵니다는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 생성자와 폼의 `categoryName.pageName`.|  
|ProfileSave|DWORD|1\/0|선택적 요소.<br /><br /> 이 값을 나타냅니다 여부는  **도구 옵션** 페이지 설정으로 저장 됩니다는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설정 메커니즘을 클릭할 때의  **가져오기\/내보내기 설정** 에  **도구** 메뉴.<br /><br /> 해당 키가 있고 그 값 1이 경우는  **도구 옵션** 페이지 설정을 지원 요청입니다.<br /><br /> 패키지를 관리 되는 프레임 워크를 기반으로 구현 하는 경우이 값을 설정의 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 생성자와 함께 제공 되는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute.SupportsProfiles%2A> 속성을 설정 `true`.|  
  
## 참고 항목  
 [Creating Registrar Scripts](/visual-cpp/atl/creating-registrar-scripts)   
 [옵션 페이지 사용](../misc/using-options-pages.md)   
 [Interop 어셈블리를 사용하여 옵션 페이지 만들기](../misc/creating-options-pages-by-using-interop-assemblies.md)   
 [How to: Create Custom Options Pages](../Topic/How%20to:%20Create%20Custom%20Options%20Pages.md)   
 [옵션 페이지](../misc/options-pages.md)   
 [옵션 페이지에 대 한 자동화 지원](../extensibility/internals/automation-support-for-options-pages.md)