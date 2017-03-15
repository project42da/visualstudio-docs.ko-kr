---
title: "방법: 저장 프로시저를 할당하여 업데이트, 삽입 및 삭제 수행(O/R 디자이너) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e88224ab-ff61-4a3a-b6b8-6f3694546cac
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 저장 프로시저를 할당하여 업데이트, 삽입 및 삭제 수행(O/R 디자이너)
저장 프로시저를 O\/R 디자이너에 추가하여 일반적인 <xref:System.Data.Linq.DataContext> 메서드로 실행할 수 있습니다.또한 엔터티 클래스의 변경 내용을 데이터베이스에 저장한 경우\(예: <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 메서드를 호출한 경우\) 저장 프로시저를 사용하여 삽입, 업데이트 및 삭제를 수행하는 기본 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 런타임 동작을 재정의할 수 있습니다.  
  
> [!NOTE]
>  클라이언트로 다시 보내야 하는 값\(예: 저장 프로시저에서 계산된 값\)을 저장 프로시저에서 반환하는 경우 저장 프로시저에 출력 매개 변수를 만듭니다.출력 매개 변수를 사용할 수 없는 경우 O\/R 디자이너에서 생성된 재정의를 사용하지 말고 부분 메서드\(Partial Method\) 구현을 작성합니다.데이터베이스에서 생성된 값에 매핑되는 멤버는 INSERT 또는 UPDATE 작업이 성공적으로 완료된 후 적절한 값으로 설정되어야 합니다.자세한 내용은 [기본 동작을 재정의할 때의 요구 사항](../Topic/Responsibilities%20of%20the%20Developer%20In%20Overriding%20Default%20Behavior.md)을 참조하십시오.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)]은 identity\(자동 증분\), rowguidcol\(데이터베이스에서 생성된 GUID\) 및 timestamp 열에 대해 데이터베이스에서 생성된 값을 자동으로 처리합니다.데이터베이스에서 생성된 값이 다른 형식의 열에 있으면 null 값이라는 예기치 않은 결과가 발생합니다.데이터베이스에서 생성된 값을 반환하려면 수동으로 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>를 `true`로 설정하고 <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>를 <xref:System.Data.Linq.Mapping.AutoSync>, <xref:System.Data.Linq.Mapping.AutoSync> 또는 <xref:System.Data.Linq.Mapping.AutoSync> 중 하나로 설정해야 합니다.  
  
## 엔터티 클래스의 업데이트 동작 구성  
 기본적으로 삽입, 업데이트 및 삭제와 같은 데이터베이스를 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 엔터티 클래스의 데이터에 대한 변경 내용으로 업데이트하는 논리가 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 런타임에서 제공됩니다.런타임에서는 열 및 기본 키 정보와 같은 테이블 스키마를 기반으로 기본 삽입, 업데이트 및 삭제 명령을 만듭니다.기본 동작을 사용하지 않으려면 테이블의 데이터를 조작하는 데 필요한 삽입, 업데이트 및 삭제 작업을 수행하기 위한 특정 저장 프로시저를 할당하여 업데이트 동작을 구성할 수 있습니다. 엔터티 클래스가 뷰에 매핑되는 경우 등과 같이 기본 동작이 수행되지 않을 때도 이렇게 할 수 있습니다.또한 저장 프로시저를 통해 데이터베이스의 테이블에 액세스해야 하는 경우에 기본 업데이트 동작을 재정의할 수 있습니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### 저장 프로시저를 지정하여 엔터티 클래스의 기본 동작을 재정의하려면  
  
1.  디자이너에서 **LINQ to SQL** 파일을 엽니다.**솔루션 탐색기**에서 .dbml 파일을 두 번 클릭합니다.  
  
2.  **서버 탐색기**\/**데이터베이스 탐색기**에서 **저장 프로시저**를 확장하여 엔터티 클래스의 삽입, 업데이트 및\/또는 삭제 명령에 사용할 저장 프로시저를 찾습니다.  
  
3.  저장 프로시저를 O\/R 디자이너로 끌어 놓습니다.  
  
     저장 프로시저는 메서드 창에 <xref:System.Data.Linq.DataContext> 메서드로 추가됩니다.자세한 내용은 [DataContext 메서드\(O\/R 디자이너\)](../data-tools/datacontext-methods-o-r-designer.md)를 참조하십시오.  
  
4.  업데이트 수행을 위해 저장 프로시저를 사용하려는 엔터티 클래스를 선택합니다.  
  
5.  **속성** 창에서 재정의할 **삽입**, **업데이트** 또는 **삭제** 명령을 선택합니다.  
  
6.  **런타임 사용** 옆의 줄임표\(...\)를 클릭하여 **동작 구성** 대화 상자를 엽니다.  
  
7.  **사용자 지정**을 선택합니다  
  
8.  **사용자 지정** 목록에서 원하는 저장 프로시저를 선택합니다.  
  
9. **메서드 인수** 및 **클래스 속성** 목록을 살펴보고 **메서드 인수**가 적절한 **클래스 속성**에 매핑되어 있는지 확인합니다.업데이트 및 삭제 명령을 위해 원래 메서드 인수\(Original\_*ArgumentName*\)를 원래 속성\(*PropertyName* \(Original\)\)에 매핑합니다.  
  
    > [!NOTE]
    >  기본적으로 메서드 인수는 이름이 일치하는 경우 클래스 속성에 매핑됩니다.속성 이름이 변경되어서 더 이상 테이블과 엔터티 클래스 간에 일치하지 않으면 디자이너에서 올바른 매핑을 결정할 수 없는 경우 매핑할 해당 클래스 속성을 선택해야 합니다.  
  
10. **확인** 또는 **적용**을 클릭합니다.  
  
    > [!NOTE]
    >  계속해서 클래스\/동작 조합을 변경한 후 **적용**을 클릭하여 해당하는 각 조합에 대한 동작을 구성할 수 있습니다.**적용**을 클릭하기 전에 클래스 또는 동작을 변경하면 변경 내용을 적용할지 묻는 경고 대화 상자가 나타납니다.  
  
     업데이트의 기본 런타임 논리 사용으로 되돌아가려면 **속성** 창에서 삽입, 업데이트 또는 삭제 명령 옆의 줄임표를 클릭한 다음 **동작 구성** 대화 상자에서 **런타임 사용**을 선택합니다.  
  
## 참고 항목  
 [O\/R 디자이너\(개체 관계형 디자이너\)](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [DataContext 메서드\(O\/R 디자이너\)](../data-tools/datacontext-methods-o-r-designer.md)   
 [연습: LINQ to SQL 클래스 만들기\(O\/R 디자이너\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)   
 [연습: Northwind Customers 테이블의 업데이트 저장 프로시저 만들기](../data-tools/walkthrough-creating-update-stored-procedures-for-the-northwind-customers-table.md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [삽입, 업데이트 및 삭제 작업](../Topic/Insert,%20Update,%20and%20Delete%20Operations.md)