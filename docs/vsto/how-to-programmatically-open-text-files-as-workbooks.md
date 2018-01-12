---
title: "방법: 프로그래밍 방식으로 통합 문서로 텍스트 파일을 열기 | Microsoft Docs"
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
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 45d2b85ea8c005d56ddc076d0b758a0c9e4a2d67
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>방법: 프로그래밍 방식으로 통합 문서로 텍스트 파일 열기
  통합 문서로 텍스트 파일을 열 수 있습니다. 열 텍스트 파일 이름을 전달 해야 합니다. 시작에 대해 구문 분석 및 열에 대 한 형식의 데이터 파일에 있는 행 번호 등 여러 가지 선택적 매개 변수를 지정할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="example"></a>예  
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 구성 요소가 필요합니다.  
  
-   라는 이름의 쉼표로 구분 된 텍스트 파일이 `Test.txt` 세 개 이상의 줄의 텍스트를 포함 하 합니다.  
  
-   텍스트 파일 `Test.txt` C 드라이브에 저장할 수  
  
## <a name="see-also"></a>참고 항목  
 [통합 문서 사용](../vsto/working-with-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서 열기](../vsto/how-to-programmatically-open-workbooks.md)   
 [방법: 프로그래밍 방식으로 새 통합 문서 만들기](../vsto/how-to-programmatically-create-new-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서 저장](../vsto/how-to-programmatically-save-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서 닫기](../vsto/how-to-programmatically-close-workbooks.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  