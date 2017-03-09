---
title: "옵션 대화 상자, 프로젝트 및 솔루션 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Projects and Solutions Options dialog box
- Options dialog box, Projects and Solutions
ms.assetid: 2801f24e-a138-488a-ae3c-e1f99a678ac0
caps.latest.revision: 12
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: 5c6c36ca969d5ca9ca3957a886ce45597159bc5c
ms.lasthandoff: 02/22/2017

---
# <a name="projects-and-solutions-options-dialog-box"></a>프로젝트 및 솔루션, 옵션 대화 상자
프로젝트를 개발 및 빌드할 때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로젝트 폴더의 기본 경로를 설정하고 **출력** 창, **작업 목록** 및 **솔루션 탐색기**의 기본 동작을 결정합니다. 이 대화 상자에 액세스하려면 **도구/옵션**을 클릭하고 **프로젝트 및 솔루션**을 확장한 후 **일반**을 클릭합니다.  
  
> [!NOTE]
>  대화 상자에서 사용할 수 있는 옵션과 메뉴 명령의 이름 및 위치는 실제 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 이 도움말 페이지는 **일반 개발 설정**을 염두에 두고 작성되었습니다. 설정을 보거나 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="settings"></a>설정  
 **프로젝트 위치**  
 새 프로젝트 및 솔루션 폴더와 디렉터리가 만들어지는 기본 위치를 설정합니다. 여러 대화 상자에서 이 옵션에 설정된 위치가 폴더 시작 지점으로 사용되기도 합니다. 예를 들어 프로젝트 열기 대화 상자에서는 내 프로젝트 바로 가기에 이 위치가 사용됩니다.  
  
 **사용자 프로젝트 템플릿 위치**  
 **새 프로젝트** 대화 상자에서 **내 템플릿** 목록을 만드는 데 사용하는 기본 위치를 설정합니다. 자세한 내용은 [방법: 템플릿 찾기 및 구성](../../ide/how-to-locate-and-organize-project-and-item-templates.md)을 참조하세요.  
  
 **사용자 항목 템플릿 위치**  
 **새 항목 추가** 대화 상자에서 **내 템플릿** 목록을 만드는 데 사용하는 기본 위치를 설정합니다. 자세한 내용은 [방법: 템플릿 찾기 및 구성](../../ide/how-to-locate-and-organize-project-and-item-templates.md)을 참조하세요.  
  
 **오류로 인해 빌드가 종료될 때 항상 오류 목록 표시**  
 프로젝트 빌드가 실패하는 경우에만 빌드 완료 시 **오류 목록** 창을 엽니다. 빌드 프로세스 중 발생하는 오류가 표시됩니다. 이 옵션을 선택 취소하면 오류는 계속 발생하지만 빌드 완료 시 창이 열리지 않습니다. 기본적으로 이 옵션은 사용하도록 설정됩니다.  
  
 **솔루션 탐색기에서 활성화된 항목 추적**  
 이 옵션을 선택하면 **솔루션 탐색기**가 자동으로 열리고 활성 항목이 선택됩니다. 선택한 항목은 프로젝트 또는 솔루션에서 다른 파일로 작업하거나 디자이너에서 다른 구성 요소로 작업하면 변경됩니다. 이 옵션을 선택 취소해도 **솔루션 탐색기**의 선택 항목이 자동으로 변경되지는 않습니다. 기본적으로 이 옵션은 사용하도록 설정됩니다.  
  
 **고급 빌드 구성 표시**  
 이 옵션을 선택하면 빌드 구성 옵션이 **프로젝트 속성 페이지** 대화 상자 및 **솔루션 속성 페이지** 대화 상자에 표시됩니다. 이 옵션을 선택 취소하면 구성 디버그 및 릴리스 하나 또는 두 개를 포함하는 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 및 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 프로젝트의 **프로젝트 속성 페이지** 대화 상자와 **솔루션 속성 페이지** 대화 상자에 빌드 구성 옵션이 나타나지 않습니다. 프로젝트에 사용자 정의 구성이 있으면 빌드 구성 옵션이 표시됩니다.  
  
 이 옵션을 선택 취소하면 **빌드** 메뉴의 명령(예: **솔루션 빌드**, **솔루션 다시 빌드** 및 **솔루션 지우기**)이 릴리스 구성에 대해 수행되고, **디버그** 메뉴의 명령(예: **디버깅 시작** 및 **디버깅하지 않고 시작**)이 디버그 구성에 대해 수행됩니다.  
  
 **솔루션 항상 표시**  
 이 옵션을 선택하면 솔루션과 솔루션에서 작동하는 모든 명령이 IDE에 항상 표시됩니다. 이 옵션을 선택 취소하면 모든 프로젝트가 독립 실행형 프로젝트로 만들어지고, 솔루션이 하나의 프로젝트만 포함하는 경우 IDE의 솔루션에서 작동하는 명령이나 솔루션 탐색기의 솔루션이 표시되지 않습니다.  
  
 **만들어질 때 새 프로젝트 저장**  
 이 옵션을 선택하면 **새 프로젝트** 대화 상자에 프로젝트의 위치를 지정할 수 있습니다. 이 옵션을 선택 취소하면 모든 새 프로젝트가 임시 프로젝트로 만들어집니다. 임시 프로젝트로 작업할 경우에는 디스크 위치를 지정하지 않아도 프로젝트를 만들고 사용할 수 있습니다.  
  
 **프로젝트 위치를 신뢰할 수 없을 때 사용자에게 경고**  
 완전히 신뢰할 수 없는 위치(예: UNC 경로 또는 HTTP 경로)에서 새 프로젝트를 만들거나 기존 프로젝트를 열려고 하면 메시지가 표시됩니다. 완전히 신뢰할 수 없는 위치에서 프로젝트를 만들거나 열려고 할 때마다 메시지를 표시할지 여부를 지정하려면 이 옵션을 사용합니다.  
  
 **빌드를 시작할 때 출력 창 표시**  
 솔루션 빌드 시작 시에 IDE에 출력 창이 자동으로 표시됩니다. 자세한 내용은 [방법: 출력 창 제어](http://msdn.microsoft.com/Library/91aebd15-8854-4a7a-9f7d-57376fb4e858)를 참조하세요. 기본적으로 이 옵션은 사용하도록 설정됩니다.  
  
 **파일 이름을 바꿀 때 기호화된 이름 바꾸기 확인**  
 이 옵션을 선택하면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에서 프로젝트에서 코드 요소에 대한 모든 참조 이름을 바꿀지 묻는 메시지 상자가 표시됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](../../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md)
