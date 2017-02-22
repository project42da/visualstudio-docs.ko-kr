---
title: "IDiaLoadCallback2 | Microsoft Docs"
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
  - "IDiaLoadCallback2 인터페이스"
ms.assetid: 9a44277d-cbed-4811-9bad-5a2aa0f09323
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaLoadCallback2
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

콜백 프로시저를 찾고, 찾는 과정에 적용 하는 제한 허용 DIA 기호를 받습니다.  
  
## 구문  
  
```  
IDiaLoadCallback2 : IDiaLoadCallback  
```  
  
## 메서드에서 Vtable 순서  
 방법 외에 [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md) 인터페이스,이 인터페이스는 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaLoadCallback2::RestrictOriginalPathAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictoriginalpathaccess.md)|원래 디버그 디렉터리에서.pdb 파일의 찾을 경우 결정 합니다.|  
|[IDiaLoadCallback2::RestrictReferencePathAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictreferencepathaccess.md)|.Exe 파일이 있는 경로에서.pdb 파일을 찾을 수 있는지 여부를 결정 합니다.|  
|[IDiaLoadCallback2::RestrictDBGAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictdbgaccess.md)|.Dbg 파일에서 디버그 정보를 찾을 수 있는지 여부를 결정 합니다.|  
|[IDiaLoadCallback2::RestrictSystemRootAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictsystemrootaccess.md)|시스템 루트 디렉터리에.pdb 파일을 검색할 수 있는지 여부를 결정 합니다.|  
  
## 설명  
 이 인터페이스를 구현 하 고 참조를 호출 하 여 제공 하는 클라이언트 응용 프로그램은 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 메서드.  메서드를 모두 구현 해야는 [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md) 인터페이스를 합니다.  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md)