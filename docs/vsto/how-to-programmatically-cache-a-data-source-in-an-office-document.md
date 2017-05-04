---
title: "방법: Office 문서에서 프로그래밍 방식으로 데이터 소스 캐싱 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "데이터[Visual Studio에서 Office 개발], 캐싱"
  - "데이터 캐싱[Visual Studio에서 Office 개발], 프로그래밍 방식으로"
  - "데이터 집합[Visual Studio에서 Office 개발], 캐싱"
  - "Office 응용 프로그램[Visual Studio에서 Office 개발], 데이터"
  - "StartCaching 메서드"
ms.assetid: 70b3fc06-7534-407e-898b-36f84e9a7516
caps.latest.revision: 43
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 43
---
# 방법: Office 문서에서 프로그래밍 방식으로 데이터 소스 캐싱
  <xref:Microsoft.Office.Tools.Word.Document>, <xref:Microsoft.Office.Tools.Excel.Workbook>, <xref:Microsoft.Office.Tools.Excel.Worksheet> 등과 같은 호스트 항목의 `StartCaching` 메서드를 호출하여 문서의 데이터 캐시에 데이터 개체를 프로그래밍 방식으로 추가할 수 있습니다.  호스트 항목의 `StopCaching` 메서드를 호출하여 데이터 캐시에서 데이터 개체를 제거할 수 있습니다.  
  
 `StartCaching` 메서드와 `StopCaching` 메서드 모두 전용 메서드이지만 IntelliSense에 표시됩니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 `StartCaching` 메서드를 사용하여 데이터 개체를 데이터 캐시에 추가하는 경우 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 특성을 사용하여 데이터 개체를 선언할 필요가 없습니다.  그러나, 데이터 캐시에 추가하려면 데이터 개체가 특정 요구 사항을 충족해야 합니다.  자세한 내용은 [데이터 캐싱](../vsto/caching-data.md)을 참조하십시오.  
  
### 데이터 개체를 프로그래밍 방식으로 캐시하려면  
  
1.  메서드 내부가 아니라 클래스 수준에서 데이터 개체를 선언합니다.  이 예제에서는 프로그래밍 방식으로 캐시하려는 `dataSet1`이라는 <xref:System.Data.DataSet>를 선언하는 것으로 가정합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#12](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#12)]
     [!code-vb[Trin_VstcoreDataExcel#12](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#12)]  
  
2.  데이터 개체를 인스턴스화한 다음 문서 또는 워크시트 인스턴스의 `StartCaching` 메서드를 호출하고 데이터 개체 이름을 전달합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#13](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#13)]
     [!code-vb[Trin_VstcoreDataExcel#13](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#13)]  
  
### 데이터 개체의 캐싱을 중지하려면  
  
1.  문서 또는 워크시트 인스턴스의 `StopCaching` 메서드를 호출하고 데이터 개체의 이름에 전달합니다.  이 예제에서는 캐싱을 중지하려는 `dataSet1`이라는 <xref:System.Data.DataSet>가 있다고 가정합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#14](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#14)]
     [!code-vb[Trin_VstcoreDataExcel#14](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#14)]  
  
    > [!NOTE]  
    >  문서 또는 워크시트의 `Shutdown` 이벤트에 대한 이벤트 처리기에서 `StopCaching`을 호출하지 마십시오.  `Shutdown` 이벤트가 발생하는 시점에서는 데이터 캐시를 수정하기에 이미 늦었기 때문입니다.  `Shutdown` 이벤트에 대한 자세한 내용은 [Office 프로젝트의 이벤트](../vsto/events-in-office-projects.md)를 참조하십시오.  
  
## 참고 항목  
 [데이터 캐싱](../vsto/caching-data.md)   
 [방법: 오프라인이나 서버에서 사용할 데이터 캐싱](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)   
 [방법: 암호로 보호된 문서의 데이터 캐시](../vsto/how-to-cache-data-in-a-password-protected-document.md)   
 [서버에 있는 문서의 데이터 액세스](../vsto/accessing-data-in-documents-on-the-server.md)   
 [데이터 저장](../data-tools/saving-data.md)  
  
  