---
title: "새 프로젝트 대화 상자에 디렉터리를 추가합니다. | Microsoft Docs"
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
  - "새 프로젝트 대화 상자, 확장"
ms.assetid: 53b328f5-20bb-49a3-bf9e-1818f4fbdf50
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# 새 프로젝트 대화 상자에 디렉터리를 추가합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

새 프로젝트 형식을 만들 때 새 디렉터리에 등록할 수도 있습니다의  **새 프로젝트** 를 사용할 수 있도록 템플릿으로 표시 하는 대화 상자입니다.  다음 코드 예제에서는 새 디렉터리 라고도 하는 노드를 등록 하는 방법을 설명 합니다.  예제에서는 VSPackage clsid\_package에 의해 노출 되는 템플릿은 등록 합니다.  왼쪽에는 결과  **새 프로젝트** 대화 상자 결정 Folder\_Label\_ResID 리소스에 의해 이름이 추가 된 노드를 제공 합니다.  이 리소스 VSPackage 위성 DLL을 로드 합니다.  
  
 해당  **폴더** 폴더에서 Folder\_Label\_ResID 노드에 표시 되는 GUID 값을 나타냅니다.  하는 GUID를 나타내는  **기타 프로젝트** 폴더에는  **프로젝트 형식** 의 창에  **새 프로젝트** 대화 상자.  경우는  **기타 프로젝트** 값이 없는 경우, 최상위 수준에 레이블이 배치 됩니다.  
  
 TemplatesDir 프로젝트 서식 파일이 포함 된 디렉터리의 전체 경로 지정 합니다.  이 파일은.vsz 파일이 나 일반 템플릿 파일이 복제 될 수 수 있습니다.  
  
 Templateslocalizedsubdir를 지정 하는 경우 지역화 된 템플릿이 저장 Templatesdir의 하위 디렉터리의 이름을 지정 하는 문자열의 리소스 ID 여야 합니다.  때문에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 문자열 리소스를 로드 위성 DLL에서 각 위성 DLL에 있는 경우 다른 하위 디렉터리 이름을 포함할 수 있습니다. SortPriority 값 정렬 우선 순위를 지정합니다.  
  
```  
NoRemove NewProjectTemplates  
{  
    NoRemove TemplateDirs  
  {  
    ForceRemove %CLSID_Package%  
    {  
      ForceRemove /1 = s '#%Folder_Label_ResID%'  
      {  
        val Folder = s '{DCF2A94A-45B0-11D1-ADBF-00C04FB6BE4C}'  
        val TemplatesDir = s '%Template_Path%'  
        val TemplatesLocalizedSubDir = s '#100'  
        val SortPriority = d 1000  
      }  
    }  
  }  
}  
```  
  
## 참고 항목  
 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)   
 [에 항목 추가 된 새 항목 추가 대화 상자](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [디렉터리에 추가 된 새 항목 추가 대화 상자](../../extensibility/internals/adding-directories-to-the-add-new-item-dialog-box.md)