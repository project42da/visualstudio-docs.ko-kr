---
title: '검사 목록: 새 프로젝트 형식을 만들지 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], creating new types
- project types, checklist for creating
ms.assetid: 29eb9c3b-1933-4741-aa85-65a33f0825ba
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 11707e62e99dd6a7920ad627d02e6e418c002e80
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="checklist-creating-new-project-types"></a>검사 목록: 새 프로젝트 형식 만들기
새 프로젝트 형식을 생성 하기 위한 몇 가지 작업을 완료 해야 합니다. 다음 검사 목록을 해당 작업에 대 한 지침을 제공합니다.  
  
1.  새 프로젝트 형식에 대 한 기능을 디자인 합니다. 자세한 내용은 참조 [프로젝트 형식에 대 한 디자인 관련 결정](../../extensibility/internals/project-type-design-decisions.md)합니다.  
  
2.  어떤 편집기가 코드 및 기타 프로젝트 요소에 대 한 사용을 확인 합니다. 코어 또는 표준 편집기를 사용할 수 있습니다 또는 만들고 프로젝트 관련 편집기를 사용할 수 있습니다. 자세한 내용은 참조 [만드는 사용자 지정 편집기 및 디자이너](../../extensibility/creating-custom-editors-and-designers.md) 및 [하는 방법: 프로젝트 관련 편집기 열기](../../extensibility/how-to-open-project-specific-editors.md)합니다.  
  
3.  프로젝트 항목에 갖습니다 참여 수준을 결정 합니다.는 **클래스 뷰** 및 **개체 브라우저**합니다. 자세한 내용은 참조 [기호를 지 원하는 검색 도구](../../extensibility/internals/supporting-symbol-browsing-tools.md)합니다.  
  
4.  프로젝트 및 프로젝트 항목에 대해 이전에 만든 디자인 결정에 따라 새 클래스를 파생 합니다.  
  
5.  다음 프로젝트 형식 구성 요소에 대 한 코드를 작성 합니다.  
  
    -   새 프로젝트를 만들고 기존 프로젝트를 열기를 관리 하려면 프로젝트 팩터리입니다. 자세한 내용은 참조 [만들기 프로젝트 인스턴스 여를 사용 하 여 프로젝트 팩터리](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)합니다.  
  
    -   프로젝트 계층 구조 및 명령 처리 합니다. 자세한 내용은 참조 [빌드에 없음: 프로젝트 형식 (c + +)를 구현 하려면 HierUtil7 프로젝트 클래스를 사용 하 여](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346), [프로젝트 모델의 요소](../../extensibility/internals/elements-of-a-project-model.md), [프로젝트 모델 핵심 구성 요소](../../extensibility/internals/project-model-core-components.md)및 [MenuCommands Vs. OleMenuCommands](../../extensibility/menucommands-vs-olemenucommands.md)합니다.  
  
    -   프로젝트에 추가 하는 등의 프로젝트 항목 관리는 **새 프로젝트** 대화 상자. 자세한 내용은 참조 [추가 프로젝트 및 프로젝트 항목 템플릿](../../extensibility/internals/adding-project-and-project-item-templates.md) 및 [등록 프로젝트 및 항목 템플릿](../../extensibility/internals/registering-project-and-item-templates.md)합니다.  
  
    -   프로젝트 상태 및 개별 항목의 지 속성입니다. 자세한 내용은 참조 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md)합니다. 솔루션 정보의 지 속성에 대 한 참조 [솔루션](../../extensibility/internals/solutions.md)합니다.  
  
    -   속성 창에 표시 하려면 구성 독립 속성입니다. 자세한 내용은 참조 [확장 속성](../../extensibility/internals/extending-properties.md)합니다.  
  
    -   프로젝트 구성 속성 구성에 종속 된 속성을 표시 하려면 속성 페이지에서 구현 합니다. 자세한 내용은 참조 [구성 옵션 관리](../../extensibility/internals/managing-configuration-options.md)합니다.  
  
    -   배포에 대 한 출력을 열거 합니다. 자세한 내용은 참조 [출력에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-output.md)합니다.  
  
    -   프로젝트 시작 서비스입니다. 자세한 내용은 참조 [프로젝트 모델의 요소](../../extensibility/internals/elements-of-a-project-model.md) 및 [프로젝트 모델에 대 한 핵심 구성 요소](../../extensibility/internals/project-model-core-components.md)합니다.  
  
    -   개체 또는 클래스에서 파생 된 `IDispatch`, 자동화에 사용할 수 있습니다.  
  
    -   XML 명령 테이블 (.vsct) 파일입니다. 자세한 내용은 참조 [Visual Studio 명령 테이블 (합니다. Vsct) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)합니다.  
  
6.  테스트, 디버깅 및 프로젝트 형식 시작 합니다.  
  
7.  프로젝트에 표시는 **프로젝트** 탭은 **참조 추가** 설정 하 여 대화 상자 `VARIANT_TRUE` 에 대 한 값으로 `VSHPROPID_ShowProjInSolutionPage`합니다. 자세한 내용은 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>를 참조하세요.  
  
8.  설치 하 여 Vspackage에 대 한 Microsoft Installer (.msi) 파일을 만듭니다. 자세한 내용은 참조 [Windows Installer와 Vspackage 설치](../../extensibility/internals/installing-vspackages-with-windows-installer.md), [프로젝트 형식을 등록](../../extensibility/internals/registering-a-project-type.md), 및 [Vspackage](../../extensibility/internals/vspackages.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 계층 구조](../../extensibility/internals/hierarchies-in-visual-studio.md)   
 [프로젝트 형식 만들어야 하는 경우](../../extensibility/internals/when-to-create-project-types.md)   
 [프로젝트 형식 만들기](../../extensibility/internals/creating-project-types.md)