---
title: "데이터 소스 창에 사용자 지정 컨트롤 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "09/21/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.datasource.howtoaddcustomcontrol"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "데이터 소스 창, 컨트롤 추가"
  - "컨트롤[Visual Studio], 데이터 소스 창에 추가"
  - "DefaultBindingPropertyAttribute 클래스, 사용"
  - "LookupBindingPropertiesAttribute 클래스, 사용"
  - "ComplexBindingPropertiesAttribute 클래스, 사용"
  - "데이터 소스 창, 컨트롤 선택"
ms.assetid: 8c43e7d2-ba94-4d9b-96de-3aa971955afd
caps.latest.revision: 42
caps.handback.revision: 39
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터 소스 창에 사용자 지정 컨트롤 추가
**데이터 소스** 창의 항목을 디자인 화면으로 끌어 데이터 바인딩된 컨트롤을 만드는 경우 만들려는 컨트롤의 형식을 선택할 수 있습니다.  데이터 소스 창의 각 항목에는 드롭다운 목록이 있고, 이 목록에는 사용자가 선택할 수 있는 컨트롤이 표시됩니다.  각 항목과 연결되는 컨트롤 집합은 해당 항목의 데이터 형식에 의해 결정됩니다.  만들려는 컨트롤이 이 목록에 나타나지 않으면 이 항목에서 설명하는 지침에 따라 원하는 컨트롤을 목록에 추가하면 됩니다.  
  
 **데이터 소스** 창에서 항목에 대해 만들려는 데이터 바인딩된 컨트롤을 선택하는 방법에 대한 자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)을 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
##  <a name="customizinglist"></a> 데이터 형식의 바인딩 가능한 컨트롤 목록 사용자 지정  
 **데이터 소스** 창에 있는 특정 데이터 형식의 항목에 대해 사용 가능한 컨트롤 목록에서 컨트롤을 추가하거나 제거하려면 다음 단계를 수행합니다.  
  
#### 데이터 형식에 대해 나열할 컨트롤을 선택하려면  
  
1.  WPF Designer 또는 Windows Forms 디자이너가 열려 있는지 확인합니다.  
  
2.  **데이터 소스** 창에 추가한 데이터 소스의 일부인 항목을 이 창에서 클릭한 다음 해당 항목의 드롭다운 메뉴를 클릭합니다.  
  
3.  드롭다운 메뉴에서 **사용자 지정**을 클릭합니다.  그러면 다음 대화 상자 중 하나가 열립니다.  
  
    -   Windows Forms 디자이너가 열려 있으면 **옵션** 대화 상자의 **데이터 UI 사용자 지정** 페이지가 열립니다.  
  
    -   WPF Designer가 열려 있으면 **컨트롤 바인딩 사용자 지정** 대화 상자가 열립니다.  
  
4.  이 대화 상자의 **데이터 형식** 드롭다운 목록에서 데이터 형식을 선택합니다.  
  
    -   테이블 또는 개체에 대한 컨트롤 목록을 사용자 지정하려면 **\[목록\]**을 선택합니다.  
  
    -   테이블의 열 또는 개체의 속성에 대한 컨트롤 목록을 사용자 지정하려면 열 또는 속성이 내부 데이터 저장소에서 갖는 데이터 형식을 선택합니다.  
  
    -   사용자 정의된 모양이 있는 데이터 개체를 표시하기 위해 컨트롤 목록을 사용자 지정하려면 **\[기타\]**를 선택합니다.  예를 들어, 응용 프로그램에 특정 개체의 속성 중 두 가지 이상을 사용하여 데이터를 표시하는 사용자 지정 컨트롤이 있으면 **\[기타\]**를 선택합니다.  
  
