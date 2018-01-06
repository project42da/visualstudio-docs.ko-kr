---
title: "방법: Office 문서에서 데이터 원본을 프로그래밍 방식으로 캐시 | Microsoft Docs"
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
- Office applications [Office development in Visual Studio], data
- datasets [Office development in Visual Studio], caching
- StartCaching method
- data caching [Office development in Visual Studio], programmatically
- data [Office development in Visual Studio], caching
ms.assetid: 70b3fc06-7534-407e-898b-36f84e9a7516
caps.latest.revision: "43"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: e117243afff5cfa73cd7a27ad8ce0230d8fd512a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-cache-a-data-source-in-an-office-document"></a>방법: Office 문서에서 프로그래밍 방식으로 데이터 소스 캐싱
  호출 하 여 문서에서 데이터 캐시에 데이터 개체를 프로그래밍 방식으로 추가할 수 있습니다는 `StartCaching` 와 같은 메서드는 호스트의 항목을 한 <xref:Microsoft.Office.Tools.Word.Document>, <xref:Microsoft.Office.Tools.Excel.Workbook>, 또는 <xref:Microsoft.Office.Tools.Excel.Worksheet>합니다. 데이터 개체를 호출 하 여 데이터 캐시에서 제거 된 `StopCaching` 메서드 호스트 항목의 합니다.  
  
 `StartCaching` 메서드 및 `StopCaching` 메서드는 private, 모두 있지만 IntelliSense에 표시 됩니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 사용 하는 경우는 `StartCaching` 데이터 개체 데이터 캐시에 데이터 개체를 추가 하는 방법을 사용 하 여 선언 하지 않아도 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 특성입니다. 그러나 데이터 개체를 데이터 캐시에 추가할 특정 요구 사항을 충족 해야 합니다. 자세한 내용은 [Caching Data](../vsto/caching-data.md)을 참조하세요.  
  
### <a name="to-programmatically-cache-a-data-object"></a>프로그래밍 방식으로 데이터 개체를 캐시 하려면  
  
1.  메서드에 포함 되지 않은 클래스 수준에서 데이터 개체를 선언 합니다. 이 예에서는 가정 선언 하는 한 <xref:System.Data.DataSet> 라는 `dataSet1` 를 프로그래밍 방식으로 캐시 합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#12](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#12)]
     [!code-vb[Trin_VstcoreDataExcel#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#12)]  
  
2.  데이터 개체를 인스턴스화하고 다음 호출에서 `StartCaching` 하는 문서 또는 워크시트 인스턴스 및 데이터 개체의 이름을 전달 합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#13](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#13)]
     [!code-vb[Trin_VstcoreDataExcel#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#13)]  
  
### <a name="to-stop-caching-a-data-object"></a>데이터 개체를 캐시를 중지 하려면  
  
1.  호출 된 `StopCaching` 하는 문서 또는 워크시트 인스턴스 및 데이터 개체의 이름을 전달 합니다. 이 예에서는 있다고 가정는 <xref:System.Data.DataSet> 라는 `dataSet1` 캐싱을 중지 하려는 합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#14](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#14)]
     [!code-vb[Trin_VstcoreDataExcel#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#14)]  
  
    > [!NOTE]  
    >  호출 하지 마십시오 `StopCaching` 에 대 한 이벤트 처리기에서는 `Shutdown` 문서 또는 워크시트의 이벤트입니다. 시간순으로는 `Shutdown` 이벤트가 발생 하면 데이터 캐시를 수정 하기에 너무 늦었습니다. 에 대 한 자세한 내용은 `Shutdown` 이벤트 참조 [Office 프로젝트의 이벤트](../vsto/events-in-office-projects.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 캐싱](../vsto/caching-data.md)   
 [방법: 오프 라인 상태가 되거나 서버에 사용할 데이터 캐싱](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)   
 [방법: 암호로 보호 된 문서에서 데이터를 캐시 합니다.](../vsto/how-to-cache-data-in-a-password-protected-document.md)   
 [서버에 있는 문서의 데이터 액세스](../vsto/accessing-data-in-documents-on-the-server.md)   
 [데이터 저장](/visualstudio/data-tools/saving-data)  
  
  