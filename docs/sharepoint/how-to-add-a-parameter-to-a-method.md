---
title: "방법: 메서드에 매개 변수 추가"
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
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "BDC[Visual Studio에서 SharePoint 개발], 메서드를 매개 변수에 추가"
  - "BDC[Visual Studio에서 SharePoint 개발], 메서드 매개 변수"
  - "BDC[Visual Studio에서 SharePoint 개발], 매개 변수"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 메서드를 매개 변수에 추가"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 메서드 매개 변수"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 매개 변수"
ms.assetid: c5b6fd32-bf85-4b2a-a01e-f9199f0fb26e
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 16
---
# 방법: 메서드에 매개 변수 추가
  매개 변수를 사용하여 메서드에 정보를 추가하거나 메서드에서 정보를 반환할 수 있습니다.  모든 메서드에는 매개 변수를 적어도 하나는 지정해야 합니다.  만들려는 메서드 형식을 지원하는 매개 변수를 디자인하는 방법에 대한 자세한 내용은 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)을 참조하십시오.  
  
 메서드에 매개 변수를 추가하면 프로젝트의 모델 파일 XML에 `<Parameter>` 요소가 추가됩니다.  `<Parameter>` 요소의 특성에 대한 자세한 내용은 [매개 변수](http://go.microsoft.com/fwlink/?LinkId=169284) 를 참조하십시오.  
  
### 메서드에 매개 변수를 추가하려면  
  
1.  엔터티에 메서드를 추가합니다.  
  
2.  선택 메뉴 모음에서 **보기**, **기타 창**, **BDC 메서드 세부 정보** 을 선택합니다.  
  
     **BDC 메서드 세부 정보** 창이 열립니다.  자세한 내용은 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)을 참조하십시오.  
  
3.  **BDC 메서드 세부 정보** 창에서 메서드 노드를 확장한 다음 **매개 변수** 노드를 확장합니다.  
  
4.  **매개 변수 추가** 목록에서 **매개 변수 만들기** 를 선택합니다.  
  
     **매개 변수** 노드 아래에 새 매개 변수가 표시됩니다.  
  
5.  메뉴 모음에서 **보기**, **속성 창**을 선택합니다.  
  
6.  **속성** 창에서 **Name** 속성이 적절한 이름으로 설정되어 있는지 확인합니다.  예를 들어 메서드에서 고객을 반환하는 경우 메서드 이름으로 GetCustomers를 지정합니다.  
  
7.  **BDC 메서드 세부 정보** 창에서 매개 변수 방향에 대해 표시되는 드롭다운 목록을 연 다음 **In**, **InOut**, **Out** 또는 **Return**을 선택합니다.  
  
     만들고 있는 형식 메서드에 대해 선택할 방향에 대한 자세한 내용은 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)를 참조하십시오.  
  
8.  매개 변수의 형식 설명자를 수정합니다.  자세한 내용은 [How to: Define the Type Descriptor of a Parameter](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)을 참조하십시오.  
  
## 참고 항목  
 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)   
 [방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md)   
 [How to: Define the Type Descriptor of a Parameter](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [방법: 메서드 인스턴스 정의](../sharepoint/how-to-define-a-method-instance.md)   
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
  