---
title: "방법: 모델에 엔터티 추가 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EntityTool
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], entity
- Business Data Connectivity service [SharePoint development in Visual Studio], adding an entity
- Business Data Connectivity service [SharePoint development in Visual Studio], entity
- BDC [SharePoint development in Visual Studio], adding an entity
ms.assetid: 139a6639-dabe-4e14-bb64-e5f4efb6f2fb
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d8cc1bf4871ef91c5b08cb77963a70e422ee3cdc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-an-entity-to-a-model"></a>방법: 모델에 엔터티 추가
  엔터티를 만들려면 Visual Studio에서 엔터티 컨트롤을 추가 **도구 상자** BDC 비즈니스 데이터 연결 () 디자이너에 끌어 합니다.  
  
### <a name="to-add-an-entity-to-the-model"></a>모델에 엔터티를 추가 하려면  
  
1.  BDC 프로젝트를 만들거나 기존 BDC 프로젝트를 엽니다. 자세한 내용은 참조 [비즈니스 데이터 연결 모델을 만드는](../sharepoint/creating-a-business-data-connectivity-model.md)합니다.  
  
2.  에 **도구 상자**에서 **BusinessDataCatalog** 그룹에서 추가 된 **엔터티** 컨트롤을 디자이너로 합니다.  
  
     새 엔터티 디자이너에 표시 됩니다. Visual Studio 추가 `<Entity>` 프로젝트에서 BDC 모델 파일의 xml 요소입니다. 엔터티 요소는 특성에 대 한 자세한 내용은 참조 [엔터티](http://go.microsoft.com/fwlink/?LinkId=169296)합니다.  
  
3.  디자이너에서 엔터티에 대 한 바로 가기 메뉴를 열고 **추가**를 선택한 후 **식별자**합니다.  
  
     새 식별자는 항목에 나타납니다.  
  
    > [!NOTE]  
    >  엔터티 및에서 식별자의 이름을 변경할 수 있습니다는 **속성** 창.  
  
4.  클래스에서 엔터티의 필드를 정의 합니다. 프로젝트에 새 클래스를 추가 하거나 개체 관계형 디자이너 (O/R 디자이너)와 같은 다른 도구를 사용 하 여 만든 기존 클래스를 사용 합니다. 다음 예에서는 라는 연락처 엔터티 클래스를 보여 줍니다.  
  
     [!code-csharp[SP_BDC_Entity_Data_Class#1](../sharepoint/codesnippet/CSharp/sp_bdc_entity_data_class/bdcmodel1/contact.cs#1)]
     [!code-vb[SP_BDC_Entity_Data_Class#1](../sharepoint/codesnippet/VisualBasic/sp_bdc_entity_data_class/bdcmodel1/contact.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md)   
 [방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)   
 [방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)   
 [방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)   
 [방법: SpecificFinder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)  
  
  