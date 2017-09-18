---
title: "방법: 데이터에 Windows Forms컨트롤 바인딩 | Microsoft Docs"
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
  - "데이터[Windows Forms], 표시"
  - "데이터 소스, 표시"
  - "데이터 표시, Windows Forms 컨트롤"
  - "Windows Forms, 데이터 표시"
ms.assetid: 0163a34a-38cb-40b9-8f38-3058a90caf21
caps.latest.revision: 28
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 데이터에 Windows Forms컨트롤 바인딩
[데이터 소스 창](../Topic/Data%20Sources%20Window.md)에서 개체를 끌어 와 데이터를 Windows Forms 컨트롤에 바인딩합니다.  항목을 **데이터 소스** 창에서 끌어 오기 전에 테이블의 컨트롤 형식은 개별 컨트롤에 대해 **자세히**로 설정하거나 <xref:System.Windows.Forms.DataGridView>에 대해 **DataGridView**로 설정할 수 있습니다.  자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)을 참조하십시오.  
  
 응용 프로그램에 필요한 컨트롤 내에서 사용할 수 없는 경우는  **데이터 원본** 창에서 컨트롤을 추가할 수 있습니다.  자세한 내용은 [데이터 소스 창에 사용자 지정 컨트롤 추가](../data-tools/add-custom-controls-to-the-data-sources-window.md)를 참조하십시오.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## 개별 컨트롤에 전체 테이블 데이터 표시  
 테이블\(개체 데이터 소스를 사용하는 경우에는 컬렉션을 나타내는 노드\)을 **데이터 소스** 창에서 Windows 응용 프로그램의 폼으로 끌어서 놓아 전체 테이블 데이터를 개별 컨트롤에 표시할 수 있습니다.  
  
#### 전체 테이블 데이터를 표시하려면  
  
1.  **데이터 소스** 창을 엽니다.  자세한 내용은 [방법: 데이터 소스 창 열기](../data-tools/how-to-open-the-data-sources-window.md)를 참조하십시오.  
  
    > [!NOTE]
    >  **데이터 소스** 창이 비어 있으면 데이터 소스를 추가합니다.  자세한 내용은 [데이터 소스 개요](../data-tools/add-new-data-sources.md)를 참조하십시오.  
  
2.  **Windows Forms 디자이너**에서 폼을 엽니다.  
  
3.  **데이터 소스** 창에서 테이블을 선택하고 드롭다운 화살표를 클릭한 다음 **자세히**를 선택합니다.  
  
4.  테이블을 **데이터 소스** 창에서 폼으로 끌어서 놓습니다.  
  
     각 열이나 속성에 대한 개별 데이터 바인딩된 컨트롤 및 적절한 제목을 가진 Label 컨트롤이 폼에 생성됩니다.  
  
## 선택한 데이터 열을 개별 컨트롤에 표시  
 개별 열\(개체 데이터 소스를 사용할 때는 속성\)을 **데이터 소스** 창에서 Windows 응용 프로그램의 폼으로 끌어서 놓아 개별 데이터 열을 개별 컨트롤에 표시합니다.  
  
#### 선택한 데이터 열을 표시하려면  
  
1.  **데이터 소스** 창을 엽니다.  자세한 내용은 [방법: 데이터 소스 창 열기](../data-tools/how-to-open-the-data-sources-window.md)를 참조하십시오.  
  
    > [!NOTE]
    >  **데이터 소스** 창이 비어 있으면 데이터 소스를 추가합니다.  자세한 내용은 [데이터 소스 개요](../data-tools/add-new-data-sources.md)를 참조하십시오.  
  
2.  테이블을 확장하여 개별 열을 표시합니다.  
  
    > [!TIP]
    >  각 열에 대해 생성된 컨트롤을 설정하려면 **데이터 소스** 창에서 열을 선택하고 드롭다운 화살표를 클릭한 다음 사용 가능한 컨트롤 목록에서 컨트롤을 선택합니다.  자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)을 참조하십시오.  
  
3.  **Windows Forms 디자이너**에서 폼을 엽니다.  
  
4.  원하는 열을 **데이터 소스** 창에서 폼으로 끌어서 놓습니다.  
  
     마우스로 끄는 각 열이나 속성에 대해 개별 데이터 바인딩된 컨트롤이 폼에 만들어지며 적절한 제목을 가진 레이블 컨트롤도 함께 만들어집니다.  
  
 **데이터 소스** 창의 항목을 기존 컨트롤\(폼에 이미 있는 컨트롤\)로 끌어 와 컨트롤을 데이터에 바인딩할 수도 있습니다.  데이터에 이미 바인딩되어 있는 컨트롤은 가장 최근에 끌어 놓은 항목에 바인딩됩니다.  
  
