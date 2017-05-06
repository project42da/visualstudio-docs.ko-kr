---
title: "방법: Creator 메서드 추가"
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
  - "BDC[Visual Studio에서 SharePoint 개발], 엔터티 추가"
  - "BDC[Visual Studio에서 SharePoint 개발], 엔터티 인스턴스 추가"
  - "BDC[Visual Studio에서 SharePoint 개발], Creator"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 엔터티 추가"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 엔터티 인스턴스 추가"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], Creator"
ms.assetid: 52f0382f-10a0-4a51-83fe-6f22f4647df8
caps.latest.revision: 30
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 29
---
# 방법: Creator 메서드 추가
  Creator 메서드는 엔터티의 데이터 소스에 새 데이터를 추가합니다.  사용자가 모델 기반 목록의 리본에서 **새 항목** 단추를 선택하면 BDC\(비즈니스 데이터 연결\) 서비스에서 이 메서드를 호출합니다.  자세한 내용은 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)을 참조하십시오.  
  
### Creator 메서드를 추가하려면  
  
1.  BDC 디자이너에서 엔터티를 선택합니다.  
  
2.  선택 메뉴 모음에서 **보기**, **기타 창**, **BDC 메서드 세부 정보** 을 선택합니다.  
  
     **BDC 메서드 세부 정보** 창이 열립니다.  이 창에 대한 자세한 내용은 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)를 참조하십시오.  
  
3.  **메서드 추가** 목록에서 **Creator 메서드 만들기** 를 선택합니다.  
  
     Visual Studio는 모델에 다음 요소들을 추가하고, 이러한 요소들은 **BDC 메서드 세부 정보** 창에 표시됩니다.  
  
    -   **Create** 메서드  
  
    -   메서드의 입력 매개 변수  
  
    -   메서드의 반환 매개 변수  
  
    -   매개 변수들에 대한 형식 설명자.  
  
    -   메서드의 메서드 인스턴스  
  
     자세한 내용은 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)을 참조하십시오.  
  
4.  **솔루션 탐색기**에서 엔터티에 대해 생성된 서비스 코드 파일의 바로가기를 연 다음 **코드 보기**를 선택합니다.  
  
     코드 편집기에서 엔터티 서비스 코드 파일이 열립니다.  엔터티 서비스 코드 파일에 대한 자세한 내용은 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)를 참조하십시오.  
  
5.  데이터 소스에 데이터를 추가하는 코드를 Creator 메서드에 추가합니다.  다음 예제에서는 SQL Server의 AdventureWorks 샘플 데이터베이스에 연락처를 추가합니다.  
  
    > [!NOTE]  
    >  `ServerName` 필드의 값을 서버 이름으로 바꿉니다.  
  
     [!code-csharp[SP_BDC#4](../snippets/csharp/VS_Snippets_OfficeSP/sp_bdc/CS/bdcmodel1/contactservice.cs#4)]
     [!code-vb[SP_BDC#4](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_bdc/VB/bdcmodel1/contactservice.vb#4)]  
  
## 참고 항목  
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [방법: Finder 메서드 추가](../sharepoint/how-to-add-a-finder-method.md)   
 [방법: SpecificFinder 메서드 추가](../sharepoint/how-to-add-a-specific-finder-method.md)   
 [방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)   
 [방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)   
 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)   
 [방법: 메서드에 매개 변수 추가](../sharepoint/how-to-add-a-parameter-to-a-method.md)   
 [방법: 메서드 인스턴스 정의](../sharepoint/how-to-define-a-method-instance.md)  
  
  