---
title: "방법: 프로그래밍 방식으로 통합 문서로 텍스트 파일 열기"
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
  - "텍스트[Visual Studio에서 Office 개발], 텍스트 파일"
  - "텍스트 파일, 통합 문서로 열기"
  - "통합 문서, 텍스트 파일 열기"
ms.assetid: 056ae3d0-7fe7-4c28-a2a5-5a948baee0e6
caps.latest.revision: 47
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 46
---
# 방법: 프로그래밍 방식으로 통합 문서로 텍스트 파일 열기
  텍스트 파일을 통합 문서로 열 수 있습니다.  열고자 하는 텍스트 파일의 이름을 전달해야 합니다.  구문 분석을 시작할 행 번호나 파일의 데이터에 대한 열 형식 등과 같은 여러 가지 선택적 매개 변수를 지정할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## 예제  
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#80)]  
  
## 코드 컴파일  
 이 예제를 실행하려면 다음 구성 요소가 준비되어 있어야 합니다.  
  
-   적어도 세 줄의 텍스트가 포함된 `Test.txt`라는 쉼표로 구분된 텍스트 파일이 있어야 합니다.  
  
-   `Test.txt` 텍스트 파일이 C 드라이브에 저장되어 있어야 합니다.  
  
## 참고 항목  
 [통합 문서 사용](../vsto/working-with-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서 열기](../vsto/how-to-programmatically-open-workbooks.md)   
 [방법: 프로그래밍 방식으로 새 통합 문서 만들기](../vsto/how-to-programmatically-create-new-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서 저장](../vsto/how-to-programmatically-save-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서 닫기](../vsto/how-to-programmatically-close-workbooks.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  