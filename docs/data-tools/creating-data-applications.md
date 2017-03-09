---
title: "데이터 응용 프로그램 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "응용 프로그램[Visual Studio], 데이터"
  - "데이터[Visual Studio]"
  - "데이터[Visual Studio], 응용 프로그램 만들기"
  - "데이터 액세스[Visual Studio], 응용 프로그램 만들기"
ms.assetid: ab334d5f-4f49-4346-bce0-3325d6130b3e
caps.latest.revision: 41
caps.handback.revision: 41
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 데이터 응용 프로그램 만들기
Visual Studio는 데이터에 액세스하는 응용 프로그램을 만드는 과정을 돕는 많은 디자인 타임 도구를 제공합니다.  여기서는 데이터 작업을 하는 응용 프로그램 작성과 관련된 기본 프로세스를 간략하게 살펴봅니다.  이 정보는 자세한 내용을 다루지 않으며 데이터 응용 프로그램의 작성과 관련된 일반적인 정보를 제공하고 이와 관련된 여러 도움말 페이지로 연결되는 링크를 제공하도록 구성되었습니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 데이터에 액세스하는 응용 프로그램을 개발할 때의 요구 사항은 경우에 따라 다릅니다.  단순히 폼에 데이터를 표시해야 할 경우가 있으며  다른 응용 프로그램 또는 프로세스와 정보를 공유하는 방법을 찾아야 할 경우도 있습니다.  
  
 데이터로 수행하는 작업이 어떤 것이든, 몇 가지 기본 개념은 이해하고 있어야 합니다.  데이터 처리의 세부 사항에 대해서 모두 알 필요는 없습니다. 예를 들어, 프로그래밍 방식으로 데이터베이스를 만드는 방법은 알 필요가 없을 수 있지만 기본적인 데이터 개념 및 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 사용할 수 있는 데이터 도구\(마법사와 디자이너\)에 대해 이해하고 있으면 큰 도움이 됩니다.  
  
 일반적인 데이터 응용 프로그램에서는 다음 다이어그램에 표시된 프로세스를 대부분 사용합니다.  
  
 ![데이터 주기 그래픽](../data-tools/media/datacyclegraphicinfo.gif "datacyclegraphicinfo")  
데이터 주기  
  
 응용 프로그램을 작성할 때는 어떤 작업을 완료하고자 하는지 생각하십시오.  다음 단원은 사용 가능한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 도구 및 개체를 찾는 데 도움이 됩니다.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]는 이전 다이어그램에 표시되는 몇 가지 프로세스를 단순화하는 마법사를 제공합니다.  예를 들어, **데이터 소스 구성 마법사**를 실행하면 데이터에 연결하고, 데이터를 받을 형식화된 데이터 집합을 만들고, 데이터를 응용 프로그램에 가져오는 데 필요한 충분한 정보가 응용 프로그램에 제공됩니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 사용할 경우 데이터 응용 프로그램의 개발에 어떻게 도움이 되는지 보려면 [연습: 간단한 데이터 응용 프로그램 만들기](../Topic/Walkthrough:%20Creating%20a%20Simple%20Data%20Application.md)를 참조하십시오.  
  
## 데이터에 연결  
 데이터를 응용 프로그램으로 가져오고 변경 내용을 다시 데이터 소스로 보내려면 일종의 양방향 통신이 이뤄져야 합니다.  이러한 양방향 통신은 주로 데이터 모델의 개체에서 처리합니다.  
  
 예를 들어, `TableAdapter`는 데이터 집합을 사용하는 응용 프로그램을 데이터베이스에 연결하고 <xref:System.Data.Objects.ObjectContext>는 Entity Framework의 엔터티를 데이터베이스에 연결합니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 응용 프로그램에서 사용 가능한 연결을 만드는 데 도움이 되는 여러 가지 도구를 제공합니다.  응용 프로그램을 데이터에 연결하는 방법에 대한 자세한 내용은 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)을 참조하십시오.  
  
 데이터 집합을 사용하여 응용 프로그램을 데이터베이스의 데이터에 연결하는 방법을 배우려면 [연습: 데이터베이스의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20a%20Database%20\(Windows%20Forms\).md)을 참조하십시오.  
  
## 데이터를 받기 위해 응용 프로그램 준비  
 응용 프로그램에서 연결되지 않은 데이터 모델을 사용하는 경우 데이터 작업을 하는 동안 응용 프로그램에서 임시로 데이터를 저장해야 합니다.  Visual Studio는 응용 프로그램에서 데이터 집합, 엔터티 및 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 개체와 같은 데이터를 임시로 저장하는 데 사용하는 개체를 만드는 데 도움이 되는 도구를 제공합니다.  
  
