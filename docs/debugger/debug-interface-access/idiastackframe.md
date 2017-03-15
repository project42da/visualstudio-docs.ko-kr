---
title: "IDiaStackFrame | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaStackFrame 인터페이스"
ms.assetid: 486d25b8-a590-41c1-bdb5-faff3ae35632
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# IDiaStackFrame
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

스택 프레임의 속성을 노출합니다.  
  
## 구문  
  
```  
IDiaStackFrame : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음은이 인터페이스에 의해 지원 되는 방법입니다.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaStackFrame::get\_allocatesBasePointer](../../debugger/debug-interface-access/idiastackframe-get-allocatesbasepointer.md)|코드에서이 주소 범위에 대 한 기본 포인터 할당 되도록 나타내는 플래그를 검색 합니다.  이 메서드는 사용되지 않습니다.|  
|[IDiaStackFrame::get\_base](../../debugger/debug-interface-access/idiastackframe-get-base.md)|프레임의 기본 주소를 검색합니다.|  
|[IDiaStackFrame::get\_cplusplusExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-cplusplusexceptionhandling.md)|C \+ \+ 예외 처리 적용 됩니다 나타내는 플래그를 검색 합니다.|  
|[IDiaStackFrame::get\_functionStart](../../debugger/debug-interface-access/idiastackframe-get-functionstart.md)|블록의 함수 진입점이 포함 되어 있음을 나타내는 플래그를 검색 합니다.|  
|[IDiaStackFrame::get\_lengthLocals](../../debugger/debug-interface-access/idiastackframe-get-lengthlocals.md)|지역 변수는 스택에 푸시된 바이트 수를 검색 합니다.|  
|[IDiaStackFrame::get\_lengthParams](../../debugger/debug-interface-access/idiastackframe-get-lengthparams.md)|매개 변수는 스택에 푸시된 바이트 수를 검색 합니다.|  
|[IDiaStackFrame::get\_lengthProlog](../../debugger/debug-interface-access/idiastackframe-get-lengthprolog.md)|프롤로그 코드 블록에서의 바이트 수를 검색합니다.|  
|[IDiaStackFrame::get\_lengthSavedRegisters](../../debugger/debug-interface-access/idiastackframe-get-lengthsavedregisters.md)|저장 된 레지스터는 스택에 푸시된 바이트 수를 검색 합니다.|  
|[IDiaStackFrame::get\_localsBase](../../debugger/debug-interface-access/idiastackframe-get-localsbase.md)|지역 변수를 기본 주소를 검색합니다.|  
|[IDiaStackFrame::get\_maxStack](../../debugger/debug-interface-access/idiastackframe-get-maxstack.md)|스택 프레임에 전달 되는 바이트 수를 검색 합니다.|  
|[IDiaStackFrame::get\_rawLVarInstanceValue](../../debugger/debug-interface-access/idiastackframe-get-rawlvarinstancevalue.md)|원시 바이트 수로 지정 된 지역 변수의 값을 검색합니다.|  
|[IDiaStackFrame::get\_registerValue](../../debugger/debug-interface-access/idiastackframe-get-registervalue.md)|지정 된 레지스터의 값을 검색합니다.|  
|[IDiaStackFrame::get\_returnAddress](../../debugger/debug-interface-access/idiastackframe-get-returnaddress.md)|프레임의 반환 주소를 검색합니다.|  
|[IDiaStackFrame::get\_size](../../debugger/debug-interface-access/idiastackframe-get-size.md)|프레임의 바이트 크기를 검색합니다.|  
|[IDiaStackFrame::get\_systemExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-systemexceptionhandling.md)|시스템 예외 처리 적용 됩니다 나타내는 플래그를 검색 합니다.|  
|[IDiaStackFrame::get\_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)|프레임 형식을 검색합니다.|  
  
## 설명  
 스택 프레임은 함수 호출의 추상화를 실행 하는 동안입니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 얻을 [IDiaEnumStackFrames::Next](../../debugger/debug-interface-access/idiaenumstackframes-next.md) 메서드가 있습니다.  볼의 [IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md) 예 가져오는 방법에 대 한 인터페이스는 `IDiaStackFrame` 인터페이스입니다.  
  
## 예제  
 스택 프레임의 다양 한 특성을 표시 하는이 예제입니다.  
  
```cpp#  
void PrintStackFrame(IDiaStackFrame* pFrame)  
{  
    if (pFrame != NULL)  
    {  
        ULONGLONG bottom = 0;  
        ULONGLONG top    = 0;  
  
        if (pFrame->get_base(&bottom) == S_OK &&  
            pFrame->get_registerValue( CV_REG_ESP, &top ) == S_OK )  
        {  
             printf("range = 0x%08I64x - 0x%08I64x\n", bottom, top);  
        }  
  
        ULONGLONG returnAddress = 0;  
        if (pFrame->get_returnAddress(&returnAddress) == S_OK)  
        {  
             printf("return address = 0x%08I64x\n", returnAddress);  
        }  
  
        DWORD lengthFrame     = 0;  
        DWORD lengthLocals    = 0;  
        DWORD lengthParams    = 0;  
        DWORD lengthProlog    = 0;  
        DWORD lengthSavedRegs = 0;  
        if (pFrame->get_size(&lengthFrame) == S_OK &&  
            pFrame->get_lengthLocals(&lengthLocals) == S_OK &&  
            pFrame->get_lengthParams(&lengthParams) == S_OK &&  
            pFrame->get_lengthProlog(&lengthProlog) == S_OK &&  
            pFrame->get_lengthSavedRegisters(&lengthSavedRegs) == S_OK)  
        {  
            printf("stack frame size          = 0x%08lx bytes\n", lengthFrame);  
            printf("length of locals          = 0x%08lx bytes\n", lengthLocals);  
            printf("length of parameters      = 0x%08lx bytes\n", lengthParams);  
            printf("length of prolog          = 0x%08lx bytes\n", lengthProlog);  
            printf("length of saved registers = 0x%08lx bytes\n", lengthSavedRegs);  
        }  
    }  
}  
```  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md)   
 [IDiaEnumStackFrames::Next](../../debugger/debug-interface-access/idiaenumstackframes-next.md)   
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)