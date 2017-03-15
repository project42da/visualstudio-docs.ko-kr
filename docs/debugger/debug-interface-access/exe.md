---
title: "Exe | Microsoft Docs"
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
  - ".dll 파일"
  - "Exe 기호"
  - ".exe 파일"
  - "실행 파일, Exe 기호"
ms.assetid: a781d2cf-55fe-4373-9cf1-b732864244e0
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# Exe
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

.Exe 또는.dll 파일의 전역 범위를 나타내는 경우 Exe만 없이 어휘 기호 또는 부모 클래스입니다.  하나의 기호에는 있는 `SymTagExe` 태그 파일 당.  [IDiaSession::get\_globalScope](../../debugger/debug-interface-access/idiasession-get-globalscope.md) 메서드 기호를 반환 합니다.  
  
## 속성  
 다음 표에서이 기호 형식에 대해 유효한 속성을 보여 줍니다.  
  
|Property|데이터 형식|설명|  
|--------------|------------|--------|  
|[IDiaSymbol::get\_age](../../debugger/debug-interface-access/idiasymbol-get-age.md)|`DWORD`|이 실행 파일의 보존 기간입니다.|  
|[IDiaSymbol::get\_guid](../../debugger/debug-interface-access/idiasymbol-get-guid.md)|`GUID`|`GUID`에 실행 파일입니다.|  
|[IDiaSymbol::get\_isCTypes](../../debugger/debug-interface-access/idiasymbol-get-isctypes.md)|`BOOL`|`TRUE`기호 파일에 연결 하는 경우 C 형식 \(DIA SDK v 8.0에만 이상\)이 실행이 파일을 포함 합니다.|  
|[IDiaSymbol::get\_isStripped](../../debugger/debug-interface-access/idiasymbol-get-isstripped.md)|`BOOL`|`TRUE`전용 기호 \(DIA SDK v 8.0에만 이상\)이이 실행 파일과 연결 된 기호 파일에서 제거 되었습니다 있을 경우.|  
|[IDiaSymbol::get\_machineType](../../debugger/debug-interface-access/idiasymbol-get-machinetype.md)|`DWORD`|대상 CPU를 나타내는 값 \(중 하나를 [CV\_CPU\_TYPE\_e 열거형](../../debugger/debug-interface-access/cv-cpu-type-e.md) 값\).|  
|[IDiaSymbol::get\_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|.Exe 파일의 이름입니다.|  
|[IDiaSymbol::get\_signature](../../debugger/debug-interface-access/idiasymbol-get-signature.md)|`DWORD`|실행 파일을 서명 합니다.|  
|[IDiaSymbol::get\_symbolsFileName](../../debugger/debug-interface-access/idiasymbol-get-symbolsfilename.md)|`BSTR`|.Exe 파일의.pdb 또는.dbg 파일에 대 한 전체 경로입니다.|  
|[IDiaSymbol::get\_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|심볼의 인덱스 ID입니다.|  
|[IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagExe` \(중 하나를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값\).|  
  
## 참고 항목  
 [IDiaSession::get\_globalScope](../../debugger/debug-interface-access/idiasession-get-globalscope.md)   
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)