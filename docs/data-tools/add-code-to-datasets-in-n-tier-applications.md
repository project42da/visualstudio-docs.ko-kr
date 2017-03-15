---
title: "방법: N 계층 응용 프로그램에서 데이터 집합에 코드 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
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
  - "n 계층 응용 프로그램, 데이터 집합 확장"
ms.assetid: d43c2ccd-4902-43d8-b1a8-d10ca5d3210c
caps.latest.revision: 20
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: N 계층 응용 프로그램에서 데이터 집합에 코드 추가
데이터 집합에 대한 partial 클래스 파일을 만들고 코드를 *DatasetName*.Dataset.Designer 파일에 추가하는 대신 여기에 추가하여 데이터 집합의 기능을 확장할 수 있습니다.  partial 클래스를 사용하면 특정 클래스의 코드를 여러 실제 파일로 나눌 수 있습니다.  자세한 내용은 [Partial](/dotnet/visual-basic/language-reference/modifiers/partial) 또는 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)을 참조하십시오.  
  
 데이터 집합을 정의하는 코드는 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)에서 데이터 집합 정의를 변경할 때마다 생성됩니다.  이 코드는 데이터 집합의 구성을 수정하는 마법사를 실행하는 도중에 변경한 경우에도 생성됩니다.  데이터 집합을 다시 생성하는 동안 코드가 삭제되지 않도록 하려면 데이터 집합의 partial 클래스 파일에 코드를 추가합니다.  
  
 기본적으로 데이터 집합과 `TableAdapter` 코드를 분리하면 각 프로젝트에 별개의 클래스 파일이 생성됩니다.  원래 프로젝트에는 `TableAdapter` 코드가 포함된 *DatasetName*.Designer.vb\(또는 *DatasetName*.Designer.cs\)라는 파일이 남습니다.  **데이터 집합 프로젝트** 속성에 지정된 프로젝트에는 데이터 집합 코드가 포함된 *DatasetName*.DataSet.Designer.vb\(또는 *DatasetName*.DataSet.Designer.cs\)라는 파일이 추가됩니다.  
  
> [!NOTE]
>  **데이터 집합 프로젝트** 속성을 설정하여 데이터 집합과 `TableAdapter`를 분리할 때 프로젝트의 기존 partial 데이터 집합 클래스는 자동으로 이동하지 않습니다.  기존의 데이터 집합 partial 클래스는 데이터 집합 프로젝트에 수동으로 옮겨야 합니다.  
  
> [!NOTE]
>  [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)에서는 유효성 검사 코드를 추가해야 할 때 <xref:System.Data.DataTable.ColumnChanging> 및 <xref:System.Data.DataTable.RowChanging> 이벤트 처리기를 생성하는 기능도 제공합니다.  자세한 내용은 [방법: N 계층 데이터 집합에 유효성 검사 추가](../data-tools/add-validation-to-an-n-tier-dataset.md)를 참조하십시오.  
  
### N 계층 응용 프로그램에서 데이터 집합에 코드를 추가하려면  
  
1.  .xsd 파일이 포함된 프로젝트를 찾습니다\([형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)\).  
  
2.  **.xsd** 파일을 두 번 클릭하여 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)를 엽니다.  
  
3.  코드를 추가하려는 데이터 테이블\(제목 표시줄의 테이블 이름\)을 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 클릭합니다.  
  
     partial 클래스가 생성되고 코드 편집기에서 열립니다.  
  
4.  partial 클래스 선언 내부에 코드를 추가합니다.  
  
     다음 예제에서는 NorthwindDataSet의 CustomersDataTable에 코드를 추가할 위치를 보여 줍니다.  
  
    ```vb#  
    Partial Public Class CustomersDataTable  
        ' Add code here to add functionality   
        ' to the CustomersDataTable.  
    End Class  
    ```  
  
    ```c#  
    partial class CustomersDataTable  
    {  
        // Add code here to add functionality  
        // to the CustomersDataTable.  
    }  
    ```  
  
## 참고 항목  
 [N 계층 데이터 응용 프로그램 개요](../data-tools/n-tier-data-applications-overview.md)   
 [방법: N 계층 응용 프로그램에서 TableAdapter에 코드 추가](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md)   
 [TableAdapter](../Topic/TableAdapters.md)   
 [TableAdapterManager 개요](../Topic/TableAdapterManager%20Overview.md)   
 [계층적 업데이트 개요](../Topic/Hierarchical%20Update%20Overview.md)   
 [데이터 응용 프로그램 만들기](../data-tools/creating-data-applications.md)   
 [Visual Studio에서 데이터 집합 작업](../data-tools/dataset-tools-in-visual-studio.md)