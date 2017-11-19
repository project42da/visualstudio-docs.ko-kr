---
title: "방법: 오프 라인 상태가 되거나 서버에 사용 하기 위해 데이터를 캐시 | Microsoft Docs"
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
- data caching [Office development in Visual Studio], server use
- Office applications [Office development in Visual Studio], data
- datasets [Office development in Visual Studio], caching
- offline data [Office development in Visual Studio]
- data [Office development in Visual Studio], caching
- data caching [Office development in Visual Studio], offline use
ms.assetid: 6246b187-9413-4336-821d-2259b1adec5a
caps.latest.revision: "49"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7a8da60aa9d9dc3ab7becb56b3b4c7701494daef
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-cache-data-for-use-offline-or-on-a-server"></a>방법: 오프라인이나 서버에서 사용할 데이터 캐싱
  표시할 수 있습니다는 문서에 캐시 되어야 데이터 항목을 사용할 수 있도록 오프 라인입니다. 이 쉽게 처리할 수는 데이터에 대 한 문서에서 문서를 서버에 저장 될 때 다른 코드에 의해 조작 될를 합니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 데이터 항목을 캐시 하 여 사용자 코드에서 데이터 항목을 선언한 경우 또는 사용 하는 경우 표시할 수 있습니다는 <xref:System.Data.DataSet>에서 속성을 설정 하 여는 **속성** 창. 캐시 되지 않는 데이터 항목을 <xref:System.Data.DataSet> 또는 <xref:System.Data.DataTable>, 문서에 캐시 되 고 조건을 충족 하는지 확인 합니다. 자세한 내용은 [Caching Data](../vsto/caching-data.md)을 참조하세요.  
  
> [!NOTE]  
>  데이터 집합으로 표시 된 Visual Basic을 사용 하 여 만든 **Cached** 및 **WithEvents** (에서 끌어 데이터 집합을 포함 하는 **데이터 소스** 창이 나 **도구 상자** 있는 **CacheInDocument** 속성이로 설정 **True**)는 밑줄 캐시에 해당 이름 앞에 붙습니다. 예를 들어 데이터 집합을 만들고 이름을 **고객**, <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> 이름은 **_Customers** 캐시에 있습니다. 사용 하는 경우 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 지정 해야이 캐시 된 항목에 액세스 하려면 **_Customers** 대신 **고객**합니다.  
  
### <a name="to-cache-data-in-the-document-using-code"></a>코드를 사용 하 여 문서에 데이터를 캐시  
  
1.  공용 필드 또는 속성 데이터 항목에 대 한 프로젝트에서 호스트 항목 클래스의 멤버로 같이 선언는 `ThisDocumen`Word 프로젝트의 클래스 또는 `ThisWorkbook` Excel 프로젝트의 클래스.  
  
2.  적용 된 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 특성을 멤버 문서의 데이터 캐시에 저장할 데이터 항목을 표시 합니다. 에 대 한 필드 선언에이 특성을 적용 하는 다음 예제는 <xref:System.Data.DataSet>합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#11](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#11)]
     [!code-vb[Trin_VstcoreDataExcel#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#11)]  
  
3.  데이터 항목의 인스턴스를 만드는 코드를 추가 및 해당 데이터베이스에서 로드 하는 경우.  
  
     데이터 항목은 처음 만들어질; 때만 로드 그런 다음 문서와 함께 캐시를 유지 하 고 업데이트 하는 다른 코드를 작성 해야 합니다.  
  
### <a name="to-cache-a-dataset-in-the-document-by-using-the-properties-window"></a>속성 창을 사용 하 여 문서에서 데이터 집합을 캐시 하려면  
  
1.  데이터 집합을 사용 하 여 프로젝트에 데이터 소스를 추가 하 여 예를 들어 Visual Studio 디자이너 도구를 사용 하 여 프로젝트에 추가 된 **데이터 소스** 창.  
  
2.  않으면 아직 하나, 있고 디자이너에서 인스턴스를 선택 합니다. 데이터 집합의 인스턴스를 만듭니다.  
  
3.  에 **속성** 창에서 설정 된 **CacheInDocument** 속성을 **True**합니다.  
  
     자세한 내용은 참조 [Office 프로젝트의 속성](../vsto/properties-in-office-projects.md)합니다.  
  
4.  에 **속성** 창의 설정는 **한정자** 속성을 **공용** (것이 기본적으로 **내부**).  
  
## <a name="see-also"></a>참고 항목  
 [데이터 캐싱](../vsto/caching-data.md)   
 [방법: 프로그래밍 방식으로 Office 문서에 데이터 소스를 캐싱](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md)   
 [방법: 암호로 보호 된 문서에서 데이터를 캐시 합니다.](../vsto/how-to-cache-data-in-a-password-protected-document.md)   
 [서버에 있는 문서의 데이터 액세스](../vsto/accessing-data-in-documents-on-the-server.md)   
 [데이터 저장](/visualstudio/data-tools/saving-data)  
  
  