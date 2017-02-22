---
title: "개요(디버그 인터페이스 액세스 SDK) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "사용자 정의 형식"
  - ".dbg 파일"
  - "모듈"
  - "인터페이스[DIA SDK]"
  - "DBG 파일"
  - "프로시저[DIA SDK]"
  - "실행 파일"
  - "COM 개체, DIA SDK"
  - "컴파일 대상"
  - "실행 가능 이미지"
ms.assetid: 720b4479-a8bc-4fec-860e-80c1a0780405
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 개요(디버그 인터페이스 액세스 SDK)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

DIA SDK를 사용 하 여 Microsoft 디버그 정보에 액세스할 수 있습니다.  DIA SDK는 Microsoft 디버그 정보 형식 변경 될 때마다 코드를 다시 작성 하지 않고도 API 집합은 COM을 기반으로 제공 합니다.  DIA SDK를 집합의 디버그 정보를 생성 하 여.pdb 및.dbg 파일에 있는 이전 버전을 읽을 수 있습니다 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 버전 5.0 이상.  
  
 DIA sdk에서 인터페이스 마다 별도로 지정 하는 경우를 제외 하 고 다른 COM 개체를 나타냅니다.  추가 인터페이스 및 추가 개체를 만들 명시적으로 쿼리를 [IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md) 또는 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)를 대신 호출 하 여 `QueryInterface` 기존 인터페이스 포인터에 대 한.  
  
## 참고 항목  
 [IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md)   
 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)