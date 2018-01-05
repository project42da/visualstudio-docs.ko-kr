---
title: "Visual Studio c + + 코어 지침 참조 검사에서 | Microsoft Docs"
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: code analysis, C++ core check
ms.assetid: f1429463-136e-41ed-8a75-a8dbf0b4fd89
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c17574722804409b58d648af66b255888e945db2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="c-core-guidelines-checker-reference"></a>C + + 핵심 지침 검사기 참조
이 섹션에는 c + + 코어 지침 검사기 경고가 나열 됩니다. 코드 분석에 대 한 정보를 참조 하십시오. [/analyze (코드 분석)](/cpp/build/reference/analyze-code-analysis) 및 [빠른 시작: C/c + +에 대 한 코드 분석](../code-quality/quick-start-code-analysis-for-c-cpp.md)합니다.  
  
**참고**: 둘 이상의 그룹에 속한 몇 가지 경고가 발생 했으며 일부 경고는 참조 항목입니다.

## <a name="ownerpointer-group"></a>OWNER_POINTER 그룹

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md)  
  이동 생성자를 설정한 경우 힙 할당 하는 대신 범위가 지정 된 개체를 반환 합니다. 참조 [c + + 코어 지침 R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)합니다. 
     
[C26403 RESET_OR_DELETE_OWNER](C26403.md)  
  다시 설정 하거나 소유자를 명시적으로 삭제\<T > '% 변수 %' 포인터입니다. 참조 [c + + 코어 지침 R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)합니다.  
     
[C26404 DONT_DELETE_INVALID](C26404.md)  
  소유자를 삭제 하지 마십시오\<T >는 유효 하지 않은 상태일 수 있습니다. 참조 [c + + 코어 지침 R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)합니다.  

[C26405 DONT_ASSIGN_TO_VALID](C26405.md)  
  소유자에 할당 하지 않으면\<T > 유효한 상태에 발생할 수 있는 합니다. 참조 [c + + 코어 지침 R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)합니다.  

[C26406 DONT_ASSIGN_RAW_TO_OWNER](C26406.md)  
  소유자에 대 한 원시 포인터를 할당 하지 않으면\<T >. 참조 [c + + 코어 지침 R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)합니다.  
  
[C26407 DONT_HEAP_ALLOCATE_UNNECESSARILY](C26407.md)  
  범위 지정 된 개체는 것을 선호 하지 않는 힙-할당 합니다 불필요 하 게 합니다. 참조 [c + + 코어 지침 R.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped)합니다.  

[C26429 USE_NOTNULL](C26429.md)  
  '% 기호 %' 기호는 nullness에 대 한 테스트 되지, not_null로 표시할 수 있습니다. 참조 [c + + 코어 지침 F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)합니다.  

[C26430 TEST_ON_ALL_PATHS](C26430.md)  
  모든 경로 대해서는 nullness 기호 '% 기호 %'은 테스트 되지 않았습니다. 참조 [c + + 코어 지침 F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)합니다.  
  
[C26431 DONT_TEST_NOTNULL](C26431.md)  
  '% Expr %' 식의 형식은 이미 gsl::not_null 합니다. Nullness에 대 한 테스트 하지 마십시오. 참조 [c + + 코어 지침 F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)합니다.  

## <a name="rawpointer-group"></a>RAW_POINTER 그룹
 
[C26400 NO_RAW_POINTER_ASSIGNMENT](c26400.md)  
소유자를 가진 할당 또는 함수 호출의 결과 할당 하지 않으면\<T > 원시 포인터를 반환 값, 소유자를 사용 하 여<T> 대신 합니다. 참조 [c + + 코어 지침 I.11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw)합니다. 

[C26401 DONT_DELETE_NON_OWNER](c26401.md)  
소유자가 아닌 원시 포인터를 삭제 하지 마십시오\<T >. 참조 [c + + 코어 지침 I.11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw)합니다. 

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md)   는 이동 생성자가 있는 경우 힙 할당 하는 대신 범위가 지정 된 개체를 반환 합니다. 참조 [c + + 코어 지침 R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr)합니다. 
 
[C26408 NO_MALLOC_FREE](C26408.md)  
  Nothrow 버전의 delete 새로 추가 된 것을 선호를 malloc () 및 free ()을 방지 합니다. 참조 [c + + 코어 지침 R.10](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-mallocfree)합니다.  
  
[C26409 NO_NEW_DELETE](C26409.md)  
  새 호출 하지 마세요 명시적으로 삭제 사용, 및 std::make_unique\<T > 대신 합니다. 참조 [c + + 코어 지침 R.11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-newdelete)합니다.  

