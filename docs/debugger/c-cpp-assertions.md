---
title: C/c + + 어설션 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [MFC], assertions
- results, checking
- result checking
- Call Stack window, assertion failures
- debugging [C++], assertions
- VERIFY macro
- assertions, side effects
- assertions
- ASSERT macro
- errors [C++], catching with assertions
- testing, error conditions with assertion statements
- _DEBUG macro
- Assertion Failed dialog box
- failures, finding locations
ms.assetid: 2d7b0121-71aa-414b-bbb6-ede1093d0bfc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 8c5180e1ef5a75a31ff6ceb6c225480e1abba5fc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="cc-assertions"></a>C/C++ 어설션
어설션 문은 프로그램의 한 지점에서 true가 될 조건을 지정 합니다. 조건이 true가 아닐 경우 어설션이 실패, 프로그램의 실행이 중단 되 고 [어설션 오류 대화 상자](../debugger/assertion-failed-dialog-box.md) 나타납니다.  
  
 Visual c + +는 다음 구문을 기반으로 하는 어설션 문을 지원 합니다.  
  
-   MFC 프로그램에 대 한 MFC 어설션입니다.  
  
-   [ATLASSERT](/cpp/atl/reference/debugging-and-error-reporting-macros#atlassert) ATL.를 사용 하는 프로그램  
  
-   C 런타임 라이브러리를 사용 하는 프로그램에 대 한 CRT 어설션 합니다.  
  
-   ANSI [assert 함수](/cpp/c-runtime-library/reference/assert-macro-assert-wassert) 다른 C/c + + 프로그램에 대 한 합니다.  
  
 논리 오류를 찾아을 작업의 결과 확인 하 고 처리 해야 하는 오류 조건을 테스트 어설션을 사용할 수 있습니다.  
  
##  <a name="BKMK_In_this_topic"></a> 항목 내용  
 [어설션 작동 방식](#BKMK_How_assertions_work)  
  
 [디버그 및 릴리스 빌드에 어설션](#BKMK_Assertions_in_Debug_and_Release_builds)  
  
 [어설션을 사용 하 여의 파생 작업](#BKMK_Side_effects_of_using_assertions)  
  
 [CRT 어설션](#BKMK_CRT_assertions)  
  
 [MFC 어설션](#BKMK_MFC_assertions)  
  
-   [MFC ASSERT_VALID 및 CObject::AssertValid](#BKMK_MFC_ASSERT_VALID_and_CObject__AssertValid)  
  
-   [AssertValid의 제한 사항](#BKMK_Limitations_of_AssertValid)  
  
 [어설션을 사용 하 여](#BKMK_Using_assertions)  
  
-   [논리 오류 검색](#BKMK_Catching_logic_errors)  
  
-   [결과 확인 하는 중](#BKMK_Checking_results_)  
  
-   [처리 되지 않은 찾기 오류](#BKMK_Testing_error_conditions_)  
  
##  <a name="BKMK_How_assertions_work"></a> 어설션 작동 방식  
 디버거 인해 중지 되는 MFC 또는 C 런타임 라이브러리 어설션을, 다음 소스를 사용할 수 있는 경우 디버거 탐색 어설션이 발생 한 소스 파일의 지점에 합니다. 어설션 메시지에도 나타납니다는 [출력 창](../ide/reference/output-window.md) 및 **어설션 오류** 대화 상자. 어설션 메시지를 복사할 수는 **출력** 나중에 참조할 저장 하려면 텍스트 창에는 창입니다. **출력** 창에는 다른 오류 메시지에도 포함 될 수 있습니다. 어설션 실패의 원인에 단서를 제공 하기 때문에 이러한 메시지를 주의 깊게 검토 합니다.  
  
 어설션을 사용 하 여 개발 하는 동안 오류를 검색 합니다. 일반적으로 각 가정에 어설션이 두 개를 사용 합니다. 예를 들어 한 인수가 NULL 임을 가정 하는 경우 어설션에서 아니라고를 테스트 하려면 사용 합니다.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Assertions_in_Debug_and_Release_builds"></a> 디버그 및 릴리스 빌드에 어설션  
 어설션 문을 컴파일할 경우에 `_DEBUG` 정의 됩니다. 그렇지 않으면 컴파일러는 null 문으로 어설션을 처리 합니다. 따라서 어설션 문이 적용 오버 헤드 없음 또는 성능 릴리스 프로그램에서 비용 및 사용 하지 않도록 할 수 `#ifdef` 지시문입니다.  
  
##  <a name="BKMK_Side_effects_of_using_assertions"></a> 어설션을 사용 하 여의 파생 작업  
 코드에 어설션 추가 하면 어설션을 부작용을 포함 하지 않는지 확인 합니다. 예를 들어를 수정 하는 경우 다음 어설션이 `nM` 값:  
  
```  
ASSERT(nM++ > 0); // Don't do this!  
  
```  
  
 때문에 `ASSERT` 프로그램의 릴리스 버전에서 식은 계산 되지 않습니다 `nM` 디버그 및 릴리스 버전에 서로 다른 값을 갖습니다. MFC에서이 문제를 방지 하려면 사용할 수 있습니다는 [확인](/cpp/mfc/reference/diagnostic-services#verify) 매크로 대신 `ASSERT`합니다.  `VERIFY` 모든 버전의 식을 계산 하지만 릴리스 버전에서 결과 확인 하지 않습니다.  
  
 함수를 가질 수 있으므로 어설션 문에서 함수 호출을 사용 하는 방법에 대 한 특히 주의 해야 예기치 않은 부작용입니다.  
  
```  
ASSERT ( myFnctn(0)==1 ) // unsafe if myFnctn has side effects  
VERIFY ( myFnctn(0)==1 ) // safe  
```  
  
 `VERIFY` 호출 `myFnctn` 디버그와 릴리스 버전 이므로를 사용할 수 있습니다. 그러나를 사용 하 여 `VERIFY` 릴리스 버전에 대 한 불필요 한 함수 호출의 오버 헤드가 있습니다.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
##  <a name="BKMK_CRT_assertions"></a> CRT 어설션  
 CRTDBG 합니다. H 헤더 파일에 정의 된 [_ASSERT 및 _ASSERTE 매크로](/cpp/c-runtime-library/reference/assert-asserte-assert-expr-macros) 어설션 검사에 대 한 합니다.  
  
|매크로|결과|  
|-----------|------------|  
|`_ASSERT`|지정 된 식이 FALSE로 계산 되는 경우의 파일 이름과 줄 번호는 `_ASSERT`합니다.|`_ASSERTE`|  
|`_ASSERTE`|와 동일 `_ASSERT`, 더하기 어설션된 식의 문자열 표현입니다.|  
  
 `_ASSERTE` 값이 false 확인 된 어설션된 식을 보고 하기 때문에 보다 강력한입니다. 이 소스 코드를 참조 하지 않고 문제를 식별할 수 있습니다. 그러나, 응용 프로그램의 디버그 버전에서 사용 하 여 설정 되었습니다. 각 식에 대 한 문자열 상수 포함 됩니다 `_ASSERTE`합니다. 많이 사용 하면 `_ASSERTE` 매크로, 메모리가 많이 차지 이러한 문자열 식입니다. 문제를를 사용 하 여 `_ASSERT` 메모리를 절약 하려면.  
  
 때 `_DEBUG` 정의 `_ASSERTE` 매크로 다음과 같이 정의 됩니다.  
  
```  
#define _ASSERTE(expr) \  
   do { \  
      if (!(expr) && (1 == _CrtDbgReport( \  
         _CRT_ASSERT, __FILE__, __LINE__, #expr))) \  
         _CrtDbgBreak(); \  
   } while (0)  
```  
  
 어설션된 식이 FALSE로 평가 되 면 [_CrtDbgReport](/cpp/c-runtime-library/reference/crtdbgreport-crtdbgreportw) (기본적으로는 메시지 대화 상자를 사용) 어설션 실패를 보고 하기 위해 호출 됩니다. 선택 하는 경우 **을 다시 시도 하십시오** 메시지 대화 상자에서 `_CrtDbgReport` 1을 반환 하 고 `_CrtDbgBreak` 디버거를 통해 호출 `DebugBreak`합니다.  
  
### <a name="checking-for-heap-corruption"></a>힙 손상 확인  
 다음 예제에서는 [_CrtCheckMemory](/cpp/c-runtime-library/reference/crtcheckmemory) 힙 손상을 확인 하려면:  
  
```  
_ASSERTE(_CrtCheckMemory());  
```  
  
### <a name="checking-pointer-validity"></a>포인터 유효성 확인  
 다음 예제에서는 [_CrtIsValidPointer](/cpp/c-runtime-library/reference/crtisvalidpointer) 읽기 또는 쓰기에 대 한 지정 된 메모리 범위가 올바른지 확인 합니다.  
  
```  
_ASSERTE(_CrtIsValidPointer( address, size, TRUE );  
```  
  
 다음 예제에서는 [_CrtIsValidHeapPointer](/cpp/c-runtime-library/reference/crtisvalidheappointer) 포인터가 가리키는 메모리에 로컬 힙 확인 하려면 (힙에 만들고 C 런타임 라이브러리의이 인스턴스에서 관리-DLL 라이브러리의 고유 인스턴스를 가질 수 있습니다 및 따라서 자체 힙의 응용 프로그램 힙 외부)입니다. 이 어설션이 null 이나 아니라 정적 변수, 스택 변수 및 다른 로컬이 아닌 메모리에 대 한 포인터도 범위를 벗어나는 주소입니다.  
  
```  
_ASSERTE(_CrtIsValidPointer( myData );  
```  
  
### <a name="checking-a-memory-block"></a>메모리 블록 확인  
 다음 예제에서는 [_CrtIsMemoryBlock](/cpp/c-runtime-library/reference/crtismemoryblock) 메모리 블록 로컬 힙에 고 올바른 블록 형식이 확인할 수 있습니다.  
  
```  
_ASSERTE(_CrtIsMemoryBlock (myData, size, &requestNumber, &filename, &linenumber));  
```  
  
 [항목 내용](#BKMK_In_this_topic)  
  
##  <a name="BKMK_MFC_assertions"></a> MFC 어설션  
 MFC 정의 [ASSERT](http://msdn.microsoft.com/Library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) 어설션 검사에 대 한 매크로입니다. 또한 정의 `MFC ASSERT_VALID` 및 `CObject::AssertValid` 의 내부 상태 검사에 대 한 메서드는 `CObject`-파생 된 개체입니다.  
  
 경우 MFC의 인수 `ASSERT` 매크로 계산 결과가 0 또는 false 이면 매크로 프로그램 실행을 중지 한 사용자에 게 알립니다; 그리고 그렇지 않은 경우 실행이 계속 됩니다.  
  
 어설션이 실패 한 경우, 메시지 대화 상자에서 어설션의 줄 번호 및 소스 파일의 이름을 표시 합니다. 대화 상자에서 다시 시도 선택 하면 상자에 대 한 호출 [AfxDebugBreak](/cpp/mfc/reference/diagnostic-services#afxdebugbreak) 으로 중단 하 고 디버거 실행이 넘어갑니다. 해당 시점에 호출 스택을 검토 하 고 어설션이 실패 한 이유를 확인 하려면 다른 디버거 기능을 사용 하 여 수입니다. 사용 하도록 설정한 경우 [Just in time 디버깅](../debugger/just-in-time-debugging-in-visual-studio.md), 및 디버거 아직 실행 되지 않는, 대화 상자에서 디버거를 시작할 수 있습니다.  
  
 다음 예제에서는 사용 하는 방법을 보여 줍니다. `ASSERT` 함수의 반환 값을 확인 하려면:  
  
```  
int x = SomeFunc(y);  
ASSERT(x >= 0);   //  Assertion fails if x is negative  
```  
  
 와 ASSERT를 사용할 수는 [IsKindOf](/cpp/mfc/reference/cobject-class.md#CObject__IsKindOf) 형식 검사 함수 인수를 제공 하는 함수:  
  
```  
ASSERT( pObject1->IsKindOf( RUNTIME_CLASS( CPerson ) ) );  
```  
  
 `ASSERT` 매크로 릴리스 버전에 없는 코드를 생성 합니다. 식을 계산 하 고 릴리스 버전에 필요한 경우 사용 된 [확인](/cpp/mfc/reference/diagnostic-services#verify) 매크로 ASSERT 대신 합니다.  
  
###  <a name="BKMK_MFC_ASSERT_VALID_and_CObject__AssertValid"></a> MFC ASSERT_VALID 및 CObject::AssertValid  
 [CObject::AssertValid](/cpp/mfc/reference/cobject-class.md#CObject__AssertValid) 메서드는 개체의 내부 상태에 대 한 런타임 검사를 제공 합니다. 재정의 필요 하지 않지만 `AssertValid` 에서 클래스를 파생 시키는 경우 `CObject`, 클래스 만들 수 있습니다 프로그램 안정적이 됩니다. `AssertValid` 모든 유효한 값이 들어 있는지 확인 하는 개체의 멤버 변수에서 어설션을 수행 해야 합니다. 예를 들어 포인터 멤버 변수가 NULL이 아닌지 확인 해야 합니다.  
  
 선언 하는 방법을 보여 주는 다음 예제는 `AssertValid` 함수:  
  
```  
class CPerson : public CObject  
{  
protected:  
    CString m_strName;  
    float   m_salary;  
public:  
#ifdef _DEBUG  
    // Override  
    virtual void AssertValid() const;  
#endif  
    // ...  
};  
  
```  
  
 재정의 하는 경우 `AssertValid`, 호출의 기본 클래스 버전 `AssertValid` 직접 검사를 수행 하기 전에. 그런 다음 다음과 같이 파생 클래스에 고유한 멤버를 확인 하려면 ASSERT 매크로 사용:  
  
```  
#ifdef _DEBUG  
void CPerson::AssertValid() const  
{  
    // Call inherited AssertValid first.  
    CObject::AssertValid();  
  
    // Check CPerson members...  
    // Must have a name.  
    ASSERT( !m_strName.IsEmpty());  
    // Must have an income.  
    ASSERT( m_salary > 0 );  
}  
#endif  
  
```  
  
 개체를 저장할 멤버 변수가 있는 경우 사용할 수 있습니다는 `ASSERT_VALID` 내부 유효성을 테스트 하려면 매크로 (해당 클래스를 재정의 하는 경우 `AssertValid`).  
  
 예를 들어 클래스 `CMyData`, 점에서 [CObList](/cpp/mfc/reference/coblist-class) 멤버 변수 중 하나입니다. `CObList` 변수인 `m_DataList`, 컬렉션을 저장 `CPerson` 개체입니다. 약식된 선언은 `CMyData` 다음과 같습니다.  
  
```  
class CMyData : public CObject  
{  
    // Constructor and other members ...  
    protected:  
        CObList* m_pDataList;  
    // Other declarations ...  
    public:  
#ifdef _DEBUG  
        // Override:  
        virtual void AssertValid( ) const;  
#endif  
    // And so on ...  
};  
  
```  
  
 `AssertValid` 에서 재정의할 `CMyData` 다음과 같습니다.  
  
```  
#ifdef _DEBUG  
void CMyData::AssertValid( ) const  
{  
    // Call inherited AssertValid.  
    CObject::AssertValid( );  
    // Check validity of CMyData members.  
    ASSERT_VALID( m_pDataList );  
    // ...  
}  
#endif  
  
```  
  
 `CMyData` 사용 하 여는 `AssertValid` 해당 데이터 멤버에 저장 된 개체의 유효성을 테스트 하기 위한 메커니즘입니다. 재정의 `AssertValid` 의 `CMyData` 호출의 `ASSERT_VALID` m_pDataList 멤버 변수 자체에 대 한 매크로입니다.  
  
 유효성 테스트에서 중지 하지 않으면이 수준 때문에 클래스 `CObList` 재정의 `AssertValid`합니다. 이 재정의 목록의 내부 상태에 대 한 테스트 추가 유효성 검사를 수행 합니다. 에 유효성을 테스트 하는 따라서는 `CMyData` 개체는 저장 된의 내부 상태에 대 한 추가 유효성 테스트를 까지로 `CObList` 목록 개체.  
  
 더 많은 일부 작업에 대 한 유효성 테스트를 추가할 수 있습니다는 `CPerson` 개체 목록에도 저장 합니다. 클래스를 파생 시킬 수 `CPersonList` 에서 `CObList` 재정의 `AssertValid`합니다. 재정의 호출 `CObject::AssertValid` 다음 목록에서 반복 하 고 호출 `AssertValid` 각 `CPerson` 개체 목록에 저장 합니다. `CPerson` 이미이 항목의 시작 부분에 표시 된 클래스에서 재정의 `AssertValid`합니다.  
  
 디버깅을 위해 빌드할 때 강력한 메커니즘입니다. 릴리스 이후에 빌드용 메커니즘은 자동으로 해제 됩니다.  
  
###  <a name="BKMK_Limitations_of_AssertValid"></a> AssertValid의 제한 사항  
 트리거된 어설션은 나타냅니다 개체가 잘못 된 실행이 중지 됩니다. 그러나 어설션의 부족 발견 된 문제가 있지만 개체 반드시 좋은 것만 나타냅니다.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Using_assertions"></a> 어설션을 사용 하 여  
  
###  <a name="BKMK_Catching_logic_errors"></a> 논리 오류 검색  
 프로그램의 논리에 따라 충족 해야 하는 조건에 대 한 어설션을 설정할 수 있습니다. 어설션이 논리 오류가 발생 하지 않는 한 아무 효과가 없습니다.  
  
 예를 들어, 변수, 컨테이너에서 가스 분자를 시뮬레이션 하는 경우 `numMols` 분자 총 수를 나타냅니다. 이 번호는 다음과 같은 MFC 어설션 문을 포함할 수 있으므로 0 보다 작을 수 없습니다.  
  
```  
ASSERT(numMols >= 0);  
  
```  
  
 또는 다음과 같은 CRT 어설션이 포함 될 수 있습니다.  
  
```  
_ASSERT(numMols >= 0);  
```  
  
 프로그램이 제대로 작동 하는 경우이 문은 아무 효과가 없습니다. 그러나 논리 오류가 발생 하는 경우 `numMols` 를 0 보다 작을 수, 어설션이 중지 하면 프로그램 실행 하 고 표시 된 [어설션 실패 대화 상자](../debugger/assertion-failed-dialog-box.md)합니다.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Checking_results_"></a> 결과 확인 하는 중  
 어설션은 작업 결과 빠른 visual 검사에서 명확 하지 테스트를 위해 중요 합니다.  
  
 예를 들어 다음 변수를 업데이트 하는 코드가 `iMols` 연결 리스트에서 가리키는 내용에 따라 `mols`:  
  
```  
/* This code assumes that type has overloaded the != operator  
 with const char *   
It also assumes that H2O is somewhere in that linked list.   
Otherwise we'll get an access violation... */  
while (mols->type != "H2O")  
{  
 iMols += mols->num;  
 mols = mols->next;  
}  
ASSERT(iMols<=numMols); // MFC version  
_ASSERT(iMols<=numMols); // CRT version  
```  
  
 에 분자 수 계산 `iMols` 보다 작거나 분자, 총 수에 반드시 `numMols`합니다. 루프에 됩니다 경우 어설션 문은 해당 조건을 테스트 인증 하는 루프 후 데 표시 되지 않습니다.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Testing_error_conditions_"></a> 처리 되지 않은 찾기 오류  
 코드의 한 지점에서 오류 조건을 테스트할 수 있는 오류 처리 해야 어설션을 사용할 수 있습니다. 다음 예제에서는 그래픽 루틴이 0 성공 또는 오류 코드를 반환합니다.  
  
```  
myErr = myGraphRoutine(a, b);  
  
/* Code to handle errors and  
   reset myErr if successful */  
  
ASSERT(!myErr); -- MFC version  
_ASSERT(!myErr); -- CRT version  
```  
  
 오류 처리 코드가 제대로 작동 하는 경우 오류를 처리 해야 하 고 `myErr` 어설션이 도달 하기 전에 0으로 다시 설정 합니다. 경우 `myErr` 된 다른 값, 어설션 실패, 프로그램 중단 되 고 [어설션 실패 대화 상자](../debugger/assertion-failed-dialog-box.md) 나타납니다.  
  
 그러나 어설션 문은 오류 처리 코드에 대 한 대체 않습니다. 다음 예제에는 최종 릴리스 코드에서 문제를 초래할 수 있는 어설션 문을 보여 줍니다.  
  
```  
myErr = myGraphRoutine(a, b);  
  
/* No Code to handle errors */  
  
ASSERT(!myErr); // Don't do this!  
_ASSERT(!myErr); // Don't do this, either!  
```  
  
 이 코드는 오류 조건을 처리 하기 위해 어설션 문을 사용 합니다. 모든 오류 코드가 반환 되는 결과적으로, `myGraphRoutine` 최종 릴리스 코드에서 처리 되지 것입니다.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
## <a name="see-also"></a>참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [네이티브 코드 디버그](../debugger/debugging-native-code.md)   
 [관리 코드에 어설션 사용](../debugger/assertions-in-managed-code.md)