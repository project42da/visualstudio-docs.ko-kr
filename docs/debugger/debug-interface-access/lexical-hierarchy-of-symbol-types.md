---
title: "기호 형식의 어휘 계층 구조 | Microsoft Docs"
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
  - "기호[DIA SDK], 형식 계층 구조"
ms.assetid: 912da653-ddfe-45a4-84aa-64281283739a
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# 기호 형식의 어휘 계층 구조
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다음 표에서 기호 유형 어휘 계층 구조를 보여 줍니다.  
  
## 기호 형식  
  
|기호 형식|설명|  
|-----------|--------|  
|[주석](../../debugger/debug-interface-access/annotation.md)|프로그램 코드에는 주석이 추가 된 위치를 지정합니다.|  
|[블록](../../debugger/debug-interface-access/block.md)|중첩 된 범위에서 함수를 지정합니다.|  
|`Compiland`|지정 된 `compiland` .exe 파일에 연결 합니다.|  
|[CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)|필요한 추가 컴파일 정보를 로드 하 고 따라서 검색할 수 실행 시간 오버 헤드를 초래 하는 컴파일 대상 데이터를 지정 합니다.|  
|[CompilandEnv](../../debugger/debug-interface-access/compilandenv.md)|컴파일 대상 컴파일하기에 중대 한 추가 환경 변수를 지정합니다.|  
|[사용자 지정\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/custom-debug-interface-access-sdk.md)|사용자 정의 기호를 지정합니다.|  
|[데이터\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/data-debug-interface-access-sdk.md)|이러한 변수는 매개 변수, 지역 변수, 전역 변수 및 클래스 멤버를 지정합니다.|  
|[Exe](../../debugger/debug-interface-access/exe.md)|전역 데이터의 범위를 지정합니다. 전체.exe 또는.dll 파일에 해당합니다.|  
|[FuncDebugEnd](../../debugger/debug-interface-access/funcdebugend.md)|정의 된 지점을 가진 함수에 지정 된 종료 하는 디버깅에.|  
|[FuncDebugStart](../../debugger/debug-interface-access/funcdebugstart.md)|정의 된 지점을 가진 함수를 지정 합니다. 어떤 디버깅 시로 설정 됩니다.|  
|[함수\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/function-debug-interface-access-sdk.md)|함수에 지정 합니다.|  
|[레이블\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/label-debug-interface-access-sdk.md)|프로그램 코드에서의 위치를 지정합니다.|  
|[PublicSymbol](../../debugger/debug-interface-access/publicsymbol.md)|실행 프로그램을 만들 때 표시 되는 외부 기호를 지정 합니다.|  
|[썽크](../../debugger/debug-interface-access/thunk.md)|지정 된 `thunk`.|  
|[UsingNameSpace](../../debugger/debug-interface-access/usingnamespace.md)|지정 된 `namespace`식별자입니다.|  
  
> [!NOTE]
>  추가적인 심볼 속성 기호 형식에 따라 사용할 수 있습니다.  이러한 속성은 개별 기호 항목에서 나열 됩니다.  
  
## 참고 항목  
 [기호 형식의 클래스 계층 구조](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)   
 [IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)   
 [기호 및 기호 태그](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)