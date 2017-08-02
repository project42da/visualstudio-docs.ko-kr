---
title: "Visual Studio 확장성 아키텍처 | Microsoft Docs"
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
  - "Visual Studio, 환경 모델"
  - "환경 모델, Visual Studio"
ms.assetid: 280fdb55-3e70-41fd-8da0-4039bf5d4894
caps.latest.revision: 17
caps.handback.revision: 17
manager: "douge"
---
# Visual Studio 확장성 아키텍처
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 \(IDE\) Vspackages를 호스트 하 고 쉽게 공유 서비스를 교환할 수 있는 프레임 워크입니다.  이러한 예는 IDE 사용자 인터페이스 \(UI\)를 구현 하는 방법입니다.  IDE 컨테이너 창의 기본 도구 모음 및 메뉴를 제공합니다.  또한 UI 프로그래밍 가능 하는 다양 한 COM 인프라를 제공 합니다.  전체 명령 처리 및 라우팅 구성표 사용자가 모두 기존에 쉽게 액세스를 제공 하 고 명령 집합을 설치를 위한 개방형 프레임 워크를 제공 합니다.  
  
## 확장 아키텍처  
 다음 그림과 해당 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 확장성 아키텍처입니다.  참고 소프트웨어 응용 프로그램의 개념이 없습니다.  대신 IDE 호스트 소프트웨어 구성 요소를 응용 프로그램 기능을 제공 하는 Vspackages를 호출 합니다.  결과적으로이 기능을 IDE에서 서비스를 공유 합니다.  Vspackages가 및 기타 Vspackages를 사용 하는 서비스를 제공 합니다.  표준 IDE 또한 광범위 한 서비스를 제공 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>, IDE 창 작업 기능을 제공 합니다.  
  
 ![환경 아키텍처 그래픽](~/docs/extensibility/internals/media/environment.gif "environment")  
Visual Studio 아키텍처의 일반화 된 보기  
  
 양방향 VSPackages 및 서비스 사이의 관계 됩니다.  VSPackages 다른 사용자가 제공 하는 서비스를 사용 하지만 또한를 사용 하 여 자체 서비스 제공할 수 있는 <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> 인터페이스입니다.  이 서비스 기반 아키텍처는 서비스 작업을 수행 하는 관련된 인터페이스의 그룹인 Microsoft ActiveX 디자이너 구현 중 증가 합니다.  엄격한 COM 관점에서 보면 모든 인터페이스가 특정 서비스의 단일 COM 클래스에서 구현 되어야 합니다.  
  
 표준 IDE 같은 중요 한 서비스를 제공 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>, <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>, 및 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>, Vspackages가 사용 됩니다.  다음 표에서 나열 하 고 이러한 서비스 중 일부에 대해 설명 합니다.  자세한 내용은 [사용 하 고 서비스를 제공 합니다.](../extensibility/using-and-providing-services.md)를 참조하십시오.  
  
|IDE 서비스|설명|  
|-------------|--------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>|기본 기능을 Vspackages에과 레지스트리 액세스 IDE 처리 서비스를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>|기본 창 작업 및 UI 관련 기능은 ide에서 도구와 문서 창을 만들 수 있는 기능 등을 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>|프로젝트를 열거 하 고 새 프로젝트를 만들고 프로젝트의 변경 내용을 모니터링 하는 등 기본 솔루션에 관련 된 기능을 제공 합니다.|  
  
 때문에 공유 서비스의 상호 작용을 통해의 긴밀 한 통합은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE 및 VSPackages 밀접 하 게 상호 의존적입니다.  그러나의 닫기 상호 작용에도 불구 하 고 이들은 서로 다른 책임이 부여 됩니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE가 다음 작업에 대 한 책임이 있습니다.  
  
-   외부 Vspackages가 중요 한 서비스를 제공 합니다.  
  
-   표준 UI 요소와 함께 참여 수 있도록 프로그래밍 인터페이스를 제공 합니다.  
  
-   사용자 작업 또는 다른 VSPackages 요청 서비스에 필요한 VSPackages 인스턴스 만들기  
  
-   통신 및 VSPackages 간 조정 가능 하 게 하는 서비스를 제공 합니다.  
  
-   솔루션 및 필요한 파일을 관리 합니다.  
  
-   창 관리를 제공 합니다.  
  
-   명령 라우팅 및 명령 모음, 메뉴, 도구 모음 및 상황에 맞는 메뉴 등을 제공합니다.  
  
-   선택 영역, 컨텍스트 및 통화를 조정 합니다.  
  
 Vspackages에 대해 다음과 같은 작업을 담당합니다.  
  
-   특정 초기화 및 종료 루틴을 수행 합니다.  
  
-   IDE를 사용 하 여 적절 한 시기에 적절 한 Vspackages를 로드 하도록 레지스트리에 정보를 기록 합니다.  
  
-   다른 Vspackages에 통신 하는 데 필요한 서비스를 제공 합니다.  
  
-   새 프로젝트 형식, 편집기 및 디자이너에 대 한 구현을 제공  
  
-   작업 항목, 도구 상자 항목 및 옵션 대화 상자와 같은 기본 제공 UI 요소에 대 한 확장을 제공합니다.  
  
## 참고 항목  
 [Visual Studio Shell](../extensibility/internals/visual-studio-shell.md)   
 [Vspackage](../extensibility/internals/vspackages.md)   
 [사용 하 고 서비스를 제공 합니다.](../extensibility/using-and-providing-services.md)   
 [방법: 서비스 가져오기](../extensibility/how-to-get-a-service.md)