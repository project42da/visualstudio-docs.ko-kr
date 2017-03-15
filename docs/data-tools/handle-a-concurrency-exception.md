---
title: "연습: 동시성 예외 처리 | Microsoft Docs"
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
  - "동시성 제어, 예외"
  - "동시성 제어, 연습"
  - "데이터 동시성, 연습"
  - "데이터 집합[Visual Basic], 오류"
  - "예외 처리, 동시성 문제"
  - "데이터 집합 업데이트, 오류"
ms.assetid: 73ee9759-0a90-48a9-bf7b-9d6fc17bff93
caps.latest.revision: 23
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: 동시성 예외 처리
두 명의 사용자가 동시에 데이터베이스에 있는 동일한 데이터를 변경하려고 하면 동시성 예외\(<xref:System.Data.DBConcurrencyException>\)가 발생합니다.  이 연습에서는 <xref:System.Data.DBConcurrencyException>을 catch하고 오류가 발생한 행을 찾아서 이를 처리하는 한 가지 전략을 보여 주는 Windows 응용 프로그램을 만듭니다.  
  
 이 연습에서는 다음 과정을 안내합니다.  
  
1.  **Windows 응용 프로그램** 프로젝트를 새로 만듭니다.  
  
2.  Northwind `Customers` 테이블을 기반으로 새 데이터 집합을 만듭니다.  
  
3.  데이터를 표시할 수 있도록 <xref:System.Windows.Forms.DataGridView>가 있는 폼을 만듭니다.  
  
4.  Northwind 데이터베이스의 `Customers` 테이블에 있는 데이터를 사용하여 데이터 집합을 채웁니다.  
  
5.  데이터 집합을 채운 후 Visual Studio에서 [Visual Database Tools](http://msdn.microsoft.com/ko-kr/6b145922-2f00-47db-befc-bf351b4809a1)를 사용하여 `Customers` 데이터 테이블에 직접 액세스하고 레코드를 변경합니다.  
  
6.  그런 다음 폼에서 동일한 레코드를 다른 값으로 변경하고 데이터 집합을 업데이트한 다음 변경된 내용을 데이터베이스에 쓰려고 시도합니다. 이렇게 하면 동시성 오류가 발생합니다.  
  
7.  오류를 catch한 다음, 계속하여 데이터베이스를 업데이트할 것인지 아니면 업데이트를 취소할 것인지 결정할 수 있도록 서로 다른 레코드 버전을 표시합니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음과 같은 요건이 필요합니다.  
  
-   업데이트를 수행할 수 있는 권한으로 Northwind 샘플 데이터베이스에 액세스합니다.  자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)을 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 새 프로젝트 만들기  
 연습을 시작하려면 먼저 새 Windows 응용 프로그램을 만듭니다.  
  
#### 새로운 Windows 응용 프로그램 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
2.  **프로젝트 형식** 창에서 프로그래밍 언어를 선택합니다.  
  
3.  **템플릿** 창에서 **Windows 응용 프로그램**을 선택합니다.  
  
4.  프로젝트의 이름을 `ConcurrencyWalkthrough`로 지정한 다음 **확인**을 클릭합니다.  
  
     프로젝트가 **솔루션 탐색기**에 추가되고 새 폼이 디자이너에 표시됩니다.  
  
## Northwind 데이터 집합 만들기  
 이 단원에서는 `NorthwindDataSet`이라는 데이터 집합을 만듭니다.  
  
#### NorthwindDataSet을 만들려면  
  
1.  **데이터** 메뉴에서 **새 데이터 소스 추가**를 선택합니다.  
  
     [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)가 열립니다.  
  
2.  **데이터 소스 형식 선택** 페이지에서 **데이터베이스**를 선택합니다.  
  
3.  사용할 수 있는 연결 목록에서 Northwind 샘플 데이터베이스에 대한 연결을 선택하거나, 연결 목록에 해당 연결이 없을 경우 **새 연결**을 클릭합니다.  
  
    > [!NOTE]
    >  로컬 데이터베이스 파일에 연결할 경우 프로젝트에 파일을 추가할 것인지를 묻는 메시지가 표시되면 **아니요**를 선택합니다.  
  
4.  **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지에서 **다음**을 클릭합니다.  
  
