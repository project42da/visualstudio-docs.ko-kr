---
title: "IDiaFrameData | Microsoft Docs"
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
  - "IDiaFrameData 인터페이스"
ms.assetid: 2f1b4986-341b-4641-89a4-226e261e9d93
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaFrameData
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

스택 프레임의 세부 정보를 제공합니다.  
  
## 구문  
  
```  
IDiaFrameData : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDiaFrameData`.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaFrameData::get\_addressSection](../../debugger/debug-interface-access/idiaframedata-get-addresssection.md)|프레임에 대 한 코드 주소 구역 부분을 검색합니다.|  
|[IDiaFrameData::get\_addressOffset](../../debugger/debug-interface-access/idiaframedata-get-addressoffset.md)|오프셋된 부분의 코드 주소 프레임을 검색합니다.|  
|[IDiaFrameData::get\_relativeVirtualAddress](../../debugger/debug-interface-access/idiaframedata-get-relativevirtualaddress.md)|이미지 상대 가상 주소 \(RVA\) 프레임에 대 한 코드를 검색합니다.|  
|[IDiaFrameData::get\_virtualAddress](../../debugger/debug-interface-access/idiaframedata-get-virtualaddress.md)|가상 주소 \(VA\) 프레임에 대 한 코드를 검색합니다.|  
|[IDiaFrameData::get\_lengthBlock](../../debugger/debug-interface-access/idiaframedata-get-lengthblock.md)|프레임에 설명 된 코드의 블록의 바이트에서 길이 검색 합니다.|  
|[IDiaFrameData::get\_lengthLocals](../../debugger/debug-interface-access/idiaframedata-get-lengthlocals.md)|지역 변수는 스택에 푸시된 바이트 수를 검색 합니다.|  
|[IDiaFrameData::get\_lengthParams](../../debugger/debug-interface-access/idiaframedata-get-lengthparams.md)|매개 변수는 스택에 푸시된 바이트 수를 검색 합니다.|  
|[IDiaFrameData::get\_maxStack](../../debugger/debug-interface-access/idiaframedata-get-maxstack.md)|스택 프레임에 전달 되는 바이트 수를 검색 합니다.|  
|[IDiaFrameData::get\_lengthProlog](../../debugger/debug-interface-access/idiaframedata-get-lengthprolog.md)|프롤로그 코드 블록에서의 바이트 수를 검색합니다.|  
|[IDiaFrameData::get\_lengthSavedRegisters](../../debugger/debug-interface-access/idiaframedata-get-lengthsavedregisters.md)|저장 된 레지스터는 스택에 푸시된 바이트 수를 검색 합니다.|  
|[IDiaFrameData::get\_program](../../debugger/debug-interface-access/idiaframedata-get-program.md)|현재 함수를 호출 하기 전에 설정 레지스터를 계산 하는 데 사용 되는 프로그램 문자열을 검색 합니다.|  
|[IDiaFrameData::get\_systemExceptionHandling](../../debugger/debug-interface-access/idiaframedata-get-systemexceptionhandling.md)|검색 시스템 예외 처리는 나타내는 플래그 적용 됩니다.|  
|[IDiaFrameData::get\_cplusplusExceptionHandling](../../debugger/debug-interface-access/idiaframedata-get-cplusplusexceptionhandling.md)|검색 해당 C\+\+ 예외 처리를 나타내는 플래그를 적용 됩니다.|  
|[IDiaFrameData::get\_functionStart](../../debugger/debug-interface-access/idiaframedata-get-functionstart.md)|블록 진입점 함수가 포함 되어 있는 표시 플래그를 검색 합니다.|  
|[IDiaFrameData::get\_allocatesBasePointer](../../debugger/debug-interface-access/idiaframedata-get-allocatesbasepointer.md)|코드에서이 주소 범위에 대 한 기본 포인터 할당 되도록 나타내는 플래그를 검색 합니다.  이 메서드는 사용되지 않습니다.|  
|[IDiaFrameData::get\_type](../../debugger/debug-interface-access/idiaframedata-get-type.md)|컴파일러가 특정 프레임 형식을 검색합니다.|  
|[IDiaFrameData::get\_functionParent](../../debugger/debug-interface-access/idiaframedata-get-functionparent.md)|데이터 인터페이스 함수를 포함 하는 것에 대 한 프레임을 검색 합니다.|  
|[IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md)|스택 해제를 수행 하 고 스택 워크가 프레임 인터페이스에서 레지스터의 현재 상태를 반환 합니다.|  
  
