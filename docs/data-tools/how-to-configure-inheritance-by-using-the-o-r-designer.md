---
title: '방법: O R 디자이너를 사용 하 여 상속 구성 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e594af12-e777-434a-bc08-7dd2dac84cdc
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: d55d91fb7275b37a1fc233377955ce0f17742f63
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-configure-inheritance-by-using-the-or-designer"></a>방법: O/R 디자이너를 사용 하 여 상속 구성
[!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)] ([!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)])는 관계형 시스템에서 주로 구현되는 단일 테이블 상속 개념을 지원합니다. 단일 테이블 상속에서는 부모 정보와 자식 정보에 대한 필드를 모두 포함하는 데이터베이스 테이블이 하나 있습니다. 관계형 데이터의 경우 판별자 열에는 해당 레코드가 어느 클래스에 속해 있는지를 판별하는 값이 포함됩니다.  
  
예를 들어 회사에 고용되어 있는 모든 사람들이 포함되어 있는 Persons 테이블을 생각해 봅시다. 어떤 사람들은 사원이고 어떤 사람들은 관리자입니다. Persons 테이블에는 관리자의 경우 1 값이 들어 있고 사원의 경우 2 값이 들어 있는 `EmployeeType`이라는 열이 있으며 이 열이 판별자 열입니다. 이 시나리오에서는 직원 서브클래스를 만든 후 `EmployeeType` 값이 2인 레코드로만 클래스를 채울 수 있습니다. 각 클래스에서 적용되지 않는 열은 제거할 수도 있습니다.  
  
상속을 사용하고 관계형 데이터에 대응하는 개체 모델을 만드는 것은 조금 복잡할 수 있습니다. 다음 절차에서는 O/R 디자이너를 사용하여 상속을 구성하는 데 필요한 단계를 요약한 것입니다. 기존 테이블과 열을 참조하지 않고 일반 단계를 따르는 것이 어려울 수 있으므로 데이터를 사용하는 연습이 제공되었습니다. 사용 하 여 상속을 구성 하기 위한 자세한 단계별 지침에 대해서는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], 참조 [연습: 만들기 LINQ to SQL 클래스를 사용 하 여 단일 테이블 상속 (O/R 디자이너) 하 여](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)합니다.  
  
## <a name="to-create-inherited-data-classes"></a>상속된 데이터 클래스를 만들려면
  
1.  열기는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 추가 하 여 한 **LINQ to SQL 클래스** 를 기존 Visual Basic 또는 C# 프로젝트 항목입니다.  
  
2.  기본 클래스로 사용할 테이블을 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]로 끌어 옵니다.  
  
3.  두 번째 테이블 복사본을 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]로 끌어 와서 이름을 바꿉니다. 이것을 파생 클래스 또는 서브클래스라고 합니다.  
  
4.  클릭 **상속** 에 **개체 관계형 디자이너** 탭은 **도구 상자**, 및 다음 하위 클래스 (이름을 바꾼 테이블)를 클릭 하 고 기본 클래스에 연결 합니다.  
  
    > [!NOTE]
    >  클릭는 **상속** 항목에 **도구 상자** 하 고 마우스 단추를 놓으면, 3 단계에서 생성 된 클래스의 두 번째 복사본을 클릭 한 다음 2 단계에서 만든 첫 번째 클래스를 클릭 합니다. 상속 선의 화살표가 첫 번째 클래스를 가리킵니다.  
  
5.  각 클래스에서 연결에 사용되지 않으므로 표시하지 않을 개체 속성을 모두 삭제합니다. 연결에 사용 되는 개체 속성을 삭제 하려고 하면 오류가 발생: [속성 \<속성 이름 >은 연결에 참여 하 고 있으므로 삭제할 수 없습니다 \<연결 이름 >](../data-tools/the-property-property-name-cannot-be-deleted-because-it-is-participating-in-the-association-association-name.md).  
  
    > [!NOTE]
    >  파생 클래스는 기본 클래스에 정의된 속성을 상속하므로 각 클래스에 동일한 열은 정의할 수 없습니다. 열은 속성으로 구현됩니다. 기본 클래스의 속성에서 상속 한정자를 설정함으로써 파생 클래스에서 열을 만들 수 있습니다. 자세한 내용은 참조 [상속 기본 사항 (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)합니다.  
  
6.  [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서 상속 선을 선택합니다.  
  
7.  에 **속성** 창의 설정는 **판별자 속성** 클래스에서 레코드를 구분 하기 위해 사용 되는 열 이름입니다.  
  
8.  설정의 **Derived Class Discriminator Value** 속성을 상속된 된 형식으로 레코드를 지정 하는 데이터베이스의 값입니다. 이는 판별자 열에 저장된 값이며 상속된 클래스를 지정하는 데 사용되는 값입니다.  
  
9. 설정의 **Base Class Discriminator Value** 속성을 기본 형식으로 레코드를 지정 하는 값입니다. 이는 판별자 열에 저장된 값이며 기본 클래스를 지정하는 데 사용되는 값입니다.  
  
10. 필요에 따라 설정할 수도 있습니다는 **Inheritance Default** 속성 상속 계층 구조의 정의 된 상속 코드와 일치 하지 않는 행을 로드할 때 사용 되는 형식을 지정 합니다. 즉, 레코드의 판별자 열의 값이 일치 하지 않는 값 중에서 값의 **Derived Class Discriminator Value** 또는 **Base Class Discriminator Value** 속성, 레코드 로 지정 된 형식으로 로드 된 **Inheritance Default**합니다.  
  
## <a name="see-also"></a>참고자료
[LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
[연습: LINQ to SQL 클래스 (O R 디자이너) 만들기](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)   
[Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)   
[LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)   
[연습: 단일 테이블 상속 (O/R 디자이너)를 사용 하 여 LINQ to SQL 클래스 만들기](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)   
[상속 기본 사항 (Visual Basic)](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)  
[상속](/dotnet/csharp/programming-guide/classes-and-structs/inheritance)