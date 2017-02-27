---
title: "SymTagEnum | Microsoft Docs"
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
  - "SymTagEnum 열거형"
ms.assetid: 528a50cf-e13d-46ec-a98c-323d5d047de9
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# SymTagEnum
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

심볼의 유형을 지정합니다.  
  
## 구문  
  
```cpp#  
enum SymTagEnum {   
   SymTagNull,  
   SymTagExe,  
   SymTagCompiland,  
   SymTagCompilandDetails,  
   SymTagCompilandEnv,  
   SymTagFunction,  
   SymTagBlock,  
   SymTagData,  
   SymTagAnnotation,  
   SymTagLabel,  
   SymTagPublicSymbol,  
   SymTagUDT,  
   SymTagEnum,  
   SymTagFunctionType,  
   SymTagPointerType,  
   SymTagArrayType,   
   SymTagBaseType,   
   SymTagTypedef,   
   SymTagBaseClass,  
   SymTagFriend,  
   SymTagFunctionArgType,   
   SymTagFuncDebugStart,   
   SymTagFuncDebugEnd,  
   SymTagUsingNamespace,   
   SymTagVTableShape,  
   SymTagVTable,  
   SymTagCustom,  
   SymTagThunk,  
   SymTagCustomType,  
   SymTagManagedType,  
   SymTagDimension,  
   SymTagCallSite,  
   SymTagInlineSite,  
   SymTagBaseInterface,  
   SymTagVectorType,  
   SymTagMatrixType,  
   SymTagHLSLType  
};  
```  
  
## Elements  
 `SymTagNull`  
 심볼 유형 없음 했음을 나타냅니다.  
  
 `SymTagExe`  
 심볼은.exe 파일입니다.  하나씩만 `SymTagExe` 기호를 기호 저장소 단위입니다.  글로벌 범위로 사용 하 고 어휘 부모가 없습니다.  
  
 `SymTagCompiland`  
 컴파일 대상 기호를 기호 저장소의 각 컴파일 구성 요소를 나타냅니다.  네이티브 응용 프로그램에 대 한 `SymTagCompiland` 이미지에 연결 된 개체 파일에 기호에 해당 합니다.  일부 유형의 Microsoft 중간 언어 \(MSIL\) 이미지는 클래스 당 한 컴파일.  
  
 `SymTagCompilandDetails`  
 심볼의 컴파일 대상 확장된 특성 들어 있음을 나타냅니다.  이러한 속성을 검색 컴파일 기호를 로드 해야 합니다.  
  
 `SymTagCompilandEnv`  
 컴파일 대상에 대해 정의 되는 환경 문자열의 기호입니다.  
  
 `SymTagFunction`  
 기호는 함수 임을 나타냅니다.  
  
 `SymTagBlock`  
 기호가 중첩 된 블록입니다.  
  
 `SymTagData`  
 데이터 기호입니다.  
  
 `SymTagAnnotation`  
 코드 주석에 대 한 상징을 나타냅니다.  이 심볼의 자식인 문자열 상수 데이터 \(`SymTagData`, `LocIsConstant`, `DataIsConstant`\).  대부분의 클라이언트가이 기호는 무시 됩니다.  
  
 `SymTagLabel`  
 기호 레이블을 나타냅니다.  
  
 `SymTagPublicSymbol`  
 공용 기호 기호입니다.  네이티브 응용 프로그램의 경우이 기호는 이미지를 연결 하는 동안 발생 했습니다 COFF 외부 기호가입니다.  
  
 `SymTagUDT`  
 사용자 정의 형식 \(구조체, 클래스 또는 공용 구조체\) 기호입니다.  
  
 `SymTagEnum`  
 열거형의 기호입니다.  
  
 `SymTagFunctionType`  
 기호는 함수 시그니처 형식 인지 나타냅니다.  
  
 `SymTagPointerType`  
 기호 포인터 형식입니다.  
  
 `SymTagArrayType`  
 배열 형식 기호입니다.  
  
 `SymTagBaseType`  
 기호는 기본 형식입니다.  
  
 `SymTagTypedef`  
 기호 이면에 `typedef`, 다른 형식에 대 한 별칭입니다.  
  
 `SymTagBaseClass`  
 기호를 사용자 정의 형식의 기본 클래스입니다.  
  
 `SymTagFriend`  
 사용자 정의 형식의 친구 기호입니다.  
  
 `SymTagFunctionArgType`  
 기호는 함수 인수 임을 나타냅니다.  
  
 `SymTagFuncDebugStart`  
 기호는 함수 프롤로그 코드의 끝 위치입니다.  
  
 `SymTagFuncDebugEnd`  
 기호는 함수 에필로그 코드의 시작 위치입니다.  
  
 `SymTagUsingNamespace`  
 기호가 현재 범위에서 현재 네임 스페이스 이름입니다.  
  
 `SymTagVTableShape`  
 기호에 가상 테이블에 대 한 설명입니다.  
  
 `SymTagVTable`  
 기호에 대 한 가상 테이블 포인터 임을 나타냅니다.  
  
 `SymTagCustom`  
 기호 사용자 지정 기호 이므로 여는 해석 되지 않는다  
  
 `SymTagThunk`  
 썽크 16 및 32 비트 코드 간에 데이터를 공유 하는 데 사용 되는 기호입니다.  
  
 `SymTagCustomType`  
 기호 사용자 지정 컴파일러 기호임을 나타냅니다.  
  
 `SymTagManagedType`  
 기호에 대 한 메타 데이터입니다.  
  
 `SymTagDimension`  
 기호 포트란 다차원 배열 임을 나타냅니다.  
  
 `SymTagCallSite`  
 기호는 호출 사이트를 나타냅니다.  
  
 `SymTagInlineSite`  
 기호 인라인 사이트를 나타냅니다.  
  
 `SymTagBaseInterface`  
 기호는 기본 인터페이스입니다.  
  
 `SymTagVectorType`  
 기호는 벡터 형식입니다.  
  
 `SymTagMatrixType`  
 행렬 형식의 기호입니다.  
  
 `SymTagHLSLType`  
 심볼의 높은 수준을 셰이더 언어 형식입니다.  
  
