---
title: 디렉터리에 추가 된 새 항목 추가 대화 상자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Add New Item dialog box, extending
ms.assetid: 67ae8af6-3752-49e8-8ce3-007aca5f7982
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b8d9989e8cf4ec8f0eb714a26e73d89fba339b71
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="adding-directories-to-the-add-new-item-dialog-box"></a>디렉터리에 추가 된 새 항목 추가 대화 상자
다음 코드 예제에서는 새로운 집합이 대 한 디렉터리를 등록 하는 방법을 보여 줍니다는 **새 항목 추가** 대화 상자. 에 대 한 디렉터리는 **새 항목 추가** 대화 상자에서 각 프로젝트에 대 한 서로 다릅니다. 디렉터리에서 발견 하는 프로젝트 하위 키 아래에 등록 되며 따라서 \<HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\Projects >:  
  
## <a name="the-registry-script"></a>레지스트리 스크립트  
  
```  
NoRemove Projects  
{  
  NoRemove %GUID_Project%  
  {  
    NoRemove AddItemTemplates  
    {  
      NoRemove TemplateDirs  
      {  
        ForceRemove %CLSID_Package%  
        {  
      ForceRemove /1 = s '#%Folder_Label_ResID%'  
          {  
            val TemplatesDir = s '%Template_Path%'     
            val SortPriority = d 2000  
          }  
        }  
      }  
    }  
  }  
}  
```  
  
 Template_Path 값 프로젝트 템플릿이 포함 된 디렉터리의 전체 경로 지정 합니다. 이러한 템플릿은.vsz 파일 또는 정형화 된 템플릿 파일을 복제할 수 있습니다.  
  
 SortPriority 값 정렬 우선 순위를 지정합니다.  
  
## <a name="adding-items-to-an-existing-project"></a>기존 프로젝트에 항목 추가  
 기존 프로젝트에 항목을 추가할 수도 있습니다. 예를 들어는 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 프로젝트 항목을 추가할 수는 \<루트 > files\microsoft Visual Studio \VC#\CSharpProjectItems\LocalProjectItems 폴더입니다. 이 경우에 `%GUID_Project%` C# 프로젝트 ({FAE04EC0-301F-11D3-BF4B-00C04F79EFBC})에 대 한 GUID입니다.  
  
 또한 프로젝트 하위 형식 프로그래밍 하 여 기존 프로젝트를 확장할 수 있습니다. 프로젝트 하위 형식으로 새 프로젝트 형식을 작성 하지 않고도 프로젝트를 확장할 수 있습니다. 프로젝트 하위 형식에 대 한 자세한 내용은 참조 [프로젝트 하위 형식](../../extensibility/internals/project-subtypes.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)   
 [항목에 추가 된 새 항목 추가 대화 상자](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [새 프로젝트 대화 상자에 디렉터리 추가](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)