> [!NOTE]
>  컨트롤에 항목을 끌어 놓을 수 있으려면 **데이터 소스** 창에서 끌어 온 항목의 기본 데이터 형식을 해당 컨트롤에 표시할 수 있어야 합니다.  예를 들어, <xref:System.Windows.Forms.CheckBox>에 날짜를 표시할 수 없으므로 데이터 형식이 <xref:System.DateTime>인 항목은 <xref:System.Windows.Forms.CheckBox>로 끌어 올 수 없습니다.  
  
#### 기존 컨트롤을 데이터에 바인딩하려면  
  
1.  **데이터 소스** 창을 엽니다.  자세한 내용은 [방법: 데이터 소스 창 열기](../data-tools/how-to-open-the-data-sources-window.md)를 참조하십시오.  
  
2.  [Windows Forms Designer](http://msdn.microsoft.com/ko-kr/3c3d61f8-f36c-4d41-b9c3-398376fabb15)에서 폼을 엽니다.  
  
3.  **데이터 소스** 창의 테이블이나 개체를 확장하여 개별 열이나 속성을 표시합니다.  
  
4.  **데이터 소스** 창에서 기존 컨트롤로 원하는 항목을 끌어 옵니다.  
  
     이제 선택한 항목에 컨트롤이 바인딩되었습니다.  
  
## DataGridView 컨트롤에 데이터 표시  
  
#### 새 Windows Forms DataGridView 컨트롤에 데이터를 표시하려면  
  
1.  **데이터 소스** 창을 엽니다.  자세한 내용은 [방법: 데이터 소스 창 열기](../data-tools/how-to-open-the-data-sources-window.md)를 참조하십시오.  
  
    > [!NOTE]
    >  **데이터 소스** 창이 비어 있으면 데이터 소스를 추가합니다.  자세한 내용은 [데이터 소스 개요](../data-tools/add-new-data-sources.md)를 참조하십시오.  
  
2.  **Windows Forms 디자이너**에서 폼을 엽니다.  
  
3.  **데이터 소스** 창에서 테이블을 선택하고 드롭다운 화살표를 클릭한 다음 **DataGridView**를 선택합니다.  
  
4.  **데이터 소스** 창에서 폼으로 테이블을 끌어 옵니다.  
  
     <xref:System.Windows.Forms.DataGridView> 컨트롤과 레코드 탐색에 사용되는 도구 스트립\(<xref:System.Windows.Forms.BindingNavigator>\)이 폼에 나타납니다.  [DataSet](../data-tools/dataset-tools-in-visual-studio.md), [TableAdapter](../data-tools/tableadapter-overview.md), <xref:System.Windows.Forms.BindingSource> 및 <xref:System.Windows.Forms.BindingNavigator>가 구성 요소 트레이에 나타납니다.  
  
#### 기존 Windows Forms DataGridView 컨트롤에 데이터를 표시하려면  
  
1.  **데이터 소스** 창을 엽니다.  자세한 내용은 [방법: 데이터 소스 창 열기](../data-tools/how-to-open-the-data-sources-window.md)를 참조하십시오.  
  
    > [!NOTE]
    >  **데이터 소스** 창이 비어 있으면 데이터 소스를 추가합니다.  자세한 내용은 [데이터 소스 개요](../data-tools/add-new-data-sources.md)를 참조하십시오.  
  
2.  **Windows Forms 디자이너**에서 폼을 엽니다.  
  
3.  **데이터 소스** 창에서 테이블을 선택하고 드롭다운 화살표를 클릭한 다음 **DataGridView**를 선택합니다.  
  
4.  **데이터 소스** 창에서 폼의 <xref:System.Windows.Forms.DataGridView>로 테이블을 끌어 옵니다.  
  
     이제 <xref:System.Windows.Forms.DataGridView> 컨트롤이 끌어 놓은 테이블에 바인딩되었습니다.  [DataSet](../data-tools/dataset-tools-in-visual-studio.md), [TableAdapter](../data-tools/tableadapter-overview.md) 및 <xref:System.Windows.Forms.BindingSource>가 구성 요소 트레이에 나타납니다.  
  
## 참고 항목  
 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)   
 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)   
 [BindingSource 구성 요소 개요](../Topic/BindingSource%20Component%20Overview.md)   
 [BindingNavigator 컨트롤 개요](../Topic/BindingNavigator%20Control%20Overview%20\(Windows%20Forms\).md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)   
 [Visual Studio에서 데이터 소스 작업을 위한 도구](../Topic/Tools%20for%20Working%20with%20Data%20Sources%20in%20Visual%20Studio.md)