## 설명  
 디버그 파일 내의 모든 기호 심볼의 유형을 지정 하는 태그를 식별 해야 합니다.  
  
 값이 열거형에서 호출에 의해 반환 되는 [IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) 메서드.  
  
 값이 열거형에서의 특정 심볼 유형으로 검색 범위를 제한 하려면 다음 메서드에 전달 됩니다.  
  
-   [IDiaSession::findSymbolByAddr](../../debugger/debug-interface-access/idiasession-findsymbolbyaddr.md)  
  
-   [IDiaSession::findSymbolByRVA](../../debugger/debug-interface-access/idiasession-findsymbolbyrva.md)  
  
-   [IDiaSession::findSymbolByRVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyrvaex.md)  
  
-   [IDiaSession::findSymbolByToken](../../debugger/debug-interface-access/idiasession-findsymbolbytoken.md)  
  
-   [IDiaSession::findSymbolByVA](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)  
  
-   [IDiaSession::findSymbolByVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyvaex.md)  
  
-   [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)  
  
-   [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)  
  
## 요구 사항  
 헤더: cvconst.h  
  
## 참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [IDiaSession::findSymbolByAddr](../../debugger/debug-interface-access/idiasession-findsymbolbyaddr.md)   
 [IDiaSession::findSymbolByRVA](../../debugger/debug-interface-access/idiasession-findsymbolbyrva.md)   
 [IDiaSession::findSymbolByRVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyrvaex.md)   
 [IDiaSession::findSymbolByToken](../../debugger/debug-interface-access/idiasession-findsymbolbytoken.md)   
 [IDiaSession::findSymbolByVA](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)   
 [IDiaSession::findSymbolByVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyvaex.md)   
 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)