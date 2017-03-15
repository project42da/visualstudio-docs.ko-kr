---
title: "디버그 인터페이스 액세스 SDK | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "디버깅[DIA SDK]"
  - "디버거[DIA SDK]"
  - "DIA SDK"
ms.assetid: 4c0abe53-11d3-4b7a-bdc7-b054f85aaf40
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# 디버그 인터페이스 액세스 SDK
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Microsoft 디버그 인터페이스 액세스 소프트웨어 개발 키트 \(DIA SDK\) 디버그 Microsoft 사후 컴파일러 도구에서 생성 한 프로그램 데이터베이스 \(.pdb\) 파일에 저장 된 정보를 제공 합니다.  사후 컴파일러 도구에서 생성 하 여.pdb 파일의 형식은 상수 개정 수행 하기 때문에 노출 하는 형식이 없는 경우도 있습니다.  DIA API를 사용 하 여 검색 하 고.pdb 파일에 디버그 정보를 검색 하는 응용 프로그램을 개발할 수 있습니다.  이러한 응용 프로그램은 수 있습니다, 예를 들어, 스택 추적 정보를 보고 하 고 성능 데이터를 분석.  
  
## 단원 내용  
 [시작](../../debugger/debug-interface-access/getting-started-debug-interface-access-sdk.md)  
 DIA SDK의 개요 기능을 제공 하 고 필수 헤더 및 라이브러리 파일 같은 DIA SDK 설치 위치를 지정 합니다.  
  
 [.Pdb 파일 쿼리](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)  
 DIA API를 사용 하 여.pdb 파일을 쿼리 하는 방법에 지침을 제공 합니다.  
  
 [기호 및 기호 태그](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)  
 기호와 기호 태그는 DIA API를 사용 하는 방법에 대해 설명 합니다.  
  
 [참조](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)  
 인터페이스, 메서드, 열거 및 구조는 DIA api를 포함합니다.  
  
 [Dia2dump 샘플](../../debugger/debug-interface-access/dia2dump-sample.md)  
 DIA API를 사용 하 여 검색 하 고 디버그 정보를 탐색 하는 방법을 보여 줍니다.  
  
 [Dia2dump.cpp 소스 파일](../../debugger/debug-interface-access/dia2dump-cpp-source-file.md)  
 소스 코드를 사용 하 여 [Dia2dump 샘플](../../debugger/debug-interface-access/dia2dump-sample.md) DIA API를 보여 줍니다.