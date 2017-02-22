---
title: "방법: 데이터 기반 단위 테스트 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.test.testresults.unittest.datadriven"
  - "vs.test.testresults.unittest.datadriven.failure"
helpviewer_keywords: 
  - "단위 테스트, 실행"
  - "단위 테스트, 데이터 기반"
  - "데이터 기반 단위 테스트"
ms.assetid: a0322bc5-02c8-4f9f-af43-100a60b1bd28
caps.latest.revision: 33
caps.handback.revision: 33
ms.author: "mlearned"
manager: "douge"
---
# 방법: 데이터 기반 단위 테스트 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Microsoft 단위 테스트 프레임 워크를 사용하여 관리 되는 코드를 테스트 메서드에서 데이터 소스에서 사용 되는 값을 검색 하는 단위 테스트 메서드를 설정할 수 있습니다.  쉽게 하나의 메서드를 사용하여 다양한 입력 테스트를 데이터 소스의 각 행에에서는 연속적으로 실행 됩니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [테스트 중인 메서드](../test/how-to-create-a-data-driven-unit-test.md#BKMK_The_method_under_test)  
  
-   [데이터 소스 만들기](../test/how-to-create-a-data-driven-unit-test.md#BKMK_Creating_a_data_source)  
  
-   [테스트 클래스에 TestContext 추가](../test/how-to-create-a-data-driven-unit-test.md#BKMK_Adding_a_TestContext_to_the_test_class)  
  
-   [테스트 메서드 쓰기](../test/how-to-create-a-data-driven-unit-test.md#BKMK_Writing_the_test_method)  
  
    -   [DataSourceAttribute 지정](../test/how-to-create-a-data-driven-unit-test.md#BKMK_Specifying_the_DataSourceAttribute)  
  
    -   [TestContext.DataRow를 사용하여 데이터에 액세스](../test/how-to-create-a-data-driven-unit-test.md#BKMK_Using_TestContext_DataRow_to_access_the_data)  
  
-   [테스트 실행 및 결과 보기](../test/how-to-create-a-data-driven-unit-test.md#BKMK_Running_the_test_and_viewing_results)  
  
 데이터 기반 단위 테스트를 만드는 단계는 다음과 같습니다.  
  
1.  테스트 메서드에서 사용 하는 값이 포함 된 데이터 원본을 만듭니다.  데이터 원본 테스트를 실행 하는 컴퓨터에 등록 된 형식일 수 있습니다.  
  
2.  추가 개인 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext> 필드와 공용 `TestContext` 속성 테스트 클래스에 있습니다.  
  
3.  단위 테스트 메서드를 만들고 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute> 특성을 추가합니다.  
  
4.  테스트에서 사용하는 값을 검색하기 위해 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext.DataRow%2A> 인덱서 속성을 사용합니다.  
  
##  <a name="BKMK_The_method_under_test"></a> 테스트 중인 메서드  
 예를 들어, 우리가 만들었다고 가정해 봅시다.  
  
1.  다른 종류의 계정에 대 한 트랜잭션을 처리하고 허용합는 `MyBank` 라고 불리는 솔루션.  
  
2.  `MyBank` 라는 `BankDb` 계정에 대한 트랜잭션을 관리 하는 프로젝트.  
  
3.  `Maths` 에 `DbBank` 프로젝트에서 트랜잭션이 모든 은행을 확인 하기 위해 수학 함수를 수행 하는 프로젝트입니다.  
  
4.  단위 테스트 프로젝트 `BankDbTests` 의 동작을 테스트 하는 `BankDb` 구성 요소입니다.  
  
5.  단위 테스트 클래스  `MathsTests`  의 동작을 확인 하는  `Maths`  클래스입니다.  
  
 `Maths` 루프를 사용 하는 두 개의 정수를 추가하는 메서드 테스트를 할 것입니다.  
  
```  
public int AddIntegers(int first, int second)  
{  
    int sum = first;  
    for( int i = 0; i < second; i++)  
    {  
        sum += 1;  
    }  
    return sum;  
}  
```  
  
##  <a name="BKMK_Creating_a_data_source"></a> 데이터 소스 만들기  
 테스트는  `AddIntegers`  메서드를 매개 변수 및 반환 될 것으로 예상 하는 합계 값의 범위를 지정 하는 데이터 원본을 만듭니다.  Sql 압축 데이터베이스 작성 예에서  `MathsData`  라는 테이블을  `AddIntegersData`  다음 열 이름 및 값을 포함 하는 것이 있습니다.  
  
|FirstNumber|SecondNumber|합계|  
|-----------------|------------------|--------|  
|0|1|1|  
|1|1|2|  
|2|\-3|\-1|  
  
##  <a name="BKMK_Adding_a_TestContext_to_the_test_class"></a> 테스트 클래스에 TestContext 추가  
 단위 테스트 프레임 워크를 `TestContext` 개체를 데이터 기반 테스트에 대 한 데이터 원본 정보를 저장 합니다.  프레임 워크는 다음이 개체의 값으로 설정 된  `TestContext`  속성을 만듭니다.  
  
```  
  
private TestContext testContextInstance;  
public TestContext TestContext  
{  
    get { return testContextInstance; }  
    set { testContextInstance = value; }  
}  
  
```  
  
 테스트 메서드를 통해 데이터에 액세스 하는  `DataRow`  의 인덱서 속성은 `TestContext`입니다.  
  
##  <a name="BKMK_Writing_the_test_method"></a> 테스트 메서드 쓰기  
 테스트 메서드에 대한  `AddIntegers`  는 매우 단순합니다.  데이터 소스의 각 행에 대해 호출  `AddIntegers`  에 **FirstNumber** 및 **SecondNumber** 열 값 매개 변수 및 반환 값에 대해 확인  **합계** 열 값입니다.  
  
```  
  
[DataSource(@"Provider=Microsoft.SqlServerCe.Client.4.0; Data Source=C:\Data\MathsData.sdf;", "Numbers")]  
[TestMethod()]  
public void AddIntegers_FromDataSourceTest()  
{  
    var target = new Maths();  
  
    // Access the data  
    int x = Convert.ToInt32(TestContext.DataRow["FirstNumber"]);  
    int y = Convert.ToInt32(TestContext.DataRow["SecondNumber"]);   
    int expected = Convert.ToInt32(TestContext.DataRow["Sum"]);  
    int actual = target.IntegerMethod(x, y);  
    Assert.AreEqual(expected, actual,  
        "x:<{0}> y:<{1}>",  
        new object[] {x, y});  
  
}  
  
```  
  
 `Assert`  메서드를 표시 하는 메시지가 포함 된  `x`  및  `y`  실패 반복 값을 확인하세요.  기본적으로 설정 된 값을  `expected`  및  `actual` , 실패 한 테스트의 세부 정보에 이미 포함 되어 있습니다.  
  
###  <a name="BKMK_Specifying_the_DataSourceAttribute"></a> DataSourceAttribute 지정  
 `DataSource`  특성 테스트 메서드에서 데이터 소스 사용 하는 테이블의 이름에 대 한 연결 문자열을 지정 합니다.  연결 문자열의 정확한 정보는 사용 중인 데이터 소스의 종류에 따라 달라집니다.  이 예제에서는 SqlServerCe 데이터베이스를 사용했습니다.  
  
```  
[DataSource(@"Provider=Microsoft.SqlServerCe.Client.4.0;Data Source=C:\Data\MathsData.sdf", "AddIntegersData")]  
```  
  
 DataSource 특성에 세 명의 생성자가 있습니다.  
  
```  
[DataSource(dataSourceSettingName)]  
```  
  
 솔루션에 대 한 app.config 파일에 저장 된 연결 정보를 사용 하는 생성자 매개 변수를 사용 합니다.  *dataSourceSettingsName* 연결 정보를 지정 하는 구성 파일의 Xml 요소 이름입니다.  
  
 app.config 파일을 사용하면 단위 테스트 자체를 변경하지 않고도 데이터 소스의 위치를 변경할 수 있다는 이점이 있습니다.  app.config 파일을 만들고 사용하는 방법에 대한 자세한 내용은 [연습: 구성 파일을 통한 데이터 소스 정의](../test/walkthrough-using-a-configuration-file-to-define-a-data-source.md)를 참조하십시오.  
  
```  
[DataSource(connectionString, tableName)]  
```  
  
 `DataSource`  생성자를 두 매개 변수를 사용 하 여 데이터 소스와 테스트 방법에 대 한 데이터가 들어 있는 테이블의 이름에 대 한 연결 문자열을 지정 합니다.  
  
 연결 문자열 형식 데이터 원본 유형에 따라 다릅니다 있지만 고정 데이터 공급자의 이름을 지정 하는 공급자 요소를 포함 해야 합니다.  
  
```  
[DataSource(  
    dataProvider,   
    connectionString,   
    tableName,  
    dataAccessMethod  
    )]  
```  
  
###  <a name="BKMK_Using_TestContext_DataRow_to_access_the_data"></a> TestContext.DataRow를 사용하여 데이터에 액세스  
 데이터에 액세스 하는  `AddIntegersData`  테이블에서 사용 하는  `TestContext.DataRow`  인덱서를 사용하세요.  `DataRow`이 <xref:System.Data.DataRow> 개체, 인덱스 또는 열 이름으로 열 값을 검색 했습니다.  개체 값이 반환 됩니다 때문에 적절 한 형식으로 변환할 필요 합니다.  
  
```  
int x = Convert.ToInt32(TestContext.DataRow["FirstNumber"]);  
  
```  
  
##  <a name="BKMK_Running_the_test_and_viewing_results"></a> 테스트 실행 및 결과 보기  
 테스트 메서드를 작성 했으면 테스트 프로젝트를 빌드하십시오.  테스트 메서드가 테스트 탐색기 창에 표시 된 **테스트 되지 실행** 그룹에 나타납니다.  테스트를 실행하고 작성하고 다시 실행할 때 테스트 탐색기는 **실패한 테스트**, **통과한 테스트**, **통과된 테스트** 및 실행하지 않은 테스트의 그룹에 결과를 표시합니다.  사용자는 **모두 실행** 을 선택해서 모든 테스트를 실행 하거나 **실행...** 을 선택해서 테스트들의 하위 집합을 실행할 수 있습니다.  
  
 테스트를 실행할 때 테스트 결과 표시줄 탐색기 상단에 애니메이션 됩니다.  테스트 실행이 끝날 때 테스트 메서드가 통과한다면 녹색이 되고 테스트가 실패하면 빨간색이 될것입니다.  테스트 실행의 요약 테스트 탐색기 창의 아래쪽에 세부 정보 창에 표시 됩니다.  테스트를 선택해서 아래쪽 창에 해당 테스트의 세부 정보를 확인하십시오.  
  
 `AddIntegers_FromDataSourceTest` 예에서 메서드 결과 표시줄이 빨간색으로 바뀝니다 및 테스트 메서드는 이동은 **테스트 실패** 실패 원본 데이터에서 반복 방법을 데이터 기반 테스트에 실패합니다.  테스트 탐색기 창에서 실패 한 데이터 기반 테스트를 선택 하면 세부 정보 창에서 데이터 행 인덱스로 식별 되는 각 반복의 결과 표시 합니다.  이 예제에서는  `AddIntegers`  알고리즘 음수 값을 올바르게 처리 하지 않습니다.  
  
 테스트 대상 메서드를 수정하고 테스트를 다시 실행 결과 모음 녹색으로 바뀌고 테스트 메서드는 이동된 **테스트 통과** 그룹으로 이동합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute?displayProperty=fullName>   
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext?displayProperty=fullName>   
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestContext.DataRow%2A?displayProperty=fullName>   
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert?displayProperty=fullName>   
 [How to: Create and Run a Unit Test](http://msdn.microsoft.com/ko-kr/5e0f43cf-5e51-48e2-9c98-0eb9324bdc48)   
 [코드 단위 테스트](../test/unit-test-your-code.md)   
 [테스트 탐색기를 사용하여 단위 테스트 실행](../test/run-unit-tests-with-test-explorer.md)   
 [관리 코드용 Microsoft 단위 테스트 프레임워크를 사용하여 .NET Framework용 단위 테스트 작성](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)