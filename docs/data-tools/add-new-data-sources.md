---
title: "데이터 소스 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.datasource.datasourcefieldspicker"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "데이터[Visual Studio], 데이터 소스"
  - "데이터 소스"
ms.assetid: ed28c625-bb89-4037-bfde-cfa435d182a2
caps.latest.revision: 56
caps.handback.revision: 41
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터 소스 개요
데이터 소스는 응용 프로그램에서 사용 가능한 데이터를 가리킵니다.  보다 구체적으로 설명하면 데이터 소스는 응용 프로그램에서 작업 대상이 되는 데이터를 나타냅니다.  데이터 소스는 데이터베이스\(로컬 데이터베이스 파일 포함\), 서비스 및 개체로부터 가져올 수 있습니다.  
  
 프로젝트에 추가한 데이터 소스는 **데이터 소스** 창에 표시됩니다.  대부분의 시나리오에서는 데이터 소스를 Windows Forms, WPF 및 Silverlight 디자이너로 끌어 와 내부 데이터에 바인딩되는 컨트롤을 만들 수 있습니다.  자세한 내용은 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)을 참조하십시오.  
  
 Visual Studio에서는 응용 프로그램에서 데이터 소스를 만들고 편집할 수 있도록 도구를 제공합니다.  Visual Studio 프로젝트의 데이터 소스는 내부 데이터 저장소에서 반환되는 개체에 따라 엔터티 데이터 모델, 데이터 집합, 서비스에서 반환되는 프록시 개체 또는 다른 개체 형식으로 표현됩니다.  
  
 데이터 소스는 **데이터 소스 구성 마법사**를 사용하여 만들고 편집합니다.  
  
## 데이터베이스로부터 만든 데이터 소스  
 **데이터 소스 구성 마법사**를 실행하고 **데이터베이스** 데이터 소스 형식을 선택하면 데이터베이스로부터 데이터 소스를 만들 수 있습니다.  자세한 내용은 [방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)을 참조하십시오.  
  
 데이터베이스로부터 데이터 소스를 만드는 경우 Visual Studio에서는 *데이터 모델*을 생성하여 프로젝트에 추가합니다.  데이터 모델은 데이터베이스의 내부 데이터에 대한 프로그래밍 가능하고 강력한 형식의 뷰입니다.  Visual Studio를 사용하면 다음 유형의 데이터 모델을 만들 수 있습니다.  
  
-   [엔터티 데이터 모델](../Topic/Entity%20Data%20Model.md)을 기반으로 하는 개념적 모델입니다.  이러한 형식의 모델은 Entity Framework 또는 WCF Data Services에서 사용할 수 있습니다.  자세한 내용은 [Entity Framework 개요](../Topic/Entity%20Framework%20Overview.md) 및 [WCF Data Services 4.5](../Topic/WCF%20Data%20Services%204.5.md)를 참조하십시오.  
  
-   형식화된 데이터 집합.  자세한 내용은 [Visual Studio에서 데이터 집합 작업](../data-tools/dataset-tools-in-visual-studio.md)을 참조하십시오.  
  
-   LINQ to SQL 클래스.  자세한 내용은 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)을 참조하십시오.  
  
    > [!NOTE]
    >  엔터티 데이터 모델 기반의 개념적 모델 및 데이터 집합과 달리 LINQ to SQL 클래스는 **데이터 소스 구성 마법사**를 사용하여 만들 수 없습니다.  이 클래스는 **데이터 소스** 창에 표시되지도 않으므로 디자이너로 끌어 와 데이터 바인딩된 컨트롤을 만들 수 없습니다.  그러나 LINQ to SQL 클래스에 기반하는 개체 데이터 소스는 만들 수 있고, 이 개체를 디자이너로 끌어 올 수 있습니다.  자세한 내용은 [방법: 테이블 및 뷰에 매핑된 LINQ to SQL 클래스 만들기\(O\/R 디자이너\)](../Topic/How%20to:%20Create%20LINQ%20to%20SQL%20classes%20mapped%20to%20tables%20and%20views%20\(O-R%20Designer\).md)을 참조하십시오.  
  
