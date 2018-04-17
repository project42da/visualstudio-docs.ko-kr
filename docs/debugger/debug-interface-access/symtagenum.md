---
title: SymTagEnum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- SymTagEnum enumeration
ms.assetid: 528a50cf-e13d-46ec-a98c-323d5d047de9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0268b6e46787e772f7343e5306713554687e869a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="symtagenum"></a>SymTagEnum
기호 유형을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
enum SymTagEnum {   
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
  
## <a name="elements"></a>요소  
 `SymTagNull`  
 기호 형식이 없는 있음을 나타냅니다.  
  
 `SymTagExe`  
 기호는.exe 파일 임을 나타냅니다. 하나만 `SymTagExe` 기호 저장소 당 기호입니다. 전역 범위로 사용 하 고 어휘 부모 릴리스 레코드가 되지 않습니다.  
  
 `SymTagCompiland`  
 기호 저장소의 각 컴파일 대상 구성 요소에 대 한 컴파일 대상 기호를 나타냅니다. 네이티브 응용 프로그램에 대 한 `SymTagCompiland` 기호 이미지에 연결 된 개체 파일에 해당 합니다. 일부 종류의 Microsoft MSIL (Intermediate Language) 이미지에 대 한 클래스 마다 하나의 compiland가 있습니다.  
  
 `SymTagCompilandDetails`  
 확장 된 특성의 컴파일 대상 기호에 포함 되어 있음을 나타냅니다. 이러한 속성을 검색 하는 컴파일 대상 기호 로드 필요할 수 있습니다.  
  
 `SymTagCompilandEnv`  
 기호는 컴파일 대상에 대해 정의 된 환경 문자열 임을 나타냅니다.  
  
 `SymTagFunction`  
 기호는 함수 임을 나타냅니다.  
  
 `SymTagBlock`  
 중첩된 된 블록 기호 임을 나타냅니다.  
  
 `SymTagData`  
 기호 데이터 임을 나타냅니다.  
  
 `SymTagAnnotation`  
 코드 주석 기호 임을 나타냅니다. 이 기호의 자식 항목은 상수 데이터 문자열 (`SymTagData`, `LocIsConstant`, `DataIsConstant`). 대부분의 클라이언트는이 기호를 무시합니다.  
  
 `SymTagLabel`  
 기호가 레이블이 임을 나타냅니다.  
  
 `SymTagPublicSymbol`  
 기호 공용 기호 임을 나타냅니다. 네이티브 응용 프로그램에 대 한이 기호는 이미지를 연결 하는 동안 발생 하는 COFF 외부 기호입니다.  
  
 `SymTagUDT`  
 기호 사용자 정의 형식 (구조체, 클래스 또는 공용 구조체) 임을 나타냅니다.  
  
 `SymTagEnum`  
 열거형 기호 임을 나타냅니다.  
  
 `SymTagFunctionType`  
 함수 서명 형식 기호 임을 나타냅니다.  
  
 `SymTagPointerType`  
 기호는 포인터 형식이 임을 나타냅니다.  
  
 `SymTagArrayType`  
 기호는 배열 형식이 임을 나타냅니다.  
  
 `SymTagBaseType`  
 기호는 기본 형식을 나타냅니다.  
  
 `SymTagTypedef`  
 기호 임을 나타냅니다는 `typedef`, 즉, 다른 형식에 대 한 별칭입니다.  
  
 `SymTagBaseClass`  
 기호는 사용자 정의 형식의 기본 클래스 임을 나타냅니다.  
  
 `SymTagFriend`  
 기호는 사용자 정의 형식의 친구 임을 나타냅니다.  
  
 `SymTagFunctionArgType`  
 기호는 함수 인수 임을 나타냅니다.  
  
 `SymTagFuncDebugStart`  
 기호는 함수 프롤로그 코드의 끝 위치 임을 나타냅니다.  
  
 `SymTagFuncDebugEnd`  
 기호는 함수의 에필로그 코드의 시작 위치 임을 나타냅니다.  
  
 `SymTagUsingNamespace`  
 기호가 현재 범위에서 활성 네임 스페이스 이름 임을 나타냅니다.  
  
 `SymTagVTableShape`  
 가상 테이블 설명에는 기호가 임을 나타냅니다.  
  
 `SymTagVTable`  
 기호에 대 한 가상 테이블 포인터 임을 나타냅니다.  
  
 `SymTagCustom`  
 기호는 사용자 지정 기호 이므로 DIA.에서 해석 되지 않습니다 나타냅니다.  
  
 `SymTagThunk`  
 기호 썽크 16와 32 비트 코드 간에 데이터를 공유 하는 데 사용 되는 임을 나타냅니다.  
  
 `SymTagCustomType`  
 사용자 지정 컴파일러 기호 기호 임을 나타냅니다.  
  
 `SymTagManagedType`  
 메타 데이터에 기호 임을 나타냅니다.  
  
 `SymTagDimension`  
 기호 포트란 다차원 배열 임을 나타냅니다.  
  
 `SymTagCallSite`  
 기호 호출 사이트를 나타냅니다.  
  
 `SymTagInlineSite`  
 기호 인라인 사이트를 나타냅니다.  
  
 `SymTagBaseInterface`  
 기본 인터페이스 기호 임을 나타냅니다.  
  
 `SymTagVectorType`  
 벡터 형식 기호 임을 나타냅니다.  
  
 `SymTagMatrixType`  
 기호 행렬 형식임을 나타냅니다.  
  
 `SymTagHLSLType`  
 기호 높은 수준 셰이더 언어 형식임을 나타냅니다.  
  
## <a name="remarks"></a>설명  
 디버그 파일 내에서 모든 기호에는 기호 형식을 지정 하는 한 식별 태그는 있습니다.  
  
 이 열거형의 값에 대 한 호출에서 반환될지는 [idiasymbol:: Get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) 메서드.  
  
 이 열거형의 값은 특정 기호 형식 검색의 범위를 제한 하려면 다음 방법에 전달 됩니다.  
  
-   [IDiaSession::findSymbolByAddr](../../debugger/debug-interface-access/idiasession-findsymbolbyaddr.md)  
  
-   [IDiaSession::findSymbolByRVA](../../debugger/debug-interface-access/idiasession-findsymbolbyrva.md)  
  
-   [IDiaSession::findSymbolByRVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyrvaex.md)  
  
-   [IDiaSession::findSymbolByToken](../../debugger/debug-interface-access/idiasession-findsymbolbytoken.md)  
  
-   [IDiaSession::findSymbolByVA](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)  
  
-   [IDiaSession::findSymbolByVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyvaex.md)  
  
-   [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)  
  
-   [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)  
  
## <a name="requirements"></a>요구 사항  
 헤더: cvconst.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [기호 형식의 어휘 계층 구조](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [Idiasession:: Findsymbolbyaddr](../../debugger/debug-interface-access/idiasession-findsymbolbyaddr.md)   
 [Idiasession:: Findsymbolbyrva](../../debugger/debug-interface-access/idiasession-findsymbolbyrva.md)   
 [Idiasession:: Findsymbolbyrvaex](../../debugger/debug-interface-access/idiasession-findsymbolbyrvaex.md)   
 [Idiasession:: Findsymbolbytoken](../../debugger/debug-interface-access/idiasession-findsymbolbytoken.md)   
 [Idiasession:: Findsymbolbyva](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)   
 [Idiasession:: Findsymbolbyvaex](../../debugger/debug-interface-access/idiasession-findsymbolbyvaex.md)   
 [Idiasession:: Findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)