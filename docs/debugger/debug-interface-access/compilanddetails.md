---
title: CompilandDetails | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: CompilandDetails symbol
ms.assetid: ddc7d794-c622-4c63-b2a6-72f8b2d0022a
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9bfbb1e05dadb18e9357e38d6ed660c248dccec4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="compilanddetails"></a>CompilandDetails
컴파일 대상 정보도 기호 분할는 `SymTagCompiland` 태그 (낮은 세부 정보)와 `SymTagCompilandDetails` 태그 (높은 세부 정보). `SymTagCompilandDetails`추가 기호를 로드 해야 합니다. 그러나 다양 한으로 사용할 수 없으면 컴파일 대상에 대 한 정보를 제공는 `SymTagCompiland` 기호입니다.  
  
## <a name="properties"></a>속성  
 다음 표에서이 기호 형식에 대해 사용할 수 있는 속성을 보여 줍니다.  
  
|속성|데이터 형식|설명|  
|--------------|---------------|-----------------|  
|[IDiaSymbol::get_backEndBuild](../../debugger/debug-interface-access/idiasymbol-get-backendbuild.md)|`DWORD`|컴파일러의 백 엔드 빌드 번호입니다.|  
|[IDiaSymbol::get_backEndMajor](../../debugger/debug-interface-access/idiasymbol-get-backendmajor.md)|`DWORD`|컴파일러의 백 엔드 주 버전 번호.|  
|[IDiaSymbol::get_backEndMinor](../../debugger/debug-interface-access/idiasymbol-get-backendminor.md)|`DWORD`|컴파일러의 백 엔드 부 버전 번호입니다.|  
|[IDiaSymbol::get_compilerName](../../debugger/debug-interface-access/idiasymbol-get-compilername.md)|`BSTR`|이 컴파일 대상 (DIA SDK v 8.0에만 또는 이상)를 생성 하는 컴파일러의 이름입니다.|  
|[IDiaSymbol::get_editAndContinueEnabled](../../debugger/debug-interface-access/idiasymbol-get-editandcontinueenabled.md)|`BOOL`|`TRUE`편집 하며 계속 하기는 컴파일에서 사용 되었습니다.|  
|[IDiaSymbol::get_frontEndBuild](../../debugger/debug-interface-access/idiasymbol-get-frontendbuild.md)|`DWORD`|컴파일러의 프런트 엔드 빌드 번호입니다.|  
|[IDiaSymbol::get_frontEndMajor](../../debugger/debug-interface-access/idiasymbol-get-frontendmajor.md)|`DWORD`|컴파일러의 프런트 엔드 주 버전 번호입니다.|  
|[IDiaSymbol::get_frontEndMinor](../../debugger/debug-interface-access/idiasymbol-get-frontendminor.md)|`DWORD`|컴파일러의 프런트 엔드 부 버전 번호입니다.|  
|[IDiaSymbol::get_hasDebugInfo](../../debugger/debug-interface-access/idiasymbol-get-hasdebuginfo.md)|`BOOL`|`TRUE`이 컴파일 대상에 디버그 정보 (DIA SDK v 8.0 이상 에서만에서).|  
|[IDiaSymbol::get_hasManagedCode](../../debugger/debug-interface-access/idiasymbol-get-hasmanagedcode.md)|`BOOL`|`TRUE`이 컴파일 대상 포함 된 경우 관리 코드 (DIA SDK v 8.0 이상 에서만에서).|  
|[IDiaSymbol::get_hasSecurityChecks](../../debugger/debug-interface-access/idiasymbol-get-hassecuritychecks.md)|`BOOL`|`TRUE`컴파일 대상으로 컴파일된 경우는 [/GS (버퍼 보안 검사)](/cpp/build/reference/gs-buffer-security-check) 컴파일러 스위치 (DIA SDK v 8.0 이상 에서만에서).|  
|[IDiaSymbol::get_isCVTCIL](../../debugger/debug-interface-access/idiasymbol-get-iscvtcil.md)|`BOOL`|`TRUE`컴파일 대상 공용 중간 언어 (CIL) 코드에서 네이티브 코드로 변환 되었습니다 하는 경우.|  
|[IDiaSymbol::get_isDataAligned](../../debugger/debug-interface-access/idiasymbol-get-isdataaligned.md)|`BOOL`|`TRUE`사용자 정의 형식 (UDT)으로 정렬 되어 있는 경우 일부 메모리 경계 (DIA SDK v 8.0에만 또는 이상)를 지정 합니다.|  
|[IDiaSymbol::get_isHotpatchable](../../debugger/debug-interface-access/idiasymbol-get-ishotpatchable.md)|`BOOL`|`TRUE`컴파일 대상으로 컴파일된 경우는 [/hotpatch (핫 패치 가능 이미지 만들기)](/cpp/build/reference/hotpatch-create-hotpatchable-image) 컴파일러 스위치 (DIA SDK v 8.0 이상 에서만에서).|  
|[IDiaSymbol::get_isLTCG](../../debugger/debug-interface-access/idiasymbol-get-isltcg.md)|`BOOL`|`TRUE`컴파일 대상으로 컴파일된 경우는 [/LTCG (링크 타임 코드 생성)](/cpp/build/reference/ltcg-link-time-code-generation) 컴파일러 스위치 (DIA SDK v 8.0 이상 에서만에서).|  
|[IDiaSymbol::get_isMSILNetmodule](../../debugger/debug-interface-access/idiasymbol-get-ismsilnetmodule.md)|`BOOL`|TRUE 이면 compiland (DIA SDK v 8.0 이상 에서만에서) 언어 MSIL (Microsoft Intermediate) 모듈입니다.|  
|[IDiaSymbol::get_language](../../debugger/debug-interface-access/idiasymbol-get-language.md)|`DWORD`|소스 코드 언어입니다.|  
|[IDiaSymbol::get_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|컴파일 대상에 대 한 기호입니다.|  
|[IDiaSymbol::get_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|어휘 부모 기호의 ID입니다.|  
|[IDiaSymbol::get_platform](../../debugger/debug-interface-access/idiasymbol-get-platform.md)|`DWORD`|컴파일 대상 컴파일한 플랫폼 (중 하나는 [CV_CPU_TYPE_e 열거형](../../debugger/debug-interface-access/cv-cpu-type-e.md) 값).|  
|[IDiaSymbol::get_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|기호 인덱스 ID입니다.|  
|[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagCompilandDetails` (중 하나는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값).|  
  
## <a name="remarks"></a>설명  
 컴파일러는 종종 2 패스 컴파일러; 형태로 제공 일부 컴파일러 버전에서는 각 패스 마다 별도 프로그램에 의해 처리 됩니다. 이 라고 프런트 엔드 및 백 엔드 컴파일러 각각 따라서 백 엔드와 프런트 엔드 버전 번호에 대 한 기호 속성.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일 대상](../../debugger/debug-interface-access/compiland.md)   
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)