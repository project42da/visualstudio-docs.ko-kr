---
title: "방법: 모델에 엔터티 추가 | Microsoft Docs"
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
  - "EntityTool"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "BDC[Visual Studio에서 SharePoint 개발], 엔터티 추가"
  - "BDC[Visual Studio에서 SharePoint 개발], 엔터티"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 엔터티 추가"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 엔터티"
ms.assetid: 139a6639-dabe-4e14-bb64-e5f4efb6f2fb
caps.latest.revision: 23
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 22
---
# 방법: 모델에 엔터티 추가
  엔터티를 만들려면, Visual Studio **도구 상자**의 엔터티 컨트롤을 BDC\(비즈니스 데이터 연결\) 디자이너에 추가합니다.  
  
### 모델에 엔터티를 추가하려면  
  
1.  BDC 프로젝트를 만들거나 기존 BDC 프로젝트를 엽니다.  자세한 내용은 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)을 참조하십시오.  
  
2.  **도구 상자**의 **BusinessDataCatalog** 그룹에서 **엔터티** 컨트롤을 디자이너에 추가합니다.  
  
     디자이너에 새 엔터티가 표시됩니다.  프로젝트의 BDC 모델 파일 XML에 `<Entity>` 요소가 추가됩니다.  엔터티 요소의 특성에 대한 자세한 내용은 [엔터티](http://go.microsoft.com/fwlink/?LinkId=169296) 를 참조하십시오.  
  
3.  디자이너에서, 엔터티의 바로 가기 메뉴를 열고 **추가** 를 선택한 다음 **식별자** 를 선택합니다.  
  
     새 식별자가 엔터티에 나타납니다.  
  
    > [!NOTE]  
    >  **속성** 창에서 엔터티 이름과 식별자를 변경할 수 있습니다.  
  
4.  클래스에 엔터티의 필드를 정의합니다.  프로젝트에 새 클래스를 추가하거나 O\/R 디자이너\(개체 관계형 디자이너\)와 같은 다른 도구를 사용하여 만든 기존 클래스를 사용할 수 있습니다.  다음 예제에서는 Contact라는 엔터티 클래스를 보여 줍니다.  
  
     [!code-csharp[SP_BDC_Entity_Data_Class#1](../snippets/csharp/VS_Snippets_OfficeSP/sp_bdc_entity_data_class/cs/bdcmodel1/contact.cs#1)]
     [!code-vb[SP_BDC_Entity_Data_Class#1](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_bdc_entity_data_class/vb/bdcmodel1/contact.vb#1)]  
  
## 참고 항목  
 [방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md)   
 [방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)   
 [방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)   
 [방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)   
 [방법: SpecificFinder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)  
  
  