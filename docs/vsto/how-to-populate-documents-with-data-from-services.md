---
title: '방법: 서비스의 데이터로 문서 채우기 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], populating with data
- Web services [Office development in Visual Studio], populating documents
- data [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7d2d042e5ca30d8aea7fc152c457b380c7c7f4f2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-populate-documents-with-data-from-services"></a>방법: 서비스의 데이터로 문서 채우기
  Windows Forms 프로젝트에서와 동일한 방식으로 Microsoft Office에 대한 문서 수준 프로젝트에서 데이터 액세스가 작동합니다. 동일한 도구 및 코드를 사용하여 데이터를 솔루션으로 가져오며, Windows Forms 컨트롤을 사용하여 데이터를 표시할 수도 있습니다. 또한 이벤트 및 데이터 바인딩 기능을 통해 향상된 Microsoft Office Excel 및 Microsoft Office Word에서 네이티브 개체인 호스트 컨트롤이라는 컨트롤을 활용할 수 있습니다. 자세한 내용은 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)을 참조하십시오.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 다음 예제에서는 디자인 타임에 문서에 데이터 바인딩된 컨트롤을 추가하는 방법을 보여 줍니다. 런타임에 VSTO 추가 기능에서 데이터 바인딩된 컨트롤을 추가 하는 방법의 예제를 보려면 [연습: VSTO의 서비스에서 데이터 바인딩 추가 기능 프로젝트에서에서](../vsto/walkthrough-binding-to-data-from-a-service-in-a-vsto-add-in-project.md)합니다.  
  
 ![비디오에 링크](../vsto/media/playvideo.gif "비디오에 링크") 관련된 동영상 데모를 참조 하십시오. [어떻게 Microsoft Excel에서 웹 서비스와 상호 작용 i: 할까요?](http://go.microsoft.com/fwlink/?LinkID=130284)합니다.  
  
### <a name="to-populate-a-document-level-project-with-data-from-a-web-service"></a>문서 수준 프로젝트를 웹 서비스의 데이터로 채우려면  
  
1.  **데이터 원본** 창을 열고 프로젝트에 대한 서비스 데이터 원본을 만듭니다. 자세한 내용은 [새 데이터 소스 추가](/visualstudio/data-tools/add-new-data-sources)를 참조하세요.  
  
2.  **데이터 원본** 창에서 원하는 테이블 또는 필드를 문서로 끌어옵니다.  
  
     문서에 컨트롤이 만들어지고 프로젝트의 개체 클래스에 바인딩된 <xref:System.Windows.Forms.BindingSource> 가 만들어지며 서비스에 대해 클래스가 생성됩니다.  
  
3.  1단계에서 연결된 웹 서비스 클래스의 인스턴스를 코드에 만듭니다.  
  
4.  웹 서비스와의 통신에 필요한 속성이 있는 경우 해당 속성의 인스턴스를 만듭니다.  
  
5.  4단계에서 만든 웹 서비스 및 모든 속성 인스턴스에서 노출된 메서드를 사용하여 데이터 요청을 만들어 보냅니다.  
  
     사용하는 메서드는 웹 서비스의 제공 항목에 따라 다릅니다.  
  
6.  웹 서비스의 데이터 응답을 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 의 <xref:System.Windows.Forms.BindingSource>속성에 할당합니다.  
  
 프로젝트를 실행하면 컨트롤이 데이터 원본 첫 번째 레코드를 표시합니다. <xref:System.Windows.Forms.BindingSource>의 개체를 사용하여 통화 이벤트를 처리하여 레코드를 스크롤하게 할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [새 데이터 원본 추가](/visualstudio/data-tools/add-new-data-sources)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [방법: 데이터베이스의 데이터로 워크시트 채우기](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [방법: 개체의 데이터로 문서 채우기](../vsto/how-to-populate-documents-with-data-from-objects.md)   
 [방법: 데이터베이스의 데이터로 문서 채우기](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [방법: 호스트 컨트롤의 데이터로 데이터 원본 업데이트](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)  
  
  