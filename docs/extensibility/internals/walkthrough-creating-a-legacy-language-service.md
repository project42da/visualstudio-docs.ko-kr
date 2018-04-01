---
title: '연습: 레거시 언어 서비스 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- language services [managed package framework], creating
ms.assetid: 6a5dd2c2-261b-4efd-a3f4-8fb90b73dc82
caps.latest.revision: 19
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 660d33dd2d5c46d8020172c1fcf74bfb64b43360
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-legacy-language-service"></a>연습: 레거시 언어 서비스 만들기
관리 되는 패키지 프레임 워크 (MPF) 언어 클래스를 사용 하 여에서 언어 서비스를 구현 하 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 은 간단 합니다. 언어 서비스, 언어 서비스 자체 및 해당 하는 언어에 대 한 파서를 호스팅하는 VSPackage 필요 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 참조 [Visual Studio SDK](../../extensibility/visual-studio-sdk.md)합니다.  
  
## <a name="locations-for-the-visual-studio-package-project-template"></a>Visual Studio 패키지 프로젝트 템플릿의 위치  
 Visual Studio 패키지 프로젝트 템플릿은 세 가지 다른 서식 파일 위치에서 찾을 수 있습니다는 **새 프로젝트** 대화 상자:  
  
1.  Visual Basic 확장성에 위치한 템플릿 프로젝트의 기본 언어는 Visual Basic입니다.  
  
2.  C# 확장성에 위치한 템플릿 프로젝트의 기본 언어는 C#입니다.  
  
3.  다른 프로젝트 형식 확장성에 위치한 템플릿 프로젝트의 기본 언어는 C++입니다.  
  
### <a name="create-a-vspackage"></a>VSPackage를 만듭니다  
  
1.  Visual Studio 패키지 프로젝트 템플릿을 사용 하 여 새 VSPackage를 만듭니다.  
  
     기존 VSPackage에는 언어 서비스를 추가 하는 경우 다음 단계를 건너뛰고 "언어 서비스 클래스 만들기" 절차로 바로 이동 합니다.  
  
2.  프로젝트의 이름에 대 한 MyLanguagePackage를 입력 하 고 클릭 **확인**합니다.  
  
     원하는 모든 이름을 사용할 수 있습니다. 여기에서 자세히 설명 하는 이러한 프로시저를 이름으로 MyLanguagePackage를 가정 합니다.  
  
3.  선택 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 언어 및 새 키 파일을 생성 하는 옵션입니다. **다음**을 클릭합니다.  
  
4.  적절 한 회사와 패키지 정보를 입력 합니다. **다음**을 클릭합니다.  
  
5.  선택 **메뉴 명령을**합니다. **다음**을 클릭합니다.  
  
     코드 조각을 지원 하지 않을 경우 방금 마침을 클릭 및 다음 단계를 무시할 수 있습니다.  
  
6.  입력 **코드 조각을 삽입** 로 **명령 이름** 및 `cmdidInsertSnippet` 에 대 한는 **명령 ID**합니다. **마침**을 클릭합니다.  
  
     **명령 이름** 및 **명령 ID** 원하는 대로 지정할 수 있으며, 다음은 단지 예입니다.  
  
### <a name="create-the-language-service-class"></a>언어 서비스 클래스 만들기  
  
1.  **솔루션 탐색기**MyLanguagePackage 프로젝트를 마우스 오른쪽 단추로 선택 **추가**, **참조**를 선택한 후는 **새 참조 추가** 단추입니다.  
  
2.  에 **참조 추가** 대화 상자에서 **Microsoft.VisualStudio.Package.LanguageService** 에 **.NET** 탭을 클릭 **확인**합니다.  
  
     이 언어 패키지 프로젝트에 대 한 한 번만 수행 해야 합니다.  
  
3.  **솔루션 탐색기**VSPackage 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가**, **클래스**합니다.  
  
4.  확인 **클래스** 템플릿 목록에서 선택 합니다.  
  
5.  입력 **MyLanguageService.cs** 클릭 및 클래스 파일의 이름에 대 한 **추가**합니다.  
  
     원하는 모든 이름을 사용할 수 있습니다. 여기에서 자세히 설명 하는이 절차에서는 `MyLanguageService` 이름으로 합니다.  
  
