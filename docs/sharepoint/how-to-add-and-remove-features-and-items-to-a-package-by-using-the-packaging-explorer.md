---
title: "방법: 패키징 탐색기를 사용 하 여 패키지에 기능과 항목을 제거 하 고 추가 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.SharePointTools.RAD.PackagingExplorer
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords: SharePoint development in Visual Studio, packages
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 25a2514f2d25661de2898be8d2ef9ff051cc5559
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-and-remove-features-and-items-to-a-package-by-using-the-packaging-explorer"></a>방법: 패키징 탐색기를 사용하여 패키지에 기능과 항목 추가 및 제거
  SharePoint 항목 및 기능을 배포 하는 패키지를 구성 하려면 패키징 탐색기를 사용할 수 있습니다. .Wsp 파일 내 SharePoint 프로젝트 항목 및 기능을 조정할 수 있습니다.  
  
 또는 보고 기능 활성화 순서를 변경 하려면 순서를 변경 하는 패키지 디자이너를 사용할 수 있습니다. 자세한 내용은 참조 [하는 방법: 패키지 디자이너를 사용 하 여 패키지에 기능과 항목을 제거 하 고 추가](../sharepoint/how-to-add-and-remove-features-and-items-to-a-package-by-using-the-package-designer.md)합니다.  
  
## <a name="opening-the-packaging-explorer"></a>패키징 탐색기 열기  
 Visual Studio 솔루션에 하나 이상의 SharePoint 프로젝트가 경우 패키징 탐색기를 열려면 다음 절차를 사용할 수 있습니다. 또는 패키징 탐색기를 자동으로 열립니다 기능이 나 패키지 디자이너를 볼 때. 모든 기능 및 패키지 디자이너를 닫은 후 패키징 탐색기를 닫습니다.  
  
#### <a name="to-open-the-packaging-explorer"></a>패키징 탐색기를 열려면  
  
1.  메뉴 모음에서 **보기**, **다른 창**, **패키징 탐색기**합니다.  
  
     **패키징 탐색기** 에 표시 된 **도구 상자**합니다.  
  
## <a name="adding-a-feature-to-a-package"></a>패키지에 기능 추가  
 패키징 탐색기를 사용 하 여 패키지에 기존 및 새 기능을 추가할 수 있습니다.  
  
#### <a name="to-add-a-sharepoint-feature"></a>SharePoint 기능을 추가 하려면  
  
1.  열기는 **패키징 탐색기**를 프로젝트에 대 한 바로 가기 메뉴를 열고 다음 선택 **기능 추가**합니다.  
  
#### <a name="to-move-an-existing-sharepoint-feature"></a>기존 SharePoint 기능을 이동 하려면  
  
1.  열기는 **패키징 탐색기**, 다음 단계 중 하나를 수행 합니다.  
  
    -   끌어서는 **기능** 한 프로젝트를 다른 프로젝트에서.  
  
    -   기능에 대 한 바로 가기 메뉴를 열고 **잘라내기**, 기능을 이동한 다음 선택 프로젝트에 대 한 바로 가기 메뉴를 열고 **붙여넣기**합니다.  
  
    > [!NOTE]  
    >  솔루션에 SharePoint 프로젝트가 두 개 이상 있는 경우 이 절차를 사용합니다.  
  
## <a name="validating-a-feature-or-package"></a>기능 또는 패키지 유효성 검사  
 파일을 확인 하 여 SharePoint 기능 및 패키지의 잠재적 문제를 식별할 수 있습니다. 경고 및 오류 출력 창 및 오류 목록 창에 표시 됩니다.  
  
#### <a name="to-validate-a-sharepoint-feature-or-package"></a>SharePoint 기능 또는 패키지의 유효성을 검사 하려면  
  
1.  열기는 **패키징 탐색기**합니다.  
  
2.  기능 또는 패키지에 대 한 바로 가기 메뉴를 열고 **유효성 검사**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  