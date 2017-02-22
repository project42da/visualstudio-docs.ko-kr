---
title: "연습: 코드 조각 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "코드 조각, 만들기"
  - "코드 조각, 가져오기"
  - "코드 조각, 참조"
  - "코드 조각, 바꾸기"
  - "코드 조각, 바로 가기"
  - "코드 조각, 템플릿"
ms.assetid: 0dcaae11-39cf-4463-9c90-2494321251c2
caps.latest.revision: 21
caps.handback.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 연습: 코드 조각 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

몇 가지 단계만으로 코드 조각을 만들 수 있습니다.  사용자가 해야 하는 일은 XML 파일을 만들고 해당 요소에 채운 후 코드를 추가하는 것입니다.  또한 참조 및 대체 매개 변수를 코드에 추가할 수 있습니다.  코드 조각 관리자의 가져오기 단추를 사용하여 설치된 Visual Studio에 코드 조각을 추가할 수 있습니다\(**도구\/코드 조각 관리자**\).  
  
> [!TIP]
>  코드 조각을 보다 쉽게 작성하는 방법에 대한 자세한 내용은 [Snippet Editor](http://go.microsoft.com/fwlink/?LinkId=251033) 와 같은 커뮤니티 도구가 있는 CodePlex 웹 사이트를 검색합니다.  
  
## 코드 조각 템플릿  
 다음은 기본적인 코드 조각 템플릿입니다.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<CodeSnippets  
    xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">  
    <CodeSnippet Format="1.0.0">  
        <Header>  
            <Title></Title>  
        </Header>  
        <Snippet>  
            <Code Language="">  
                <![CDATA[]]>  
            </Code>  
        </Snippet>  
    </CodeSnippet>  
</CodeSnippets>  
  
```  
  
### 코드 조각을 만들려면  
  
1.  Visual Studio에서 새 XML 파일을 만들고 위에 표시된 템플릿을 추가합니다.  
  
2.  코드 조각의 제목을 채웁니다. 예: 제목 요소의 "Hello World VB".  
  
3.  코드 요소의 언어 특성에 있는 코드 조각 언어를 입력합니다.  이 예제에서는 "VB"를 사용합니다.  
  
4.  코드 요소 안의 CDATA 섹션에 일부 코드를 추가합니다. 예를 들면 다음과 같습니다.  
  
    ```  
    <Code Language="VB">  
        <![CDATA[Console.WriteLine("Hello, World!")]]>  
    </Code>  
  
    ```  
  
5.  코드 조각을 VBCodeSnippet.snippet으로 저장합니다.  
  
### Visual Studio에 코드 조각을 추가하려면  
  
1.  코드 조각 관리자를 사용하여 Visual Studio 설치에 사용자 고유의 조각을 직접 추가할 수 있습니다.  코드 조각 관리자를 엽니다\(**도구\/코드 조각 관리자**\).  
  
2.  **가져오기** 단추를 클릭합니다.  
  
3.  이전 절차에서 코드 조각을 저장했던 위치로 이동하여 위치를 선택하고 **열기**를 클릭합니다.  
  
4.  **코드 조각 가져오기** 대화 상자를 열면 오른쪽 창 선택 항목에서 코드 조각을 추가할 위치를 선택하라는 메시지가 표시됩니다.  선택 항목 중 하나는 **내 코드 조각**이어야 합니다.  선택하고 **마침**을 클릭한 다음 **확인**을 클릭합니다.  
  
5.  코드 조각은 다음 위치로 복사됩니다.  
  
     `%USERPROFILE%\Documents\Visual Studio 2013\Code Snippets\Visual Basic\내 코드 조각`  
  
6.  Visual Basic 프로젝트와 코드 파일을 차례로 열어서 코드 조각을 테스트합니다.  파일의 상황에 맞는 메뉴에서 **코드 조각 삽입**을 클릭한 후 **내 코드 조각**을 클릭합니다.  이름이 **내 Visual Basic 코드 조각**인 코드 조각이 표시되어야 합니다.  두 번 클릭합니다.  
  
7.  코드에 삽입된 `Console.WriteLine("Hello, World!")`이 표시되어야 합니다.  
  
### 설명 및 바로 가기 필드 추가  
  
1.  코드 조각 관리자에서 설명 필드는 코드 조각에 대한 자세한 정보를 제공합니다.  바로 가기는 코드 조각을 삽입하기 위해 입력할 수 있는 태그입니다.  `%USERPROFILE%\Documents\Visual Studio 2013\Code Snippets\Visual Basic\My Code Snippet\VBCodeSnippet.snippet` 파일을 열어 추가한 코드 조각을 편집합니다.  
  
2.  헤더 요소에 만든 이 및 설명 요소를 추가하고 채웁니다.  
  
3.  헤더 요소는 다음과 같습니다.  
  
    ```  
    <Header>  
        <Title>Hello World VB</Title>  
        <Author>Myself</Author>  
        <Description>Says Hello to the world.</Description>  
    </Header>  
  
    ```  
  
4.  코드 조각 관리자를 열고 코드 조각을 선택합니다.  오른쪽 창에는 설명 및 만든 이 필드가 이제 채워진 것을 볼 수 있습니다.  
  
5.  바로 가기를 추가하려면 만든 이 및 설명 요소 옆에 바로 가기 요소를 추가합니다.  
  
    ```  
    <Header>  
        <Title>Hello World VB</Title>  
        <Author>Myself</Author>  
        <Description>Says Hello to the world.</Description>  
        <Shortcut>hello</Shortcut>  
    </Header>  
  
    ```  
  
6.  코드 조각 파일을 다시 저장합니다.  
  
7.  바로 가기를 테스트하려면 Visual Basic 프로젝트를 열고 코드 파일을 엽니다.  파일에 `hello`를 입력하고 TAB을 누릅니다.  코드 조각은 삽입되어야 합니다.  
  
### 참조 및 가져오기를 추가하려면  
  
1.  Visual Basic 코드 조각을 사용하면 References 요소를 사용하여 프로젝트에 참조를 추가하고 Imports 요소를 사용하여 Imports 선언을 추가할 수 있습니다. \(다른 언어의 코드 조각에는 이 기능이 없습니다.\) 예를 들어 코드 샘플의 `Console.WriteLine`을 `MessageBox.Show`로 변경하는 경우 System.Windows.Forms.dll 어셈블리를 프로젝트에 추가할 필요가 있습니다.  
  
2.  코드 조각을 엽니다.  
  
3.  코드 조각 요소 아래에 참조 요소를 추가합니다.  
  
    ```  
    <References>  
        <Reference>  
            <Assembly>System.Windows.Forms.dll</Assembly>  
        </Reference>  
    </References>  
  
    ```  
  
4.  코드 조각 요소 아래에 가져오기 요소를 추가합니다.  
  
    ```  
    <Imports>  
        <Import>  
           <Namespace>System.Windows.Forms</Namespace>  
        </Import>  
    </Imports>  
  
    ```  
  
5.  CDATA 섹션을 다음으로 변경합니다.  
  
    ```  
    <![CDATA[MessageBox.Show("Hello, World!")]]>  
    ```  
  
6.  코드 조각을 저장합니다.  
  
7.  Visual Basic 프로젝트를 열고 코드 조각을 추가합니다.  
  
8.  코드 파일의 맨 위에 가져오기 문이 표시됩니다.  
  
    ```  
    Imports System.Windows.Forms  
  
    ```  
  
9. 프로젝트의 속성을 찾습니다.  참조 탭에는 System.Windows.Forms.dll에 대한 참조가 포함되어 있습니다.  
  
### 대체 파일 추가  
  
1.  코드 조각의 일부를 사용자가 바꾸도록 하려는 경우가 있습니다. 예를 들어, 변수를 추가하고 사용자가 해당 변수를 현재 프로젝트의 변수로 바꾸도록 할 수 있습니다.  두 가지 형식의 교체인 리터럴과 개체를 제공할 수 있습니다.  리터럴은 몇 가지 유형\(문자열 리터럴, 변수 이름 또는 숫자 값의 문자열 표현\)의 문자열입니다.  문자열 이외의 일부 형식의 인스턴스 개체입니다.  이 절차에서 리터럴 대체 및 개체 대체를 선언하고 이러한 대체 사항을 참조하여 코드를 변경합니다.  
  
2.  코드 조각을 엽니다.  
  
3.  이 예제에서는 SQL 연결 문자열을 사용하므로, 적절한 참조를 추가하려면 가져오기 및 참조 요소를 변경해야 합니다.  
  
    ```  
    <References>  
        <Reference>  
            <Assembly>System.Data.dll</Assembly>  
        </Reference>  
        <Reference>  
            <Assembly>System.Xml.dll</Assembly>  
        </Reference>  
    </References>  
    <Imports>  
        <Import>  
            <Namespace>System.Data</Namespace>  
        </Import>  
        <Import>  
            <Namespace>System.Data.SqlClient</Namespace>  
        </Import>  
    </Imports>  
  
    ```  
  
4.  SQL 연결 문자열의 리터럴 대체를 선언하려면 Snippet 요소에서 Declarations 요소를 추가하고 그 안에 ID, 도구 설명, 대체 기본 값에 대한 하위 요소로 Literal 요소를 추가합니다.  
  
    ```  
    <Declarations>  
        <Literal>  
            <ID>SqlConnString</ID>  
            <ToolTip>Replace with a SQL connection string.</ToolTip>  
            <Default>"SQL connection string"</Default>  
        </Literal>  
    </Declarations>  
  
    ```  
  
5.  SQL 연결을 위한 개체 대체를 선언하려면 Declarations 요소 안에 Object 요소를 추가하고 ID, 개체 형식, 도구 설명 및 기본 값에 대한 하위 요소를 추가합니다.  결과 Declarations 요소는 다음과 같습니다.  
  
    ```  
    <Declarations>  
        <Literal>  
            <ID>SqlConnString</ID>  
            <ToolTip>Replace with a SQL connection string.</ToolTip>  
            <Default>"SQL connection string"</Default>  
        </Literal>  
        <Object>  
            <ID>SqlConnection</ID>  
            <Type>System.Data.SqlClient.SqlConnection</Type>  
            <ToolTip>Replace with a connection object in your application.</ToolTip>  
            <Default>dcConnection</Default>  
        </Object>  
    </Declarations>  
    ```  
  
6.  코드 섹션에서 $ 기호로 둘러 쌓인 대체 항목을 참조합니다. 예: `$replacement$`:  
  
    ```  
    <Code Language="VB" Kind="method body">  
        <![CDATA[Dim daCustomers As SqlDataAdapter  
            Dim selectCommand As SqlCommand  
  
            daCustomers = New SqlClient.SqlDataAdapter()  
            selectCommand = new SqlClient.SqlCommand($SqlConnString$)  
            daCustomers.SelectCommand = selectCommand  
            daCustomers.SelectCommand.Connection = $SqlConnection$]]>  
    </Code>  
    ```  
  
7.  코드 조각을 저장합니다.  
  
8.  Visual Basic 프로젝트를 열고 코드 조각을 추가합니다.  
  
9. 코드는 대체 `SQL 연결 문자열` 및 `dcConnection`가 밝은 오렌지색으로 강조 표시되는 것과 같이 표시되어야 합니다.  TAB을 눌러 서로 이동합니다.  
  
    ```  
    Dim daCustomers As SqlDataAdapter  
    Dim selectCommand As SqlCommand  
  
    daCustomers = New SqlClient.SqlDataAdapter()  
    selectCommand = New SqlClient.SqlCommand("SQL connection string")  
    daCustomers.SelectCommand = selectCommand  
    daCustomers.SelectCommand.Connection = dcConnection  
  
    ```  
  
## 참고 항목  
 [코드 조각 스키마 참조](../ide/code-snippets-schema-reference.md)