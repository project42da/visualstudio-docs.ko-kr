---
title: "방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기 | Microsoft Docs"
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
  - "사용자 지정 리본, XML"
  - "리본 메뉴 사용자 지정, XML"
  - "리본 메뉴 내보내기"
  - "리본[Visual Studio에서 Office 개발], 내보내기"
  - "리본[Visual Studio에서 Office 개발], XML"
  - "리본 디자이너[Visual Studio에서 Office 개발]"
  - "XML[Visual Studio에서 Office 개발], 리본 메뉴"
ms.assetid: 96e0e9ed-4392-4f45-ac33-b6f7c22ea321
caps.latest.revision: 37
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 33
---
# 방법: 리본 디자이너에서 리본 XML로 리본 메뉴 내보내기
  **리본\(비주얼 디자이너\)** 항목은 가능한 모든 유형의 리본 사용자 지정을 지원하지는 않습니다.  고급 방식으로 리본 메뉴를 사용자 지정하려면 디자이너의 리본 메뉴를 리본 XML로 내보내고 XML을 직접 편집합니다.  
  
> [!NOTE]  
>  일부 속성 값은 리본 XML 파일에 나타나지 않습니다.  자세한 내용은 [리본 개요](../vsto/ribbon-overview.md)을 참조하십시오.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### 리본 디자이너에서 리본 XML로 리본 메뉴를 내보내려면  
  
1.  **솔루션 탐색기**에서 리본 코드 파일을 마우스 오른쪽 단추로 클릭한 다음 **디자이너 보기**를 클릭합니다.  
  
2.  리본 디자이너를 마우스 오른쪽 단추로 클릭한 다음 **XML로 리본 내보내기**를 클릭합니다.  
  
     Visual Studio에서 프로젝트에 리본 XML 파일 및 리본 XML 코드 파일이 추가됩니다.  
  
3.  리본 코드 클래스에서 `TODO:`로 시작하는 주석을 찾습니다.  
  
4.  개발하는 솔루션 형식에 따라 **ThisAddin**, **ThisWorkbook** 또는 **ThisDocument** 클래스에 이러한 주석의 코드 블록을 복사합니다.  
  
     Microsoft Office 응용 프로그램에서는 이 코드를 통해 사용자 지정 리본 메뉴를 찾아 로드합니다.  자세한 내용은 [리본 XML](../vsto/ribbon-xml.md)을 참조하십시오.  
  
5.  **ThisAddin**, **ThisWorkbook** 또는 **ThisDocument** 클래스에서 코드 블록의 주석 처리를 제거합니다.  
  
     주석 처리가 제거된 코드는 다음 예제와 비슷해야 합니다.  이 예제에서 리본 클래스는 `MyRibbon`입니다.  
  
     [!code-csharp[Trin_Ribbon_Custom_Tab_XML#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Ribbon_Custom_Tab_XML/CS/ThisAddIn.cs#1)]
     [!code-vb[Trin_Ribbon_Custom_Tab_XML#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Ribbon_Custom_Tab_XML/VB/ThisAddIn.vb#1)]  
  
6.  리본 XML 코드 파일로 전환하고 `Ribbon Callbacks` 영역을 찾습니다.  
  
     이 영역에서 단추 클릭과 같은 사용자 동작을 처리하는 콜백 메서드를 작성해야 합니다.  
  
7.  리본 디자이너 코드에 작성한 각 이벤트 처리기에 대한 콜백 메서드를 만듭니다.  
  
8.  이벤트 처리기의 이벤트 처리기 코드를 모두 콜백 메서드로 이동하고 리본 확장성\(RibbonX\) 프로그래밍 모델에 사용할 수 있도록 코드를 수정합니다.  
  
     콜백 메서드 작성 및 RibbonX 프로그래밍 모델 사용에 대한 자세한 내용은 [리본 XML](../vsto/ribbon-xml.md)을 참조하십시오.  
  
## 참고 항목  
 [리본 개요](../vsto/ribbon-overview.md)   
 [리본 디자이너](../vsto/ribbon-designer.md)   
 [리본 XML](../vsto/ribbon-xml.md)   
 [연습: 리본 디자이너를 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [연습: 리본 XML을 사용하여 사용자 지정 탭 만들기](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  