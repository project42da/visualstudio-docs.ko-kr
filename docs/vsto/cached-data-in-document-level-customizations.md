---
title: "문서 수준 사용자 지정에서 캐시 된 데이터 | Microsoft Docs"
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
helpviewer_keywords:
- data islands [Office development in Visual Studio]
- view [Office development in Visual Studio]
- caching data [Office development in Visual Studio], about caching data
- data caching [Office development in Visual Studio], about data caching
- data [Office development in Visual Studio], cache
- data [Office development in Visual Studio], document-level solutions
- document-level customizations [Office development in Visual Studio], data model
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1fe9465c3f238941ace0d5b6fc438c7d5d93ec64
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="cached-data-in-document-level-customizations"></a>문서 수준 사용자 지정의 캐시된 데이터
  문서 수준 사용자 지정의 기본 목적은 Office 문서에서 보기에서 데이터를 분리 하는 것입니다. 데이터는 숫자와 텍스트를 포함 하는 문서에 저장 된 정보를 나타냅니다. 보기는 사용자 인터페이스 및 Microsoft Office Word 및 Microsoft Office Excel의 개체 모델을 가리킵니다.  
  
 Visual Studio의 문서 수준 사용자 지정 보기에서 데이터를로 포함할 수 있도록 하 여 데이터를 분리 한 *데이터 아일랜드*라고도 하는 *데이터 캐시*합니다. Word 또는 Excel을 시작 하지 않고 직접 데이터를 수정 하거나 읽을 수 있습니다. Microsoft Office가 설치 되지 않은 서버에 있는 문서의 데이터를 수정 해야 하는 경우에 유용 합니다. Word 및 Excel 클라이언트 환경;에 사용할 목적 서버에서 실행 되도록 설계 되지 않습니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 문서 수준 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 [Office 솔루션 개발 개요 &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md) 및 [문서 수준 사용자 지정 아키텍처](../vsto/architecture-of-document-level-customizations.md)합니다.  
  
## <a name="understanding-the-cached-data-programming-model"></a>캐시 된 데이터 프로그래밍 모델 이해  
 데이터 아일랜드는 특정 요구 사항을 충족 하는 솔루션의 모든 개체를 포함할 수 있습니다. 이러한 개체에는 <xref:System.Data.DataSet> 개체 <xref:System.Data.DataTable> 개체 및에서 serialize 할 수 있는 다른 모든 개체는 <xref:System.Xml.Serialization.XmlSerializer> 클래스입니다. 자세한 내용은 참조 하십시오. 참조 [데이터 캐싱](../vsto/caching-data.md)합니다.  
  
 캐시 된 데이터에 대 한 보기를 제공 하려면 Windows Forms 컨트롤을 바인딩할 수 있습니다 및 *호스트 컨트롤* 문서 데이터 아일랜드에 개체를 합니다. 데이터 아일랜드와 데이터 바인딩된 컨트롤 간의 데이터 바인딩은 동기화를 유지 합니다. 컨트롤에 종속 되는 데이터 유효성 검사 코드를 추가할 수도 있습니다. 자세한 내용은 참조 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)합니다.  
  
 호스트 컨트롤은 Excel 및 Word 개체 모델의 네이티브 개체의 버전을 확장 합니다. 네이티브 개체와 달리 호스트 컨트롤은 관리 되는 데이터 개체에 직접 바인딩할 수 있습니다. 자세한 내용은 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md) 및 [Windows Forms Controls on Office Documents Overview](../vsto/windows-forms-controls-on-office-documents-overview.md)를 참조하세요.  
  
## <a name="accessing-cached-data-on-the-server"></a>서버에서 캐시 된 데이터에 액세스  
 문서에서 캐시 된 데이터에 액세스 하려면 사용할 수 있습니다는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스입니다. 이 클래스는의 일부는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], 실행 중인 Excel 또는 Word 없이 서버에서 사용할 수 있습니다. 사용자가 열 때 문서에서 캐시 된 데이터를 수정 하 고 데이터에 바인딩된 모든 컨트롤의 변경 내용을 자동으로 동기화 됩니다 사용자가 업데이트 된 데이터로 표시 됩니다. 자세한 내용은 [Accessing Data in Documents on the Server](../vsto/accessing-data-in-documents-on-the-server.md)을 참조하세요.  
  
 Excel 및 Word 클라이언트에서 볼 수만 서버에 데이터를 쓰지 필요 하지 않습니다. Excel 및 Word도 않아도를 서버에 설치 됩니다. 데이터 아일랜드를 포함 하는 문서 빠르게 일괄 처리를 수행 하는 기능과 향상 된 확장성을 제공 합니다.  
  
## <a name="data-caching-for-offline-use"></a>데이터를 오프 라인 캐싱  
 오프 라인 시나리오를 지원 하 고 데이터 아일랜드에 데이터를 저장 합니다. 사용자는 먼저가 문서를 열거나 문서는 서버에서 요청을 하는 경우 데이터 아일랜드는 가장 최근의 데이터가 채워집니다. 데이터 아일랜드 문서에 캐시 및 오프 라인으로 표시 한 다음 됩니다. 사용자 (및 코드) 연결을 사용할 수 있더라도 데이터를 조작할 수 있습니다. 사용자는 다음 작업을 다시 연결 되 면 서버 데이터 소스에 다시 전파할 수 데이터를 변경 합니다.  
  
## <a name="cached-data-and-custom-xml-parts-compared"></a>캐시 된 데이터와 비교 하는 사용자 지정 XML 부분  
 사용자 지정 XML 부분을 문서에 임의의 XML 부분을 저장 하는 방법으로 2007 Microsoft Office system에서 도입 되었습니다. 사용자 지정 XML 부분 여러 데이터 캐시와 같은 시나리오에서 유용 하지만, 데이터 아일랜드와 사용자 지정 XML 부분 간의 차이가 있습니다. 사용자 지정 XML 부분에 대 한 자세한 내용은 참조 [사용자 지정 XML 부분 개요](../vsto/custom-xml-parts-overview.md)합니다.  
  
 다음 표에서 차이점 및 유사점 보여 줍니다.  
  
||데이터 캐시|사용자 지정 XML 부분|  
|-|----------------|----------------------|  
|Office 응용 프로그램에는 이러한 사용할 수 있습니까?|다음 응용 프로그램에 대 한 문서 수준 사용자 지정:<br /><br /> -Excel<br />단어|다음 응용 프로그램에 대 한 문서 수준 및 응용 프로그램 수준 솔루션:<br /><br /> -Excel<br />-PowerPoint<br />단어|  
|어떤 유형의 데이터를 저장할 수 있습니다?|특정 요구 사항을 충족 하는 사용자 지정 어셈블리의 모든 공용 개체입니다. 자세한 내용은 [Caching Data](../vsto/caching-data.md)을 참조하세요.|모든 XML 데이터입니다.|  
|Microsoft Office 응용 프로그램을 시작 하지 않고 데이터를 액세스할 수 있습니까?|사용 하 여 예,는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스에서 제공 되는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]합니다.|예,의 클래스를 사용 하 여는 <xref:System.IO.Packaging> 네임 스페이스 또는 Open XML 형식 SDK를 사용 하 여 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Office 솔루션의 데이터](../vsto/data-in-office-solutions.md)   
 [Visual Studio의 Office 솔루션 아키텍처](../vsto/architecture-of-office-solutions-in-visual-studio.md)  
  
  