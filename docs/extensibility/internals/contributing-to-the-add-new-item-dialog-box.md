---
title: "기여 하는 새 항목 추가 대화 상자 | Microsoft Docs"
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
  - "새 항목 추가 대화 상자에 기여"
ms.assetid: b2e53175-9372-4d17-8c2b-9264c9e51e9c
caps.latest.revision: 18
caps.handback.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
---
# 기여 하는 새 항목 추가 대화 상자
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트 하위 유형을 완전 새 디렉터리 항목을 제공할 수 있습니다의  **새 항목 추가** 등록 하 여 대화 상자  **항목 추가**  템플릿 아래는 `Projects` 레지스트리 하위 키입니다.  
  
## 추가할 새 항목 템플릿 등록  
 이 섹션 아래에 있는 **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\8.0\\Projects** 레지스트리에서.  아래의 레지스트리 항목으로 간주는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 가상의 프로젝트 하위에서 집계 됩니다.  항목에 대 한의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 아래 나열 되어 있습니다.  
  
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
  
 `AddItemTemplates\TemplateDirs` 하위 키 레지스트리 항목에 항목에 대 한 디렉터리 경로를 포함의  **새 항목 추가**  대화 상자 배치.  
  
 환경을 자동으로 로드는 `AddItemTemplates` 에서 데이터는 `Projects` 레지스트리 하위 키입니다.  이 하위 형식 특정 프로젝트 형식에 대 한 데이터 뿐만 아니라 기본 프로젝트 구현에 대 한 데이터를 포함할 수 있습니다.  각 프로젝트의 하위 프로젝트 형식으로 식별 됩니다 `GUID`.  대안을 설정 하는 프로젝트 하위 형식을 지정할 수 있습니다 `Add Item` 템플릿을 사용 해야 합니다 특정 flavored 프로젝트 인스턴스에 대 한 지원 하 여는 `VSHPROPID_ AddItemTemplatesGuid` 열거형에서 <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> 에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> 구현 프로젝트 하위 형식의 GUID 값을 반환 합니다.  경우 `VSHPROPID_AddItemTemplatesGuid` 속성이 지정 하지 않으면 기본 프로젝트 GUID를 사용 합니다.  
  
 항목을 필터링 할 수 있습니다의  **새 항목 추가** 대화 상자를 구현 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg> 프로젝트 하위 집계 개체 인터페이스에 있습니다.  집계 하 여 데이터베이스 프로젝트를 구현 프로젝트 하위에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트, 필터링 할 수 있습니다는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 특정 항목에서  **새 항목 추가** 대화 상자 사용 하 여 필터링을 구현, 지원 하 여 데이터베이스 프로젝트 항목을 추가할 수 있습니다 `VSHPROPID_ AddItemTemplatesGuid` 에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>.  필터링 하 고 항목 추가 대 한 자세한 내용은  **새 항목 추가** 대화 상자를 참조 하십시오 [에 항목 추가 된 새 항목 추가 대화 상자](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md).  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [일반적으로 프로젝트를 확장 하는 데 사용 되는 개체에 대 한 Catid](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)