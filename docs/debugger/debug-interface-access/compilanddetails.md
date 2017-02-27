---
title: "CompilandDetails | Microsoft Docs"
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
  - "CompilandDetails 기호"
ms.assetid: ddc7d794-c622-4c63-b2a6-72f8b2d0022a
caps.latest.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 19
---
# CompilandDetails
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

컴파일 대상 정보 기호가 있는 사이 분할 되는 `SymTagCompiland` 태그 \(낮은 세부\) 하는 `SymTagCompilandDetails` 태그 \(높은 세부 정보\).  `SymTagCompilandDetails`다른 기호를 로드 해야 합니다.  그러나 다양 한 사용할 수 없습니다 컴파일 대상에 대 한 정보 제공은 `SymTagCompiland` 기호입니다.  
  
## 속성  
 다음 표에서이 기호 형식에 대해 유효한 속성을 보여 줍니다.  
  
|Property|데이터 형식|설명|  
|--------------|------------|--------|  
|[IDiaSymbol::get\_backEndBuild](../../debugger/debug-interface-access/idiasymbol-get-backendbuild.md)|`DWORD`|컴파일러 백 엔드 빌드 번호입니다.|  
|[IDiaSymbol::get\_backEndMajor](../../debugger/debug-interface-access/idiasymbol-get-backendmajor.md)|`DWORD`|컴파일러의 백 엔드 주 버전 번호입니다.|  
|[IDiaSymbol::get\_backEndMinor](../../debugger/debug-interface-access/idiasymbol-get-backendminor.md)|`DWORD`|컴파일러 백 엔드 부 버전 번호입니다.|  
|[IDiaSymbol::get\_compilerName](../../debugger/debug-interface-access/idiasymbol-get-compilername.md)|`BSTR`|컴파일이 대상 \(DIA SDK v 8.0에만 이상\)을 생성 한 컴파일러의 이름입니다.|  
|[IDiaSymbol::get\_editAndContinueEnabled](../../debugger/debug-interface-access/idiasymbol-get-editandcontinueenabled.md)|`BOOL`|`TRUE`편집 하며 계속 하기에서 컴파일이 활성화 된 경우.|  
|[IDiaSymbol::get\_frontEndBuild](../../debugger/debug-interface-access/idiasymbol-get-frontendbuild.md)|`DWORD`|컴파일러 프런트 엔드 빌드 번호입니다.|  
|[IDiaSymbol::get\_frontEndMajor](../../debugger/debug-interface-access/idiasymbol-get-frontendmajor.md)|`DWORD`|컴파일러 프런트 엔드 주 버전 번호입니다.|  
|[IDiaSymbol::get\_frontEndMinor](../../debugger/debug-interface-access/idiasymbol-get-frontendminor.md)|`DWORD`|컴파일러 프런트 엔드 부 버전 번호입니다.|  
|[IDiaSymbol::get\_hasDebugInfo](../../debugger/debug-interface-access/idiasymbol-get-hasdebuginfo.md)|`BOOL`|`TRUE`이 컴파일 \(DIA SDK v 8.0에만 이상\)의 디버그 정보가 있는 경우.|  
|[IDiaSymbol::get\_hasManagedCode](../../debugger/debug-interface-access/idiasymbol-get-hasmanagedcode.md)|`BOOL`|`TRUE`이 컴파일 대상 관리 되는 코드 \(DIA SDK v 8.0에만 이상\) 포함 된 경우.|  
|[IDiaSymbol::get\_hasSecurityChecks](../../debugger/debug-interface-access/idiasymbol-get-hassecuritychecks.md)|`BOOL`|`TRUE`컴파일 대상으로 컴파일한 경우는 [\/GS\(버퍼 보안 검사\)](/visual-cpp/build/reference/gs-buffer-security-check) 컴파일러 스위치 \(DIA SDK v 8.0에만 이상\).|  
|[IDiaSymbol::get\_isCVTCIL](../../debugger/debug-interface-access/idiasymbol-get-iscvtcil.md)|`BOOL`|`TRUE`컴파일 대상 공통 중간 언어 \(CIL\) 코드에서 네이티브 코드로 변환 하는 경우.|  
|[IDiaSymbol::get\_isDataAligned](../../debugger/debug-interface-access/idiasymbol-get-isdataaligned.md)|`BOOL`|`TRUE`사용자 정의 형식 \(UDT\) 정렬 된 경우 일부 메모리 경계 \(DIA SDK v 8.0에만 이상\)를 지정 합니다.|  
|[IDiaSymbol::get\_isHotpatchable](../../debugger/debug-interface-access/idiasymbol-get-ishotpatchable.md)|`BOOL`|`TRUE`컴파일 대상으로 컴파일한 경우는 [\/hotpatch\(핫 패치 가능 이미지 만들기\)](/visual-cpp/build/reference/hotpatch-create-hotpatchable-image) 컴파일러 스위치 \(DIA SDK v 8.0에만 이상\).|  
|[IDiaSymbol::get\_isLTCG](../../debugger/debug-interface-access/idiasymbol-get-isltcg.md)|`BOOL`|`TRUE`컴파일 대상으로 컴파일한 경우는 [\/LTCG\(링크 타임 코드 생성\)](/visual-cpp/build/reference/ltcg-link-time-code-generation) 컴파일러 스위치 \(DIA SDK v 8.0에만 이상\).|  
|[IDiaSymbol::get\_isMSILNetmodule](../../debugger/debug-interface-access/idiasymbol-get-ismsilnetmodule.md)|`BOOL`|TRUE 이면 컴파일 \(DIA SDK v 8.0에만 이상\)를 Microsoft 중간 언어 \(MSIL\) 모듈입니다.|  
|[IDiaSymbol::get\_language](../../debugger/debug-interface-access/idiasymbol-get-language.md)|`DWORD`|소스 코드 언어입니다.|  
|[IDiaSymbol::get\_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|컴파일 대상에 대 한 기호입니다.|  
|[IDiaSymbol::get\_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|어휘 부모 심볼의 ID입니다.|  
|[IDiaSymbol::get\_platform](../../debugger/debug-interface-access/idiasymbol-get-platform.md)|`DWORD`|컴파일 대상 된 컴파일할 플랫폼 \(중 하나를 [CV\_CPU\_TYPE\_e 열거형](../../debugger/debug-interface-access/cv-cpu-type-e.md) 값\).|  
|[IDiaSymbol::get\_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|심볼의 인덱스 ID입니다.|  
|[IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|반환 `SymTagCompilandDetails` \(중 하나를 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값\).|  
  
## 설명  
 컴파일러는 종종 컴파일러 2 패스 라는 형태로 제공. 일부 컴파일러 버전에서는 매번 별도 프로그램으로 처리 합니다.  이러한 프런트 엔드 및 백 엔드 컴파일러는 각각 따라서 백 엔드 및 프런트 엔드 버전 번호에 대 한 심볼 속성 이라고 합니다.  
  
## 참고 항목  
 [컴파일 대상](../../debugger/debug-interface-access/compiland.md)   
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)