5.  **연결된 컨트롤** 상자에서 선택한 데이터 형식에 대해 사용할 컨트롤을 선택하거나 목록에서 제거할 컨트롤의 선택을 취소합니다.  
  
    > [!NOTE]
    >  선택하려는 컨트롤이 **연결된 컨트롤** 상자에 나타나지 않으면 원하는 컨트롤을 목록에 추가해야 합니다.  자세한 내용은 [데이터 형식의 연결된 컨트롤 목록에 컨트롤 추가](#addingcontrols)를 참조하십시오.  
  
6.  **확인**을 클릭합니다.  
  
7.  **데이터 소스** 창에서 하나 이상의 컨트롤을 연결한 데이터 형식의 항목을 클릭한 다음 해당 항목의 드롭다운 메뉴를 클릭합니다.  
  
     **연결된 컨트롤** 상자에서 선택한 컨트롤이 이제 해당 항목의 드롭다운 메뉴에 나타납니다.  
  
##  <a name="addingcontrols"></a> 데이터 형식의 연결된 컨트롤 목록에 컨트롤 추가  
 컨트롤을 데이터 형식과 연결하려 하지만 해당 컨트롤이 **연결된 컨트롤** 상자에 나타나지 않으면 원하는 컨트롤을 목록에 추가해야 합니다.  컨트롤은 현재 솔루션 또는 참조되는 어셈블리 내에 있고 **도구 상자**에서 사용할 수 있어야 하며, 컨트롤의 데이터 바인딩 동작을 지정하는 특성이 지정되어 있어야 합니다.  
  
#### 연결된 컨트롤 목록에 컨트롤을 추가하려면  
  
1.  **도구 상자**를 마우스 오른쪽 단추로 클릭하고 **항목 선택**을 선택하여 원하는 컨트롤을 **도구 상자**에 추가합니다.  
  
     컨트롤은 다음 특성 중 하나를 가져야 합니다.  
  
    |특성|설명|  
    |--------|--------|  
    |<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|<xref:System.Windows.Forms.TextBox>와 같이 단일 열\(또는 속성\)을 표시하는 단순 컨트롤에서 이 특성을 구현합니다.|  
    |<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|<xref:System.Windows.Forms.DataGridView>와 같이 데이터의 목록\(또는 테이블\)을 표시하는 컨트롤에서 이 특성을 구현합니다.|  
    |<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|<xref:System.Windows.Forms.ComboBox>와 같이 데이터의 목록\(또는 테이블\)을 표시하지만 단일 열이나 속성도 표시해야 하는 컨트롤에서 이 특성을 구현합니다.|  
  
2.  **옵션** 대화 상자의 **데이터 UI 사용자 지정** 페이지\(Windows Forms의 경우\) 또는 **컨트롤 바인딩 사용자 지정** 대화 상자\(WPF의 경우\)를 엽니다.  자세한 내용은 [데이터 형식의 바인딩 가능한 컨트롤 목록 사용자 지정](#customizinglist)을 참조하십시오.  
  
3.  이제 **도구 상자**에 추가한 컨트롤이 **연결된 컨트롤** 상자에 나타납니다.  
  
    > [!NOTE]
    >  현재 솔루션 내에 있거나 참조된 어셈블리에 있으며 앞에 나온 테이블의 데이터 바인딩 특성 중 하나를 구현하는 컨트롤만 연결된 컨트롤 목록에 추가될 수 있습니다.  **데이터 소스** 창에서 사용할 수 없는 사용자 지정 컨트롤에 데이터를 바인딩하려면 **도구 상자**에서 디자인 화면으로 해당 컨트롤을 끌어 온 다음 바인딩할 항목을 **데이터 소스** 창에서 해당 컨트롤로 끌어 옵니다.  
  
## 참고 항목  
 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)   
 [데이터 소스 개요](../data-tools/add-new-data-sources.md)   
 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)   
 [연습: 단순 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md)   
 [연습: 복합 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md)   
 [연습: 조회 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)   
 [컨트롤 바인딩 사용자 지정 대화 상자](../data-tools/customize-control-binding-dialog-box.md)