---
title: '방법: 프로젝트 출력 참조 추가 | Microsoft Docs'
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
- project output references [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, project output references
- SharePoint development in Visual Studio, advanced packaging tools
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8be3cd7576dcd42391c2f1bda1bd2d997ea958ac
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-a-project-output-reference"></a>방법: 프로젝트 출력 참조 추가
  비 SharePoint 프로젝트 어셈블리 (또는 Silverlight 프로젝트의.xap 파일) SharePoint를 배포 하려면 프로젝트 출력 참조로 추가 합니다.  
  
 이 프로세스는 두 프로젝트 간에 솔루션 빌드 종속성을 만듭니다. SharePoint 프로젝트 빌드 및 배포 하기 전에 프로젝트 출력 참조와 관련 된 프로젝트는 빌드됩니다.  
  
### <a name="to-add-a-project-output-reference"></a>프로젝트 출력 참조를 추가 하려면  
  
1.  하나 이상의 SharePoint 프로젝트 및 비 SharePoint 프로젝트가 두 개를 포함 하는 솔루션을 로드 합니다.  
  
2.  **솔루션 탐색기**을 SharePoint 프로젝트 노드에서 항목을 선택 합니다.  
  
3.  에 **속성** 창 선택는 **프로젝트 출력 참조** 속성을 선택한 후 줄임표 (![ASP.NET 모바일 디자이너 줄임표](../sharepoint/media/mwellipsis.gif "ASP 합니다. NET 모바일 디자이너 줄임표")) 단추를 클릭 합니다.  
  
4.  에 **프로젝트 출력 참조** 대화 상자에서 선택 하는 **추가** 단추입니다.  
  
5.  속성 창에 있는 화살표 옆에 선택는 **배포 유형을** 속성을 다음와 같은 참조 하는 비 SharePoint 항목에 대 한 적절 한 값을 선택 하 고 **ElementFile**합니다.  
  
6.  옆에 있는 화살표를 선택 **프로젝트 이름**비 SharePoint 프로젝트 항목의 이름을 선택한 다음 선택에서 **확인** 단추입니다.  
  
## <a name="see-also"></a>참고 항목  
 [패키지 및 프로젝트 항목에 대 한 배포 정보 제공](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [방법: 안전 컨트롤로 표시 제어](../sharepoint/how-to-mark-controls-as-safe-controls.md)   
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  