---
title: "연습: 자동화를 사용하여 관리되는 VSPackage 확장 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "관리되는 VSPackage, 자동화를 사용하여 확장"
  - "자동화[Visual Studio SDK], 연습"
  - "자동화[Visual Studio SDK], 관리되는 VSPackage"
ms.assetid: 7fd2000b-8ec3-4d83-b169-d38008fb57ee
caps.latest.revision: 35
caps.handback.revision: 35
manager: "douge"
---
# 연습: 자동화를 사용하여 관리되는 VSPackage 확장
이 연습에서는 자동화를 사용하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE\(통합 개발 환경\)를 조작하는 관리되는 VSPackage를 만드는 방법을 보여 줍니다. 샘플 관리되는 VSPackage를 만든 다음 결과 VSPackage에서 자동화 메서드를 사용하여 **출력** 창에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 속성을 표시합니다.  
  
## 사전 요구 사항  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)을 참조하세요.  
  
## Visual Studio 패키지 프로젝트 템플릿의 위치  
 Visual Studio 패키지 프로젝트 템플릿은 **새 프로젝트** 대화 상자의 세 가지 서로 다른 위치에 있습니다.  
  
1.  Visual Basic 확장성에 위치한 템플릿 프로젝트의 기본 언어는 Visual Basic입니다.  
  
2.  C\# 확장성에 위치한 템플릿 프로젝트의 기본 언어는 C\#입니다.  
  
3.  다른 프로젝트 형식 확장성에 위치한 템플릿 프로젝트의 기본 언어는 C\+\+입니다.  
  
### 관리되는 VSPackage를 만들려면  
  
1.  `Auto`라는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 패키지 프로젝트를 만듭니다.  
  
     관리되는 VSPackage를 만드는 방법에 대한 자세한 내용은 [연습: Visual Studio 패키지 템플릿을 사용하여 메뉴 명령 만들기](../Topic/Walkthrough:%20Creating%20a%20Menu%20Command%20By%20Using%20the%20Visual%20Studio%20Package%20Template.md)를 참조하세요.  
  
2.  **프로그래밍 언어 선택** 페이지에서 언어를 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]로 설정합니다.  
  
3.  **VSPackage 기본 정보** 페이지의 기본값을 그대로 유지합니다.  
  
4.  **VSPackage 옵션 선택** 페이지에서 **메뉴 명령** 확인란을 선택합니다.  
  
5.  **명령 옵션** 페이지에서 **명령 이름**을 `Auto`로 변경합니다.  
  
6.  **마침** 단추를 클릭합니다.  
  
     템플릿이 Auto라는 관리되는 프로젝트를 생성합니다.  
  
7.  솔루션을 빌드하고 오류 없이 컴파일되는지 확인합니다.  
  
### 자동화 모델을 호출하려면  
  
1.  **솔루션 탐색기**에서 Auto 프로젝트 노드를 마우스 오른쪽 단추로 클릭한 다음 **추가**, **참조**를 차례로 클릭합니다.  
  
2.  **참조** 대화 상자의 **.NET** 탭에서 **EnvDTE**을 두 번 클릭합니다.  
  
     EnvDTE 자동화 네임스페이스에 대한 참조가 추가됩니다.  
  
3.  AutoPackage 파일에서 다음 네임스페이스 참조를 추가합니다.  
  
     [!code-cs[VSSDKAuto#1](../misc/codesnippet/CSharp/walkthrough-extending-managed-vspackages-by-using-automation_1.cs)]
     [!code-vb[VSSDKAuto#1](../misc/codesnippet/VisualBasic/walkthrough-extending-managed-vspackages-by-using-automation_1.vb)]  
  
4.  AutoPackage 파일에서 `MenuItemCallback` 메서드의 본문을 다음 줄로 바꿉니다.  
  
     [!code-cs[VSSDKAuto#2](../misc/codesnippet/CSharp/walkthrough-extending-managed-vspackages-by-using-automation_2.cs)]
     [!code-vb[VSSDKAuto#2](../misc/codesnippet/VisualBasic/walkthrough-extending-managed-vspackages-by-using-automation_2.vb)]  
  
 이 코드는 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A>를 호출하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE를 나타내는 <xref:EnvDTE.DTE> 자동화 개체를 가져옵니다.`MenuItemCallback`의 자동화 코드는 **출력** 창에 **Test**라는 새 창을 만듭니다. 그런 다음 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 이름 및 버전이 **출력** 창에 기록됩니다.  
  
1.  F5 키를 눌러 디버그 모드에서 Auto 프로젝트를 빌드하고 시작합니다.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 실험적 빌드\([!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Exp\)가 시작됩니다.  
  
    > [!NOTE]
    >  이 시점에는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 두 버전이 모두 열려 있습니다.  
  
2.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Exp의 **도구** 메뉴에서 **Auto**를 클릭합니다.  
  
     **Test**라는 새 창이 **출력** 창에서 열리고 다음을 표시합니다.  
  
    ```  
    Name is Microsoft Visual Studio Version is x.xx  
    ```  
  
     여기서 x.xx는 최신 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 버전 번호입니다.  
  
     자동화 샘플에 대한 자세한 내용은 [Visual Studio용 자동화 샘플](http://www.microsoft.com/downloads/details.aspx?familyid=3ff9c915-30e5-430e-95b3-621dccd25150&displaylang=en)을 참조하세요.  
  
## 참고 항목  
 [Extending the Visual Studio Environment](../Topic/Extending%20the%20Visual%20Studio%20Environment.md)