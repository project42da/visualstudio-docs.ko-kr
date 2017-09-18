---
title: "Visual Studio에서 데이터에 컨트롤 바인딩 | Microsoft Docs"
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
  - "데이터 소스 창"
  - "데이터 소스, 데이터 표시"
  - "데이터, 표시"
  - "데이터 표시"
ms.assetid: be8b6623-86a6-493e-ab7a-050de4661fd6
caps.latest.revision: 40
caps.handback.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual Studio에서 데이터에 컨트롤 바인딩
데이터를 컨트롤에 바인딩하여 응용 프로그램 사용자에게 데이터를 표시할 수 있습니다.  데이터 바인딩된 컨트롤은 Visual Studio의 **데이터 소스** 창에서 디자이너 화면으로 항목을 끌어 만들 수 있습니다.  
  
 이 항목에서는 데이터 바인딩된 컨트롤을 만드는 데 사용할 수 있는 데이터 소스에 대해 설명합니다.  또한 데이터 바인딩과 관련된 일반적인 작업에 대해서도 설명합니다.  데이터 바인딩된 컨트롤을 만드는 방법에 대한 보다 자세한 내용은 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md), [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md) 및 [Visual Studio에서 데이터에 Silverlight 컨트롤 바인딩](../Topic/Binding%20Silverlight%20Controls%20to%20Data%20in%20Visual%20Studio.md)을 참조하십시오.  
  
## 데이터 소스  
 데이터 소스는 응용 프로그램에서 사용 가능한 데이터를 가리킵니다.  데이터 소스는 데이터베이스, 서비스 또는 개체로부터 만들 수 있습니다.  자세한 내용은 [데이터 소스 개요](../data-tools/add-new-data-sources.md)을 참조하십시오.  
  
 일부 데이터 소스의 경우 **데이터 소스** 창에서 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수 있게 허용하지만 모든 데이터 소스가 그러한 것은 아닙니다.  다음 표에서는 어떠한 데이터 소스가 지원되는지 보여 줍니다.  
  
|데이터 소스|**Windows Forms 디자이너**에서의 끌어서 놓기 지원|**WPF Designer**에서의 끌어서 놓기 지원|**Silverlight 디자이너**에서의 끌어서 놓기 지원|  
|------------|-----------------------------------------|-----------------------------------|---------------------------------------|  
|데이터 집합|예|예|아니요|  
|엔터티 데이터 모델|아니요<sup>1</sup>|예|예|  
|LINQ to SQL 클래스|아니요<sup>2</sup>|아니요<sup>2</sup>|아니요<sup>2</sup>|  
|[!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)], WCF 서비스, 웹 서비스 등의 서비스|예|예|예|  
|Object|예|예|예|  
|SharePoint|예|예|예|  
  
 1.  **Windows Forms 디자이너**가 열려 있는 경우 **데이터 소스** 창의 항목은 읽기 전용이며 디자이너로 끌어 올 수 없습니다.  그러나 이 경우에도 엔터티 데이터 모델에 기반하는 개체 데이터 소스를 새로 추가한 후 해당 개체를 디자이너로 끌어 오면 데이터 바인딩된 컨트롤을 만들 수 있습니다.  
  
 2.  LINQ to SQL 클래스는 **데이터 소스** 창에 표시되지 않습니다.  그러나 LINQ to SQL 클래스에 기반하는 개체 데이터 소스를 새로 만든 다음 해당 개체를 디자이너로 끌어 와 데이터 바인딩된 컨트롤을 만들 수는 있습니다.  자세한 내용은 [연습: LINQ to SQL 클래스 만들기\(O\/R 디자이너\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)을 참조하십시오.  
  
## 데이터 소스 창  
 데이터 소스는 프로젝트에서 **데이터 소스** 창의 항목으로 사용할 수 있습니다.  이 창의 항목을 끌어 오면 내부 데이터에 바인딩되는 컨트롤을 만들 수 있습니다.  자세한 내용은 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)을 참조하십시오.  
  
 **데이터 소스** 창에 표시되는 각 데이터 형식의 경우 디자이너로 항목을 끌 때 기본 컨트롤이 만들어집니다.  이와 같이 만들어지는 컨트롤은 **데이터 소스** 창에서 항목을 끌어 오기 전에 변경할 수 있습니다.  자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)을 참조하십시오.  
  
## 컨트롤을 데이터에 바인딩하는 것과 관련된 작업  
 다음 표에서는 컨트롤을 데이터에 바인딩할 때 수행하는 가장 일반적인 작업 중 일부를 보여 줍니다.  
  
|Task|추가 정보|  
|----------|-----------|  
|**데이터 소스** 창을 엽니다.|[방법: 데이터 소스 창 열기](../data-tools/how-to-open-the-data-sources-window.md)|  
|프로젝트에 데이터 소스를 추가합니다.|[방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)<br /><br /> [방법: 개체의 데이터에 연결](../Topic/How%20to:%20Connect%20to%20Data%20in%20Objects.md)<br /><br /> [방법: 서비스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-service.md)|  
|**데이터 소스** 창의 항목을 디자이너로 항목을 끌 때 만들어지는 컨트롤을 설정합니다.|[데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)|  
|**데이터 소스** 창의 항목과 연결되는 컨트롤 목록을 수정합니다.|[데이터 소스 창에 사용자 지정 컨트롤 추가](../data-tools/add-custom-controls-to-the-data-sources-window.md)|  
|데이터 바인딩된 컨트롤을 만듭니다.|[Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)<br /><br /> [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)<br /><br /> [Visual Studio에서 데이터에 Silverlight 컨트롤 바인딩](../Topic/Binding%20Silverlight%20Controls%20to%20Data%20in%20Visual%20Studio.md)|  
  
 데이터에 바인딩된 컨트롤을 만든 후 다음 작업 중 하나를 수행할 수 있습니다.  
  
|Task|자세한 내용|  
|----------|------------|  
|내부 데이터 소스의 데이터 편집|[응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)|  
|데이터에 대한 변경 내용 확인|[데이터 유효성 검사](../Topic/Validating%20Data.md)|  
|업데이트된 데이터를 다시 데이터베이스에 저장|[데이터 저장](../data-tools/saving-data.md)|  
  
## 참고 항목  
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)   
 [Visual Studio에서 데이터에 Silverlight 컨트롤 바인딩](../Topic/Binding%20Silverlight%20Controls%20to%20Data%20in%20Visual%20Studio.md)   
 [방법: 데이터베이스의 그림에 컨트롤 바인딩](../data-tools/bind-controls-to-pictures-from-a-database.md)   
 [Visual Studio의 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)   
 [Visual Studio에서 데이터 소스 작업을 위한 도구](../Topic/Tools%20for%20Working%20with%20Data%20Sources%20in%20Visual%20Studio.md)