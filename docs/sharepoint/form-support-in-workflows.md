---
title: 워크플로에서 지원 구성 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, workflows
- workflows [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7214a472eff3b9181362932828f3ffee2f4fbe48
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767399"
---
# <a name="form-support-in-workflows"></a>워크플로의 폼 지원
  폼의 네 가지 유형의 워크플로에서 사용할 수 있습니다: 연결, 시작, 작업 및 수정 합니다. 이러한 양식 형식은 ASPX 양식 또는 InfoPath 양식 기반 될 수 있습니다. 이 수준을 지원 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 특정 폼은 다음 표에 설명 되어 있는 여러 가지 요인에 따라 결정을 제공 합니다. 워크플로 폼 형식에 대 한 자세한 내용은 참조 [워크플로 Forms 개요](http://go.microsoft.com/fwlink/?LinkId=185228) MSDN 웹 사이트에 있습니다.  
  
## <a name="xml-refactoring"></a>XML 리팩터링
 ASPX 연결 또는 시작 폼을 추가 하는 경우는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 워크플로 프로젝트 항목 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 자동으로 동기화는 연결 또는 시작 폼을 참조 하는 특성을 유지 하려면 워크플로 Elements.xml 파일에서 XML을 리팩터링 형식 이름이 나 배포 경로가 업데이트 될 때마다 또는 폼 삭제 됩니다. 그러나 다른 양식 형식을 사용 하 여 태스크 또는 수정 양식과 같은 워크플로에서 Elements.xml 파일 리팩터링 되지 않습니다.  
  
## <a name="form-support-in-new-visual-studio-workflows"></a>새 Visual Studio 워크플로의 폼 지원
 다음 표에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에서 만든 워크플로에서 ASPX 또는 InfoPath 양식에서 다양 한 폼 형식에 대 한 지원을 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
|양식 유형|ASPX 양식으로 Visual Studio에서 만든 워크플로|InfoPath 양식을 사용 하 여 Visual Studio에서 만든 워크플로|  
|---------------|---------------------------------------------------------|-----------------------------------------------------------------|  
|형식 연결|-를 사용 하 여 워크플로에 ASPX 연결 폼을 추가할 수 있습니다는 **워크플로 연결 양식** 항목 템플릿을 합니다.<br />폼 추가, 변경, 되거나 삭제 되거나 배포 경로가 변경 될 때 워크플로의-Elements.xml 파일 리팩터링 되었습니다.<br />-자세한 내용은 참조 [연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)합니다.|-InfoPath 연결 양식 템플릿이 없는에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.<br />-간 통합이 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 및 InfoPath 디자이너입니다.<br />-워크플로 Elements.xml 파일 리팩터링 되지 않습니다.|  
|시작|-를 사용 하 여 워크플로에 ASPX 초기화 폼을 추가할 수 있습니다는 **워크플로 시작 양식** 항목 템플릿을 합니다.<br />폼 추가, 변경, 되거나 삭제 되거나 배포 경로가 변경 될 때 워크플로의-Elements.xml 파일 리팩터링 되었습니다.<br />-자세한 내용은 참조 [연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)합니다.|-InfoPath 연결 양식 템플릿이 없는에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.<br />-간 통합이 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 및 InfoPath 디자이너입니다.<br />-워크플로 Elements.xml 파일 리팩터링 되지 않습니다.|  
|작업|-ASPX 작업 양식 서식 파일은 영어로 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. 응용 프로그램 페이지를 만들고 코드를 추가 해야 합니다.<br />-워크플로 Elements.xml 파일 리팩터링 되지 않습니다.<br />-자세한 내용은 참조 [워크플로 작업 양식 (SharePoint Foundation)](http://go.microsoft.com/fwlink/?LinkId=187674)|-InfoPath 작업 양식 템플릿이 없는에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.<br />-간 통합이 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 및 InfoPath 디자이너입니다.<br />-워크플로 Elements.xml 파일 리팩터링 되지 않습니다.|  
|수정|-ASPX 수정 양식 서식 파일은 영어로 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. 수정 양식을 추가 하려면 응용 프로그램 페이지를 만들고 코드를 추가 합니다.<br />-워크플로 Elements.xml 파일 리팩터링 되지 않습니다. 수동으로 적절 하 게 편집 해야 합니다.<br />-자세한 내용은 참조 [워크플로 수정 양식 (SharePoint Foundation)](http://go.microsoft.com/fwlink/?LinkId=187675)|-InfoPath 수정 양식 템플릿이 없는에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.<br />-간 통합이 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 및 InfoPath 디자이너입니다.<br />-워크플로 Elements.xml 파일 리팩터링 되지 않습니다.|  
  
## <a name="form-support-in-imported-sharepoint-reusable-workflows"></a>가져온된 SharePoint 다시 사용할 수 있는 워크플로의 폼 지원
 다음 표에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에 가져오는 SharePoint 재사용 가능한 워크플로에서 ASPX 또는 InfoPath 양식에 다양 한 폼 형식에 대 한 지원을 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
|양식 유형|SharePoint Designer에서 가져온 ASPX 양식은 있는 재사용 가능한 워크플로|SharePoint Designer에서 가져온 InfoPath 양식에 있는 재사용 가능한 워크플로|  
|---------------|-------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|  
|형식 연결|-폼 워크플로의 Elements.xml 파일에서 참조 됩니다.<br />폼이 변경 되거나 삭제 되거나 배포 경로가 변경 될 때 워크플로의-Elements.xml 파일 리팩터링 되었습니다.|-폼은 가져왔지만 워크플로의 Elements.xml 에서도 참조 되지 않습니다.<br />-워크플로 Elements.xml 파일 리팩터링 되지 않습니다.|  
|시작|-폼 워크플로의 Elements.xml 파일에서 워크플로 통해 참조 됩니다.<br />폼이 변경 되거나 삭제 되거나 배포 경로가 변경 될 때 워크플로의-Elements.xml 파일 리팩터링 되었습니다.|-폼은 가져왔지만 워크플로의 Elements.xml 에서도 참조 되지 않습니다.<br />-워크플로 Elements.xml 파일 리팩터링 되지 않습니다. **참고:** 규칙 및 속성 추가 하 고 해야이 시나리오에서 실행 되도록 변경 합니다.|  
|작업|-폼 워크플로의 Elements.xml 파일에서 참조 됩니다.<br />-워크플로 Elements.xml 파일 리팩터링 되지 않습니다.|-폼은 가져왔지만 워크플로의 Elements.xml 에서도 참조 되지 않습니다.<br />-워크플로 Elements.xml 파일 리팩터링 되지 않습니다. **참고:** 규칙 및 속성 추가 하 고 해야이 시나리오에서 실행 되도록 변경 합니다.|  
|수정|해당 사항 없음. ASPX 수정 양식 SharePoint Designer에서 만들 수 없습니다.|해당 사항 없음. InfoPath 수정 양식 기본 제공 SharePoint 서버 워크플로 워크플로 내보낼 때.wsp 파일에 포함 되지 않습니다는 제외 하 고 SharePoint Designer에서 만들 수 없습니다.|  
  
## <a name="see-also"></a>참고자료
 [연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)   
 [SharePoint 워크플로 솔루션 만들기](../sharepoint/creating-sharepoint-workflow-solutions.md)   
 [기존 SharePoint 사이트에서 항목 가져오기](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)  
  
  
