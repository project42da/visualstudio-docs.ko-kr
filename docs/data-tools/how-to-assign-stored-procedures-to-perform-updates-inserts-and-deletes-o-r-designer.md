---
title: "업데이트를 수행 하는 저장 프로시저 insert, 및 Linq to SQL O/R 디자이너에서에서 delete | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e88224ab-ff61-4a3a-b6b8-6f3694546cac
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: f0d6910d2bf449172bac86a3ecd18be8169ef244
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-or-designer"></a>방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 합니다.
저장 프로시저를 O/R 디자이너에 추가하여 일반적인 <xref:System.Data.Linq.DataContext> 메서드로 실행할 수 있습니다. 기본값을 재정의 하려면 사용할 수도 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 데이터베이스에 변경 내용을 엔터티 클래스에서 저장 될 때 삭제 및 삽입, 업데이트를 수행 하는 런타임 동작 (예를 들어 호출 하는 경우는 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 메서드).  
  
> [!NOTE]
>  클라이언트로 다시 보내야 하는 값(예: 저장 프로시저에서 계산된 값)을 저장 프로시저에서 반환하는 경우 저장 프로시저에 출력 매개 변수를 만듭니다. 출력 매개 변수를 사용할 수 없는 경우 O/R 디자이너에서 생성된 재정의를 사용하지 말고 부분 메서드(Partial Method) 구현을 작성합니다. 데이터베이스에서 생성된 값에 매핑되는 멤버는 INSERT 또는 UPDATE 작업이 성공적으로 완료된 후 적절한 값으로 설정되어야 합니다. 자세한 내용은 참조 [는에서 기본 동작 재정의 개발자의 책임](/dotnet/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior)합니다.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)]은 identity(자동 증분), rowguidcol(데이터베이스에서 생성된 GUID) 및 timestamp 열에 대해 데이터베이스에서 생성된 값을 자동으로 처리합니다. 데이터베이스에서 생성된 값이 다른 형식의 열에 있으면 null 값이라는 예기치 않은 결과가 발생합니다. 데이터베이스에서 생성된 값을 반환하려면 수동으로 <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>를 `true`로 설정하고 <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>를 <xref:System.Data.Linq.Mapping.AutoSync>, <xref:System.Data.Linq.Mapping.AutoSync> 또는 <xref:System.Data.Linq.Mapping.AutoSync> 중 하나로 설정해야 합니다.  
  
## <a name="configuring-the-update-behavior-of-an-entity-class"></a>엔터티 클래스의 업데이트 동작 구성  
 기본적으로 (삽입, 업데이트 및 삭제)는 데이터베이스의 데이터에 대 한 변경 내용으로 업데이트 하는 논리가 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 엔터티 클래스에서 제공 되는 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 런타임. 런타임에 기본을 기반으로 하는 INSERT, UPDATE 및 DELETE 명령을 만듭니다는 테이블 (열과 기본 키 정보)의 스키마입니다. 기본 동작은 바람직하지 않은 경우에 필요한 삽입, 업데이트 및 테이블의 데이터를 조작 하는 데 필요한 삭제를 수행 하기 위한 특정 저장된 프로시저를 할당 하 여 업데이트 동작을 구성할 수 있습니다. 엔터티 클래스가 뷰에 매핑되는 때와 같이 기본 동작이 생성되지 않은 경우에도 이렇게 할 수 있습니다. 또한 저장 프로시저를 통해 데이터베이스의 테이블에 액세스해야 하는 경우에 기본 업데이트 동작을 재정의할 수 있습니다.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-assign-stored-procedures-to-override-the-default-behavior-of-an-entity-class"></a>저장 프로시저를 지정하여 엔터티 클래스의 기본 동작을 재정의하려면  
  
1.  열기는 **LINQ to SQL** 디자이너에는 파일입니다. (에서.dbml 파일을 두 번 클릭 **솔루션 탐색기**.)  
  
2.  **서버 탐색기**/**데이터베이스 탐색기**, 확장 **저장 프로시저** 저장된 프로시저 Insert, Update에 대 한 사용 하려는 찾습니다. 및/또는 엔터티 클래스의 명령을 삭제 합니다.  
  
3.  저장 프로시저를 O/R 디자이너로 끌어 놓습니다.  
  
     저장 프로시저는 메서드 창에 <xref:System.Data.Linq.DataContext> 메서드로 추가됩니다. 자세한 내용은 참조 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)합니다.  
  
4.  업데이트 수행을 위해 저장 프로시저를 사용하려는 엔터티 클래스를 선택합니다.  
  
5.  에 **속성** 창 재정의할 선택 (**삽입**, **업데이트**, 또는 **삭제**).  
  
6.  단어 옆의 줄임표 (...) **런타임 사용** 열려는 **동작 구성** 대화 상자.  
  
7.  선택 **사용자 지정**합니다.  
  
8.  원하는 저장된 프로시저를 선택는 **사용자 지정** 목록입니다.  
  
9. 목록을 살펴보고 **메서드 인수** 및 **클래스 속성** 되었는지 확인 하 고 **메서드 인수** 을 적절 한 map **클래스속성**. 원래 메서드 인수 (Original_*ArgumentName*)를 원래 속성 (*PropertyName* (Original)) Update 및 Delete 명령에 대 한 합니다.  
  
    > [!NOTE]
    >  기본적으로 메서드 인수는 이름이 일치하는 경우 클래스 속성에 매핑됩니다. 속성 이름이 변경되어서 더 이상 테이블과 엔터티 클래스 간에 일치하지 않으면 디자이너에서 올바른 매핑을 결정할 수 없는 경우 매핑할 해당 클래스 속성을 선택해야 합니다.  
  
10. 클릭 **확인** 또는 **적용**합니다.  
  
    > [!NOTE]
    >  계속 클릭으로 각 클래스/동작 조합에 대 한 동작을 구성할 수 있습니다 **적용** 각 변경 합니다. 클릭 하기 전에 클래스 또는 동작을 변경 하는 경우 **적용**, 변경 내용을 적용 하려면 나타납니다 묻는 경고 대화 상자가 있습니다.  
  
업데이트를 위한 기본 런타임 논리 사용으로 되돌리려면 Insert, Update, 옆의 줄임표 또는 삭제 명령은 **속성** 창과 선택 **런타임을 사용** 에  **동작 구성** 대화 상자.  
  
## <a name="see-also"></a>참고 항목
[Visual Studio에서 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
[DataContext 메서드](../data-tools/datacontext-methods-o-r-designer.md)   
[LINQ to SQL (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/index)   
[삽입, 업데이트 및 삭제 작업 (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/insert-update-and-delete-operations)