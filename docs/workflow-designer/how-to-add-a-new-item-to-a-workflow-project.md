---
title: "방법: 워크플로 프로젝트에 새 항목 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 5c6180ca-af10-4513-b0cb-7d478fd84eab
caps.latest.revision: "14"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: e2031f084b11f9879fd94f5d2e454e0966ed3787
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-new-item-to-a-workflow-project"></a>방법: 워크플로 프로젝트에 새 항목 추가
워크플로 프로젝트를 만든 후에는 워크플로 활동, 디자이너 및 다른 친숙한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 항목을 프로젝트에 추가할 수 있습니다.  
  
 다음 표에서는 워크플로 프로젝트에 추가할 수 있는 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 항목을 보여 줍니다.  
  
|이름|설명|  
|----------|-----------------|  
|동작|다른 활동으로 구성할 활동입니다. 선택할 때와 동일한 XAML 파일이 프로젝트에 추가이 항목을 선택 하 고 **활동 라이브러리** 새 프로젝트에 대 한 템플릿을 합니다. [!INCLUDE[crabout](../test/includes/crabout_md.md)]이 절차에 참조 [하는 방법: 활동 라이브러리 만들기](../workflow-designer/how-to-create-an-activity-library.md)합니다.|  
|활동 디자이너|활동의 디자인 타임 환경을 사용자 지정할 디자이너입니다. 선택할 때와 동일한 파일이 프로젝트에 추가이 항목을 선택 하 고 **활동 디자이너 라이브러리** 새 프로젝트에 대 한 템플릿을 합니다. [!INCLUDE[crabout](../test/includes/crabout_md.md)]이 절차에 참조 [하는 방법: 활동 디자이너 라이브러리 만들기](../workflow-designer/how-to-create-an-activity-designer-library.md)합니다.|  
|Code 활동|코드로 작성된 실행 논리가 포함된 활동입니다. <xref:System.Activities.CodeActivity.Execute%2A> 메서드의 재정의가 포함된 소스 코드 파일이 이미 생성되어 있습니다.|  
|WCF 워크플로 서비스|워크플로 활동을 사용하여 빌드된 [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] 서비스입니다. 선택할 때와 동일한 파일이 프로젝트에 추가이 항목을 선택 하 고 **WCF 워크플로 서비스 응용 프로그램** 새 프로젝트에 대 한 템플릿을 합니다. [!INCLUDE[crabout](../test/includes/crabout_md.md)]이 절차에 참조 [하는 방법: WCF 워크플로 서비스 응용 프로그램 만들기](../workflow-designer/how-to-create-a-wcf-workflow-service-application.md)합니다.|  
  
### <a name="to-add-a-new-item-to-a-workflow-project"></a>워크플로 프로젝트에 새 항목을 추가하려면  
  
1.  에 **프로젝트** 메뉴를 클릭 하 여 **새 항목 추가...** .  
  
     **새 항목 추가** 대화 상자가 열립니다.  
  
2.  에 **설치 된 템플릿** 창 선택 **워크플로** 그룹입니다.  
  
3.  네 항목 중 하나를 선택합니다. 앞의 표에 선택할 수 있는 항목이 나열되어 있습니다.  
  
4.  항목에 대 한 이름을 입력는 **이름** 상자 대화 상자의 맨 아래에 있습니다.  
  
5.  클릭 **추가** 를 현재 워크플로 프로젝트에 항목을 추가 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [워크플로 프로젝트 만들기](../workflow-designer/creating-a-workflow-project.md)