6.  MyLanguageService.cs 파일에 다음 추가 `using` 문.  
  
     [!code-csharp[CreatingALanguageService(ManagedPackageFramework)#1](../../extensibility/internals/codesnippet/CSharp/walkthrough-creating-a-legacy-language-service_1.cs)]
     [!code-vb[CreatingALanguageService(ManagedPackageFramework)#1](../../extensibility/internals/codesnippet/VisualBasic/walkthrough-creating-a-legacy-language-service_1.vb)]  
  
7.  수정 된 `MyLanguageService` 클래스에서 파생 하는 <xref:Microsoft.VisualStudio.Package.LanguageService> 클래스:  
  
     [!code-csharp[CreatingALanguageService(ManagedPackageFramework)#2](../../extensibility/internals/codesnippet/CSharp/walkthrough-creating-a-legacy-language-service_2.cs)]
     [!code-vb[CreatingALanguageService(ManagedPackageFramework)#2](../../extensibility/internals/codesnippet/VisualBasic/walkthrough-creating-a-legacy-language-service_2.vb)]  
  
8.  "LanguageService" 및에서 커서의 위치는 **편집**, **IntelliSense** 메뉴 선택 **추상 클래스 구현**합니다. 이 언어 서비스 클래스를 구현 하 고 최소 필요한 메서드를 추가 합니다.  
  
9. 에 설명 된 대로 추상 메서드를 구현 [레거시 언어 서비스 구현](../../extensibility/internals/implementing-a-legacy-language-service2.md)합니다.  
  
### <a name="register-the-language-service"></a>언어 서비스를 등록 합니다.  
  
1.  MyLanguagePackagePackage.cs 파일을 열고 다음 추가 `using` 문:  
  
     [!code-vb[CreatingALanguageService(ManagedPackageFramework)#3](../../extensibility/internals/codesnippet/VisualBasic/walkthrough-creating-a-legacy-language-service_3.vb)]
     [!code-csharp[CreatingALanguageService(ManagedPackageFramework)#3](../../extensibility/internals/codesnippet/CSharp/walkthrough-creating-a-legacy-language-service_3.cs)]  
  
2.  에 설명 된 대로 언어 서비스 클래스를 등록 [레거시 언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service1.md)합니다. 이 ProvideXX 특성 및 "언어 서비스 Proffering" 섹션을 포함 합니다. 이 항목 TestLanguageService를 사용 하는 경우 MyLanguageService를 사용 합니다.  
  
### <a name="the-parser-and-scanner"></a>파서 및 스캐너  
  
1.  파서 및 해당 언어에 대해 스캐너에 설명 된 대로 구현 [레거시 언어 서비스 파서 및 스캐너](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)합니다.  
  
     파서 및 스캐너를 구현 하는 방법은 전적으로 개발자가 되 고이 항목의 범위를 벗어납니다.  
  
## <a name="language-service-features"></a>언어 서비스 기능  
 언어 서비스의 각 기능을 구현 하려면 있습니다 일반적으로 적절 한 MPF 언어 서비스 클래스에서 클래스를 파생, 필요에 따라 모든 추상 메서드를 구현 하 고 적절 한 메서드를 재정의 합니다. 지원 하려면 어떤 클래스를 만들고에서 파생 되는 기능에 따라 달라 집니다. 이러한 기능에 대 한 자세한 설명은 [레거시 언어 서비스 기능](../../extensibility/internals/legacy-language-service-features1.md)합니다. 다음 절차는 일반적인 방법을 MPF 클래스에서 클래스를 파생 하는 것을 것입니다.  
  
#### <a name="deriving-from-an-mpf-class"></a>MPF 클래스에서 파생 된  
  
1.  **솔루션 탐색기**VSPackage 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가**, **클래스**합니다.  
  
2.  확인 **클래스** 템플릿 목록에서 선택 합니다.  
  
     클래스 파일에 대 한 적절 한 이름을 입력 하 고 클릭 **추가**합니다.  
  
3.  새 클래스 파일에 다음 추가 `using` 문.  
  
     [!code-csharp[CreatingALanguageService(ManagedPackageFramework)#4](../../extensibility/internals/codesnippet/CSharp/walkthrough-creating-a-legacy-language-service_4.cs)]
     [!code-vb[CreatingALanguageService(ManagedPackageFramework)#4](../../extensibility/internals/codesnippet/VisualBasic/walkthrough-creating-a-legacy-language-service_4.vb)]  
  
4.  원하는 MPF 클래스에서 파생 되도록 클래스를 수정 합니다.  
  
5.  적어도 기본 클래스의 생성자와 동일한 매개 변수를 사용 하는 클래스 생성자를 추가 하 고 기본 클래스 생성자에 로그온 하는 생성자 매개 변수를 전달 합니다.  
  
     예를 들어에서 파생 된 클래스에 대 한 생성자는 <xref:Microsoft.VisualStudio.Package.Source> 클래스는 다음과 같을 수 있습니다.  
  
     [!code-csharp[CreatingALanguageService(ManagedPackageFramework)#5](../../extensibility/internals/codesnippet/CSharp/walkthrough-creating-a-legacy-language-service_5.cs)]
     [!code-vb[CreatingALanguageService(ManagedPackageFramework)#5](../../extensibility/internals/codesnippet/VisualBasic/walkthrough-creating-a-legacy-language-service_5.vb)]  
  
6.  **편집**, **IntelliSense** 메뉴 선택 **추상 클래스 구현** 기본 클래스에 모든 추상 메서드를 구현 해야 하는 경우.  
  
7.  그렇지 않은 경우 클래스의 내부 캐럿 위치를 지정 하 고 메서드를 재정의할 수를 입력 합니다.  
  
     예를 들어 입력 `public override` 해당 클래스에서 재정의 될 수 있는 모든 메서드의 목록을 볼 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [레거시 언어 서비스를 구현합니다.](../../extensibility/internals/implementing-a-legacy-language-service1.md)