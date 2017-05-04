---
title: "BDC 모델 디자인 도구 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.SharePointTools.BDC.Method_Details"
  - "VS.SharePointTools.BDC.Explorer"
  - "VS.SharePointTools.BDC.Diagram"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "BDC[Visual Studio에서 SharePoint 개발], BDC 탐색기"
  - "BDC[Visual Studio에서 SharePoint 개발], 디자이너"
  - "BDC[Visual Studio에서 SharePoint 개발], 메서드 세부 정보"
  - "BDC[Visual Studio에서 SharePoint 개발], 시각적 도구"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], BDC 탐색기"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 디자이너"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 메서드 세부 정보"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 시각적 도구"
ms.assetid: dbd7b746-9e93-4ed4-a546-4a6f17a4725f
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 15
---
# BDC 모델 디자인 도구 개요
  BDC 디자이너, **BDC 메서드 세부 정보** 창 및 **BDC 탐색기**를 사용하여 BDC\(비즈니스 데이터 연결\) 모델을 디자인할 수 있습니다.  
  
 **BDC 탐색기**를 사용하여 모델을 찾아보거나 검색하고 형식 설명자를 정의할 수 있습니다.  
  
## BDC 디자이너  
 BDC 디자이너를 통해 모델에 엔터티를 정의하고 엔터티 간의 관계를 시각적으로 정렬할 수 있습니다.  BDC 디자이너를 사용하여 다음 작업을 수행합니다.  
  
-   모델에 엔터티를 추가합니다.  
  
-   모델에서 엔터티를 제거합니다.  
  
-   엔터티 간의 관계를 정의합니다.  
  
 BDC 디자이너를 열려면, 프로젝트의 모델 파일을 두 번 클릭 하거나 모델 파일에 대 한 바로 가기 메뉴를 선택한 후 **열기** 를 선택합니다.  **도구 상자** 의 **엔터티** 를 디자이너로 끌어오거나 복사하여 모델에 엔터티를 추가합니다.  두 엔터티 간에 관계를 만들려면 **도구 상자** 에서 **연결** 컨트롤을 선택하고 첫 번째 엔터티를 선택한 다음 두 번째 엔터티를 선택합니다.  
  
## BDC 메서드 세부 정보 창  
 **BDC 메서드 세부 정보** 창에서 메서드의 매개 변수, 인스턴스 및 필터 설명자를 정의할 수 있습니다.  
  
 **BDC 메서드 세부 정보** 창에서 Finder, SpecificFinder, Creator, Updater 및 Deleter 메서드를 빠르게 생성할 수 있습니다.  이러한 메서드를 생성하면 매개 변수, 인스턴스, 형식 설명자 등의 메타데이터가 메서드에 추가됩니다.  특정 시나리오에 맞게 이 메타데이터를 수정할 수 있습니다.  
  
 **BDC 메서드 세부 정보** 창을 열려면, 메뉴 표시줄에서 **보기** , **다른 창**, **BDC 메서드 세부 정보** 를 차례대로 선택합니다.  
  
 **BDC 메서드 세부 정보** 창에서 메서드를 보려면 BDC 디자이너에서 엔터티를 선택합니다.  그러면 선택한 엔터티의 메서드가 **BDC 메서드 세부 정보** 창에 표시됩니다.  BDC 디자이너에서 엔터티를 선택하지 않으면 **BDC 메서드 세부 정보** 창에 정보가 표시되지 않습니다.  
  
 매개 변수, 인스턴스 및 필터 설명자를 정의하려면 **BDC 메서드 세부 정보** 창에서 노드를 확장하거나 축소합니다.  **BDC 탐색기**를 사용하여 형식 설명자를 정의합니다.  
  
## BDC 탐색기  
 **BDC 탐색기**에는 모델을 구성하는 요소가 표시됩니다.  **BDC 탐색기** 를 열려면, 메뉴 표시줄에서 **보기**, **다른 창**, **BDC 탐색기** 를 차례대로 선택합니다.  모델을 찾아보려면 **BDC 탐색기**에서 노드를 확장합니다.  각 노드는 모델 파일의 XML에 있는 요소를 나타냅니다.  
  
 **BDC 탐색기**에서 노드를 선택하면 **속성** 창에 선택한 노드의 속성이 표시됩니다.  이러한 속성 중 대부분은 모델 파일의 특성에 해당합니다.  **BDC 탐색기** 위쪽에 있는 검색 상자를 사용하여 모델을 검색할 수 있습니다.  
  
> [!NOTE]  
>  식별자, 사용자 지정 속성, 지역화된 문자열, 연결 그룹, 작업, 필터 설명자, 작업 제어 목록 및 기본 매개 변수 값은 **BDC 탐색기**에 표시되지 않습니다.  
  
### 형식 설명자 정의  
 **BDC 탐색기**를 사용하여 형식 설명자를 정의합니다.  BDC 탐색기를 통해 형식 설명자를 한 번 정의하면 모델의 다른 곳에서 해당 형식 설명자를 다시 사용할 수 있습니다.  이 작업을 수행하려면 형식 설명자를 복사하여 다른 매개 변수나 형식 설명자에 붙여넣으면 됩니다.  
  
> [!NOTE]  
>  원래 형식 설명자를 변경해도 해당 형식 설명자의 복사본은 변경되지 않습니다.  
  
 자세한 내용은 [How to: Define the Type Descriptor of a Parameter](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)을 참조하십시오.  
  
## 참고 항목  
 [방법: BDC 모델 만들기](../sharepoint/how-to-create-a-bdc-model.md)   
 [방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md)   
 [방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)   
 [방법: SpecificFinder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md)   
 [방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)   
 [방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)   
 [엔터티 간 연결 만들기](../sharepoint/creating-an-association-between-entities.md)   
 [연습: 비즈니스 데이터를 사용하여 SharePoint에 외부 목록 만들기](../sharepoint/walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data.md)   
 [SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)   
 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
  