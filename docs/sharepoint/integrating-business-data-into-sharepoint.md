---
title: "SharePoint에 비즈니스 데이터 통합 | Microsoft Docs"
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
  - "BDC[Visual Studio에서 SharePoint 개발], 데이터 집계"
  - "BDC[Visual Studio에서 SharePoint 개발], 비즈니스 데이터"
  - "BDC[Visual Studio에서 SharePoint 개발], 모델 만들기"
  - "BDC[Visual Studio에서 SharePoint 개발], 데이터"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 데이터 집계"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 비즈니스 데이터"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 모델 만들기"
  - "비즈니스 데이터 연결 서비스[Visual Studio에서 SharePoint 개발], 데이터"
ms.assetid: e092e3d6-2c5f-4060-ae86-d37db8967559
caps.latest.revision: 19
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 18
---
# SharePoint에 비즈니스 데이터 통합
  SharePoint에 비즈니스 데이터를 통합할 수 있습니다.  비즈니스 데이터는 [!INCLUDE[TLA#tla_sqlsvr](../sharepoint/includes/tlasharptla-sqlsvr-md.md)], Siebel, SAP, 웹 서비스 등의 백 엔드 서버 응용 프로그램을 통해 제공될 수 있습니다.  사용자는 외부 목록을 사용하거나 SharePoint의 비즈니스 데이터 웹 파트를 사용하여 비즈니스 데이터를 보거나 추가, 업데이트 또는 삭제할 수 있습니다. 사용자는 Microsoft Outlook 등의 Microsoft Office 응용 프로그램에서 오프라인으로 이 데이터에 액세스할 수도 있습니다.  자세한 내용은 [외부 데이터를 표시할수 있는 곳은?](http://go.microsoft.com/fwlink/?LinkId=169295) 을 참조하십시오.  
  
 SharePoint에 데이터를 통합하려면 BDC\(비즈니스 데이터 연결\) 서비스의 모델을 만듭니다.  BDC 서비스는 데이터 정보를 비즈니스 응용 프로그램에 저장하는 SharePoint의 한 응용 프로그램입니다.  자세한 내용은 [비지니스 데이터 연결 \(BDC\) 서비스](http://go.microsoft.com/fwlink/?LinkID=169276) 을 참조하십시오.  
  
## Visual Studio의 모델  
 Visual Studio의 모델을 사용하면 사용자 지정 코드를 작성하여 백 엔드 데이터 소스에서 데이터를 검색하고 업데이트할 수 있습니다.  여러 데이터 소스의 데이터를 집계할 수도 있습니다.  예를 들어 [!INCLUDE[ssNoVersion](../sharepoint/includes/ssnoversion-md.md)] 데이터베이스와 웹 서비스의 데이터가 포함된 고객 목록을 표시할 수 있습니다.  
  
 SharePoint에 이미 배포된 모델을 가져올 수도 있습니다.  모델을 가져온 후 사용자 지정 코드를 추가하거나, Visual Studio를 사용하여 모델을 패키징하고 여러 SharePoint 서버 팜에 배포할 수 있습니다.  자세한 내용은 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)을 참조하십시오.  
  
## Visual Studio에서 모델 디자인  
 디자이너와 여러 도구 창을 사용하여 모델을 디자인할 수 있습니다.  모델을 디자인하면 Visual Studio에서 모델 XML을 생성합니다.  자세한 내용은 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)을 참조하십시오.  
  
 모델에는 엔터티와 메서드가 포함됩니다.  
  
### 엔터티  
 엔터티는 필드 컬렉션을 설명합니다.  예를 들어 엔터티는 데이터베이스의 테이블을 나타낼 수 있습니다.  엔터티는 SharePoint에 외부 콘텐츠 형식으로 표시됩니다.  외부 콘텐츠 형식에 대한 자세한 내용은 [외부 콘텐츠 형식 이란?](http://go.microsoft.com/fwlink/?LinkId=169293) 을 참조하십시오.  
  
### 메서드  
 메서드를 사용하면 외부 콘텐츠 형식의 사용자가 엔터티의 필드에 대해 작업을 수행할 수 있습니다.  예를 들어 Updater 메서드를 사용하면 사용자가 고객의 주소와 생년월일을 변경할 수 있습니다. 여기서 `Address` 및 `BirthDate`는 `Customer` 엔터티의 필드입니다.  
  
 Visual Studio에서는 모델의 각 엔터티에 대해 서비스 코드 파일을 생성합니다.  모델에 메서드를 추가하면 Visual Studio에서 서비스 코드 파일에 해당 메서드를 생성합니다.  적절한 작업을 수행하는 코드를 각 메서드에 추가합니다.  예를 들어 모델에 Creator 메서드를 추가하면 Visual Studio에서 서비스 코드 파일에 Creator 메서드를 생성합니다.  이 메서드는 사용자가 모델을 기반으로 하는 목록에서 **새 항목** 단추를 클릭할 때 BDC 서비스에서 호출됩니다.  따라서 데이터 소스에 새 데이터를 추가하는 코드를 Creator 메서드에 추가합니다.  자세한 내용은 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)을 참조하십시오.  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)|새 모델을 만들거나 SharePoint에서 내보낸 모델을 가져오는 방법을 보여 줍니다.|  
|[비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)|Visual Studio 디자인 도구를 사용하여 모델의 요소를 디자인하는 방법에 대해 설명합니다.|  
|[BCS를 사용하여 솔루션을 만들 때, SharePoint Designer 와 Visual Studio 중 사용해야 하는 경우는?](http://go.microsoft.com/fwlink/?LinkID=183448)|BDC의 모델을 만들기 위해 Visual Studio를 사용할지, 아니면 SharePoint Designer를 사용할지를 결정하는 데 도움이 됩니다.|  
  
  