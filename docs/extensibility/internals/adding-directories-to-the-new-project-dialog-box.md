---
title: "새 프로젝트 대화 상자에 디렉터리를 추가 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: New Project dialog box, extending
ms.assetid: 53b328f5-20bb-49a3-bf9e-1818f4fbdf50
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f24fd3c3a0ffb537c63346ef867a2a43481acfa9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="adding-directories-to-the-new-project-dialog-box"></a>새 프로젝트 대화 상자에 디렉터리를 추가합니다.
새 프로젝트 형식을 만들 때도 등록할 수 있는 새 디렉터리에는 **새 프로젝트** 대화 상자를 사용 하기 위해 템플릿으로 표시 합니다. 다음 코드 예제에서는 노드라고도 함 새 디렉터리를 등록 하는 방법을 설명 합니다. 예제에서는 VSPackage CLSID_Package에 의해 노출 되는 템플릿 등록 됩니다. 왼쪽 결과적으로는 **새 프로젝트** 대화 상자에서는 Folder_Label_ResID 리소스에 따른 이름으로 추가 된 노드를 제공 합니다. 이 리소스는 VSPackage 위성 DLL에서에서 로드 됩니다.  
  
 **폴더** 값 Folder_Label_ResID 노드가 표시 되는 폴더의 GUID를 나타냅니다. 예에서 GUID 나타냅니다는 **기타 프로젝트** 폴더에는 **프로젝트 형식** 의 창은 **새 프로젝트** 대화 상자. 경우는 **기타 프로젝트** 값이 없음, 레이블이 최상위에 배치 됩니다.  
  
 TemplatesDir 값 프로젝트 템플릿이 포함 된 디렉터리의 전체 경로 지정 합니다. 이 파일은.vsz 파일 또는 일반적인 템플릿 파일을 복제할 수 있습니다.  
  
 TemplatesLocalizedSubDir를 지정 하면 TemplatesDir 지역화 된 서식 파일을 보유 하는의 하위 디렉터리의 이름을 지정 하는 문자열의 리소스 ID 여야 합니다. 때문에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 문자열 리소스 로드 위성 DLL에서에서이 있는 각 위성 DLL 포함 될 수 있고 다른 하위 디렉터리 이름입니다. SortPriority 값 정렬 우선 순위를 지정합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)   
 [항목에 추가 된 새 항목 추가 대화 상자](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [새 항목 추가 대화 상자에 디렉터리 추가](../../extensibility/internals/adding-directories-to-the-add-new-item-dialog-box.md)