> [!NOTE]
>  연결되지 않은 데이터 모델을 사용하는 응용 프로그램은 일반적으로 데이터베이스에 연결하고, 데이터를 응용 프로그램으로 가져오는 쿼리를 실행하고, 데이터베이스와의 연결을 끊고, 데이터를 오프라인으로 조작한 다음 데이터베이스에 다시 연결하여 데이터베이스를 업데이트합니다.  
  
 응용 프로그램에서 형식화된 데이터 집합을 만드는 방법에 대한 자세한 내용은 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)를 참조하십시오.  n 계층 응용 프로그램에서 데이터 집합을 사용하는 방법에 대한 자세한 내용은 [방법: 데이터 집합 및 TableAdapter를 다른 프로젝트로 분리](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)를 참조하십시오.  
  
 데이터 집합을 만드는 방법을 배우려면 [연습: 데이터 집합 디자이너를 사용하여 데이터 집합 만들기](../data-tools/walkthrough-creating-a-dataset-with-the-dataset-designer.md)에 나오는 절차를 수행하십시오.  
  
 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 개체를 만드는 방법을 배우려면 [연습: LINQ to SQL 클래스 만들기\(O\/R 디자이너\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)에 나오는 절차를 수행하십시오.  
  
## 데이터를 응용 프로그램으로 페치  
 응용 프로그램에서 연결되지 않은 데이터 모델을 사용하는지 여부에 관계없이 데이터를 응용 프로그램으로 페치할 수 있어야 합니다.  데이터베이스에 대해 쿼리 또는 저장 프로시저를 실행하여 데이터를 응용 프로그램으로 가져옵니다.  데이터 집합에 데이터를 저장하는 응용 프로그램은 `TableAdapter`를 사용하여 쿼리 및 저장 프로시저를 실행하는 반면, 엔터티에 데이터를 저장하는 응용 프로그램은 [LINQ to Entities](../Topic/LINQ%20to%20Entities.md)를 사용하거나 엔터티를 저장 프로시저에 직접 연결하여 쿼리를 실행합니다.  TableAdapter를 사용하는 쿼리를 만들고 편집하는 방법에 대한 자세한 내용은 [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md) 및 [방법: TableAdapter 쿼리 편집](../data-tools/how-to-edit-tableadapter-queries.md)을 참조하십시오.  
  
 데이터를 데이터 집합에 로드하고 쿼리와 저장 프로시저를 실행하는 방법에 대한 자세한 내용은 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)를 참조하십시오.  
  
 데이터를 데이터 집합으로 로드하는 방법을 배우려면 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)에 나오는 절차를 수행하고 폼 로드 이벤트 처리기의 코드를 살펴보십시오.  
  
 데이터를 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 개체로 로드하는 방법을 배우려면 [연습: LINQ to SQL 클래스 만들기\(O\/R 디자이너\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)에 나오는 절차를 수행하십시오.  
  
 SQL 쿼리를 작성하고 실행하는 방법을 배우려면 [방법: 행을 반환하는 SQL 문 만들기 및 실행](../Topic/How%20to:%20Create%20and%20Execute%20an%20SQL%20Statement%20that%20Returns%20Rows.md)을 참조하십시오.  
  
 저장 프로시저를 실행하는 방법을 배우려면 [방법: 행을 반환하는 저장 프로시저 실행](../Topic/How%20to:%20Execute%20a%20Stored%20Procedure%20that%20Returns%20Rows.md)을 참조하십시오.  
  
## 폼에서 데이터 표시  
 응용 프로그램에 데이터를 바인딩한 이후에는 일반적으로 폼에 데이터를 표시하여 사용자가 데이터를 보거나 수정할 수 있게 합니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에는 항목을 폼 위로 끌어 와 데이터를 표시하는 데이터 바인딩된 컨트롤을 자동으로 만들 수 있는 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)이 있습니다.  데이터 바인딩 및 사용자에게 데이터를 표시하는 방법에 대한 자세한 내용은 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)를 참조하십시오.  
  
 사용자에게 데이터를 표시하는 방법을 배우려면 다음 연습에 나오는 절차를 수행하십시오. 특히 **데이터 소스** 창에서 항목을 끌어 오는 프로세스를 주의하여 보십시오.  
  
-   [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md).  
  
-   [연습: WCF 데이터 서비스에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md)  
  