5.  **테이블** 노드를 확장하고 `Customers` 테이블을 선택합니다.  데이터 집합의 기본 이름은 `NorthwindDataSet`입니다.  
  
6.  **마침**을 클릭하여 프로젝트에 데이터 집합을 추가합니다.  
  
## 데이터 바인딩된 DataGridView 컨트롤 만들기  
 이 단원에서는 **데이터 소스** 창에서 Windows Form으로 **Customers** 항목 개체를 끌어 <xref:System.Windows.Forms.DataGridView>를 만듭니다.  
  
#### Customers 테이블에 바인딩된 DataGridView를 만들려면  
  
1.  **데이터** 메뉴에서 **데이터 소스 표시**를 선택하여 **데이터 소스 창**을 엽니다.  
  
2.  **데이터 소스** 창에서 **NorthwindDataSet** 노드를 확장하고 **Customers** 테이블을 선택합니다.  
  
3.  테이블 노드에서 아래쪽 화살표를 클릭하고 드롭다운 목록에서 **DataGridView**를 선택합니다.  
  
4.  테이블을 폼의 빈 영역으로 끌어 옵니다.  
  
     `CustomersDataGridView`라는 <xref:System.Windows.Forms.DataGridView> 컨트롤과 `CustomersBindingNavigator`라는 <xref:System.Windows.Forms.BindingNavigator>가 <xref:System.Windows.Forms.BindingSource>에 바인딩되고, 이는 다시 `NorthwindDataSet`의 `Customers` 테이블에 바인딩됩니다.  
  
## 검사점  
 이제 폼을 테스트하여 이 지점까지 예상한 대로 동작하는지 확인할 수 있습니다.  
  
#### 폼을 테스트하려면  
  
1.  F5 키를 눌러 응용 프로그램을 실행합니다.  
  
     `Customers` 테이블의 데이터로 채워진 <xref:System.Windows.Forms.DataGridView> 컨트롤이 있는 폼이 표시됩니다.  
  
2.  **디버그** 메뉴에서 **디버깅 중지**를 선택합니다.  
  
## 동시성 오류 처리  
 오류를 처리하는 방법은 응용 프로그램의 기본이 되는 특정 비즈니스 규칙에 따라 달라집니다.  이 연습의 경우 동시성 오류가 발생한 후 다음과 같은 동시성 오류 처리 방법을 보여 줍니다.  
  
 이 응용 프로그램은 사용자에게 세 가지 버전의 레코드를 보여 줍니다.  
  
-   데이터베이스의 현재 레코드  
  
-   데이터 집합에 로드된 원래 레코드  
  
-   데이터 집합에서 변경할 내용  
  
 따라서 사용자는 제안된 버전으로 데이터베이스를 덮어 쓰거나 업데이트를 취소한 다음 데이터베이스의 새 값으로 데이터 집합을 새로 고칠 수 있습니다.  
  
#### 동시성 오류를 처리할 수 있도록 하려면  
  
1.  사용자 지정 오류 처리기를 만듭니다.  
  
2.  사용자에게 선택 목록을 표시합니다.  
  
3.  사용자의 응답을 처리합니다.  
  
4.  업데이트를 다시 보내거나 데이터 집합의 데이터를 다시 설정합니다.  
  
### 동시성 오류를 처리할 코드 추가  
 업데이트를 수행하는데 예외가 발생하면 일반적으로 예외에서 제공하는 정보를 바탕으로 조치를 취하게 됩니다.  
  
 이 단원에서는 데이터베이스를 업데이트하려고 시도하는 코드를 추가하고 <xref:System.Data.DBConcurrencyException>이 발생한 경우 이를 처리하고 다른 예외도 있으면 처리합니다.  
  
> [!NOTE]
>  이 연습의 뒷부분에서 `CreateMessage` 및 `ProcessDialogResults` 메서드를 추가합니다.  
  
##### 동시성 오류에 대한 오류 처리를 추가하려면  
  
