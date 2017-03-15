---
title: "연습: XML 데이터를 데이터 집합으로 읽어 오기 | Microsoft Docs"
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
  - "데이터[Visual Studio], XML 파일 읽기"
  - "데이터 액세스[Visual Studio], XML 데이터"
  - "데이터 집합[Visual Basic], XML 데이터 읽기"
  - "데이터 읽기, XML 파일"
  - "파일 읽기, XML"
  - "XML 읽기"
  - "XML[Visual Studio], 읽기"
  - "XML 문서, 읽기"
ms.assetid: fae72958-0893-47d6-b3dd-9d42418418e4
caps.latest.revision: 18
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: XML 데이터를 데이터 집합으로 읽어 오기
ADO.NET에서는 간단하게 XML 데이터를 처리할 수 있는 방법을 제공합니다.  이 연습에서는 XML 데이터를 데이터 집합으로 로드하는 Windows 응용 프로그램을 만들어  데이터 집합을 <xref:System.Windows.Forms.DataGridView>에 표시합니다.  그리고 XML 파일 내용을 기반으로 하는 XML 스키마를 텍스트 상자에 표시합니다.  
  
 이 연습은 다음과 같은 다섯 개의 주요 단계로 구성됩니다.  
  
1.  새 프로젝트를 만듭니다.  
  
2.  데이터 집합으로 읽어 올 XML 파일을 만듭니다.  
  
3.  사용자 인터페이스를 만듭니다.  
  
4.  데이터 집합을 만들고 XML 파일을 읽은 다음 <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시합니다.  
  
5.  XML 파일을 기반으로 하는 XML 스키마를 <xref:System.Windows.Forms.TextBox> 컨트롤에 표시하는 코드를 추가합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 새 프로젝트 만들기  
 이 단계에서는 이 연습이 포함될 Visual Basic 또는 Visual C\# 프로젝트를 만듭니다.  
  
#### 새 Windows 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
2.  프로젝트 이름을 `ReadingXML`로 지정합니다.  
  
3.  **Windows 응용 프로그램**을 선택하고 **확인**을 클릭합니다.  자세한 내용은 [클라이언트 응용 프로그램](../Topic/Developing%20Client%20Applications%20with%20the%20.NET%20Framework.md)를 참조하십시오.  
  
     **ReadingXML** 프로젝트가 만들어져 솔루션 탐색기에 추가됩니다.  
  
## 데이터 집합으로 읽어 올 XML 파일 만들기  
 이 연습에서는 데이터 집합으로 XML 데이터를 읽어 오는 데 초점을 맞추고 있으므로 XML 파일 내용을 제공합니다.  
  
#### 데이터 집합으로 읽어 올 XML 파일을 만들려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
2.  **XML 파일**을 선택하고 파일 이름을 `authors.xml`로 지정한 다음 **추가**를 클릭합니다.  
  
     XML 파일이 디자이너로 로드되어 편집할 수 있습니다.  
  
3.  다음과 같은 코드를 XML 선언 아래의 편집기에 붙여넣습니다.  
  
    ```xml  
    <Authors_Table>  
      <authors>  
        <au_id>172-32-1176</au_id>  
        <au_lname>White</au_lname>  
        <au_fname>Johnson</au_fname>  
        <phone>408 496-7223</phone>  
        <address>10932 Bigge Rd.</address>  
        <city>Menlo Park</city>  
        <state>CA</state>  
        <zip>94025</zip>  
        <contract>true</contract>  
      </authors>  
      <authors>  
        <au_id>213-46-8915</au_id>  
        <au_lname>Green</au_lname>  
        <au_fname>Margie</au_fname>  
        <phone>415 986-7020</phone>  
        <address>309 63rd St. #411</address>  
        <city>Oakland</city>  
        <state>CA</state>  
        <zip>94618</zip>  
        <contract>true</contract>  
      </authors>  
      <authors>  
        <au_id>238-95-7766</au_id>  
        <au_lname>Carson</au_lname>  
        <au_fname>Cheryl</au_fname>  
        <phone>415 548-7723</phone>  
        <address>589 Darwin Ln.</address>  
        <city>Berkeley</city>  
        <state>CA</state>  
        <zip>94705</zip>  
        <contract>true</contract>  
      </authors>  
      <authors>  
        <au_id>267-41-2394</au_id>  
        <au_lname>Hunter</au_lname>  
        <au_fname>Anne</au_fname>  
        <phone>408 286-2428</phone>  
        <address>22 Cleveland Av. #14</address>  
        <city>San Jose</city>  
        <state>CA</state>  
        <zip>95128</zip>  
        <contract>true</contract>  
      </authors>  
      <authors>  
        <au_id>274-80-9391</au_id>  
        <au_lname>Straight</au_lname>  
        <au_fname>Dean</au_fname>  
        <phone>415 834-2919</phone>  
        <address>5420 College Av.</address>  
        <city>Oakland</city>  
        <state>CA</state>  
        <zip>94609</zip>  
        <contract>true</contract>  
      </authors>  
    </Authors_Table>  
    ```  
  
