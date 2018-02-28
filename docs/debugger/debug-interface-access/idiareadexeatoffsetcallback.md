---
title: IDiaReadExeAtOffsetCallback | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtOffsetCallback interface
ms.assetid: 3c961641-3ce3-4bc3-bd6e-a802fa3bec49
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: abb829d12f05a9c220bc22647659c438180d237e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idiareadexeatoffsetcallback"></a>IDiaReadExeAtOffsetCallback
클라이언트 응용 프로그램을 파일 위치에 따라 지정 된 대로 실행 파일의 바이트를 제공할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDiaReadExeAtOffsetCallback : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDiaReadExeAtOffsetCallback`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDiaReadExeAtOffsetCallback::ReadExecutableAt](../../debugger/debug-interface-access/idiareadexeatoffsetcallback-readexecutableat.md)|지정 된 실행 파일에서 지정된 된 오프셋에서 시작 하는 바이트 수를 읽습니다.|  
  
## <a name="remarks"></a>설명  
 클라이언트 응용 프로그램 실행 파일의 파일에 절대 오프셋을 사용 하 여 실행 파일의 바이트를 제공 하기 위해이 인터페이스를 구현 합니다. 상대 가상 주소를 사용 하려면 구현 된 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 메서드는 클라이언트 응용 프로그램에서 구현 하 고에 전달 되는 [idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 파일을 읽기 위한 대체 방법으로 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)