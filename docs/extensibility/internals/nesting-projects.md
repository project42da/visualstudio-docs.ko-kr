---
title: "중첩 프로젝트 | Microsoft Docs"
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
  - "프로젝트 중첩"
  - "중첩된 프로젝트"
  - "프로젝트 [Visual Studio SDK] 자식 프로젝트"
  - "중첩 프로젝트 [Visual Studio SDK]"
ms.assetid: 12cce037-9840-4761-845e-5abd5fb317b0
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# 중첩 프로젝트
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

VS 패키지를 사용 하는 엔터프라이즈 응용 프로그램 개발자에 이와 유사한 종류의 프로젝트에서 함께 그룹화 편리 하 게 수 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 를 사용 하 여 *중첩 프로젝트*합니다. 예를 들어, 엔터프라이즈 템플릿 프로젝트 범주로 그룹 프로젝트에 대 한 중첩 된 프로젝트를 사용합니다. 비즈니스 외관 프로젝트, 웹 UI 프로젝트의 경우 등에 하나의 범주에 함께 그룹화 됩니다.  
  
 이 시나리오의 경우 개발자는 각 부모 프로젝트 아래의 중첩할 수는 프로젝트 수에 제한이 없음을 개발자 한계를 프로그래밍 방식으로 제공할 수 있지만 이 유형의 그룹화 만들 수도 있습니다 재귀적으로 부모의 하위 항목인 자식의 하위 프로젝트 될 자식에서 자식 프로젝트와 동일한 형식의 프로젝트 중첩 될 수 있는 경우.  
  
 중첩 프로젝트의 내장 함수는 일부가 아닙니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 중첩을 사용 하도록 설정 하 고 자식 프로젝트 내의 중첩 하위 프로젝트는 코드를 작성 해야 합니다. 부모 프로젝트 특수 VSPackage 또는 프로젝트 형식에 만들어져 등록 된 중첩 프로젝트를 구현 하는 데 필요한 코드가 포함 된 고유 GUID입니다.  
  
 C\# Example.Nested 프로젝트 샘플에서 중첩된 프로젝트의 예를 찾을 수 있습니다.  
  
## 중첩된 프로젝트 예제  
 ![중첩 프로젝트 솔루션](../../extensibility/internals/media/vsnestedprojects.gif "vsNestedProjects")  
중첩된 프로젝트 예제  
  
## 참고 항목  
 [방법: 중첩 된 프로젝트를 구현 합니다.](../../extensibility/internals/how-to-implement-nested-projects.md)   
 [중첩된 프로젝트 언로드 및 다시 로드에 대 한 고려 사항](../../extensibility/internals/considerations-for-unloading-and-reloading-nested-projects.md)   
 [중첩된 프로젝트에 대 한 마법사 지원](../../extensibility/internals/wizard-support-for-nested-projects.md)   
 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)   
 [중첩된 프로젝트에 대 한 처리 명령 구현](../../extensibility/internals/implementing-command-handling-for-nested-projects.md)   
 [중첩된 프로젝트에 대 한 항목 추가 대화 상자를 필터링](../../extensibility/internals/filtering-the-additem-dialog-box-for-nested-projects.md)   
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)   
 [마법사 \(합니다. Vsz\) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)