4.  **파일** 메뉴에서 **authors.xml 저장**을 가리킵니다.  
  
## 사용자 인터페이스 만들기  
 이 응용 프로그램의 사용자 인터페이스는 다음과 같은 내용으로 구성됩니다.  
  
-   XML 파일의 내용을 데이터로 표시할 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   XML 파일의 XML 스키마를 표시할 <xref:System.Windows.Forms.TextBox> 컨트롤  
  
-   <xref:System.Windows.Forms.Button> 컨트롤 두 개  
  
    -   첫 번째 단추는 XML 파일을 데이터 집합으로 읽어 들여 <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시합니다.  
  
    -   두 번째 단추는 데이터 집합에서 스키마를 추출하여 <xref:System.IO.StringWriter>를 통해 <xref:System.Windows.Forms.TextBox> 컨트롤에 표시합니다.  
  
#### 컨트롤을 폼에 추가하려면  
  
1.  디자인 뷰에서 `Form1`을 엽니다.  
  
2.  **도구 상자**에서 다음 컨트롤을 폼으로 끌어 옵니다.  
  
    -   <xref:System.Windows.Forms.DataGridView> 컨트롤 하나  
  
    -   <xref:System.Windows.Forms.TextBox> 컨트롤 하나  
  
    -   <xref:System.Windows.Forms.Button> 컨트롤 두 개  
  
3.  다음 속성을 설정합니다.  
  
    |컨트롤|Property|설정|  
    |---------|--------------|--------|  
    |`TextBox1`|**Multiline**|`true`|  
    ||**ScrollBars**|**세로**|  
    |`Button1`|**Name**|`ReadXmlButton`|  
    ||**Text**|`Read XML`|  
    |`Button2`|**Name**|`ShowSchemaButton`|  
    ||**Text**|`Show Schema`|  
  
## XML 데이터를 받을 데이터 집합 만들기  
 이 절차에서는 `authors`라는 새 데이터 집합을 만듭니다.  데이터 집합에 대한 자세한 내용은 [Visual Studio에서 데이터 집합 작업](../data-tools/dataset-tools-in-visual-studio.md)를 참조하십시오.  
  
#### XML 데이터를 받을 새 데이터 집합을 만들려면  
  
1.  **솔루션 탐색기**에 **Form1**의 소스 파일이 선택된 상태에서 **솔루션 탐색기** 도구 모음에서 **디자이너 보기**를 클릭합니다.  
  
2.  [도구 상자, 데이터 탭](../ide/reference/toolbox-data-tab.md)에서 **데이터 집합**을 **Form1**로 끌어 옵니다.  
  
3.  선택  **형식화 되지 않은 데이터 집합** 에 있는  **데이터 집합 추가** 클릭 하 고 대화 상자를  **확인**.  
  
     구성 요소 트레이에 **DataSet1**이 추가됩니다.  
  
4.  **속성** 창에서 **이름**과 <xref:System.Data.DataSet.DataSetName%2A> 속성을 `AuthorsDataSet`으로 설정합니다.  
  
