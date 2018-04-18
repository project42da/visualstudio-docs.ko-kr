---
title: IDiaStackWalkHelper | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2 interface
ms.assetid: d66e5c84-565d-494e-8486-f91db9a34548
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 881fcbb4f019ad9cb6321423c12269fb6e3ad78f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idiastackwalkhelper"></a>IDiaStackWalkHelper
프로그램 디버그 데이터베이스 (.pdb) 파일을 사용 하 여 스택을 탐색을 용이 하 게 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
IDiaStackWalkHelper: IUnknown  
  
```  
  
## <a name="methods-in-vtable-order"></a>VTable 순서의 메서드  
 다음 표에서의 메서드 `IDiaStackWalkHelper`:  
  
|메서드|설명|  
|------------|-----------------|  
|[IDiaStackWalkHelper::get_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-get-registervalue.md)|레지스터의 값을 검색합니다.|  
|[IDiaStackWalkHelper::put_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-put-registervalue.md)|레지스터의 값을 설정합니다.|  
|[IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)|메모리에 실행 파일의 이미지에서 데이터 블록을 읽습니다.|  
|[IDiaStackWalkHelper::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddress.md)|가장 가까운 함수 반환 주소에 대 한 지정 된 스택 프레임을 검색합니다.|  
|[IDiaStackWalkHelper::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddressstart.md)|또는 지정한 스택 주소 근처에서 반송 주소에 대 한 지정 된 스택 프레임을 검색합니다.|  
|[IDiaStackWalkHelper::frameForVA](../../debugger/debug-interface-access/idiastackwalkhelper-frameforva.md)|지정된 된 가상 주소 포함 된 스택 프레임을 검색 합니다.|  
|[IDiaStackWalkHelper::symbolForVA](../../debugger/debug-interface-access/idiastackwalkhelper-symbolforva.md)|지정된 된 가상 주소를 포함 하는 기호를 검색 합니다. **참고:** 기호 형식이 같아야 합니다. `SymTagFunctionType` (의 값은 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 열거형)입니다.|  
|[IDiaStackWalkHelper::pdataForVA](../../debugger/debug-interface-access/idiastackwalkhelper-pdataforva.md)|지정된 된 가상 주소와 연결 된 PDATA 데이터 블록을 반환 합니다.|  
|[IDiaStackWalkHelper::imageForVA](../../debugger/debug-interface-access/idiastackwalkhelper-imageforva.md)|실행 파일의 메모리 공간에 가상 주소 위치 지정 된 실행 파일의 시작 가상 주소를 검색 합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 스택 프레임의 목록을 프로그램 실행 중 생성 되는 파일에 대 한 정보를 얻으려면 DIA 코드에 의해 호출 됩니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 클라이언트 응용 프로그램 실행 중에 스택을 지원 하기 위해이 인터페이스를 구현 합니다. 이 인터페이스의 인스턴스를 전달 되는 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) 또는 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)   
 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)