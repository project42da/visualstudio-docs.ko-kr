---
title: IDiaReadExeAtRVACallback | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaReadExeAtRVACallback interface
ms.assetid: b2892513-3952-4f99-9b98-60cb9b1fdc91
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: fdc876897d5106f4d03d5b25b51dec5572837f21
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idiareadexeatrvacallback"></a>IDiaReadExeAtRVACallback
클라이언트 응용 프로그램을 상대 가상 주소에 지정 된 대로 실행 파일의 바이트를 제공할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDiaReadExeAtRVACallback : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDiaReadExeAtRVACallback`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDiaReadExeAtRVACallback::ReadExecutableAtRVA](../../debugger/debug-interface-access/idiareadexeatrvacallback-readexecutableatrva.md)|지정 된 수의 지정 된 상대 가상 주소 (RVA) 실행 파일에서 바이트를 읽습니다.|  
  
## <a name="remarks"></a>설명  
 클라이언트 응용 프로그램 실행 파일의 파일에 상대 가상 주소를 사용 하 여 실행 파일의 바이트를 제공 하기 위해이 인터페이스를 구현 합니다. 절대 파일 오프셋을 사용 하려면 구현 된 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md) 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 메서드는 클라이언트 응용 프로그램에서 구현 하 고에 전달 되는 [idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) 파일을 읽기 위한 대체 방법으로 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)