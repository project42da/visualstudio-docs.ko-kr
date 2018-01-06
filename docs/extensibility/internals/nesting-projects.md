---
title: "중첩 프로젝트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project nesting
- nested projects
- projects [Visual Studio SDK], child projects
- projects [Visual Studio SDK], nesting
ms.assetid: 12cce037-9840-4761-845e-5abd5fb317b0
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5b91f9dc00b9130f2c239bd3254f78376bc0fdf3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="nesting-projects"></a>중첩 프로젝트
VS 패키지를 사용 하는 엔터프라이즈 응용 프로그램 개발자 비슷한 형식의 프로젝트에서 함께 그룹화 편리 하 게 수 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 를 사용 하 여 *중첩 프로젝트*합니다. 예를 들어, 엔터프라이즈 템플릿 프로젝트 범주로 그룹 프로젝트에 대 한 중첩 된 프로젝트를 사용합니다. 비즈니스 외관 프로젝트, 웹 UI 프로젝트 및에 하나의 범주에 함께 그룹화 됩니다.  
  
 이 시나리오에서는 즉 개발자 각 부모 프로젝트 아래에 중첩할 수는 프로젝트 수에 제한이 없음을 개발자 한계를 프로그래밍 방식으로 제공할 수 있지만 있습니다. 이 유형의 그룹화 만들 수도 있습니다 재귀,이 경우 부모의 하위 항목인 자식의 하위 프로젝트 될 자식 아래 자식 프로젝트와 같은 유형의 프로젝트에 중첩 될 수 있습니다.  
  
 중첩 프로젝트의 내장 함수는 일부가 아닙니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 코드 중첩을 활성화 하 고 자식 프로젝트 내의 중첩 하위 프로젝트를 작성 해야 합니다. 부모 프로젝트는 특별 한 VSPackage 또는 프로젝트 형식에 만들고 프로젝트 중첩을 구현 하는 데 필요한 코드를 포함 하는 고유 GUID를 가진 등록.  
  
 C# Example.Nested Project 예제에 중첩 된 프로젝트의 예제를 찾을 수 있습니다.  
  
## <a name="nested-projects-example"></a>중첩 된 프로젝트 예제  
 ![중첩 프로젝트 솔루션](../../extensibility/internals/media/vsnestedprojects.gif "vsNestedProjects")  
중첩 된 프로젝트 예제  
  
## <a name="see-also"></a>참고 항목  
 [방법: 중첩 된 프로젝트를 구현 합니다.](../../extensibility/internals/how-to-implement-nested-projects.md)   
 [중첩 된 프로젝트 언로드 및 다시 로드에 대 한 고려 사항](../../extensibility/internals/considerations-for-unloading-and-reloading-nested-projects.md)   
 [중첩 된 프로젝트에 대 한 마법사 지원](../../extensibility/internals/wizard-support-for-nested-projects.md)   
 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)   
 [중첩 된 프로젝트에 대 한 처리 명령 구현](../../extensibility/internals/implementing-command-handling-for-nested-projects.md)   
 [중첩 된 프로젝트에 대 한 필터링 항목 추가 대화 상자](../../extensibility/internals/filtering-the-additem-dialog-box-for-nested-projects.md)   
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)   
 [마법사(.Vsz) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)