## 설명  
 프레임에 대해 사용할 수 있는 세부 주소와 블록 길이 의해 지정 된 주소 범위 내에서 실행 포인트입니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 얻을 [IDiaEnumFrameData::Next](../../debugger/debug-interface-access/idiaenumframedata-next.md) 또는 [IDiaEnumFrameData::Item](../../debugger/debug-interface-access/idiaenumframedata-item.md) 방법입니다.  참조는 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md) 인터페이스에 대 한 자세한 내용은.  
  
## 예제  
 속성을 인쇄 하는이 예제는 `IDiaFrameData` 개체입니다.  참조는 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md) 인터페이스를 하는 방법의 예를 `IDiaFrameData` 인터페이스에서 얻은 합니다.  
  
```cpp#  
void PrintFrameData(IDiaFrameData* pFrameData){  
    DWORD dwSect;  
    DWORD dwOffset;  
    DWORD cbBlock;  
    DWORD cbLocals; // Number of bytes reserved for the function locals  
    DWORD cbParams; // Number of bytes reserved for the function arguments  
    DWORD cbMaxStack;  
    DWORD cbProlog;  
    DWORD cbSavedRegs;  
    BOOL  bSEH;  
    BOOL  bEH;  
    BOOL  bStart;  
    BSTR  wszProgram;  
  
    if(pFrameData->get_addressSection(&dwSect) == S_OK &&   
       pFrameData->get_addressOffset(&dwOffset) == S_OK &&  
       pFrameData->get_lengthBlock(&cbBlock) == S_OK &&  
       pFrameData->get_lengthLocals(&cbLocals) == S_OK &&  
       pFrameData->get_lengthParams(&cbParams) == S_OK &&  
       pFrameData->get_maxStack(&cbMaxStack) == S_OK &&  
       pFrameData->get_lengthProlog(&cbProlog) == S_OK &&  
       pFrameData->get_lengthSavedRegisters(&cbSavedRegs) == S_OK &&  
       pFrameData->get_systemExceptionHandling(&bSEH) == S_OK &&  
       pFrameData->get_cplusplusExceptionHandling(&bEH) == S_OK &&  
       pFrameData->get_functionStart(&bStart) == S_OK )  
    {  
        wprintf(L"Frame address  : %04X:%08X\n", dwSect, dwOffset);  
        wprintf(L"Block size     : 0x%8X\n", cbBlock);  
        wprintf(L"Locals size    : 0x%8X\n", cbLocals);  
        wprintf(L"Parms size     : 0x%8X\n", cbParams);  
        wprintf(L"Max stack used : 0x%8X\n", cbMaxStack);  
        wprintf(L"Prolog size    : 0x%8X\n", cbProlog);  
        wprintf(L"Saved regs size: 0x%8X\n", cbSavedRegs);  
        wprintf(L"System Exception Handling: %c\n", bSEH ? L'Y' : L'N');  
        wprintf(L"C++ Exception Handling   : %c\n", bEH ? L'Y' : L'N');  
        wprintf(L"Function starts in block : %c\n", bStart ? L'Y' : L'N');  
  
        if (pFrameData->get_program(&wszProgram) == S_OK)  
        {  
            wprintf(L"Program used for register set: %s\n", wszProgram);  
            SysFreeString(wszProgram);  
        }  
        else  
        {  
            wprintf(L"\n");  
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
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaEnumFrameData::Item](../../debugger/debug-interface-access/idiaenumframedata-item.md)   
 [IDiaEnumFrameData::Next](../../debugger/debug-interface-access/idiaenumframedata-next.md)