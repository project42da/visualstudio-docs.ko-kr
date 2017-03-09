---
title: "방법: 샘플 데이터베이스 설치 | Microsoft Docs"
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
  - "Adventure Works 샘플 데이터베이스"
  - "데이터[Visual Studio], 샘플 데이터베이스"
  - "Northwind 샘플 데이터베이스"
  - "샘플 데이터베이스, Adventure Works"
  - "샘플 데이터베이스, Northwind"
ms.assetid: ed1291f6-604c-4972-ae22-0345c6dea12e
caps.latest.revision: 56
caps.handback.revision: 56
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 방법: 샘플 데이터베이스 설치
많은 데이터 예제에 Northwind, Pubs 및 AdventureWorks 예제 데이터베이스에 연결할 수 있는 기능이 필요합니다.  다음 절차를 사용하여 이러한 데이터베이스를 설치하고 연결할 수 있습니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## 데이터베이스 설치  
 많은 데이터 예제에 예제 데이터베이스를 웹 사이트에서 다운로드할 수 있는 기능이 필요합니다.  예제 데이터베이스에는 AdventureWorks, Northwind 및 Pubs 데이터베이스 등이 있습니다.  
  
#### SQL Server용 Northwind 및 Pubs 샘플 데이터베이스를 설치하려면  
  
1.  [Northwind 및 Pubs 샘플 데이터베이스](http://go.microsoft.com/fwlink?linkid=64296) 웹 사이트로 이동합니다.  
  
2.  설치 관리자를 다운로드하여 실행합니다.  
  
     설치 관리자에서 **SQL Server 2000 예제 데이터베이스** 폴더를 컴퓨터의 루트 폴더에 추가합니다\(예:  **C:\\SQL Server 2000 예제 데이터베이스**\).  
  
3.  원하는 데이터베이스의 SQL 스크립트\(Northwind 또는 Pubs\)를 찾습니다.  
  
    > [!WARNING]
    >  .MDF 데이터베이스 파일은 현재 버전의 SQL Server에서 사용할 수 있는 형식으로 쉽게 변환할 수 없으므로 스크립트를 사용하여 데이터베이스를 만드는 것이 좋습니다.  
  
4.  **서버 탐색기**에서 데이터베이스를 설치할 SQL Server 인스턴스와의 연결을 만듭니다.  사용할 특정 SQL Server가 없으면 Visual Studio와 함께 자동으로 설치된 데이터베이스를 사용할 수 있습니다.  이렇게 하려면 `(localdb) \v11.0`을 서버 이름으로 지정합니다.  
  
     연결을 만들려면 다음 단계를 수행합니다.  
  
    ###### SQL Server 인스턴스와의 연결을 만들려면  
  
    1.  **서버 탐색기**에서 **데이터 연결** 노드의 바로 가기 메뉴를 열고 **연결 추가**를 선택합니다.  
  
         **연결 추가** 대화 상자가 나타납니다.  
  
    2.  Pubs 또는 Northwind 데이터베이스를 만들 SQL Server 이름을 입력하거나 \(localdb\) \\v11.0을 입력합니다.  
  
    3.  **데이터베이스 이름 선택 또는 입력**의 목록에서 tempdb와 같은 데이터베이스를 선택합니다.  
  
    4.  **연결 테스트** 단추를 선택하여 모든 것이 올바르게 작동하는지 확인하고 **확인** 단추를 선택합니다.  
  
         새 연결 노드가 **서버 탐색기**에 나타납니다.  
  
5.  서버의 연결 노드에 대한 바로 가기 메뉴에서 **새 쿼리** 단추를 선택합니다.  
  
     편집 창이 열리고 빈 .sql 스크립트 파일이 표시됩니다.  
  
6.  instnwnd.sql 또는 instpubs.sql의 내용을 편집기 창에 붙여 넣습니다.  
  
7.  쿼리 실행 단추\(쿼리 창 오른쪽 위의 열린 녹색 삼각형 아이콘\)를 선택합니다.  
  
     쿼리가 정상적으로 실행되면 **명령이 완료되었습니다.** 메시지가 표시됩니다.  이 경우 Northwind 또는 pubs 데이터베이스가 작성된 것입니다.  
  
     이제 샘플 데이터베이스에 대한 연결을 추가해야 합니다.  **서버 탐색기**에서 **데이터 연결** 노드의 바로 가기 메뉴를 열고 **연결 추가**를 선택합니다.  
  
8.  앞에서 선택했던 것과 같은 데이터베이스 서버를 선택합니다. 단, 이번에는 데이터베이스 이름 선택 또는 입력에서 Northwind 또는 pubs 데이터베이스를 선택하고 **확인** 단추를 선택합니다.  
  
     새 노드가 샘플 데이터베이스에 대한 데이터 연결 아래에 나타납니다.  
  
9. 편집기 창을 닫고 쿼리 파일을 저장하지 않을 것입을 확인합니다.  데이터베이스를 만든 후에는 데이터베이스 생성 스크립트를 저장할 필요가 없습니다.  
  
#### AdventureWorks 샘플 데이터베이스를 설치하려면  
  
-   [CodePlex 웹 사이트](http://go.microsoft.com/fwlink/?linkid=87843)에서 AdventureWorks 샘플 데이터베이스를 다운로드합니다.  
  
#### Microsoft Access용 Northwind 샘플 데이터베이스를 설치하려면  
  
1.  Microsoft Access 2010 이상에서 Northwind용 온라인 템플릿을 검색하고 **데스크톱 Northwind 2007 샘플 데이터베이스**를 선택합니다.  
  
2.  Microsoft Access에서 데이터베이스 파일을 Northwind.accdb로 저장합니다.  
  
 Access 데이터베이스의 새 확장명은 .accdb입니다.  [Microsoft Access 2010을 사용한 데이터 프로그래밍](http://msdn.microsoft.com/library/office/ff965871.aspx)을 참조하세요.  Access를 사용하여 Northwind 데이터베이스에 연결하려면 [방법: Northwind 데이터베이스에 연결](../data-tools/how-to-connect-to-the-northwind-database.md)를 참조하세요.  
  
## .NET Framework 보안  
 예제 데이터베이스는 설명용으로 제공되었을 뿐, 반드시 최상의 보안 관리를 보여 주는 것은 아닙니다.  
  
## 참고 항목  
 [SQL Server 버전 및 Edition과 해당 구성 요소를 확인하는 방법](http://support.microsoft.com/kb/321185)   
 [연습: Visual Studio에서 로컬 데이터베이스 파일 만들기](../data-tools/create-a-sql-database-by-using-a-designer.md)   
 [방법: Northwind 데이터베이스에 연결](../data-tools/how-to-connect-to-the-northwind-database.md)