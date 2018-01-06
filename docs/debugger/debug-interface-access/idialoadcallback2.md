---
title: IDiaLoadCallback2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaLoadCallback2 interface
ms.assetid: 9a44277d-cbed-4811-9bad-5a2aa0f09323
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: ee2733643350b2fea9b78a9d876037497d35e41a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idialoadcallback2"></a>IDiaLoadCallback2
DIA 기호 찾기 프로시저, 찾기 프로세스에 적용할 수를 제한할 수에서 콜백을 받습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDiaLoadCallback2 : IDiaLoadCallback  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 메서드 외에도 [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md) 인터페이스,이 인터페이스는 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDiaLoadCallback2::RestrictOriginalPathAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictoriginalpathaccess.md)|원래 디버그 디렉터리에.pdb 파일을 찾는 경우를 결정 합니다.|  
|[IDiaLoadCallback2::RestrictReferencePathAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictreferencepathaccess.md)|.Exe 파일이 있는 경로에 허용 된.pdb 파일을 찾는 경우를 결정 합니다.|  
|[IDiaLoadCallback2::RestrictDBGAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictdbgaccess.md)|.Dbg 파일에서 디버그 정보를 찾고 허용 되는지 여부를 결정 합니다.|  
|[IDiaLoadCallback2::RestrictSystemRootAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictsystemrootaccess.md)|시스템 루트 디렉터리에.pdb 파일을 검색할 허용 된 경우를 결정 합니다.|  
  
## <a name="remarks"></a>설명  
 클라이언트 응용 프로그램이이 인터페이스를 구현 하 고 호출에 대 한 참조를 제공 된 [idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 메서드. 메서드를 모두 구현 하는 [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md) 인터페이스에도 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md)