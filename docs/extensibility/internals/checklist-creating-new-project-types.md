---
title: "검사 목록: 새 프로젝트 형식 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 [Visual Studio SDK] 새 형식 만들기"
  - "프로젝트 형식 만들기에 대 한 검사 목록"
ms.assetid: 29eb9c3b-1933-4741-aa85-65a33f0825ba
caps.latest.revision: 23
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 23
---
# 검사 목록: 새 프로젝트 형식 만들기
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

새 프로젝트 형식을 만드는 몇 가지 작업을 완료 해야 합니다. 다음 검사 목록을 해당 작업에 대 한 지침을 제공합니다.  
  
1.  새 프로젝트 형식에 대 한 기능을 디자인 합니다. 자세한 내용은 [프로젝트 형식에 대 한 설계 결정 사항](../../extensibility/internals/project-type-design-decisions.md)을 참조하세요.  
  
2.  코드 및 기타 프로젝트 요소에 대 한 어떤 편집기가 사용을 확인 합니다. 핵심 또는 표준 편집기를 사용 하 여 또는 만들고 프로젝트에 특정 편집기를 사용 하 여 수 있습니다. 자세한 내용은 [사용자 지정 편집기 및 디자이너 만들기](../../extensibility/creating-custom-editors-and-designers.md) 및 [방법: 프로젝트에 특정 편집기 열기](../../extensibility/how-to-open-project-specific-editors.md)를 참조하세요.  
  
3.  프로젝트 항목에는 참여 수준을 결정은 **클래스 뷰** 및 **개체 브라우저**합니다. 자세한 내용은 [기호 검색 도구를 지원합니다.](../../extensibility/internals/supporting-symbol-browsing-tools.md)을 참조하세요.  
  
4.  이전에 만든 프로젝트 및 프로젝트 항목에 대 한 디자인 결정에 따라 새 클래스를 파생 합니다.  
  
5.  다음 프로젝트 유형 구성 요소에 대 한 코드를 작성 합니다.  
  
    -   새 프로젝트를 만들고 기존 프로젝트 열기를 관리 하려면 프로젝트 팩터리입니다. 자세한 내용은 [프로젝트 팩터리를 사용 하 여 프로젝트 인스턴스 만들기](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)을 참조하세요.  
  
    -   프로젝트 계층 구조 및 명령 처리 합니다. 자세한 내용은 참조 [빌드에 없음: 프로젝트 형식 \(c \+ \+\)를 구현 하기 위한 HierUtil7 프로젝트 클래스를 사용 하 여](http://msdn.microsoft.com/ko-kr/a5c16a09-94a2-46ef-87b5-35b815e2f346), [프로젝트 모델의 요소](../../extensibility/internals/elements-of-a-project-model.md), [프로젝트 모델에 대 한 핵심 구성 요소](../../extensibility/internals/project-model-core-components.md) 및 [MenuCommand 및 OleMenuCommand](../../misc/menucommands-vs-olemenucommands.md)합니다.  
  
    -   프로젝트 항목 관리, 프로젝트를 추가 하는 등의 **새 프로젝트** 대화 상자입니다. 자세한 내용은 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md) 및 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)를 참조하세요.  
  
    -   프로젝트 상태 및 개별 항목의 지 속성입니다. 자세한 내용은 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md)을 참조하세요. 솔루션 정보의 지 속성을 참조 하십시오. [솔루션](../../extensibility/internals/solutions.md)합니다.  
  
    -   속성 창에 표시 하려면 구성 독립 속성입니다. 자세한 내용은 [속성 확장](../../extensibility/internals/extending-properties.md)을 참조하세요.  
  
    -   프로젝트 구성에 종속 된 속성을 표시 하려면 속성 페이지에서 구현 되는 구성 속성입니다. 자세한 내용은 [구성 옵션 관리](../../extensibility/internals/managing-configuration-options.md)을 참조하십시오.  
  
    -   배포에 대 한 출력을 열거 합니다. 자세한 내용은 [출력에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-output.md)을 참조하십시오.  
  
    -   프로젝트 시작 서비스입니다. 자세한 내용은 [프로젝트 모델의 요소](../../extensibility/internals/elements-of-a-project-model.md) 및 [프로젝트 모델에 대 한 핵심 구성 요소](../../extensibility/internals/project-model-core-components.md)를 참조하세요.  
  
    -   개체 또는 클래스에서 파생 된 `IDispatch`, 자동화에서 사용할 수 있습니다.  
  
    -   XML 명령 테이블 \(.vsct\) 파일입니다. 자세한 내용은 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)을 참조하십시오.  
  
6.  테스트, 디버깅 및 프로젝트 형식 시작 합니다.  
  
7.  프로젝트에 표시는 **프로젝트** 탭은 **참조 추가** 설정 하 여 대화 상자 `VARIANT_TRUE` 에 대 한 값으로 `VSHPROPID_ShowProjInSolutionPage`합니다. 자세한 내용은 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>를 참조하세요.  
  
8.  여 Vspackage를 설치 하기 위한 Microsoft Installer \(.msi\) 파일을 만듭니다. 자세한 내용은 [Windows Installer를 사용 하 여 Vspackage를 설치](../../extensibility/internals/installing-vspackages-with-windows-installer.md), [프로젝트 형식 등록](../../extensibility/internals/registering-a-project-type.md) 및 [Vspackage](../../extensibility/internals/vspackages.md)을 참조하십시오.  
  
## 참고 항목  
 [Visual Studio에서 계층 구조](../../extensibility/internals/hierarchies-in-visual-studio.md)   
 [프로젝트 형식 만들어야 하는 경우](../../extensibility/internals/when-to-create-project-types.md)   
 [프로젝트 형식 만들기](../../extensibility/internals/creating-project-types.md)