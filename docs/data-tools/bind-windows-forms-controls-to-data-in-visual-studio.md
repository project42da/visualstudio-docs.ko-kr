---
title: "Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "데이터[Windows Forms], 데이터 소스"
  - "데이터[Windows Forms], 표시"
  - "데이터 소스, 데이터 표시"
  - "폼에 데이터 표시"
  - "데이터 표시, Windows Forms"
  - "폼, 데이터 표시"
  - "Windows Forms, 데이터 바인딩"
  - "Windows Forms, 데이터 표시"
ms.assetid: 243338ef-41af-4cc5-aff7-1e830236f0ec
caps.latest.revision: 37
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩
데이터를 Windows Forms에 바인딩하여 응용 프로그램 사용자에게 데이터를 표시할 수 있습니다.  이와 같은 데이터 바인딩된 컨트롤을 만들려면 Visual Studio의 **데이터 소스** 창에서 Windows Forms 디자이너로 항목을 끌어 오면 됩니다.  이 항목에서는 데이터 바인딩된 Windows Forms 응용 프로그램을 만드는 데 관련된 가장 일반적인 몇 가지 작업, 도구 및 클래스에 대해 설명합니다.  
  
 Visual Studio에서 데이터 바인딩된 컨트롤을 만드는 방법에 대한 자세한 내용은 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)을 참조하십시오.  Windows Forms에서의 데이터 바인딩에 대한 자세한 내용은 [Windows Forms 데이터 바인딩](../Topic/Windows%20Forms%20Data%20Binding.md)을 참조하십시오.  
  
## Windows 응용 프로그램의 폼에 데이터 표시 관련 작업  
 다음 표에서는 Windows 응용 프로그램의 폼에 데이터를 표시하는 데 관련된 일반적인 작업을 보여 줍니다.  
  
|Task|추가 정보|  
|----------|-----------|  
|데이터 바인딩된 컨트롤을 만듭니다.<br /><br /> 기존 컨트롤을 데이터에 바인딩합니다.|[방법: 데이터에 Windows Forms컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data.md)|  
|부모\-자식 관계로 관련 데이터를 표시하는 컨트롤을 만듭니다. 그러면 사용자가 특정 컨트롤에서 데이터 레코드를 선택하면 선택된 레코드의 관련 데이터가 다른 컨트롤에 표시됩니다.|[방법: Windows Forms 응용 프로그램에서 관련 데이터 표시](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md)|  
|*조회 테이블*을 만듭니다.  조회 테이블은 다른 테이블의 외래 키 필드 값을 기반으로 특정 테이블의 정보를 표시합니다.|[방법: Windows Forms 응용 프로그램에서 조회 테이블 만들기](../data-tools/create-lookup-tables-in-windows-forms-applications.md)|  
|컨트롤이 데이터를 표시하는 방식을 지정합니다.|[Formatting and Advanced Binding Dialog Box](http://msdn.microsoft.com/ko-kr/42638120-9e6f-436b-985f-4036664230fd)|  
|**데이터 소스** 창에서 제공하는 스마트 캡션 기능의 동작을 변경합니다.|[방법: Visual Studio에서 데이터 바인딩된 컨트롤에 대한 캡션을 만드는 방식 사용자 지정](../data-tools/customize-how-visual-studio-creates-captions-for-data-bound-controls.md)|  
|매개 변수 있는 쿼리를 실행하는 컨트롤을 추가합니다.|[방법: Windows Forms 응용 프로그램에 매개 변수가 있는 Query 추가](../Topic/How%20to:%20Add%20a%20Parameterized%20Query%20to%20a%20Windows%20Forms%20Application.md)|  
|이미지 컨트롤을 사용하여 데이터베이스의 이미지를 표시할 수 있도록 열을 설정합니다.|[방법: 데이터베이스의 그림에 컨트롤 바인딩](../data-tools/bind-controls-to-pictures-from-a-database.md)|  
|데이터 집합의 데이터를 필터링하거나 정렬합니다.|[방법: Windows Forms 응용 프로그램에서 데이터 필터링 및 정렬](../data-tools/filter-and-sort-data-in-a-windows-forms-application.md)|  
  
 다음 항목에서는 Windows Forms 컨트롤을 데이터에 바인딩하는 예제를 제공합니다.  
  
 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)  
 데이터베이스에서 데이터를 쿼리하고 Windows Form에서 데이터를 표시하는 방법에 대해 단계별로 자세하게 설명합니다.  
  
 [연습: Windows Form에 관련 데이터 표시](../Topic/Walkthrough:%20Displaying%20Related%20Data%20on%20a%20Windows%20Form.md)  
 두 관련 테이블의 데이터를 표시하고 Windows Form에서 데이터를 표시하는 방법에 대해 단계별로 자세하게 설명합니다.  
  
 [연습: 데이터 검색을 위한 Windows Form 만들기](../data-tools/create-a-windows-form-to-search-data.md)  
 사용자 입력에 기반하여 데이터베이스 검색을 수행하는 Windows 폼을 만드는 방법을 단계별로 자세하게 설명합니다.  
  
 [연습: Windows Forms 응용 프로그램에서 조회 테이블 만들기](../Topic/Walkthrough:%20Creating%20a%20Lookup%20Table%20in%20a%20Windows%20Forms%20Application.md)  
 다른 테이블에서 선택된 데이터를 기반으로 하는 테이블의 데이터를 표시하는 방법을 단계별로 자세하게 설명합니다.  
  
 [연습: Windows Forms 간에 데이터 전달](../data-tools/pass-data-between-forms.md)  
 응용 프로그램의 한 폼에서 다른 폼으로 값을 전달하는 방법을 단계별로 자세하게 설명합니다.  
  
 [연습: 단순 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md)  
 **데이터 소스** 창에서 사용할 수 있는 사용자 지정 컨트롤을 만드는 방법을 단계별로 자세하게 설명합니다.  
  
 [연습: 복합 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md)  
 **데이터 소스** 창에서 사용할 수 있는 사용자 지정 컨트롤을 만드는 방법을 단계별로 자세하게 설명합니다.  
  
 [연습: 조회 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)  
 **데이터 소스** 창에서 사용할 수 있는 사용자 지정 컨트롤을 만드는 방법을 단계별로 자세하게 설명합니다.  
  
