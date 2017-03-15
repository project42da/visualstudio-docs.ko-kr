---
title: "검색 식의 고급 검색 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도움말 뷰어 2.0, 코드 검색"
  - "도움말 뷰어 2.0, 프로그래밍 언어에 따른 코드 검색"
  - "도움말 뷰어 2.0, 키워드 검색"
  - "도움말 뷰어 2.0, 제목 검색"
  - "코드 검색[도움말 뷰어 2.0]"
  - "제목 검색[도움말 뷰어 2.0]"
ms.assetid: 0cdc1746-8481-45ec-9c53-d0d89cdcbd5e
caps.latest.revision: 9
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 9
---
# 검색 식의 고급 검색 연산자
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

고급 검색 연산자를 사용하면 간단한 검색 표현으로부터 더 복잡한 검색 표현을 만들어 콘텐츠 검색을 상세하게 할 수 있다.  다음 표에서 볼 수 있듯이 이러한 연산자는 쿼리를 실행할 컨텍스트를 제한합니다.  
  
> [!WARNING]
>  검색 엔진이 이를 인식하려면 최종 콜론을 포함하여 고급 검색 연산자를 입력하고 콜론 앞에 공백을 포함하지 않아야 합니다.  
  
|검색하기|사용할 도구|예제|결과|  
|----------|------------|--------|--------|  
|항목 제목의 용어|제목:|제목:binaryreader|제목에 "binaryreader"를 포함하는 항목입니다.|  
|코드 예제의 용어|코드:|코드:readdouble|코드 예제에서 "readdouble"을 포함하는 항목입니다.|  
|특정 프로그래밍 언어 예제의 용어|코드:vb:|코드:vb:문자열|Visual Basic 예제에서 "문자열"을 포함하는 항목입니다.|  
|특정 인덱스 키워드에 관련된 항목|키워드:|키워드:readbyte|"Readbyte" 인덱스 키워드에 관련된 항목입니다.|  
  
 다음 코드를 사용할 수 있습니다. 여러 프로그래밍 언어 중 하나에 대한 콘텐츠를 찾을 수 있는 연산자는 특정 프로그래밍 언어로 표시된 내용에만 결과를 반환합니다.  다음 표에 이 연산자를 지원하는 프로그래밍 언어의 목록이 나와 있습니다.  
  
|프로그래밍 언어|사용할 도구|  
|--------------|------------|  
|Visual Basic|코드:vb<br /><br /> 또는<br /><br /> 코드:visualbasic|  
|C\#|코드:c\#<br /><br /> 또는<br /><br /> 코드:csharp|  
|C\+\+|코드:cpp<br /><br /> 또는<br /><br /> 코드:C\+\+<br /><br /> 또는<br /><br /> 코드:cplusplus|  
|\/F|코드:f\#<br /><br /> 또는<br /><br /> 코드:fsharp|  
|JavaScript|코드:javascript<br /><br /> 또는<br /><br /> 코드:js|  
|XAML|code:xaml|  
  
## 참고 항목  
 [검색 식의 논리 연산자](../ide/logical-operators-in-search-expressions.md)   
 [전체 텍스트 검색 팁](../ide/full-text-search-tips.md)