-   [연습: WCF 데이터 서비스에 Silverlight 컨트롤 바인딩](../Topic/Walkthrough:%20Binding%20Silverlight%20Controls%20to%20a%20WCF%20Data%20Service.md)  
  
## 응용 프로그램에서 데이터 편집  
 사용자에게 데이터를 표시하면 사용자는 데이터를 다시 데이터베이스로 전송하기 전에 새 레코드를 추가하고 레코드를 편집 및 삭제하는 수정 작업을 하는 경우가 많습니다.  
  
 데이터 집합에 로드된 데이터를 다루는 방법에 대한 자세한 내용은 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)을 참조하십시오.  
  
## 데이터 유효성 검사  
 데이터를 변경할 때는 값이 데이터 집합에 적용되거나 데이터베이스에 기록되기 전에 변경 내용을 확인하는 것이 좋습니다.  *유효성 검사*는 이러한 새 값이 응용 프로그램의 요구 사항에 부합하는지 확인하는 프로세스의 이름입니다.  응용 프로그램에서 값이 변경될 때 해당 값을 확인하는 논리를 추가할 수 있습니다.  Visual Studio는 열 및 행 변경 시 데이터 유효성을 검증하는 코드를 쉽게 추가할 수 있는 도구를 제공합니다.  자세한 내용은 [데이터 유효성 검사](../Topic/Validating%20Data.md)을 참조하십시오.  
  
 응용 프로그램에 데이터 유효성 검사를 추가하는 방법을 배우려면 [연습: 데이터 집합에 유효성 검사 추가](../Topic/Walkthrough:%20Adding%20Validation%20to%20a%20Dataset.md)를 참조하십시오.  
  
 n 계층 응용 프로그램으로 분리되어 있는 데이터 집합에 데이터 유효성 검사를 추가하는 방법을 배우려면 [방법: N 계층 데이터 집합에 유효성 검사 추가](../data-tools/add-validation-to-an-n-tier-dataset.md)를 참조하십시오.  
  
## 데이터 저장  
 응용 프로그램에서 변경 작업을 하고 해당 변경 내용의 유효성을 검사한 다음에는 일반적으로 변경 내용을 다시 데이터베이스로 보냅니다.  데이터 집합에 데이터를 저장하는 응용 프로그램은 일반적으로 TableAdapterManager를 사용하여 데이터를 저장합니다.  자세한 내용은 [TableAdapterManager 개요](../Topic/TableAdapterManager%20Overview.md)을 참조하십시오.  Entity Framework 응용 프로그램은 <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> 메서드를 사용하여 데이터를 저장합니다.  
  
 업데이트된 데이터를 다시 데이터베이스로 보내는 방법에 대한 자세한 내용은 [데이터 저장](../data-tools/saving-data.md)을 참조하십시오.  
  
 업데이트된 데이터를 데이터 집합에서 데이터베이스로 보내는 방법을 배우려면 [연습: 관련 데이터 테이블의 데이터 저장\(계층적 업데이트\)](../Topic/Walkthrough:%20Saving%20Data%20from%20Related%20Data%20Tables%20\(Hierarchical%20Update\).md)에 나오는 절차를 수행하십시오.  
  
## 관련 항목  
 [Visual Studio의 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)  
 데이터를 다루는 응용 프로그램을 만드는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 사용하여 응용 프로그램을 데이터에 연결하고 응용 프로그램에 필요한 데이터 소스를 만드는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)  
 응용 프로그램에서 데이터 집합 및 엔터티 데이터 모델 등의 데이터 모델을 사용하는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)  
 데이터를 응용 프로그램으로 로드하는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)  
 Windows Forms 컨트롤, WPF 컨트롤 및 Silverlight 컨트롤을 데이터 소스에 바인딩하는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)  
 응용 프로그램에서 데이터를 변경하는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [데이터 유효성 검사](../Topic/Validating%20Data.md)  
 데이터 변경 내용의 유효성 검사를 추가하는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [데이터 저장](../data-tools/saving-data.md)  
 응용 프로그램에서 업데이트한 데이터를 데이터베이스로 보내는 방법 또는 업데이트한 데이터를 XML 등의 다른 형식으로 저장하는 방법을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [Visual Studio에서 데이터 소스 작업을 위한 도구](../Topic/Tools%20for%20Working%20with%20Data%20Sources%20in%20Visual%20Studio.md)  
 Visual Studio에서 데이터 소스를 다루는 데 사용할 수 있는 **데이터 소스** 창 및 ADO.NET 엔터티 데이터 모델 디자이너 같은 도구를 설명하는 항목에 대한 링크를 제공합니다.