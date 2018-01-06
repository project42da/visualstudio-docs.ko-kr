---
title: "옵션 페이지 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed package framework, creating Tools Options pages
- Tools Options pages [Visual Studio SDK], creating using managed package framework
ms.assetid: 1bf11fec-dece-4943-8053-6de1483c43eb
caps.latest.revision: "29"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ae8540a2f372abacd8eda6e63cd868edbb050392
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-options-pages"></a>옵션 페이지 만들기
에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 관리 패키지 프레임 워크 클래스에서 파생 된 <xref:Microsoft.VisualStudio.Shell.DialogPage> 확장는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 추가 하 여 IDE **옵션** 아래 페이지는 **도구** 메뉴.  
  
 구현 하는 개체는 주어진 **도구 옵션** 하 여 특정 Vspackage와 연결 된 페이지는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 개체입니다.  
  
 환경에서 인스턴스화하는 특정 구현 하는 개체 이므로 **도구 옵션** 특정 페이지에서는 IDE에서 표시 되 면 페이지:  
  
-   A **도구 옵션** VSPackage를 구현 하는 개체 아니라 자체의 개체에 페이지를 구현 해야 합니다.  
  
-   개체는 여러 구현할 수 없습니다 **도구 옵션** 페이지입니다.  
  
## <a name="registering-as-a-tools-options-page-provider"></a>도구 옵션 페이지 공급자로 등록 하는 중  
 VSPackage 지원 사용자 구성을 통해 **도구 옵션** 페이지 이러한를 제공 하는 개체를 나타냅니다. **도구 옵션** 의 인스턴스를 적용 하 여 페이지 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 는 적용할<xref:Microsoft.VisualStudio.Shell.Package>구현 합니다.  
  
 인스턴스가 하나 있어야 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 에 대 한 모든 <xref:Microsoft.VisualStudio.Shell.DialogPage>-파생 형식이 구현 하는 **도구 옵션** 페이지.  
  
 각 인스턴스에 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 구현 하는 형식을 사용 하 여는 **도구 옵션** 페이지, 범주 및 식별 하는 데 사용 되는 하위 범주를 포함 하는 문자열을 **도구 옵션** 페이지 및 리소스 제공 된 형식을 등록 하는 정보는 **도구 옵션** 페이지.  
  
## <a name="persisting-tools-options-page-state"></a>도구 옵션 페이지 상태 유지  
 경우는 **도구 옵션** 자동화 지원이 설정 된 페이지 구현이 등록 되어, IDE 함께 다른 모든 페이지의 상태를 유지 해야 **도구 옵션** 페이지입니다.  
  
 VSPackage를 사용 하 여 고유한 지 속성을 관리할 수 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute>합니다. 하나만 또는 지 속성의 다른 방법을 사용 해야 합니다.  
  
## <a name="implementing-dialogpage-class"></a>구현 하는 DialogPage 클래스  
 VSPackage의 구현을 제공 하는 개체는 <xref:Microsoft.VisualStudio.Shell.DialogPage>-파생 된 형식 상속 된 다음과 같은 기능을 이용할 수 있습니다.  
  
-   기본 사용자 인터페이스 창입니다.  
  
-   기본 지 속성 메커니즘이 사용 가능한 경우 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 는 클래스에 적용 되 또는 경우에는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute.SupportsProfiles%2A> 속성이로 설정 되어 `true` 에 대 한는 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> 클래스에 적용 되는 합니다.  
  
-   자동화 지원 합니다.  
  
 구현 하는 개체에 대 한 최소 요구 사항을 **도구 옵션** 페이지를 사용 하 여 <xref:Microsoft.VisualStudio.Shell.DialogPage> 공용 속성에 추가 합니다.  
  
 클래스는 제대로으로 등록 하는 경우는 **도구 옵션** 다음 공용 속성에서 사용할 수 있는 공급자 페이지는 **옵션** 섹션은 **도구** 의 형태로 메뉴는 속성 표입니다.  
  
 이러한 모든 기본 기능을 재정의할 수 있습니다. 예를 들어 생성 하려면 보다 정교한 사용자 인터페이스 필요의 기본 구현만 재정의 <xref:Microsoft.VisualStudio.Shell.DialogPage.Window%2A>합니다.  
  
## <a name="example"></a>예  
 다음은 옵션 페이지의 간단한 "hello world" 구현 합니다. Visual Studio 패키지 템플릿을 사용 하 여 만든 기본 프로젝트에 다음 코드를 추가 **메뉴 명령을** 옵션을 선택 옵션 페이지 기능을 시연 적절 하 게 됩니다.  
  
### <a name="description"></a>설명  
 다음 클래스에는 최소한의 "hello world" 옵션 페이지를 정의합니다. 사용자가 공용을 설정할 수를 열 때 `HelloWorld` 속성 표에 속성입니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[UI_UserSettings_ToolsOptionPages#11](../../extensibility/internals/codesnippet/CSharp/creating-options-pages_1.cs)]
 [!code-vb[UI_UserSettings_ToolsOptionPages#11](../../extensibility/internals/codesnippet/VisualBasic/creating-options-pages_1.vb)]  
  
### <a name="description"></a>설명  
 패키지 클래스에 다음 특성을 적용 페이지 옵션은 사용할 수 있도록 패키지를 로드 하는 경우. 숫자는 범주 및 페이지에 대 한 임의의 리소스 Id 및 끝에 부울 값은 페이지 자동화를 지원 하는지 여부를 지정 합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[UI_UserSettings_ToolsOptionPages#07](../../extensibility/internals/codesnippet/CSharp/creating-options-pages_2.cs)]
 [!code-vb[UI_UserSettings_ToolsOptionPages#07](../../extensibility/internals/codesnippet/VisualBasic/creating-options-pages_2.vb)]  
  
### <a name="description"></a>설명  
 다음 이벤트 처리기 옵션 페이지에서 설정 속성의 값에 따라 결과 표시 합니다. 사용 하 여는 <xref:Microsoft.VisualStudio.Shell.Package.GetDialogPage%2A> 결과와 메서드를 명시적으로 페이지에 의해 노출 되는 속성에 액세스 하려면 사용자 지정 옵션 페이지 형식으로 캐스팅 합니다.  
  
 패키지 템플릿으로 생성 하는 프로젝트의 경우에서이 함수 호출의 `MenuItemCallback` 기본 명령에 연결 하는 함수에 추가 **도구** 메뉴.  
  
### <a name="code"></a>코드  
 [!code-csharp[UI_UserSettings_ToolsOptionPages#08](../../extensibility/internals/codesnippet/CSharp/creating-options-pages_3.cs)]
 [!code-vb[UI_UserSettings_ToolsOptionPages#08](../../extensibility/internals/codesnippet/VisualBasic/creating-options-pages_3.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [확장 사용자 설정 및 옵션](../../extensibility/extending-user-settings-and-options.md)   
 [옵션 페이지의 자동화 지원](../../extensibility/internals/automation-support-for-options-pages.md)