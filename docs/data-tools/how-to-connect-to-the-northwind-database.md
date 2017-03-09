---
title: "방법: Northwind 데이터베이스에 연결 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "연결[Visual Studio], Northwind 데이터베이스"
  - "Northwind 샘플 데이터베이스"
ms.assetid: cc6cb79f-d035-41f8-b398-8d4a45922bfb
caps.latest.revision: 29
caps.handback.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 방법: Northwind 데이터베이스에 연결
Visual Studio를 사용하여 데이터베이스 응용 프로그램을 만드는 방법을 배우려면 Northwind 데이터베이스에 연결하여 해당 제품의 설명서에 나와 있는 여러 예제를 연습해 보아야 합니다.  진행하는 예제에 따라 SQL Server 또는 데이터베이스 파일의 데이터베이스\(예: Microsoft Access 또는 SQL Server용 데이터베이스\)에 연결됩니다.  
  
## Northwind 데이터베이스에 대한 데이터 연결 만들기  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### Northwind 데이터베이스에 대한 데이터 연결을 만들려면\(SQL Server\)  
  
1.  **보기** 메뉴에서 **서버 탐색기**\/**데이터베이스 탐색기**를 선택합니다.  
  
2.  **서버 탐색기**\/**데이터베이스 탐색기**에서 **데이터 연결**의 바로 가기 메뉴를 연 다음 **연결 추가**를 선택합니다.  
  
     **연결 추가**를 선택하면 **데이터 소스 선택** 대화 상자 또는 **연결 추가** 대화 상자가 나타납니다.  
  
3.  **데이터 소스 선택** 대화 상자가 나타나면 **Microsoft SQL Server**를 선택하고 **확인**을 선택합니다.  
  
     **연결 추가** 대화 상자가 나타나는 경우 **데이터 소스**가 **Microsoft SQL Server\(SqlClient\)**가 아니면 **변경** 단추를 선택하여 **데이터 소스 변경** 대화 상자를 열고 **Microsoft SQL Server**를 선택한 후에 **확인** 단추를 선택합니다.  
  
4.  **서버 이름** 목록에서 Northwind 데이터베이스가 있는 서버의 이름을 지정합니다.  
  
5.  사용 중인 SQL Server 및 Northwind 데이터베이스 버전의 요구 사항에 따라 **Windows 인증 사용** 또는 **SQL Server 인증 사용**을 선택한 다음 SQL Server를 실행 중인 컴퓨터에 로그온하는 데 사용할 사용자 이름과 암호를 입력합니다.  
  
6.  **데이터베이스 이름 선택 또는 입력** 목록에서 Northwind 데이터베이스를 선택합니다.  
  
7.  **연결 테스트**를 선택하여 Northwind 데이터베이스에 대한 연결을 확인합니다.  
  
8.  **확인**을 선택합니다.  
  
     Northwind 데이터베이스에 대한 데이터 연결이 **서버 탐색기**\/**데이터베이스 탐색기**에 추가됩니다.  
  
 SQL Server 데이터베이스의 원격 인스턴스에 연결할 수 있을 뿐 아니라 데이터베이스가 포함된 실제 파일에 직접 연결할 수도 있습니다.  그러므로 응용 프로그램의 일부분으로 데이터베이스 파일을 배포할 수 있는 프로젝트에 데이터베이스 파일을 추가할 수 있습니다.  현재 지원되는 로컬 데이터베이스 파일은 SQL Server Compact 데이터베이스 파일\(.sdf\), [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] 및 SQL Server Express 데이터베이스 파일\(.mdf\), 그리고 Microsoft Access 데이터베이스 파일\(.mdb 또는 .accdb\)입니다.  
  
#### Northwind 데이터베이스\(SQL Server 데이터베이스 파일\(.mdf\)에 대한 데이터 연결을 만들려면  
  
1.  **보기** 메뉴에서 **서버 탐색기**\/**데이터베이스 탐색기**를 선택합니다.  
  
2.  **서버 탐색기**\/**데이터베이스 탐색기**에서 **데이터 연결**의 바로 가기 메뉴를 연 다음 **연결 추가**를 선택합니다.  
  
     **연결 추가**를 선택하면 **연결 추가** 대화 상자 또는 **데이터 소스 선택** 대화 상자가 나타납니다.  
  
3.  **데이터 소스 선택** 대화 상자가 나타나면 **Microsoft SQL Server 데이터베이스 파일**을 선택하고 **확인**을 선택합니다.  
  
4.  **연결 추가** 대화 상자가 나타나면 **데이터 소스**가 **Microsoft SQL Server 데이터베이스 파일\(SqlClient\)**로 설정되어 있는지 확인합니다.  데이터 소스가 **Microsoft SQL Server 데이터베이스 파일\(SqlClient\)**로 설정되어 있지 않으면 **변경**을 선택하여 **데이터 소스 변경** 대화 상자를 열고 **Microsoft SQL Server 데이터베이스 파일**을 선택한 후에 **확인** 단추를 선택합니다.  
  
5.  **찾아보기**를 선택하여 Northwind 데이터베이스가 포함된 .mdf 파일을 찾습니다.  
  
6.  사용 중인 Northwind 데이터베이스 버전의 요구 사항에 따라 **Windows 인증 사용** 또는 **SQL Server 인증**을 선택한 다음 SQL Server를 실행 중인 컴퓨터에 로그온하는 데 사용할 사용자 이름과 암호를 입력합니다.  
  
7.  **확인** 단추를 선택합니다.  
  
     Northwind 데이터베이스에 대한 데이터 연결이 **서버 탐색기**\/**데이터베이스 탐색기**에 추가됩니다.  
  
> [!NOTE]
>  [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]에는 Northwind 데이터베이스 파일\(.mdf\)에 적용되는 변경 내용이 포함되어 있습니다.  자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)를 참조하세요.  
  
#### Northwind 데이터베이스에 대한 데이터 연결을 만들려면\(Access 데이터베이스 파일\(.mdb 또는 .accdb\)\)  
  
1.  **보기** 메뉴에서 **서버 탐색기**\/**데이터베이스 탐색기**를 선택합니다.  
  
2.  **서버 탐색기**\/**데이터베이스 탐색기**에서 **데이터 연결**의 바로 가기 메뉴를 연 다음 **연결 추가**를 선택합니다.  
  
     **연결 추가**를 선택하면 **연결 추가** 대화 상자 또는 **데이터 소스 선택** 대화 상자가 나타납니다.  
  
3.  **데이터 소스 선택** 대화 상자가 나타나면 **Microsoft Access 데이터베이스 파일**을 선택하고 **확인**을 선택합니다.  
  
4.  **연결 추가** 대화 상자가 나타나면 **데이터 소스**가 **Microsoft Access 데이터베이스 파일**로 설정되어 있는지 확인합니다.  데이터 소스가 **Microsoft Access 데이터베이스 파일**로 설정되어 있지 않으면 **변경**을 선택하여 **데이터 소스 변경** 대화 상자를 열고 **Microsoft Access 데이터베이스 파일**을 선택한 후에 **확인** 단추를 선택합니다.  
  
5.  **찾아보기**를 선택하여 Northwind 데이터베이스가 포함된 .mdb 또는 .accdb 파일을 찾습니다.  
  
6.  사용 중인 Northwind 데이터베이스 버전에 필요한 경우 사용자 이름과 암호를 입력합니다.  
  
7.  **확인**을 선택합니다.  
  
     Northwind 데이터베이스에 대한 데이터 연결이 **서버 탐색기**\/**데이터베이스 탐색기**에 추가됩니다.  
  
## 참고 항목  
 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)   
 [Microsoft Access 2010을 사용한 데이터 프로그래밍](http://msdn.microsoft.com/library/office/ff965871.aspx)   
 [데이터 연습](../Topic/Data%20Walkthroughs.md)