[C26429 USE_NOTNULL](C26429.md)  
  '% 기호 %' 기호는 nullness에 대 한 테스트 되지, not_null로 표시할 수 있습니다. 참조 [c + + 코어 지침 F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)합니다.  
  
[C26430 TEST_ON_ALL_PATHS](C26430.md)  
  모든 경로 대해서는 nullness 기호 '% 기호 %'은 테스트 되지 않았습니다. 참조 [c + + 코어 지침 F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)합니다.  
  
[C26431 DONT_TEST_NOTNULL](C26431.md)  
  '% Expr %' 식의 형식은 이미 gsl::not_null 합니다. Nullness에 대 한 테스트 하지 마십시오. 참조 [c + + 코어 지침 F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value)합니다.  
  
[C26481 NO_POINTER_ARITHMETIC](C26481.md)  
  포인터 산술 연산을 사용 하지 마십시오. 범위를 대신 사용 합니다. 참조 [c + + 코어 지침 Bounds.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)합니다.  

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md)   
  식 '%expr% ': 포인터 decay 배열이 없습니다. 참조 [c + + 코어 지침 Bounds.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)합니다.  

## <a name="uniquepointer-group"></a>UNIQUE_POINTER 그룹
  
[C26410 NO_REF_TO_CONST_UNIQUE_PTR](C26410.md)  
  매개 변수 '% 매개 변수 %'에 대 한 참조는 `const` 고유 포인터 const T * 또는 const T를 사용 하 여 & 대신 합니다. 참조 [c + + 코어 지침 R.32](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-uniqueptrparam)합니다.  
     
[C26411 NO_REF_TO_UNIQUE_PTR](C26411.md)  
  T * 또는 T 사용, 매개 변수 '% 매개 변수 %'는 고유한 포인터에 대 한 참조 및 다시 할당 되거나 다시 설정 되지 않습니다 및 대신 합니다. 참조 [c + + 코어 지침 R.33](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-reseat)합니다.  
     
[C26414 RESET_LOCAL_SMART_PTR](C26414.md)  
  이동, 복사, 다시 할당 또는 '% 기호 %'와 같은 로컬 스마트 포인터를 다시 설정 합니다. 참조 [c + + 코어 지침 R.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped)합니다.  
    
[C26415 SMART_PTR_NOT_NEEDED](C26415.md)  
  스마트 포인터 매개 변수 '% 기호 %'가 포함 된 액세스 포인터에만 사용 됩니다. T 또는 T *를 사용 하 여 & 대신 합니다. 참조 [c + + 코어 지침 R.30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam)합니다.  

## <a name="sharedpointer-group"></a>SHARED_POINTER 그룹

[C26414 RESET_LOCAL_SMART_PTR](C26414.md)  
  이동, 복사, 다시 할당 또는 '% 기호 %'와 같은 로컬 스마트 포인터를 다시 설정 합니다. 참조 [c + + 코어 지침 R.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped)합니다.  
    
[C26415 SMART_PTR_NOT_NEEDED](C26415.md)  
  스마트 포인터 매개 변수 '% 기호 %'가 포함 된 액세스 포인터에만 사용 됩니다. T 또는 T *를 사용 하 여 & 대신 합니다. 참조 [c + + 코어 지침 R.30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam)합니다.  
    
[C26416 NO_RVALUE_REF_SHARED_PTR](C26416.md)  
  공유 포인터 매개 변수 '% 기호 %'는 rvalue 참조로 전달 됩니다. 대신 값으로 전달 합니다. 참조 [c + + 코어 지침 R.34](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-owner)합니다.  
  
[C26417 NO_LVALUE_REF_SHARED_PTR](C26417.md)  
  공유 포인터 매개 변수 '% 기호 %' 참조로 전달 하 고 다시 설정 하지 또는 다시 할당 합니다. T 또는 T *를 사용 하 여 & 대신 합니다. 참조 [c + + 코어 지침 R.35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam)합니다.  
  
[C26418 NO_VALUE_OR_CONST_REF_SHARED_PTR](C26418.md)  
  공유 포인터 매개 변수 '% 기호 %' 복사 되거나 이동 합니다. T 또는 T *를 사용 하 여 & 대신 합니다. 참조 [c + + 코어 지침 R.36](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-const)합니다.  

## <a name="declaration-group"></a>선언 그룹
    
[C26426 NO_GLOBAL_INIT_CALLS](C26426.md)  
  전역 이니셜라이저는 constexpr이 아닌 함수 '% 기호 %'를 호출합니다. 참조 [c + + 코어 지침 I.22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects)합니다.  
  
[C26427 NO_GLOBAL_INIT_EXTERNS](C26427.md)  
  '% 기호 %' extern 개체를 액세스 하는 전역 이니셜라이저입니다. 참조 [c + + 코어 지침 I.22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects)합니다.  
  
