---
title: "IDiaReadExeAtOffsetCallback | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "IDiaReadExeAtOffsetCallback 인터페이스"
ms.assetid: 3c961641-3ce3-4bc3-bd6e-a802fa3bec49
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaReadExeAtOffsetCallback
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

파일 위치에 의해 지정 된 실행 파일의 바이트 수를 제공 하는 클라이언트 응용 프로그램이 있습니다.  
  
## 구문  
  
```  
IDiaReadExeAtOffsetCallback : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDiaReadExeAtOffsetCallback`.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaReadExeAtOffsetCallback::ReadExecutableAt](../../debugger/debug-interface-access/idiareadexeatoffsetcallback-readexecutableat.md)|지정한 실행 파일의 지정 된 오프셋에서 시작 하는 바이트 수를 읽습니다.|  
  
## 설명  
 클라이언트 응용 프로그램 실행 파일의 파일에는 절대 오프셋을 사용 하 여 실행 파일에서 바이트를 제공 하기 위해이 인터페이스를 구현 합니다.  상대 가상 주소를 사용 하려면 구현에서 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 이 메서드는 클라이언트 응용 프로그램에서 구현 되 고 전달 되는 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 는 또 다른 방법은 파일을 읽는 방법입니다.  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)