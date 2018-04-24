---
title: IDiaEnumStackFrames | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumStackFrames interface
ms.assetid: 3d1e8403-c9fc-42ff-ae35-0ab9a5ed2ad7
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 64539a1f10cfa2a263e36095cea40e58244ef6d8
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumstackframes"></a>IDiaEnumStackFrames
사용할 수 있는 다양 한 스택 프레임을 열거 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IDiaEnumStackFrames::Next](../../debugger/debug-interface-access/idiaenumstackframes-next.md)|열거형 시퀀스에서 지정된 된 수의 스택 프레임 요소를 검색합니다.|  
|[IDiaEnumStackFrames::Reset](../../debugger/debug-interface-access/idiaenumstackframes-reset.md)|열거형 시퀀스 시작 부분으로 다시 설정합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 가져올는 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) 또는 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md) 메서드.  
  
## <a name="example"></a>예제  
 다운로드 하 고 사용 하는 방법을 보여 주는이 예제는 `IDiaEnumStackFrames` 인터페이스입니다. 참조는 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md) 의 구현에 대 한 인터페이스는 `PrintStackFrame` 함수입니다.  
  
```C++  
void DumpStackFrames(IDiaStackWalker*     pStackWalker,  
                     IDiaStackWalkHelper* pStackWalkHelper,  
                     CV_CPU_TYPE_e        cpuType)  
{  
    if (pStackWalker != NULL && pStackWalkHelper != NULL)  
    {  
        CComPtr<IDiaEnumStackFrames> pEnumsFrames;  
        HRESULT hr;  
        hr = pStackWalker->getEnumFrames2(cpuType, pStackWalkHelper, &pEnumFrames);  
        if (SUCCEEDED(hr) && pEnumFrames != NULL)  
        {  
             CComPtr<IDiaStackFrame> pStackFrame;  
             DWORD celt = 0;  
  
             while (pEnumFrames->Next(1, &pStackFrame, &celt) == S_OK)  
             {  
                 PrintStackFrame(pStackFrame);  
             }  
             pStackFrame = NULL;  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)   
 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)   
 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)