---
title: "컴파일 대상 | Microsoft Docs"
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
  - "컴파일 대상 기호"
  - "컴파일 대상, 컴파일 대상 기호"
ms.assetid: c798eb2b-664a-41ec-ae90-5e9d292507ca
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# 컴파일 대상
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

하나의 `SymTagCompiland` 는.exe 파일에 각 컴파일 대상 연결에 대 한 기호입니다.  컴파일 정보 기호가 있는 사이 분할 되는 `SymTagCompiland` 추가 컴파일 대상 기호를 로드 하지 않고 검색할 수 있습니다, 태그, 및 기호에 `SymTagCompilandDetails` 태그를 추가 기호를 로드 해야 할 수 있습니다.  
  
## 속성  
 다음 표에서이 기호 형식에 대해 유효한 속성을 보여 줍니다.  
  
|Property|데이터 형식|설명|  
|--------------|------------|--------|  
|[IDiaSymbol::get\_editAndContinueEnabled](../../debugger/debug-interface-access/idiasymbol-get-editandcontinueenabled.md)|`BOOL`|`TRUE`편집 하며 계속 하기가 활성화 되었습니다 경우에 컴파일 됩니다.|  
|[IDiaSymbol::get\_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|.Exe 파일에 대 한 기호입니다.|  
|[IDiaSymbol::get\_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|어휘 부모 심볼의 ID입니다.|  
|[IDiaSymbol::get\_libraryName](../../debugger/debug-interface-access/idiasymbol-get-libraryname.md)|`BSTR`|개체를 로드 한 라이브러리 또는 개체 파일의 이름입니다.|  
|[IDiaSymbol::get\_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|컴파일 대상의 개체 파일의 파일 이름입니다.|  
|[IDiaSymbol::get\_sourceFileName](../../debugger/debug-interface-access/idiasymbol-get-sourcefilename.md)|`BSTR`|소스 파일의 이름입니다.|  
|[IDiaSymbol::get\_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|심볼의 인덱스 ID입니다.|  
|[IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagCompiland` \(중 하나를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값\).|  
  
## 참고 항목  
 [CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)   
 [CompilandEnv](../../debugger/debug-interface-access/compilandenv.md)   
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)