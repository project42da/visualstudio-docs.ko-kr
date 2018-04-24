---
title: IDiaLoadCallback | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback interface
ms.assetid: 2f18c64c-2cf0-43fc-a447-21e82702ca2a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fbde460fadf89b27745fd05729fda6736fb3d3d7
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idialoadcallback"></a>IDiaLoadCallback
프로시저를 찾는 위치 시도의 진행률을 보고할 수 있는 사용자 인터페이스를 지원할 DIA 기호에서 콜백을 받습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDiaLoadCallback : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 메서드는이 인터페이스에 의해 노출 됩니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDiaLoadCallback::NotifyDebugDir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md)|.Exe 파일에는 디버그 디렉터리가 발견 되었을 때 호출 됩니다.|  
|[IDiaLoadCallback::NotifyOpenDBG](../../debugger/debug-interface-access/idialoadcallback-notifyopendbg.md)|후보.dbg 파일 열린 때 호출 됩니다.|  
|[IDiaLoadCallback::NotifyOpenPDB](../../debugger/debug-interface-access/idialoadcallback-notifyopenpdb.md)|후보.pdb 파일이 열린 때 호출 됩니다.|  
|[IDiaLoadCallback::RestrictRegistryAccess](../../debugger/debug-interface-access/idialoadcallback-restrictregistryaccess.md)|기호 검색 경로 찾을 레지스트리 쿼리를 사용할 수 있으면 결정 합니다.|  
|[IDiaLoadCallback::RestrictSymbolServerAccess](../../debugger/debug-interface-access/idialoadcallback-restrictsymbolserveraccess.md)|기호를 확인 하도록 기호 서버에 대 한 액세스 허용 된 경우를 결정 합니다.|  
  
## <a name="remarks"></a>설명  
 클라이언트 응용 프로그램이이 인터페이스를 구현 하 고 호출에 대 한 참조를 제공 된 [idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 메서드.  
  
 로드 프로세스에서 설정할 수 있는 추가 제한 사항에 대 한 참조는 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md) 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)