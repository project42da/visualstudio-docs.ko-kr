---
title: "데이터 소스 창에서 끌어올 때 만들 컨트롤 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "09/21/2016"
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
  - "데이터 소스 창, 컨트롤 선택"
  - "Windows Forms, 데이터 표시"
  - "데이터[Visual Studio], Windows Forms에 표시"
  - "데이터[Visual Studio], 데이터 소스 창"
ms.assetid: 20597ff8-0c98-43ec-8fb1-05376804ba48
caps.latest.revision: 31
caps.handback.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터 소스 창에서 끌어올 때 만들 컨트롤 설정
**데이터 소스** 창에서 WPF Designer 또는 Windows Forms 디자이너로 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수 있습니다.  **데이터 소스** 창의 각 항목에는 디자이너로 항목을 끌 때 만들어지는 기본 컨트롤이 있습니다.  그러나 기본 컨트롤 대신 다른 컨트롤이 만들어지도록 선택할 수 있습니다.  
  
## 데이터 테이블 또는 개체에 대해 컨트롤이 만들어지도록 설정  
 데이터 테이블 또는 개체를 나타내는 항목을 **데이터 소스** 창에서 끌어 오기 전에 모든 데이터를 컨트롤 하나에 표시할지 아니면 각 열 또는 속성을 여러 개의 컨트롤에 개별적으로 표시할지 선택할 수 있습니다.  
  
 이 컨텍스트에서 *개체*라는 용어는 사용자 지정 비즈니스 개체, 엔터티 데이터 모델의 엔터티 또는 서비스에서 반환하는 개체를 가리킵니다.  
  
#### 데이터 테이블 또는 개체에 대해 컨트롤이 만들어지도록 설정하려면  
  
1.  WPF Designer 또는 Windows Forms 디자이너가 열려 있는지 확인합니다.  
  
2.  **데이터 소스** 창에서 데이터 테이블이나 개체를 나타내며 설정할 대상인 항목을 선택합니다.  
  
3.  해당 항목의 드롭다운 메뉴를 클릭한 후 이 메뉴에서 다음 항목 중 하나를 클릭합니다.  
  
    -   각 데이터 필드를 별도의 컨트롤에 표시하려면 **자세히**를 클릭합니다.  이 경우 데이터 항목을 디자이너로 끌면 부모 데이터 테이블 또는 개체의 각 열이나 속성에 대해 서로 다른 데이터 바인딩된 컨트롤이 만들어지고 각 컨트롤에는 레이블이 지정됩니다.  
  
    -   단일 컨트롤에 모든 데이터를 표시하려면 목록에서 다른 컨트롤을 선택합니다. 예를 들어, WPF 응용 프로그램의 경우 **DataGrid** 또는 **List**를 선택하고 Windows Forms 응용 프로그램의 경우 **DataGridView**를 선택합니다.  
  
     사용 가능한 컨트롤의 목록은 열려 있는 디자이너에 따라 달라집니다. 또한 프로젝트가 대상으로 하는 .NET Framework의 버전 및 데이터 바인딩을 지원하는 사용자 지정 컨트롤을 **도구 상자**에 추가했는지 여부에 따라 달라지기도 합니다.  만들려는 컨트롤이 사용 가능한 컨트롤 목록에 있으면 해당 컨트롤을 목록에 추가할 수 있습니다.  자세한 내용은 [데이터 소스 창에 사용자 지정 컨트롤 추가](../data-tools/add-custom-controls-to-the-data-sources-window.md)을 참조하십시오.  
  
     데이터 테이블 또는 개체에 대한 컨트롤의 목록에 추가할 수 있는 사용자 지정 Windows Forms 컨트롤을 **데이터 소스** 창에서 만드는 방법을 배우려면 [연습: 복합 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md)를 참조하십시오.  
  
## 데이터 열 또는 속성에 대해 컨트롤이 만들어지도록 설정  
 열 또는 개체의 속성을 나타내는 항목을 **데이터 소스** 창에서 디자이너로 끌어 오기 전에 만들어질 컨트롤을 설정할 수 있습니다.  
  
#### 열 또는 속성에 대해 컨트롤이 만들어지도록 설정하려면  
  
1.  WPF Designer 또는 Windows Forms 디자이너가 열려 있는지 확인합니다.  
  
2.  **데이터 소스** 창에서 원하는 테이블 또는 개체를 확장하여 열 또는 속성을 표시합니다.  
  
3.  컨트롤이 만들어지도록 설정할 각 열 또는 속성을 선택합니다.  
  
4.  열 또는 속성의 드롭다운 메뉴를 클릭한 다음 해당 항목을 디자이너로 끌어 올 때 만들려는 컨트롤을 선택합니다.  
  
     사용 가능한 컨트롤의 목록은 열려 있는 디자이너에 따라 달라집니다. 또한 프로젝트가 대상으로 하는 .NET Framework의 버전 및 데이터 바인딩을 지원하는 어떤 사용자 지정 컨트롤이 **도구 상자**에 추가되었는지에 따라 달라지기도 합니다.  만들려는 컨트롤이 사용 가능한 컨트롤 목록에 있으면 해당 컨트롤을 목록에 추가할 수 있습니다.  자세한 내용은 [데이터 소스 창에 사용자 지정 컨트롤 추가](../data-tools/add-custom-controls-to-the-data-sources-window.md)을 참조하십시오.  
  
     데이터 열 또는 속성에 대한 컨트롤의 목록에 추가할 수 있는 사용자 지정 컨트롤을 **데이터 소스** 창에서 만드는 방법을 배우려면 [연습: 단순 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md)를 참조하십시오.  
  
     열 또는 속성에 대한 컨트롤을 만들지 않으려면 드롭다운 메뉴에서 **없음**을 선택합니다.  이렇게 하면 특정 열 또는 속성을 제외한 채 부모 테이블 또는 개체를 디자이너로 끌어 오려는 경우에 도움이 됩니다.  
  
## 참고 항목  
 [데이터 연습](../Topic/Data%20Walkthroughs.md)   
 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)   
 [데이터 소스 개요](../data-tools/add-new-data-sources.md)   
 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)   
 [데이터 소스 창에 사용자 지정 컨트롤 추가](../data-tools/add-custom-controls-to-the-data-sources-window.md)