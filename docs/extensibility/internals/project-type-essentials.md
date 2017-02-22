---
title: "프로젝트 형식 Essentials | Microsoft Docs"
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
  - "프로젝트 형식 [Visual Studio SDK]"
ms.assetid: 09991589-2300-430e-b6a4-7f2b95fe676f
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로젝트 형식 Essentials
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 와 같은 언어에 대 한 몇 가지 프로젝트 형식에 포함 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 또는 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]합니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 또한 사용자 고유의 프로젝트 형식을 만들 수 있습니다.  
  
 사용자 지정 명령, 편집기, 또는 도구 창을 추가 하려는 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 새 프로젝트 형식을 만들지 않고 수행할 수 있습니다. 자세한 내용은 다음 항목을 참조하세요.  
  
-   [명령, 메뉴 및 도구 모음](../../extensibility/internals/commands-menus-and-toolbars.md)  
  
-   [편집기와 언어 서비스 확장](../../extensibility/editor-and-language-service-extensions.md)  
  
-   [확장 및 도구 창을 사용자 지정](../../extensibility/extending-and-customizing-tool-windows.md)  
  
 마찬가지로,는 제공 된 동작을 사용자 지정 하려는 경우 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 프로젝트 형식 할 수 있는 프로젝트 하위 형식을 사용 합니다. 자세한 내용은 [프로젝트 하위 형식](../../extensibility/internals/project-subtypes.md)을 참조하세요.  
  
 이외의 다른 언어에 따라 프로젝트에 대 한 새 프로젝트 유형을 만들어야 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 다음 중 하나 이상의 지원 하려는 경우:  
  
-   빌드  
  
-   배포  
  
-   여러 구성  
  
-   소스 제어  
  
-   디버깅  
  
-   솔루션 탐색기에서 프로젝트 항목  
  
-   **프로젝트 열기** 또는 **새 프로젝트** 대화 상자  
  
-   프로젝트 중첩  
  
-   프로젝트 형식의 기능에 대 한 자세한 내용은 다음을 참조 합니다.  
  
-   프로젝트 유형은 인터페이스 집합을 구현 하는 vspackage에서 개체 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 것으로 예상 합니다. 하면 C\#을 사용 하는 프로젝트 유형을 개발 하는 경우 관리 되는 패키지 프레임 워크 프로젝트 클래스 필요한 인터페이스를 구현 및 사용 하면 해당 구현을 상속 합니다. 자세한 내용은 [프로젝트 형식 \(C\#\)를 구현 하는 관리 되는 패키지 프레임 워크를 사용 하 여](../../extensibility/internals/using-the-managed-package-framework-to-implement-a-project-type-csharp.md)을 참조하세요.  
  
-   C \+ \+ 개발자를 위한 HierUtil 라이브러리의 클래스를 비슷한 방식으로 작동 합니다. 자세한 내용은 참조 [빌드에 없음: 프로젝트 형식 \(c \+ \+\)를 구현 하기 위한 HierUtil7 프로젝트 클래스를 사용 하 여](http://msdn.microsoft.com/ko-kr/a5c16a09-94a2-46ef-87b5-35b815e2f346)합니다.  
  
-   프로젝트 형식.exe 또는.dll 어셈블리에 기반 하는 일반적인 소스 코드 파일 이외의 데이터를 지원할 수 있습니다. 예를 들어 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 데이터베이스 프로젝트에 디스크에 저장 된 스크립트 및 쿼리 파일에 대 한 참조가 포함 및 명령 추가 **솔루션 탐색기** 실행 하는 스크립트 및 데이터베이스에 있지만 프로젝트에 대 한 쿼리 지원 하지 않으므로 빌드 동작 합니다. 자세한 내용은 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md)을 참조하세요.  
  
-   프로젝트 형식 파일을 전혀 사용 하지 않아도 됩니다. 예를 들어 프로젝트 형식 데이터베이스에 모든 데이터를 저장할 수 있습니다.[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 형식 프로젝트 및 프로젝트 항목에 대 한 데이터를 유지 하는 방법을 완전히 제어를 제공 합니다. 자세한 내용은 [프로젝트 형식에 대 한 설계 결정 사항](../../extensibility/internals/project-type-design-decisions.md)을 참조하십시오.  
  
-   프로젝트 형식을 제공 해야는 *프로젝트 팩터리*, 프로젝트의 인스턴스를 만드는 개체는 때마다 입력 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 를 열거나 해당 프로젝트 유형을 기반으로 하는 프로젝트를 만듭니다. 자세한 내용은 [프로젝트 팩터리를 사용 하 여 프로젝트 인스턴스 만들기](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)을 참조하십시오.  
  
-   프로젝트 형식에는 프로젝트 및 프로젝트 항목에 대 한 템플릿을 제공 해야 합니다.[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자가 새 프로젝트를 만들고 기존 프로젝트에 새 항목을 추가 하는 경우 서식 파일을 사용 합니다. 자세한 내용은 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)을 참조하세요.  
  
-   프로젝트 형식에는 디버그 및 릴리스 등의 여러 구성을 지원할 수 있습니다. 사용자가 제공 하는 속성 페이지를 사용 하 여 프로젝트의 다양 한 구성을 변경할 수 있습니다. 자세한 내용은 [구성 옵션 관리](../../extensibility/internals/managing-configuration-options.md)을 참조하세요.  
  
## 참고 항목  
 [배포 프로젝트 형식](../../extensibility/internals/deploying-project-types.md)