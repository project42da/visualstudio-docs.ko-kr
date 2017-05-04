---
title: "방법: 메서드 인스턴스 정의 | Microsoft Docs"
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
  - "BDC[Visual Studio에서 SharePoint 개발], 메서드"
  - "BDC[Visual Studio에서 SharePoint 개발], 메서드 인스턴스"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 메서드"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 메서드 인스턴스"
ms.assetid: f0c8a686-c0de-414e-8de9-f228f59d1eb3
caps.latest.revision: 14
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# 방법: 메서드 인스턴스 정의
  모델의 모든 메서드에 대해 적어도 하나의 메서드 인스턴스를 정의해야 합니다.  
  
 **BDC 메서드 세부 정보** 창에서 메서드 인스턴스를 추가합니다.  메서드 인스턴스를 추가하면 프로젝트의 모델 파일 XML에 `<MethodInstance>` 요소가 추가됩니다.  `<MethodInstance>` 요소의 특성에 대한 자세한 내용은 [MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282) 를 참조하십시오.  
  
### 메서드 인스턴스를 정의하려면  
  
1.  **BDC 메서드 세부 정보** 창에서 메서드 노드를 확장한 다음 **인스턴스** 노드를 확장합니다.  
  
2.  **메서드 인스턴스 추가** 목록에서 **Finder 인스턴스 만들기** 를 선택합니다.  
  
     **인스턴스** 노드 아래에 새 메서드 인스턴스가 표시됩니다.  
  
3.  메뉴 모음에서 **보기**, **속성 창** 을 선택합니다.  
  
4.  **속성** 창에서 메서드 인스턴스의 속성을 설정합니다.  각 속성에 대한 자세한 내용은 [MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282) 을 참조하십시오.  
  
## 참고 항목  
 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)   
 [방법: 모델에 엔터티 추가](../sharepoint/how-to-add-an-entity-to-a-model.md)   
 [방법: 메서드에 매개 변수 추가](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [How to: Define the Type Descriptor of a Parameter](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md)   
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)  
  
  