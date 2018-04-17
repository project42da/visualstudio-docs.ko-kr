---
title: '방법: 데이터베이스의 데이터로 문서 채우기 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents, populating with data
- data, adding to documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: bfbdb5b71a84ea2f3ab9a86cc2d2df33213e5a98
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-populate-documents-with-data-from-a-database"></a>방법: 데이터베이스의 데이터로 문서 채우기
  Windows Forms 프로젝트의 데이터에 액세스하는 것과 동일한 방식으로 Microsoft Office에 대한 문서 수준 프로젝트의 데이터에 액세스할 수 있습니다. 동일한 도구 및 코드를 사용하여 데이터베이스의 데이터를 솔루션으로 가져오며, Windows Forms 컨트롤을 사용하여 데이터를 표시할 수 있습니다.  
  
 또한 호스트 컨트롤을 사용하여 데이터를 표시할 수 있습니다. 호스트 컨트롤은 이벤트 및 데이터 바인딩 기능을 통해 향상된 Microsoft Office Word의 네이티브 개체입니다. 자세한 내용은 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)을 참조하십시오.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 다음 예제에서는 디자이너를 사용하여 문서 수준 프로젝트에 데이터 바인딩된 컨트롤을 추가하는 방법을 보여 줍니다. 런타임에 VSTO 추가 기능 프로젝트에서 데이터 바인딩된 컨트롤을 추가 하는 방법의 예제를 보려면 [연습: 단순 데이터 바인딩 vsto에서 추가 기능 프로젝트에서에서](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md)합니다.  
  
 ![비디오에 링크](../vsto/media/playvideo.gif "비디오에 링크") 관련된 동영상 데모를 참조 하십시오. [Word 2007 콘텐츠 컨트롤 사용 하 여 Visual Studio Tools for Office System (3.0)에 데이터 바인딩](http://go.microsoft.com/fwlink/?LinkId=136785)합니다.  
  
## <a name="adding-a-control-to-a-document-at-design-time"></a>디자인 타임에 문서에 컨트롤 추가  
  
#### <a name="to-populate-a-document-with-data-from-a-database"></a>데이터베이스의 데이터로 문서를 채우려면  
  
1.  디자이너에서 문서를 열고 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 Word 문서 수준 프로젝트를 엽니다.  
  
2.  열기는 **데이터 소스** 창 데이터베이스에서 데이터 소스를 만듭니다. 자세한 내용은 참조 [새 연결 추가](../data-tools/add-new-connections.md)합니다.  
  
3.  원하는 필드를 끌어는 **데이터 소스** 을 문서 창입니다.  
  
 콘텐츠 컨트롤이 문서에 추가됩니다. 콘텐츠 컨트롤의 형식은 선택한 필드의 데이터 형식에 따라 달라집니다. 자세한 내용은 [Content Controls](../vsto/content-controls.md)을 참조하세요.  
  
 데이터 필드를 선택 하 여 다른 컨트롤을 추가할 수는 **데이터 소스** 창과 한 다음 드롭다운 목록에서 다른 컨트롤을 선택 합니다.  
  
## <a name="objects-in-the-project"></a>프로젝트의 개체  
 컨트롤 외에도 다음과 같은 데이터 관련 개체가 프로젝트에 자동으로 추가됩니다.  
  
-   데이터베이스에서 연결된 데이터 테이블을 캡슐화하는 형식화된 데이터 집합. 자세한 내용은 참조 [Visual Studio의 데이터 집합 도구](/visualstudio/data-tools/dataset-tools-in-visual-studio)합니다.  
  
-   컨트롤을 형식화된 데이터 집합에 연결하는 <xref:System.Windows.Forms.BindingSource>. 자세한 내용은 [BindingSource Component Overview](/dotnet/framework/winforms/controls/bindingsource-component-overview)을 참조하세요.  
  
-   데이터베이스에 형식화 된 데이터 집합을 연결 하는 TableAdapter. 자세한 내용은 참조 [만들기 및 Tableadapter를 구성](../data-tools/create-and-configure-tableadapters.md)합니다.  
  
-   TableAdapterManager, 계층적 업데이트를 사용 하도록 설정 하려면 데이터 집합의 테이블 어댑터를 조정 하는 데 사용 됩니다. 자세한 내용은 참조 [계층적 업데이트](../data-tools/hierarchical-update.md) 및 [TableAdapterManager 참조](../data-tools/fill-datasets-by-using-tableadapters.md#tableadaptermanager-reference)합니다.  
  
 프로젝트를 실행하면 컨트롤이 데이터 소스의 첫 번째 레코드를 표시합니다. <xref:System.Windows.Forms.BindingSource>를 사용하여 사용자가 레코드를 스크롤할 수 있게 할 수 있습니다.  
  
#### <a name="to-scroll-through-the-records"></a>레코드를 스크롤하려면  
  
-   <xref:System.Windows.Forms.BindingSource.MoveNext%2A> 및 <xref:System.Windows.Forms.BindingSource.MovePrevious%2A>와 같은 <xref:System.Windows.Forms.BindingSource> 메서드를 사용합니다.  
  
 형식화 된 데이터 집합 및 데이터베이스에 업데이트를 보내는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 호스트 컨트롤의 데이터로 데이터 소스 업데이트](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [새 데이터 원본 추가](/visualstudio/data-tools/add-new-data-sources)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [방법: 개체의 데이터로 문서 채우기](../vsto/how-to-populate-documents-with-data-from-objects.md)   
 [방법: 호스트 컨트롤의 데이터로 데이터 소스를 업데이트 합니다.](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [Office 솔루션 개요에서 로컬 데이터베이스 파일을 사용 하 여](../vsto/using-local-database-files-in-office-solutions-overview.md)   
 [Windows Forms 응용 프로그램에서 데이터에 연결](/visualstudio/data-tools/connecting-to-data-in-windows-forms-applications)   
 [BindingSource 구성 요소 개요](/dotnet/framework/winforms/controls/bindingsource-component-overview)  
  
  