---
title: "방법: 개체의 데이터로 문서 채우기 | Microsoft Docs"
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
helpviewer_keywords: 
  - "문서[Visual Studio에서 Office 개발], 데이터로 채우기"
  - "데이터[Visual Studio에서 Office 개발], 문서에 추가"
ms.assetid: 83e6ebac-e468-4bef-a91c-78c7bf597a75
caps.latest.revision: 41
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 39
---
# 방법: 개체의 데이터로 문서 채우기
  Windows Forms 프로젝트에서와 동일한 방식으로 Microsoft Office에 대한 문서 수준 프로젝트에서 데이터 개체의 데이터에 액세스할 수 있습니다. 동일한 도구 및 코드를 사용하여 개체의 데이터를 솔루션으로 가져오며, Windows Forms 컨트롤을 사용하여 데이터를 표시할 수 있습니다. 또한 호스트 컨트롤을 사용하여 데이터를 표시할 수 있습니다. 호스트 컨트롤은 이벤트 및 데이터 바인딩 기능을 통해 향상된 Microsoft Office Word의 네이티브 개체입니다. 자세한 내용은 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)을 참조하십시오.  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
 개체의 데이터로 문서를 채우려면 세 가지 기본 단계를 완료해야 합니다.  
  
-   데이터에 바인딩할 수 있는 문서에 컨트롤을 추가합니다.  
  
-   문서에 데이터 개체를 추가합니다.  
  
-   BindingSource에 데이터 개체를 연결합니다.  
  
## 데이터 개체 추가  
  
#### 데이터 개체를 추가하려면  
  
-   **데이터 원본** 창을 열고 개체에서 데이터 원본을 만듭니다. 자세한 내용은 [방법: 개체의 데이터에 연결](../Topic/How%20to:%20Connect%20to%20Data%20in%20Objects.md)을 참조하세요.  
  
## BindingSource에 데이터 개체 연결  
 문서 수준 프로젝트에서 문서에 컨트롤을 추가하고 디자인 타임에 데이터에 바인딩합니다.  
  
 VSTO 추가 기능 프로젝트에서 컨트롤을 만들고 런타임에 바인딩합니다.  
  
### 문서 수준 프로젝트  
  
##### BindingSource에 데이터 개체를 연결하려면  
  
1.  **데이터 원본** 창에서 원하는 데이터 필드를 문서로 끌어옵니다. 그러면 자동으로 컨트롤을 만듭니다.  
  
2.  코드에서 데이터 원본에 대해 선택한 개체 유형의 인스턴스를 만듭니다.  
  
3.  인스턴스를 <xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성에 할당합니다.  
  
### 응용 프로그램 수준 프로젝트  
  
##### BindingSource에 데이터 개체를 연결하려면  
  
1.  코드에서 데이터 원본과 연결되는 개체 유형의 인스턴스를 만듭니다.  
  
2.  <xref:System.Windows.Forms.BindingSource>의 인스턴스를 만듭니다.  
  
3.  데이터 원본 인스턴스를 <xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 속성에 할당합니다.  
  
4.  데이터 원본을 데이터 바인딩으로 컨트롤에 추가합니다.  
  
## 참고 항목  
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [데이터 소스 개요](../data-tools/add-new-data-sources.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../Topic/Binding%20Windows%20Forms%20controls%20to%20data%20in%20Visual%20Studio.md)   
 [방법: 데이터베이스의 데이터로 문서 채우기](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [방법: Host 컨트롤의 데이터로 데이터 원본 업데이트](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [Windows Forms 응용 프로그램에서 데이터에 연결](/visual-studio/data-tools/connecting-to-data-in-windows-forms-applications)   
 [BindingSource 구성 요소 개요](../Topic/BindingSource%20Component%20Overview.md)  
  
  