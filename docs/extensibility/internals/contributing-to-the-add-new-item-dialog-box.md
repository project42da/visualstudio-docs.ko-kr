---
title: 에 기여 하는 새 항목 추가 대화 상자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Add New Item dialog box, contributing to
ms.assetid: b2e53175-9372-4d17-8c2b-9264c9e51e9c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6d8b35537828f99fe3683e03feac3960d6ca4adc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="contributing-to-the-add-new-item-dialog-box"></a>에 기여 하는 새 항목 추가 대화 상자
프로젝트 하위 형식에 대 한 항목의 전체 새 디렉터리를 제공할 수는 **새 항목 추가** 등록 하 여 대화 상자 **항목 추가** 에서 템플릿은 `Projects` 레지스트리 하위 키입니다.  
  
## <a name="registering-add-new-item-templates"></a>등록 새 항목 추가 템플릿  
 이 섹션 아래에 있는 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects** 레지스트리에 합니다. 아래의 레지스트리 항목 가정는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 가상 프로젝트 하위 형식에서 프로젝트를 집계 합니다. 에 대 한 항목은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트는 다음과 같습니다.  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects\{F184B08F-C81C-45F6-A57F-5ABD9991F28F}]  
@="#2143"  
"DefaultProjectExtension"="vbproj"  
"PossibleProjectExtensions"="vbproj;vbp"  
"ProjectTemplatesDir"="visualStudioInstallPath\\Vb\\.\\VBProjects"  
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects\{F184B08F-C81C-45F6-A57F-5ABD9991F28F}\AddItemTemplates\TemplateDirs\{12345678-1234-1234-1122334455667788}\/1]  
@="#100"  
"TemplatesDir"="projectSubTypeTemplatesDir\\VBProjectItems"  
```  
  
 `AddItemTemplates\TemplateDirs` 항목에서 사용할 수 있게 하는 디렉터리의 경로로 레지스트리 항목을 포함 하는 하위 키의 **새 항목 추가** 대화 상자에 배치 됩니다.  
  
 환경에 모든 항목을 자동으로 로드 된 `AddItemTemplates` 정리 된 데이터는 `Projects` 레지스트리 하위 키입니다. 이 기본 프로젝트 구현에 대 한 데이터와 특정 프로젝트 하위 형식에 대 한 데이터에 포함할 수 있습니다. 각 프로젝트 하위 형식 프로젝트 형식으로 식별 되 `GUID`합니다. 대체 집합이 프로젝트 하위 형식을 지정할 수 `Add Item` 서식 파일에 사용할 특정 버전이 지정 된 프로젝트 인스턴스를 지원 하 여는 `VSHPROPID_ AddItemTemplatesGuid` 열거형에서 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> 에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> GUID를 반환 하는 데 구현 프로젝트 하위 유형의 값입니다. 경우 `VSHPROPID_AddItemTemplatesGuid` 속성을 지정 하지 않으면 기본 프로젝트 GUID는 사용 됩니다.  
  
 항목을 필터링 할 수 있습니다는 **새 항목 추가** 구현 하 여 대화 상자는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg> 프로젝트 하위 형식 aggregator 개체의 인터페이스입니다. 집계 하 여 데이터베이스 프로젝트를 구현 하는 프로젝트 하위 형식 예를 들어 한 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트를 필터링 할 수는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 에서 항목을 특정은 **새 항목 추가** 대화 상자 및 필터링을 구현 하 여 설정, 추가할 수 프로젝트의 특정 항목을 지원 하 여 데이터베이스 `VSHPROPID_ AddItemTemplatesGuid` 에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>합니다. 필터링 및 항목을 추가 대 한 자세한 내용은 **새 항목 추가** 대화 상자, 참조 [새 항목 추가 대화 상자에 항목 추가](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [일반적으로 프로젝트를 확장하는 데 사용되는 개체에 대한 CATID](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)