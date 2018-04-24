---
title: Exe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- .dll files
- Exe symbol
- .exe files
- executable files, Exe symbol
ms.assetid: a781d2cf-55fe-4373-9cf1-b732864244e0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 899b168428428e0e4df3330691358571d7da9ed1
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="exe"></a>Exe
.Exe 또는.dll 파일의 전역 범위를 나타내므로 Exe는 유일한 어휘는 포함 하지 않고 기호 또는 부모 클래스. 하나의 기호가 없는 `SymTagExe` 파일당 태그입니다. [idiasession:: Get_globalscope](../../debugger/debug-interface-access/idiasession-get-globalscope.md) 메서드 기호를 반환 합니다.  
  
## <a name="properties"></a>속성  
 다음 표에서이 기호 형식에 대해 사용할 수 있는 속성을 보여 줍니다.  
  
|속성|데이터 형식|설명|  
|--------------|---------------|-----------------|  
|[IDiaSymbol::get_age](../../debugger/debug-interface-access/idiasymbol-get-age.md)|`DWORD`|이 실행 파일의 연령입니다.|  
|[IDiaSymbol::get_guid](../../debugger/debug-interface-access/idiasymbol-get-guid.md)|`GUID`|`GUID` 이 실행 파일입니다.|  
|[IDiaSymbol::get_isCTypes](../../debugger/debug-interface-access/idiasymbol-get-isctypes.md)|`BOOL`|`TRUE` 와 연결 된 기호 파일 (DIA SDK v 8.0 이상 에서만에서) C 형식을이 실행 파일에 포함 되어 있습니다.|  
|[IDiaSymbol::get_isStripped](../../debugger/debug-interface-access/idiasymbol-get-isstripped.md)|`BOOL`|`TRUE` 전용 기호가 있어야이 실행 파일 (DIA SDK v 8.0 이상 에서만에서)와 관련 된 기호 파일에서 잘렸습니다 하는 경우.|  
|[IDiaSymbol::get_machineType](../../debugger/debug-interface-access/idiasymbol-get-machinetype.md)|`DWORD`|대상 CPU를 나타내는 값 (중 하나는 [CV_CPU_TYPE_e 열거형](../../debugger/debug-interface-access/cv-cpu-type-e.md) 값).|  
|[IDiaSymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|.Exe 파일의 이름입니다.|  
|[IDiaSymbol::get_signature](../../debugger/debug-interface-access/idiasymbol-get-signature.md)|`DWORD`|실행 파일의 서명입니다.|  
|[IDiaSymbol::get_symbolsFileName](../../debugger/debug-interface-access/idiasymbol-get-symbolsfilename.md)|`BSTR`|.Exe 파일의.pdb 파일이 나.dbg 파일에 대 한 전체 경로입니다.|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|기호 인덱스 ID입니다.|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagExe` (중 하나는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값).|  
  
## <a name="see-also"></a>참고 항목  
 [Idiasession:: Get_globalscope](../../debugger/debug-interface-access/idiasession-get-globalscope.md)   
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)