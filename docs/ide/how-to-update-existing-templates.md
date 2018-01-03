---
title: "방법: 기존 템플릿 업데이트 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- item templates, updating existing templates
- Visual Studio templates, updating existing templates
- project templates, updating existing templates
ms.assetid: d585e45b-7fe2-45fa-9cf3-7f2bc060f3c4
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 28ae63c6dba9d352025d5c87d838772a81cf989d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-update-existing-templates"></a>방법: 기존 템플릿 업데이트
템플릿을 만들고 파일을 .zip 파일로 압축한 후 템플릿을 수정하려고 할 수 있습니다. 템플릿의 파일을 수동으로 변경하거나 해당 템플릿을 기반으로 하는 프로젝트에서 새 템플릿을 내보내는 방법으로 이 작업을 수행할 수 있습니다.  
  
## <a name="using-the-export-template-wizard-to-update-an-existing-template"></a>템플릿 내보내기 마법사를 사용하여 기존 템플릿 업데이트  
Visual Studio에서는 기존 템플릿을 업데이트하는 데 사용할 수 있는 **템플릿 내보내기** 마법사를 제공합니다.  
  
#### <a name="to-use-export-template-to-update-an-existing-template"></a>템플릿 내보내기를 사용하여 기존 템플릿을 업데이트하려면  
  
1.  **파일**, **새로 만들기**, **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.  
  
2.  업데이트할 템플릿을 선택하고 프로젝트의 이름과 위치를 입력한 다음 **확인**을 선택합니다.  
  
3.  Visual Studio에서 프로젝트를 수정합니다.  
  
4.  **프로젝트** 메뉴에서 **템플릿 내보내기**를 선택합니다.  

    **템플릿 내보내기 마법사**가 열립니다.  

5.  마법사에서 표시되는 메시지를 따라 템플릿을 .zip 파일로 내보냅니다.  

6.  이전 템플릿 .zip 파일을 삭제합니다.  
  
## <a name="manually-updating-an-existing-template"></a>기존 템플릿 수동 업데이트  
압축된 .zip 파일에 있는 파일을 수정하여 Visual Studio 외부에서 기존 템플릿을 업데이트할 수 있습니다.  
  
#### <a name="to-manually-update-an-existing-template"></a>기존 템플릿을 수동으로 업데이트하려면  
  
1.  템플릿을 포함하는 .zip 파일을 찾습니다. 기본적으로 이 파일은 %USERPROFILE%\Documents\Visual Studio \<version\>\My Exported Templates\.에 있습니다.  
  
2.  .zip 파일의 압축을 풉니다.  
  
3.  현재 템플릿 파일을 수정 또는 삭제하거나 템플릿에 새 파일을 추가합니다.  
  
4.  .vstemplate XML 파일을 열어서 수정한 다음 저장하여 업데이트된 동작 또는 새 파일을 처리합니다.  

    .vstemplate 스키마에 대한 자세한 내용은 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)를 참조하세요. 원본 파일에서 매개 변수화할 수 있는 항목에 대한 자세한 내용은 [템플릿 매개 변수](../ide/template-parameters.md)를 참조하세요.  
  
5.  템플릿에 있는 파일을 선택하고 마우스 오른쪽 단추를 클릭한 다음 **보내기** 및 **압축(ZIP) 폴더**를 선택합니다.  

    선택한 파일이 .zip 파일로 압축됩니다.  
  
6.  새 .zip 파일을 이전 .zip 파일과 같은 디렉터리에 넣습니다.  
  
7.  추출된 템플릿 파일과 이전 템플릿 .zip 파일을 삭제합니다.  
  
8.  개발자 명령 프롬프트의 승격된 인스턴스를 시작합니다.  

  1. 시작 메뉴에서 **Visual Studio \<버전\>**, **개발자 명령 프롬프트**로 이동합니다.  

  2. 상황에 맞는 메뉴(마우스 오른쪽 단추 클릭)에서 **자세히**, **관리자 권한으로 실행**을 선택합니다.  
  
9. `devenv /installvstemplates` 명령을 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
[템플릿 사용자 지정](../ide/customizing-project-and-item-templates.md)   
[프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)   
[Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
[템플릿 매개 변수](../ide/template-parameters.md)   
[방법: 시작 키트 만들기](../ide/how-to-create-starter-kits.md)