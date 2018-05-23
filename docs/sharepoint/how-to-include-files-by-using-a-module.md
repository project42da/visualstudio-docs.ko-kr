---
title: '방법: 모듈을 사용 하 여 파일 포함 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, modules
- modules [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: daea134298e84e7ddddf419da2124924fe9ef121
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
---
# <a name="how-to-include-files-by-using-a-module"></a>방법: 모듈을 사용하여 파일 포함
  *모듈* (으로 다름 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] 모듈)은 SharePoint에 ASPX 마스터 페이지 파일, 텍스트 파일 또는 이미지를 배포할 수 있도록 하는 컨테이너입니다.  
  
 문서 라이브러리 외부 문서 라이브러리 또는 일반 파일 (예: default.aspx)으로 파일을 배포 하려면 선택할 수 있습니다. 문서 라이브러리에 파일을 추가 하려면 지정 `Type="GhostableInLibrary"` 특성으로는 **파일** 요소입니다. 이 설정은 SharePoint 라이브러리에 추가 될 때 파일에는 목록 항목을 만드는 지시 합니다. 문서 라이브러리 외부 파일을 배포 하려면를 지정 하거나 `Type="Ghostable"` 생략 된 **형식** 특성입니다.  
  
## <a name="adding-a-module-to-a-sharepoint-solution"></a>SharePoint 솔루션에 모듈을 추가합니다.  
  
#### <a name="to-add-a-module"></a>모듈을 추가 하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint 프로젝트를 열거나 만듭니다.  
  
     자세한 내용은 참조 [SharePoint 프로젝트 및 프로젝트 항목 템플릿](../sharepoint/sharepoint-project-and-project-item-templates.md)합니다.  
  
2.  **솔루션 탐색기**, 프로젝트 노드를 선택한 다음 메뉴 모음에서 메뉴 **프로젝트**, **새 항목 추가**합니다.  
  
     **새 항목 추가** 대화 상자가 열립니다.  
  
3.  SharePoint 템플릿의 목록에서 선택 된 **모듈** 서식 파일을 선택한 후는 **추가** 단추 합니다.  
  
     이 단계에서는 프로젝트에서 Module1이라는 노드를 만듭니다.  
  
4.  Module1 아래에서 Sample.txt 파일을 삭제합니다.  
  
     Sample.txt 예를 들어 목적으로 모든 새 모듈에 포함 되 고 필요 하지 않습니다. (파일은 삭제도 제거 함을 항목 모듈의 Elements.xml 파일에서 note).  
  
5.  파일을 SharePoint에서 특정 폴더 구조에 배포 하려는 경우에 Module1 아래에서 해당 폴더를 만들어 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Module1 노드를 선택 하 여 선택한 다음 메뉴 모음 선택에서 **프로젝트**, **새로 만들기 폴더**합니다.  
  
6.  파일을 추가 하 고 다음 메뉴 모음에서 선택 하려는 폴더를 선택 **프로젝트**, **기존 항목 추가**합니다.  
  
7.  SharePoint에 배포 하 고 다음을 선택 하려는 하나 이상의 파일을 선택 된 **추가** 단추입니다.  
  
     파일을 프로젝트에 추가 하면에 대 한 항목이 자동으로 모듈의 Elements.xml 파일에 추가 됩니다. 프로젝트가 배포 되는 파일이에 의해 지정 되는 프로젝트의 루트 디렉터리에 상대적인 SharePoint 서버에 복사 됩니다는 **파일** 요소의 **Url** 와 같은 특성 `Url="Module1/New Folder/SomeFile.doc`합니다. 파일에 대 한 배포 위치를 변경 하려는 경우 하나을 다른 폴더로 이동에 **솔루션 탐색기** 변경 하거나 해당 **Url** 설정 합니다.  
  
8.  문서 라이브러리에 표시 하려는 모든 파일에 대 한 추가 `Type="GhostableInLibrary"` Elements.xml에 입력 되는 특성입니다. 예를 들어 개체에 적용된  
  
    ```xml  
    <File Path="Module1\Some Folder\SomePage.aspx" Url="Module1/Some Folder/SomePage.aspx" Type="GhostableInLibrary" />  
    ```  
  
9. 프로젝트를 배포 합니다.  
  
     파일은 SharePoint의 지정된 된 위치에 복사합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)   
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)  
  
  