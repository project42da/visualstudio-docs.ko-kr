---
title: "URL 선택기 대화 상자 (Visual Studio에서 SharePoint 개발) | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.SharePointTools.VWD.URLPicker
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, URL picker
- SharePoint development in Visual Studio, designer
ms.assetid: 33f8f521-e1f8-4242-a580-8a4bd9cb5ddc
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c97bd5e6fb9ad320a9f353eaa67114931a0d1b54
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="url-picker-dialog-box-sharepoint-development-in-visual-studio"></a>URL 선택기 대화 상자(Visual Studio에서 SharePoint 개발)
  URL 선택기 대화 상자에서 프로젝트에 있거나 SharePoint를 실행하는 로컬 서버에 있는 마스터 페이지 파일 또는 이미지 파일과 같은 파일을 선택할 수 있습니다.  
  
 이 대화 상자는 속성을 설정하기 위해 파일을 선택하는 옵션이 있는 경우에 표시됩니다. 줄임표 단추를 선택 하 여이 대화 상자를 열 수 있습니다 (![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.gif "ASP.NET 모바일 디자이너 줄임표"))를 클릭 하 고 **속성** 창. 줄임표 단추도도 표시 IntelliSense 프롬프트 특정 특성에 값을 할당 하는 경우는 **소스** 디자이너의 뷰.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **프로젝트 폴더**  
 프로젝트 또는 SharePoint를 실행하는 로컬 서버에 정의된 폴더 목록을 표시합니다. 확장 단추를 선택하여 하위 폴더를 표시합니다.  
  
 확장은 **프로젝트** 노드를 프로젝트에 파일을 선택 합니다. 대화 상자에 선택 가능한 파일로 표시 프로젝트의 파일에에서는 다음 조건을 충족 해야 합니다.  
  
-   매핑된 폴더에 파일을 포함 되어야 합니다.  
  
-   파일은 솔루션 패키지에 추가 되어야 합니다.  
  
-   다른 프로젝트에서 파일을 찾을 수 없습니다.  
  
 이러한 조건을 충족 하지 않는 파일을 참조 하려는 경우 파일의 경로 수동으로 입력 해야 합니다.  
  
 확장의 **서버** 노드 SharePoint를 실행 하는 로컬 서버에 있는 파일을 선택할 수 있습니다. 이러한 파일 대화 상자에 선택 가능한 파일로 표시는 다음 조건을 충족 해야 합니다.  
  
-   파일을 다음 매핑된 폴더 중 하나에 있어야: **이미지**, **레이아웃**, 또는 **보려면**합니다.  
  
-   SharePoint 콘텐츠 데이터베이스에서 파일을 찾을 수 없습니다.  
  
 이러한 조건을 충족 하지 않는 파일을 참조 하려는 경우 파일의 경로 수동으로 입력 해야 합니다.  
  
 **폴더의 내용**  
 선택한 폴더에 있는 파일 목록을 표시합니다. 파일을 선택한 다음 선택에서 **확인** 단추를 호출한 프로세스에 선택 항목이 전송 하 고 대화 상자를 닫습니다.  
  
 **파일 형식**  
 수행하고 있는 작업에 적합한 파일 목록에서 선택할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 용 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)   
  
  