## <a name="class-group"></a>클래스 그룹
    
[C26432 DEFINE_OR_DELETE_SPECIAL_OPS](C26432.md)  
  정의 하거나 '% 기호 %' 형식에서 기본 작업을 삭제 하는 경우 정의 하거나 모두 삭제 합니다. 참조 [c + + 코어 지침 C.21](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c21-if-you-define-or-delete-any-default-operation-define-or-delete-them-all)합니다.  
  
[C26434 DONT_HIDE_METHODS](C26434.md)  
  함수 '%symbol_1% '는 비가상 함수 '%symbol_2% '를 숨깁니다. 참조 [c + + 코어 지침 C.128](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c128-virtual-functions-should-specify-exactly-one-of-virtual-override-or-final)합니다.  
  
[C26436 NEED_VIRTUAL_DTOR](C26436.md)  
  형식에 가상 함수가 ' % 기호 %' 중 하나가 공용 가상 또는 보호 된 비가상 소멸자를 필요합니다. 참조 [c + + 코어 지침 C.35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c35-a-base-class-destructor-should-be-either-public-and-virtual-or-protected-and-nonvirtual)합니다.  

## <a name="type-group"></a>형식 그룹
    
[C26437 DONT_SLICE](C26437.md)  
  분할 되지 않습니다. 참조 [c + + 코어 지침 ES.63](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es63-dont-slice)합니다.  

## <a name="style-group"></a>스타일 그룹  
[C26438 NO_GOTO](C26438.md)  
  방지 `goto`합니다. 참조 [c + + 코어 지침 ES.76](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es76-avoid-goto)합니다.  
  
## <a name="function-group"></a>기능 그룹
    
[C26439 SPECIAL_NOEXCEPT](C26439.md)  
  이러한 종류의 함수가 throw 되지 않습니다. 선언 `noexcept`합니다. 참조 [c + + 코어 지침 F.6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept)합니다.  
  
[C26440 DECLARE_NOEXCEPT](C26440.md)  
  '% 기호 %' 함수를 선언할 수 있습니다 `noexcept`합니다. 참조 [c + + 코어 지침 F.6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept)합니다.  

## <a name="concurrency-group"></a>동시성 그룹
    
