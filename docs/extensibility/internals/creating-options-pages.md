---
title: "옵션 페이지 만들기 | Microsoft Docs"
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
  - "관리 되는 패키지 프레임 워크 도구 옵션 페이지 만들기"
  - "도구 옵션 페이지 [Visual Studio SDK]를 사용 하 여 만드는 패키지 프레임 워크를 관리 하는"
ms.assetid: 1bf11fec-dece-4943-8053-6de1483c43eb
caps.latest.revision: 29
caps.handback.revision: 29
ms.author: "gregvanl"
manager: "ghogen"
---
# 옵션 페이지 만들기
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 관리 되는 패키지 프레임 워크 클래스에서 파생 된 <xref:Microsoft.VisualStudio.Shell.DialogPage> 확장의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 추가 하 여 IDE **옵션** 아래 페이지는 **도구** 메뉴.  
  
 구현 하는 개체는 주어진 **도구 옵션** 페이지에서 특정 Vspackage 연관 된는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 개체입니다.  
  
 환경에서 인스턴스화하는 특정 구현 하는 개체 때문에 **도구 옵션** 특정 페이지 IDE에 의해 표시 되 면 페이지:  
  
-   A **도구 옵션** VSPackage를 구현 하는 개체 아니라 자체의 개체에 페이지를 구현 해야 합니다.  
  
-   개체를 여러 개 구현할 수 없습니다 **도구 옵션** 페이지입니다.  
  
## 도구 옵션 페이지 공급자로 등록 하는 중  
 VSPackage 지원 사용자 구성을 통해 **도구 옵션** 페이지는이 제공 하는 개체를 나타냅니다 **도구 옵션** 의 인스턴스를 적용 하 여 페이지 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 적용할는 <xref:Microsoft.VisualStudio.Shell.Package> 구현 합니다.  
  
 인스턴스가 하나 있어야 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 에 대 한 모든 <xref:Microsoft.VisualStudio.Shell.DialogPage>\-파생 형식을 구현 하는 **도구 옵션** 페이지입니다.  
  
 각 인스턴스 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 구현 하는 형식을 사용 하 여는 **도구 옵션** 페이지, 범주 및 식별 하는 데 사용 되는 하위 범주를 포함 하는 문자열을 **도구 옵션** 페이지 및 리소스 정보로 제공 하는 형식을 등록 하는 **도구 옵션** 페이지.  
  
## 도구 옵션 페이지 상태 유지  
 경우에 **도구 옵션** 페이지 구현에 등록 된 자동화 지원을 사용 하도록 설정, 다른 모든 함께 페이지의 상태를 유지 하는 IDE **도구 옵션** 페이지입니다.  
  
 VSPackage를 사용 하 여 자체 지 속성을 관리할 수 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute>합니다. 하나만 또는 지 속성의 다른 메서드를 사용 해야 합니다.  
  
## DialogPage 클래스를 구현합니다.  
 VSPackage의 구현을 제공 하는 개체는 <xref:Microsoft.VisualStudio.Shell.DialogPage>\-파생된 형식을 다음과 같은 상속 된 기능을 이용할 수 있습니다.  
  
-   기본 사용자 인터페이스 창입니다.  
  
-   기본 지 속성 메커니즘을 사용할 수 있는 경우 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 클래스에 적용 됩니다 또는 경우에는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute.SupportsProfiles%2A> 속성이 `true` 에 대 한는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 클래스에 적용 되는 합니다.  
  
-   자동화를 지원 합니다.  
  
 구현 하는 개체에 대 한 최소 요구 사항을 **도구 옵션** 페이지를 사용 하 여 <xref:Microsoft.VisualStudio.Shell.DialogPage> 추가 공용 속성입니다.  
  
 클래스는 정상적으로 등록 하는 경우는 **도구 옵션** 페이지 공급자, 공용 속성에서 사용할 수 있는 다음는 **옵션** 의 섹션은 **도구** 속성 표 형태의 메뉴.  
  
 이러한 모든 기본 기능을 재정의할 수 있습니다. 예를 들어 더 정교한 사용자를 만들려면 인터페이스 필요의 기본 구현만 재정의 <xref:Microsoft.VisualStudio.Shell.DialogPage.Window%2A>합니다.  
  
## 예제  
 다음은 옵션 페이지의 간단한 "hello world" 구현 합니다. Visual Studio 패키지 템플릿을 사용 하 여 만든 기본 프로젝트에 다음 코드를 추가 **메뉴 명령** 옵션을 선택 된 옵션 페이지 기능을 보여 적절 하 게 됩니다.  
  
### 설명  
 다음 클래스에는 최소한의 "hello world" 옵션 페이지를 정의합니다. 사용자가 공용을 설정할 수 열리면 `HelloWorld` 속성 표의 속성입니다.  
  
### 코드  
 [!code-cs[UI_UserSettings_ToolsOptionPages#11](../../extensibility/internals/codesnippet/CSharp/creating-options-pages_1.cs)]
 [!code-vb[UI_UserSettings_ToolsOptionPages#11](../../extensibility/internals/codesnippet/VisualBasic/creating-options-pages_1.vb)]  
  
### 설명  
 패키지 클래스에 다음 특성을 적용 페이지 옵션은 사용할 수 있도록 패키지를 로드 하는 경우. 숫자는 범주 및 페이지에 대 한 임의의 리소스 Id 및 끝에 부울 값은 페이지 자동화를 지원 하는지 여부를 지정 합니다.  
  
### 코드  
 [!code-cs[UI_UserSettings_ToolsOptionPages#07](../../extensibility/internals/codesnippet/CSharp/creating-options-pages_2.cs)]
 [!code-vb[UI_UserSettings_ToolsOptionPages#07](../../extensibility/internals/codesnippet/VisualBasic/creating-options-pages_2.vb)]  
  
### 설명  
 다음 이벤트 처리기 옵션 페이지에서 설정 속성의 값에 따라 결과 표시 합니다. 사용 하 여는 <xref:Microsoft.VisualStudio.Shell.Package.GetDialogPage%2A> 메서드 결과를 페이지에 의해 노출 되는 속성에 액세스 하는 사용자 지정 옵션 페이지 형식으로 명시적으로 캐스팅 합니다.  
  
 패키지 템플릿으로 생성 된 프로젝트의 경우에서이 함수를 호출 하는 `MenuItemCallback` 기본 명령에 연결 하는 함수에 추가 **도구** 메뉴.  
  
### 코드  
 [!code-cs[UI_UserSettings_ToolsOptionPages#08](../../extensibility/internals/codesnippet/CSharp/creating-options-pages_3.cs)]
 [!code-vb[UI_UserSettings_ToolsOptionPages#08](../../extensibility/internals/codesnippet/VisualBasic/creating-options-pages_3.vb)]  
  
## 참고 항목  
 [확장 사용자 설정 및 옵션](../../extensibility/extending-user-settings-and-options.md)   
 [옵션 페이지에 대 한 자동화 지원](../../extensibility/internals/automation-support-for-options-pages.md)