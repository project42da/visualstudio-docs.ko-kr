---
title: "IDiaReadExeAtRVACallback | Microsoft Docs"
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
  - "IDiaReadExeAtRVACallback 인터페이스"
ms.assetid: b2892513-3952-4f99-9b98-60cb9b1fdc91
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaReadExeAtRVACallback
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

상대 가상 주소에 지정 된 대로 실행 파일의 바이트 수를 제공 하는 클라이언트 응용 프로그램이 있습니다.  
  
## 구문  
  
```  
IDiaReadExeAtRVACallback : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDiaReadExeAtRVACallback`.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaReadExeAtRVACallback::ReadExecutableAtRVA](../../debugger/debug-interface-access/idiareadexeatrvacallback-readexecutableatrva.md)|지정한 상대 가상 주소 \(RVA\) 실행 파일을 시작 하는 바이트 수를 지정 된 수를 읽습니다.|  
  
## 설명  
 클라이언트 응용 프로그램 실행 파일의 파일에의 상대 가상 주소를 사용 하 여 실행 파일에서 바이트를 제공 하기 위해이 인터페이스를 구현 합니다.  구현 절대 파일 오프셋을 사용 하 여 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md) 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 이 메서드는 클라이언트 응용 프로그램에서 구현 되 고 전달 되는 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 는 또 다른 방법은 파일을 읽는 방법입니다.  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)