### 로컬 데이터베이스 파일로부터 만든 데이터 소스  
 Access 데이터베이스\(.mdb 파일\), SQL Server Express LocalDB 데이터베이스\(.mdf 파일\) 및 SQL Server Express 데이터베이스\(.mdf 파일\)와 같은 데이터베이스 파일로부터 데이터 소스를 만들 수도 있습니다.  이러한 데이터베이스 파일로부터 데이터 소스를 만들면 데이터베이스 파일을 직접 프로젝트에 추가할 수 있습니다.  자세한 내용은 다음 항목을 참조하십시오.  
  
-   [로컬 데이터 개요](../data-tools/local-data-overview.md)  
  
-   [방법: 프로젝트의 로컬 데이터 파일 관리](../data-tools/how-to-manage-local-data-files-in-your-project.md)  
  
## 서비스로부터 만든 데이터 소스  
 **데이터 소스 구성 마법사**를 실행하고 **서비스** 데이터 소스 형식을 선택하면 서비스로부터 데이터 소스를 만들 수 있습니다.  자세한 내용은 [방법: 서비스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-service.md)을 참조하십시오.  
  
 서비스로부터 데이터 소스를 만드는 경우 Visual Studio에서는 서비스 참조를 프로젝트에 추가합니다.  또한 Visual Studio에서는 해당 서비스에 의해 반환되는 개체에 대응하는 프록시 개체도 만듭니다.  예를 들어, 데이터 집합을 반환하는 서비스는 프로젝트에서 데이터 집합으로 표현되고, 특정 형식을 반환하는 서비스는 프로젝트에서 반환되는 형식으로 표현됩니다.  
  
 다음 유형의 서비스로부터 데이터 소스를 만들 수 있습니다.  
  
-   WCF 데이터 서비스.  자세한 내용은 [개요](../Topic/WCF%20Data%20Services%20Overview.md)을 참조하십시오.  
  
-   WCF\(Windows Communication Foundation\) 서비스.  자세한 내용은 [Windows Communication Foundation Services and WCF Data Services in Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)을 참조하십시오.  
  
-   웹 서비스.  자세한 내용은 [Not in Build: Introduction to Programming Web Services in Managed Code](http://msdn.microsoft.com/ko-kr/bd8861f3-39e1-4c06-995e-677e007eb961)을 참조하십시오.  
  
    > [!NOTE]
    >  **데이터 소스** 창에 표시되는 항목은 서비스에서 반환하는 데이터에 따라 달라집니다.  일부 서비스는 **데이터 소스 구성 마법사**가 바인딩할 수 있는 개체를 만드는 데 필요한 정보를 충분히 제공하지 않을 수도 있습니다.  예를 들어, 서비스에서 형식화되지 않은 데이터 집합을 반환하면 마법사가 완료될 때 **데이터 소스** 창에 아무런 항목도 표시되지 않습니다.  이는 형식화되지 않은 데이터 집합이 스키마를 제공하지 않아 마법사가 데이터 소스를 만드는 데 필요한 정보를 충분히 갖지 못하기 때문입니다.  
  
## 개체로부터 만든 데이터 소스  
 **데이터 소스 구성 마법사**를 실행하고 **개체** 데이터 소스 형식을 선택하면 public 속성을 하나 이상 노출하는 개체로부터 데이터 소스를 만들 수 있습니다.  개체의 public 속성은 **데이터 소스** 창에 표시됩니다.  자세한 내용은 [방법: 개체의 데이터에 연결](../Topic/How%20to:%20Connect%20to%20Data%20in%20Objects.md)을 참조하십시오.  
  
 개체 바인딩에 대한 자세한 내용은 [Visual Studio에서 개체 바인딩](../data-tools/bind-objects-in-visual-studio.md)을 참조하십시오.  
  
## SharePoint 목록으로부터 만든 데이터 소스  
 **데이터 소스 구성 마법사**를 실행하고 **SharePoint** 데이터 소스 형식을 선택하면 SharePoint 목록으로부터 데이터 소스를 만들 수 있습니다.  SharePoint는 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]를 통해 데이터를 노출하기 때문에 SharePoint 데이터 소스는 서비스로부터 데이터 소스를 만드는 경우와 동일하게 만들어집니다.  **데이터 소스 구성 마법사**에서 **SharePoint**를 선택하면 **서비스 참조 추가** 대화 상자가 열립니다. 이 대화 상자에서는 SharePoint 서버를 가리켜 SharePoint 데이터 서비스에 연결할 수 있습니다.  자세한 내용은 [방법: 서비스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-service.md)을 참조하십시오.  
  
## 참고 항목  
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)   
 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)   
 [Visual Studio의 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)