---
title: 기호 형식의 어휘 계층 구조 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols [DIA SDK], type hierarchies
ms.assetid: 912da653-ddfe-45a4-84aa-64281283739a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 81cd3e54d61682962109afb59a396645ef65294d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="lexical-hierarchy-of-symbol-types"></a>기호 형식의 어휘 계층 구조
다음 표에서 어휘 계층 구조에서 기호 형식을 보여 줍니다.  
  
## <a name="symbol-types"></a>기호 형식  
  
|기호 형식|설명|  
|-----------------|-----------------|  
|[주석](../../debugger/debug-interface-access/annotation.md)|프로그램 코드에서 주석이 추가 된 위치를 지정합니다.|  
|[블록](../../debugger/debug-interface-access/block.md)|함수에서 중첩 된 범위를 지정합니다.|  
|`Compiland`|지정 된 `compiland` .exe 파일에 연결 합니다.|  
|[CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)|컴파일 대상 데이터를 추가 컴파일 대상 세부 정보를 로드 해야 하 고 따라서 검색할 런타임 오버 헤드를 유발 될 수 있습니다를 지정 합니다.|  
|[CompilandEnv](../../debugger/debug-interface-access/compilandenv.md)|컴파일 대상 컴파일에 중요 한 추가 환경 변수를 지정합니다.|  
|[사용자 지정(디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/custom-debug-interface-access-sdk.md)|사용자 정의 기호를 지정합니다.|  
|[데이터(디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/data-debug-interface-access-sdk.md)|매개 변수, 지역 변수, 전역 변수 및 클래스 멤버와 같은 변수를 지정합니다.|  
|[Exe](../../debugger/debug-interface-access/exe.md)|데이터의 전역 범위 지정 전체.exe 또는.dll 파일에 해당합니다.|  
|[FuncDebugEnd](../../debugger/debug-interface-access/funcdebugend.md)|정의 된 지점에 있는 함수를 지정 합니다. 종료 하는 것을 디버깅 합니다.|  
|[FuncDebugStart](../../debugger/debug-interface-access/funcdebugstart.md)|정의 된 지점에 있는 함수를 지정 합니다. 어떤 디버깅 시작 되려고 합니다.|  
|[함수(디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/function-debug-interface-access-sdk.md)|함수를 지정 합니다.|  
|[레이블(디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/label-debug-interface-access-sdk.md)|프로그램 코드에서 위치를 지정합니다.|  
|[PublicSymbol](../../debugger/debug-interface-access/publicsymbol.md)|실행 프로그램을 빌드할 때 표시 되는 외부 기호를 지정 합니다.|  
|[썽크](../../debugger/debug-interface-access/thunk.md)|지정 된 `thunk`합니다.|  
|[UsingNameSpace](../../debugger/debug-interface-access/usingnamespace.md)|지정 된 `namespace`식별자입니다.|  
  
> [!NOTE]
>  추가 기호 속성 기호 형식에 따라 사용할 수 있습니다. 이러한 속성은 개별 기호 항목에 나열 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [기호 형식의 클래스 계층 구조](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)   
 [Idiasymbol:: Get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)   
 [기호 및 기호 태그](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)