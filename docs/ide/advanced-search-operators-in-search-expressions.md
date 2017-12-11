---
redirect_url: /visualstudio/ide/logical-operators-in-search-expressions
ms.openlocfilehash: fe896af873197c95a4b226396e0b6333fdc40cfa
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
제목: "검색 식의 고급 검색 연산자 | Microsoft Docs" ms.custom: "" ms.date: "06/02/2017" ms.reviewer: "" ms.suite: "" ms.technology: 
  - "vs-help-viewer" ms.tgt_pltfrm: "" ms.topic: "article" helpviewer_keywords: 
  - "도움말 뷰어, 키워드 검색"
  - "도움말 뷰어, 코드 검색"
  - "도움말 뷰어, 프로그래밍 언어에 따른 코드 검색"
  - "제목 검색, 제목 검색"
  - "코드 검색 [도움말 뷰어]"
  - "제목 검색 [도움말 뷰어]" ms.assetid: 0cdc1746-8481-45ec-9c53-d0d89cdcbd5e caps.latest.revision: 9 author: "gewarren" ms.author: "gewarren" manager: ghogen
---
# <a name="advanced-search-operators-in-search-expressions"></a>검색 식의 고급 검색 연산자
도움말 뷰어에서 고급 검색 연산자를 사용하여 항목에서 검색어를 찾을 위치를 지정하여 콘텐츠 검색을 구체화합니다. 다음 표에서 4개의 사용 가능한 고급 검색 연산자를 설명합니다.

|검색 대상|기능|예제|결과|  
|-------------------|---------|-------------|------------|  
|항목 제목의 용어|title:|title:binaryreader|제목에 “binaryreader”가 포함된 항목입니다.|  
|코드 예제의 용어|code:|code:readdouble|코드 예제에 “readdouble”이 포함된 항목입니다.|  
|특정 프로그래밍 언어 예제의 용어|code:vb:|code:vb:string|Visual Basic 코드 예제에 “string”이 포함된 항목입니다.|  
|특정 인덱스 키워드와 연결된 항목|keyword:|keyword:readbyte|“readbyte” 인덱스 키워드와 연결된 항목입니다.|  

> [!WARNING]
>  검색 엔진이 이러한 연산자를 인식하려면 고급 검색 연산자 뒤에 불필요한 공백 없이 마지막으로 콜론을 입력해야 합니다.    

## <a name="programming-languages-for-code-examples"></a>코드 예제에 대한 프로그래밍 언어
연산자를 사용하여 다양한 프로그래밍 언어에 대한 콘텐츠를 찾을 수 있지만, 이 연산자는 프로그래밍 언어 레이블로 표시된 콘텐츠에 대한 결과만 반환합니다. 특정 프로그래밍 언어에 대한 예제를 반환하려면 다음과 같은 프로그래밍 언어 값 중 하나를 사용합니다.  

|프로그래밍 언어|검색 연산자 구문|  
|--------------------|---------|  
|Visual Basic|code:vb<br/>code:visualbasic|  
|C#|code:c#<br/>code:csharp|  
|C++|code:cpp<br/>code:c++<br/>code:cplusplus|  
|F#|code:f#<br/>code:fsharp|  
|JavaScript|code:javascript<br/>code:js|  
|XAML|code:xaml|
