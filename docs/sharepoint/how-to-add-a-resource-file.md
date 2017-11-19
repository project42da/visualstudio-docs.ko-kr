---
title: "방법: 리소스 파일 추가 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- resource files [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, resource files
ms.assetid: 2b4ac232-992e-4070-8e98-6f11eb88e1a8
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7233bc1a739bd3bf6544aad879f898bf3848ee7b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-resource-file"></a>방법: 리소스 파일 추가
  리소스 파일을 추가 하기 위한 명령을 솔루션 노드와 솔루션 탐색기에서 기능 노드의 바로 가기 메뉴입니다. 자세한 내용은 참조 [SharePoint 솔루션 지역화](../sharepoint/localizing-sharepoint-solutions.md)합니다.  
  
### <a name="to-add-a-global-resource-file-to-a-sharepoint-solution"></a>SharePoint 솔루션에 전역 리소스 파일을 추가 하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], SharePoint 솔루션을 엽니다.  
  
2.  **솔루션 탐색기**SharePoint 프로젝트 노드를 선택한 다음 메뉴 모음에서 메뉴 **프로젝트**, **새 항목 추가**합니다.  
  
3.  에 **새 항목 추가** 대화 상자에서 선택 하는 **전역 리소스 파일** 서식 파일을 선택한 후는 **추가** 단추입니다.  
  
    > [!NOTE]  
    >  전역 리소스 파일 프로젝트 항목 템플릿을 SharePoint 프로젝트 항목을 선택 하는 경우에 나타납니다.  
  
4.  에 **리소스 추가** 대화 상자에서 리소스 파일의 예: 영어 (미국) 문화권을 선택 합니다.  
  
     이 단계는 전역 리소스 파일 형식으로 리소스 솔루션에 추가*x***.** *문화권***.** resx Resource1.en US.resx 등입니다.  
  
5.  경우는 **리소스 편집기** 열립니다 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 리소스 파일에 리소스를 추가 합니다.  
  
### <a name="to-add-a-feature-resource-file-to-a-sharepoint-feature"></a>SharePoint 기능에 기능 리소스 파일을 추가 하려면  
  
1.  SharePoint 솔루션 이미에서 열려 있지 않으면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 솔루션을 엽니다.  
  
2.  **솔루션 탐색기**, 아래에 있는 기능이 이름에 대 한 바로 가기 메뉴를 열고는 **기능** 노드를 선택한 후 **기능 리소스 추가**합니다.  
  
     이 단계는 리소스 파일 형식으로의 기능으로 추가 *ResourceFileName***.** *문화권***.** resx Feature1.en US.resx 등입니다.  
  
3.  경우는 **리소스 편집기** 열립니다 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 리소스 파일에 리소스를 추가 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)  
  
  