## XML을 데이터 집합으로 읽어 오기 위해 이벤트 처리기 만들기  
 **Read XML** 단추를 클릭하면 XML 파일을 데이터 집합으로 읽어 온 다음 데이터 집합에 바인딩하는 <xref:System.Windows.Forms.DataGridView> 컨트롤에 속성을 설정합니다.  
  
#### ReadXmlButton\_Click 이벤트 처리기에 코드를 추가하려면  
  
1.  **솔루션 탐색기**에서 **Form1**을 선택하고 **솔루션 탐색기** 도구 모음에서 **디자이너 보기** 단추를 클릭합니다.  
  
2.  **Read XML** 단추를 두 번 클릭합니다.  
  
     **코드 편집기**가 `ReadXmlButton_Click` 이벤트 처리기에서 열립니다.  
  
3.  다음 코드를 `ReadXmlButton_Click` 이벤트 처리기에 입력합니다.  
  
     [!code-cs[VbRaddataFillingAndExecuting#2](../data-tools/codesnippet/CSharp/read-xml-data-into-a-dataset_1.cs)]
     [!code-vb[VbRaddataFillingAndExecuting#2](../data-tools/codesnippet/VisualBasic/read-xml-data-into-a-dataset_1.vb)]  
  
4.  `ReadXMLButton_Click` 이벤트 처리기 코드에서 `filepath =` 엔트리를 올바른 경로로 변경합니다.  
  
## Textbox에 스키마를 표시하기 위해 이벤트 처리기 만들기  
 **Show Schema** 단추를 클릭하면 <xref:System.IO.StringWriter> 개체를 만들어 스키마로 채우고 <xref:System.Windows.Forms.TextBox>에 표시합니다.  
  
#### ShowSchemaButton\_Click 이벤트 처리기에 코드를 추가하려면  
  
1.  **솔루션 탐색기**에서 **Form1**을 선택한 다음 **디자이너 보기** 단추를 클릭합니다.  
  
2.  **Show Schema** 단추를 두 번 클릭합니다.  
  
     **코드 편집기**가 `ShowSchemaButton_Click` 이벤트 처리기에서 열립니다.  
  
3.  다음 코드를 `ShowSchemaButton_Click` 이벤트 처리기에 입력합니다.  
  
     [!code-cs[VbRaddataFillingAndExecuting#3](../data-tools/codesnippet/CSharp/read-xml-data-into-a-dataset_2.cs)]
     [!code-vb[VbRaddataFillingAndExecuting#3](../data-tools/codesnippet/VisualBasic/read-xml-data-into-a-dataset_2.vb)]  
  
## 테스트  
 이제 폼을 테스트하여 예상한 대로 동작하는지 확인할 수 있습니다.  
  
#### 폼을 테스트하려면  
  
1.  F5 키를 눌러 응용 프로그램을 실행합니다.  
  
2.  **Read XML** 단추를 클릭합니다.  
  
     DataGridView에 XML 파일 내용이 표시됩니다.  
  
3.  **Show Schema** 단추를 클릭합니다.  
  
     텍스트 상자에 XML 파일의 XML 스키마가 표시됩니다.  
  
## 다음 단계  
 이 연습에서는 XML 파일의 내용을 기반으로 스키마를 만들고 XML 파일을 데이터 집합으로 읽어 들일 때의 기본 사항을 보여 줍니다.  이후에 수행할 수 있는 작업은 다음과 같습니다.  
  
-   데이터 집합에서 데이터를 편집하여 XML 형식으로 다시 기록합니다.  자세한 내용은 <xref:System.Data.DataSet.WriteXml%2A>을 참조하십시오.  
  
-   데이터 집합에서 데이터를 편집하여 데이터베이스에 기록합니다.  자세한 내용은 [데이터 저장](../data-tools/saving-data.md)을 참조하십시오.  
  
## 참고 항목  
 [데이터 연습](../Topic/Data%20Walkthroughs.md)   
 [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [Visual Studio의 XML 도구](../xml-tools/xml-tools-in-visual-studio.md)