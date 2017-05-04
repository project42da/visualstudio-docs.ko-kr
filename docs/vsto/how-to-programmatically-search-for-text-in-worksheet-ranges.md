---
title: "방법: 프로그래밍 방식으로 워크시트 범위에서 텍스트 검색 | Microsoft Docs"
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
  - "텍스트[Visual Studio에서 Office 개발], 워크시트에서 검색"
  - "텍스트 검색, 워크시트"
  - "워크시트, 검색"
ms.assetid: a6902711-fefb-450a-a76b-b1446d11c423
caps.latest.revision: 48
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 47
---
# 방법: 프로그래밍 방식으로 워크시트 범위에서 텍스트 검색
  <xref:Microsoft.Office.Interop.Excel.Range> 개체의 <xref:Microsoft.Office.Interop.Excel.Range.Find%2A> 메서드를 사용하면 범위 내에서 텍스트를 검색할 수 있습니다.  이 텍스트는 `#NULL!` 또는 `#VALUE!`와 같이 워크시트 셀에 나타날 수 있는 오류 문자열일 수도 있습니다.  오류 문자열에 대한 자세한 내용은 [Cell Error Values](HV10038459)를 참조하십시오.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 다음 예제에서는 `Fruits`라는 범위를 검색하고 "apples"라는 단어가 포함된 셀의 글꼴을 수정합니다.  이 프로시저에서는 이전에 지정한 검색 설정을 사용하여 검색을 반복하는 <xref:Microsoft.Office.Interop.Excel.Range.FindNext%2A> 메서드도 사용합니다.  검색을 시작할 셀만 지정하면 나머지는 <xref:Microsoft.Office.Interop.Excel.Range.FindNext%2A> 메서드에 의해 자동으로 처리됩니다.  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Interop.Excel.Range.FindNext%2A> 메서드를 사용할 때 검색 범위의 끝에 도달하면 검색 범위의 시작 부분으로 돌아와 검색 작업이 이어집니다.  따라서 검색 작업이 무한 루프에 빠지지 않도록 코드를 작성해야 합니다.  다음 샘플 프로시저에서는 이 문제를 처리하기 위해 <xref:Microsoft.Office.Interop.Excel.Range.Address%2A> 속성을 사용하는 한 가지 방법을 보여 줍니다.  
  
 ![비디오에 링크](../vsto/media/playvideo.png "비디오에 링크") 관련 비디오 데모를 보려면 [How Do I: Use the Find Method in an Excel Add\-in?](http://go.microsoft.com/fwlink/?LinkID=130294)을 참조하십시오.  
  
### 워크시트 범위에서 텍스트를 검색하려면  
  
1.  전체 범위, 처음 찾은 범위 및 현재 찾은 범위를 추적하기 위한 변수를 선언합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#58](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#58)]
     [!code-vb[Trin_VstcoreExcelAutomation#58](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#58)]  
  
2.  검색을 시작할 셀을 제외한 모든 매개 변수를 지정하여 일치하는 첫 번째 범위를 검색합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#59](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#59)]
     [!code-vb[Trin_VstcoreExcelAutomation#59](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#59)]  
  
3.  값이 일치할 때까지 검색을 계속 진행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#60](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#60)]
     [!code-vb[Trin_VstcoreExcelAutomation#60](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#60)]  
  
4.  처음 찾은 범위\(`firstFind`\)를 **Nothing**과 비교합니다.  `firstFind`에 값이 없는 경우에는 찾은 범위\(`currentFind`\)가 저장됩니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#61](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#61)]
     [!code-vb[Trin_VstcoreExcelAutomation#61](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#61)]  
  
5.  찾은 범위의 주소가 처음 찾은 범위의 주소와 일치하면 루프가 종료됩니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#62](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#62)]
     [!code-vb[Trin_VstcoreExcelAutomation#62](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#62)]  
  
6.  찾은 범위의 모양을 설정합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#63](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#63)]
     [!code-vb[Trin_VstcoreExcelAutomation#63](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#63)]  
  
7.  다른 검색을 수행합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#64](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#64)]
     [!code-vb[Trin_VstcoreExcelAutomation#64](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#64)]  
  
 다음 예제에서는 전체 메서드를 보여 줍니다.  
  
## 예제  
 [!code-csharp[Trin_VstcoreExcelAutomation#57](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#57)]
 [!code-vb[Trin_VstcoreExcelAutomation#57](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#57)]  
  
## 참고 항목  
 [범위 작업](../vsto/working-with-ranges.md)   
 [방법: 프로그래밍 방식으로 통합 문서에서 일정 범위에 스타일 적용](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)   
 [방법: 프로그래밍 방식으로 코드에서 워크시트 범위 참조](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  