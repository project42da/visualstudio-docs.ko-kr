---
title: "IDiaLoadCallback | Microsoft Docs"
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
  - "IDiaLoadCallback 인터페이스"
ms.assetid: 2f18c64c-2cf0-43fc-a447-21e82702ca2a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaLoadCallback
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

콜백 프로시저를 찾고, 따라서 위치 시도의 진행률을 보고 하는 사용자 인터페이스를 사용 하면 DIA 기호를 받습니다.  
  
## 구문  
  
```  
IDiaLoadCallback : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 메서드는이 인터페이스에 의해 노출 됩니다.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaLoadCallback::NotifyDebugDir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md)|.Exe 파일에 디버그 디렉터리를 찾을 수 없는 경우에 호출 됩니다.|  
|[IDiaLoadCallback::NotifyOpenDBG](../../debugger/debug-interface-access/idialoadcallback-notifyopendbg.md)|후보.dbg 파일을 열 때 호출 됩니다.|  
|[IDiaLoadCallback::NotifyOpenPDB](../../debugger/debug-interface-access/idialoadcallback-notifyopenpdb.md)|후보.pdb 파일을 열 때 호출 됩니다.|  
|[IDiaLoadCallback::RestrictRegistryAccess](../../debugger/debug-interface-access/idialoadcallback-restrictregistryaccess.md)|레지스트리 쿼리 기호 검색 경로 찾는 데 사용할 수 있는지 확인 합니다.|  
|[IDiaLoadCallback::RestrictSymbolServerAccess](../../debugger/debug-interface-access/idialoadcallback-restrictsymbolserveraccess.md)|액세스 기호 서버의 기호를 확인할 수 있는지 여부를 결정 합니다.|  
  
## 설명  
 이 인터페이스를 구현 하 고 참조를 호출 하 여 제공 하는 클라이언트 응용 프로그램은 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 메서드.  
  
 로드 프로세스에 부과 될 수 있습니다 추가 제한 사항에 대 한 참조를 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md) 인터페이스입니다.  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)