---
title: IDiaStackWalkFrame | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackWalkFrame interface
ms.assetid: 42d82845-d6f6-4846-9ecd-9dd169216077
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: be50964aaadad30aa13d6627be2ad1637e6123b3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiastackwalkframe"></a>IDiaStackWalkFrame
호출 사이의 스택 컨텍스트를 유지 관리는 [idiaframedata:: Execute](../../debugger/debug-interface-access/idiaframedata-execute.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
IDiaStackWalkFrame : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDiaStackWalkFrame`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDiaStackWalkFrame::get_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-get-registervalue.md)|레지스터의 값을 검색합니다.|  
|[IDiaStackWalkFrame::put_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-put-registervalue.md)|레지스터의 값을 설정합니다.|  
|[IDiaStackWalkFrame::readMemory](../../debugger/debug-interface-access/idiastackwalkframe-readmemory.md)|이미지에서 메모리를 읽습니다.|  
|[IDiaStackWalkFrame::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddress.md)|가장 가까운 함수 반환 주소에 대 한 지정 된 스택 프레임을 검색합니다.|  
|[IDiaStackWalkFrame::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddressstart.md)|반송 주소에 도달 했거나 지정된 된 주소에 대 한 지정 된 스택 프레임을 검색합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 데 프로그램 실행 중 읽고 및 레지스터를 기록 하 고으로 메모리에 액세스 하 고 주소를 반환 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스를 구현 하 고 인터페이스의 인스턴스를 전달 하는 클라이언트 응용 프로그램은 [idiaframedata:: Execute](../../debugger/debug-interface-access/idiaframedata-execute.md) 메서드. 호출 될 때마다 레지스터의 상태를 유지 하기 위해이 인터페이스의 동일한 인스턴스를 다시 사용 된 `execute` 메서드. `execute` 메서드 반환 주소를 확인 하려면이 인터페이스를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md)