## 데이터 스마트 태그  
 데이터 작업을 위한 스마트 태그를 여러 컨트롤에서 사용할 수 있습니다.  특정 컨트롤이 폼에 추가되면 데이터와 관련하여 수행 가능한 작업 집합을 스마트 태그에서 사용할 수 있습니다.  
  
## BindingSource 구성 요소  
 <xref:System.Windows.Forms.BindingSource> 구성 요소는 두 가지 역할을 합니다.  첫째, 폼의 컨트롤을 데이터에 바인딩할 때 추상화 계층을 제공합니다.  폼의 컨트롤은 데이터 소스에 직접 바인딩되는 것이 아니라 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩됩니다.  
  
 둘째, 개체 컬렉션을 관리할 수 있습니다.  <xref:System.Windows.Forms.BindingSource>에 형식을 추가하면 해당 형식의 목록이 만들어집니다.  
  
 <xref:System.Windows.Forms.BindingSource> 구성 요소에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [BindingSource 구성 요소](../Topic/BindingSource%20Component.md)  
  
-   [BindingSource 구성 요소 개요](../Topic/BindingSource%20Component%20Overview.md)  
  
-   [BindingSource 구성 요소 아키텍처](../Topic/BindingSource%20Component%20Architecture.md)  
  
## BindingNavigator 컨트롤  
 이 구성 요소는 Windows 응용 프로그램에서 표시하는 데이터를 탐색하기 위한 사용자 인터페이스를 제공합니다.  자세한 내용은 [BindingNavigator 컨트롤](../Topic/BindingNavigator%20Control%20\(Windows%20Forms\).md)을 참조하십시오.  
  
## DataGridView 컨트롤  
 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하면 여러 종류의 데이터 소스에서 가져온 표 형식 데이터를 표시하고 편집할 수 있습니다.  데이터는 <xref:System.Windows.Forms.DataGridView.DataSource%2A> 속성을 사용하여 <xref:System.Windows.Forms.DataGridView>에 바인딩할 수 있습니다.  자세한 내용은 [DataGridView 컨트롤 개요](../Topic/DataGridView%20Control%20Overview%20\(Windows%20Forms\).md)을 참조하십시오.  
  
## 참고 항목  
 [데이터 연습](../Topic/Data%20Walkthroughs.md)   
 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)   
 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)   
 [데이터 소스 개요](../data-tools/add-new-data-sources.md)   
 [연습: 단순 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md)   
 [연습: 복합 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md)   
 [연습: 조회 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)