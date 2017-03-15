---
title: "시작(디버그 인터페이스 액세스 SDK) | Microsoft Docs"
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
  - ".dbg 파일"
  - "DBG 파일"
ms.assetid: cb3d040a-2846-40d7-bdbc-8a5beb5dd2f6
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# 시작(디버그 인터페이스 액세스 SDK)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

해당 디버그 인터페이스 액세스 \(DIA\) SDK 교육용 설명서와 DIA API를 사용 하는 방법을 보여 주는 샘플을 제공 합니다.  인터페이스와 메서드 DIA SDK에.pdb 파일과.dbg 파일을 열고 해당 콘텐츠 기호, 값, 특성, 주소 및 기타 디버깅 정보를 검색 하는 사용자 지정 응용 프로그램을 개발 하는 데 사용 합니다.  또한이 SDK 기호를 C\+\+ 응용 프로그램에 관련 된 속성에 대 한 참조 표를 제공 합니다.  
  
 DIA SDK를 가장 잘 사용 하려면 다음 사항을 숙지 해야 합니다.  
  
-   C \+ \+ 프로그래밍 언어  
  
-   COM 프로그래밍  
  
-   샘플 컴파일 Visual Studio 통합된 개발 환경 \(IDE\)  
  
 DIA SDK Visual Studio 정상적으로 설치 되어 있으며 기본 위치  *\[드라이브\]*\\Program Files\\Microsoft Visual Studio 9.0\\DIA SDK입니다.  이 사용 하는 데 필요한 모든 수 있도록 포함 하는 설치의 일부로 DIA SDK를 구현 하는 msdia90.dll를 자동으로 등록 됩니다 `dia2.h` 프로그램 및 링크를 `diaguids.lib`.  
  
 헤더: include\\dia2.h  
  
 라이브러리: lib\\diaguids.lib  
  
 DLL: bin\\msdia80.dll  
  
 IDL: idl\\dia2.idl  
  
## 단원 내용  
 [개요](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)  
 기본 아키텍처를 검토합니다.  
  
 [.Pdb 파일 쿼리](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)  
 DIA API를 사용 하 여.pdb 파일을 쿼리 하는 방법에 대 한 단계별 지침을 제공 합니다.  
  
## 참고 항목  
 [디버그 인터페이스 액세스 SDK](../../debugger/debug-interface-access/debug-interface-access-sdk.md)