1.  `Form1_Load` 메서드 아래에 다음 코드를 추가합니다.  
  
     [!code-cs[VbRaddataConcurrency#1](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_1.cs)]
     [!code-vb[VbRaddataConcurrency#1](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_1.vb)]  
  
2.  다음과 같이 되도록 `CustomersBindingNavigatorSaveItem_Click` 메서드를 대체하여 `UpdateDatabase` 메서드를 호출합니다.  
  
     [!code-cs[VbRaddataConcurrency#2](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_2.cs)]
     [!code-vb[VbRaddataConcurrency#2](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_2.vb)]  
  
### 사용자에게 선택 목록 표시  
 방금 작성한 코드는 사용자에게 오류 정보를 표시하는 `CreateMessage` 프로시저를 호출합니다.  이 연습에서는 사용자에게 각기 다른 버전의 레코드를 표시하는 메시지 상자를 사용하여, 사용자가 변경 내용으로 레코드를 덮어쓸 것인지 아니면 편집을 취소할 것인지 선택할 수 있게 합니다.  사용자가 메시지 상자의 옵션을 선택하면 즉, 단추를 클릭하면 응답이 `ProcessDialogResult` 메서드로 전달됩니다.  
  
##### 사용자에게 표시할 메시지를 만들려면  
  
-   다음과 같은 코드를 **코드 편집기**에 추가하여 메시지를 만듭니다.  `UpdateDatabase` 메서드 아래에 다음 코드를 입력합니다.  
  
     [!code-cs[VbRaddataConcurrency#4](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_3.cs)]
     [!code-vb[VbRaddataConcurrency#4](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_3.vb)]  
  
### 사용자의 응답 처리  
 메시지 상자에 대한 사용자의 응답을 처리하는 코드도 작성해야 합니다.  선택할 수 있는 옵션은 변경할 내용으로 데이터베이스의 현재 레코드를 덮어쓰거나 아니면 로컬 변경 내용을 포기하고 현재 데이터베이스에 있는 레코드를 사용하여 데이터 테이블을 새로 고치는 것입니다.  사용자가 "예"를 선택한 경우, <xref:System.Data.DataTable.Merge%2A> 메서드는 *preserveChanges* 인수는 `true`로 설정되어 함께 호출된다.  레코드의 원래 버전이 데이터베이스의 레코드와 일치하므로 성공적으로 업데이트를 끝낼 수 있습니다.  
  
##### 사용자가 메시지 상자에 입력한 내용을 처리하려면  
  
-   이전 단원에서 추가한 코드 아래에 다음 코드를 추가합니다.  
  
     [!code-cs[VbRaddataConcurrency#3](../data-tools/codesnippet/CSharp/handle-a-concurrency-exception_4.cs)]
     [!code-vb[VbRaddataConcurrency#3](../data-tools/codesnippet/VisualBasic/handle-a-concurrency-exception_4.vb)]  
  
## 테스트  
 이제 폼을 테스트하여 예상한 대로 동작하는지 확인할 수 있습니다.  동시성 위반을 시뮬레이션하려면 NorthwindDataSet을 채운 후 데이터베이스의 데이터를 변경해야 합니다.  
  
#### 폼을 테스트하려면  
  
1.  F5 키를 눌러 응용 프로그램을 실행합니다.  
  
2.  폼이 나타나면 계속 실행되도록 두고 Visual Studio IDE로 전환합니다.  
  
3.  **보기** 메뉴에서 **서버 탐색기**를 선택합니다.  
  
4.  **서버 탐색기**에서 응용 프로그램이 사용하고 있는 연결을 확장한 다음 **테이블** 노드를 확장합니다.  
  
5.  **Customers** 테이블을 마우스 오른쪽 단추로 클릭하고 **테이블 데이터 표시**를 선택합니다.  
  
6.  첫 번째 레코드\(`ALFKI`\)에서 `ContactName`을 `Maria Anders2`로 변경합니다.  
  
    > [!NOTE]
    >  다른 행으로 이동하여 변경 내용을 커밋합니다.  
  
7.  실행 중인 `ConcurrencyWalkthrough`의 폼으로 전환합니다.  
  
8.  폼의 첫 번째 레코드\(`ALFKI`\)에서 `ContactName`을 `Maria Anders1`로 변경합니다.  
  
9. **Save** 단추를 클릭합니다.  
  
     동시성 오류가 발생하고 메시지 상자가 표시됩니다.  
  
10. **No**를 클릭하면 업데이트가 취소되고 데이터 집합이 현재 데이터베이스에 있는 값으로 업데이트되고, **Yes**를 클릭하면 변경된 값이 데이터베이스에 기록됩니다.  
  
## 참고 항목  
 [데이터 연습](../Topic/Data%20Walkthroughs.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)