[C26441 NO_UNNAMED_GUARDS](C26441.md)  
 가드 개체 이름을 지정 해야 합니다. 참조 [c + + 핵심 지침 cp.44](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#cp44-remember-to-name-your-lock_guards-and-unique_locks)합니다.  

## <a name="const-group"></a>CONST 그룹
    
C26460 USE_CONST_REFERENCE_ARGUMENTS:  
  '% 함수 %' 함수에 대 한 참조 인수 '% 인수 %'으로 표시할 수 있습니다 `const`합니다. 참조 [c + + 핵심 지침 con.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref)합니다.  
  
C26461 USE_CONST_POINTER_ARGUMENTS: '% 함수 %' 함수에 대 한 포인터 인수 '% 인수 %'에 대 한 포인터로 표시할 수 있습니다 `const`합니다. 참조 [c + + 핵심 지침 con.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref)합니다.  
  
C26462 USE_CONST_POINTER_FOR_VARIABLE:  
  '% 변수 %'가 가리키는 값을 한 번만 할당할에 대 한 포인터로 표시 `const`합니다. 참조 [c + + 핵심 지침 con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction)합니다.  
  
C26463 USE_CONST_FOR_ELEMENTS:  
  '% 배열 %' 배열의 요소를 한 번만 표시 요소 할당 된 `const`합니다. 참조 [c + + 핵심 지침 con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction)합니다.  
  
C26464 USE_CONST_POINTER_FOR_ELEMENTS:  
  '% 배열 %' 배열의 요소를 가리키고 값은 한 번만 표시 요소에 대 한 포인터를 할당 됩니다 `const`합니다. 참조 [c + + 핵심 지침 con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction)합니다.  

C26496 USE_CONST_FOR_VARIABLE:  
  '% 변수 %' 변수가 한 번만 할당로 표시 `const`합니다. 참조 [c + + 핵심 지침 con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction)합니다.  
  
C26497 USE_CONSTEXPR_FOR_FUNCTION:  
  이 함수 % 함수 %를 표시할 수 없습니다 `constexpr` 컴파일 시간 계산을 사용할 경우. 참조 [c + + 코어 지침 F.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rf-constexpr)합니다.  
  
C26498 USE_CONSTEXPR_FOR_FUNCTIONCALL:  
  이 함수 호출 % 함수 % צ ְ ײ `constexpr` 컴파일 시간 계산을 사용할 경우. 참조 [c + + 핵심 지침 con.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-constexpr)합니다.  

## <a name="type-group"></a>형식 그룹
C26465 NO_CONST_CAST_UNNECESSARY:  
  사용 하지 않는 `const_cast` 캐스팅 하 `const`합니다. `const_cast`필수가 아닙니다. 상수 성을 또는 변동성이이 변환에 의해 제거 되지 않습니다. 참조 [c + + 코어 지침 Type.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-constcast)합니다.  
  
C26466 NO_STATIC_DOWNCAST_POLYMORPHIC:  
  사용 하지 않는 `static_cast` downcast 합니다. 다형 형식에서 캐스팅 dynamic_cast를 사용 해야 합니다. 참조 [c + + 코어 지침 Type.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-downcast)합니다.  
  
C26471 NO_REINTERPRET_CAST_FROM_VOID_PTR:  
  사용 하지 않는 `reinterpret_cast`합니다. void * 캐스트 צ ְ ײ `static_cast`합니다. 참조 [c + + 코어 지침 Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast)합니다.  
  
[C26472 NO_CASTS_FOR_ARITHMETIC_CONVERSION](C26472.md)  
  사용 하지 않는 한 `static_cast` 산술 변환에 대 한 합니다. 중괄호 초기화, gsl::narrow_cast 또는 gsl::narow를 사용 합니다. 참조 [c + + 코어 지침 Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast)합니다.  
  
[C26473 NO_IDENTITY_CAST](C26473.md)  
  소스 형식과 대상 유형 동일한 있는 포인터 형식 간의 캐스팅 하지 마십시오. 참조 [c + + 코어 지침 Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast)합니다.  
  
[C26474 NO_IMPLICIT_CAST](C26474.md)  
  변환이 암시적 일 수 있는 경우 포인터 형식 간의 캐스팅 하지 마십시오. 참조 [c + + 코어 지침 Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast)합니다.  
  
[C26475 NO_FUNCTION_STYLE_CASTS](C26475.md)  
  함수 스타일 캐스트 C를 사용 하지 마십시오. 참조 [c + + 코어 지침 ES.49](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es49-if-you-must-use-a-cast-use-a-named-cast)합니다.  
     
C26490 NO_REINTERPRET_CAST:  
  사용 하지 않는 `reinterpret_cast`합니다. 참조 [c + + 코어 지침 Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)합니다.  
  
C26491 NO_STATIC_DOWNCAST:  
  사용 하지 않는 `static_cast` downcast 합니다. 참조 [c + + 코어 지침 Type.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)합니다.  
  
C26492 NO_CONST_CAST:  
  사용 하지 않는 `const_cast` 캐스팅 하 `const`합니다. 참조 [c + + 코어 지침 Type.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)합니다.  
    
C26493 NO_CSTYLE_CAST:  
  C 스타일 캐스트를 사용 하지 마십시오. 참조 [c + + 코어 지침 Type.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)합니다. 
     
C26494 VAR_USE_BEFORE_INIT:  
  '% 변수 %' 변수는 초기화 되지 않았습니다. 항상 개체를 초기화 합니다. 참조 [c + + 코어 지침 Type.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)합니다.  
  
C26495 MEMBER_UNINIT:  
  '% 변수 %' 변수는 초기화 되지 않았습니다. 항상 멤버 변수를 초기화 합니다. 참조 [c + + 코어 지침 Type.6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type)합니다.  
  
## <a name="bounds-group"></a>경계 그룹

[C26481 NO_POINTER_ARITHMETIC](C26481.md)   
  포인터 산술 연산을 사용 하지 마십시오. 범위를 대신 사용 합니다. 참조 [c + + 코어 지침 Bounds.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)합니다.  
  
C26482 NO_DYNAMIC_ARRAY_INDEXING:  
  상수 식을 사용 하 여 배열에만 인덱스입니다. 참조 [c + + 코어 지침 Bounds.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)합니다.  
  
C26483 STATIC_INDEX_OUT_OF_RANGE:  
  값 % 값 % 경계를 벗어납니다 (0, % 바인딩된 %) 변수 '% 변수 %'입니다. 배열 범위 내에 있는 상수 식을 사용 하 여 배열에만 인덱스입니다. 참조 [c + + 코어 지침 Bounds.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)합니다.  

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md)   
  식 '%expr% ': 포인터 decay 배열이 없습니다. 참조 [c + + 코어 지침 Bounds.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds)합니다.  
  
## <a name="see-also"></a>참고 항목  
[C + + 코어 지침 검사기를 사용 하 여](using-the-cpp-core-guidelines-checkers.md)
