---
title: "C/C++ 어설션 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "_DEBUG 매크로"
  - "ASSERT 매크로"
  - "어설션 오류 대화 상자"
  - "어설션"
  - "어설션, 파생 작업"
  - "호출 스택 창, 어설션 오류"
  - "디버깅[C++], 어설션"
  - "디버깅[MFC], 어설션"
  - "오류[C++], 어설션으로 catch"
  - "오류, 위치 찾기"
  - "결과 확인"
  - "결과, 확인"
  - "테스트, 어설션 문이 있는 오류 조건"
  - "VERIFY 매크로"
ms.assetid: 2d7b0121-71aa-414b-bbb6-ede1093d0bfc
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# C/C++ 어설션
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

어설션 문은 프로그램의 한 지점에서 true가 되도록 조건을 지정합니다.  조건이 true가 아니면, 어설션 오류가 발생하고 프로그램 실행이 중단되며 [어설션 오류 대화 상자](../debugger/assertion-failed-dialog-box.md)가 나타납니다.  
  
 Visual C\+\+에서는 다음 구문을 기반으로 하는 어설션 문을 지원합니다.  
  
-   MFC 프로그램용 MFC 어설션  
  
-   ATL을 사용하는 프로그램용 [ATLASSERT](../Topic/ATLASSERT.md)  
  
-   C 런타임 라이브러리를 사용하는 프로그램용 CRT 어설션  
  
-   기타 C\/C\+\+ 프로그램용 ANSI [assert function](/visual-cpp/c-runtime-library/reference/assert-macro-assert-wassert)  
  
 어설션을 논리 오류 찾기, 작업의 결과 확인, 및 처리 해야 할 오류 조건 테스트에 사용할 수 있습니다.  
  
##  <a name="BKMK_In_this_topic"></a> 항목 내용  
 [어설션 작업 방법](#BKMK_How_assertions_work)  
  
 [디버그 및 릴리스 빌드에서 어설션](#BKMK_Assertions_in_Debug_and_Release_builds)  
  
 [어설션 사용으로 인한 부작용](#BKMK_Side_effects_of_using_assertions)  
  
 [CRT 어설션](#BKMK_CRT_assertions)  
  
 [MFC 어설션](#BKMK_MFC_assertions)  
  
-   [MFC ASSERT_VALID 및 CObject::AssertValid](#BKMK_MFC_ASSERT_VALID_and_CObject__AssertValid)  
  
-   [AssertValid 한계](#BKMK_Limitations_of_AssertValid)  
  
 [어설션 사용](#BKMK_Using_assertions)  
  
-   [논리 오류 찾기.](#BKMK_Catching_logic_errors)  
  
-   [결과 확인](#BKMK_Checking_results_)  
  
-   [처리 되지 않은 오류 찾기](#BKMK_Testing_error_conditions_)  
  
##  <a name="BKMK_How_assertions_work"></a> 어설션 작업 방법  
 MFC나 C 런타임 라이브러리 어설션으로 인해 디버거가 중지될 때, 만약 소스 파일이 있는 경우, 디버거는 소스 파일에서 어설션이 발생한 지점을 탐색합니다.  **어설션 오류** 대화 상자와 [출력 창](../ide/reference/output-window.md) 모두에 어설션 메시지가 나타납니다.  어설션 메시지를 **출력** 창에서 텍스트 창으로 복사해 저장하면 나중에 참조할 수 있습니다.  **출력** 창에 다른 오류 메시지가 있는 경우도 있습니다.  이 메시지를 주의 깊게 검토하면 어설션 오류의 원인을 찾을 수 있습니다.  
  
 어설션을 사용하여 개발 하는 동안 오류를 감지.  일반적으로, 각 가정에 대한 하나의 어설션을 사용 합니다.  예를 들어, 인수가 NULL이 아니라고 생각되면 어설션 문을 사용하여 테스트하십시오.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Assertions_in_Debug_and_Release_builds"></a> 디버그 및 릴리스 빌드에서 어설션  
 어설션 문은 `_DEBUG` 가 정의된 경우에만 컴파일합니다.  그렇지 않은 경우, 컴파일러는 어설션을 null 문으로 처리 합니다.  따라서, 어설션 문은 오버 헤드 혹은 최종 릴리스 프로그램의 성능 비용을 부과 하지 않고, `#ifdef` 지시문을 사용하지 않도록 합니다.  
  
##  <a name="BKMK_Side_effects_of_using_assertions"></a> 어설션 사용으로 인한 부작용  
 코드에 어설션을 추가할 경우 어설션에 의도하지 않은 연산이 없는지 확인하십시오.  예를 들어, `nM` 값을 수정하는 다음 어설션을 고려하세요:  
  
```  
ASSERT(nM++ > 0); // Don't do this!  
  
```  
  
 프로그램의 릴리스 버전에서는 `ASSERT` 식을 계산하지 않기 때문에, 디버그 버전과 릴리스 버전에서 `nM` 의 값이 다릅니다.  MFC에서 이 문제를 방지 하려면, [확인](../Topic/VERIFY.md) 매크로를 `ASSERT` 대신 사용할 수 있습니다.  `VERIFY` 는 모든 버전에서 식을 계산 하지만 릴리스 버전에서는 결과를 확인 하지 않습니다.  
  
 함수를 계산할 때 예기치 않은 의도하지 않은 연산이 발생할 수 있으므로 어설션 문에서 함수를 호출할 때는 특히 주의하십시오.  
  
```  
ASSERT ( myFnctn(0)==1 ) // unsafe if myFnctn has side effects  
VERIFY ( myFnctn(0)==1 ) // safe  
```  
  
 `VERIFY` 는 디버그 버전과 릴리스 버전에서 모두 `myFnctn` 을 호출하기 때문에 사용이 가능합니다.  그러나, 릴리스 버전에서는 `VERIFY` 의 사용은 여전히 불필요한 함수 호출의 오버헤드를 부과합니다.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
##  <a name="BKMK_CRT_assertions"></a> CRT 어설션  
 CRTDBG.H 헤더 파일에서 [\_ASSERT 및 \_ASSERTE 매크로](/visual-cpp/c-runtime-library/reference/assert-asserte-assert-expr-macros)를 정의하여 어설션을 확인합니다.  
  
|매크로|결과|  
|---------|--------|  
|`_ASSERT`|지정된 식이 FALSE로 계산될 경우, 결과 값은 `_ASSERT`의 파일 이름과 줄 번호입니다.|`_ASSERTE`|  
|`_ASSERTE`|`_ASSERT`와 마찬가지이며, 여기에 어설션된 식의 문자열 표시가 추가됩니다.|  
  
 `_ASSERTE`는 결과 값이 FALSE인 어설션된 식을 보고하기 때문에 보다 효과적입니다.  따라서 소스 코드를 참조하지 않고도 문제를 식별할 수 있습니다.  그러나 응용 프로그램의 디버그 버전에는 `_ASSERTE`로 어설션된 식마다 문자열 상수가 포함됩니다.  `_ASSERTE` 매크로를 많이 사용하면 이러한 문자열 식이 메모리를 많이 차지합니다.  문제가 생기면 `_ASSERT`를 사용하여 메모리를 절약하십시오.  
  
 `_DEBUG` 가 정의될 때, `_ASSERTE` 매크로가 다음과 같이 정의됩니다:  
  
```  
#define _ASSERTE(expr) \  
   do { \  
      if (!(expr) && (1 == _CrtDbgReport( \  
         _CRT_ASSERT, __FILE__, __LINE__, #expr))) \  
         _CrtDbgBreak(); \  
   } while (0)  
```  
  
 어설션된 식이 FALSE로 계산되면 [\_CrtDbgReport](/visual-cpp/c-runtime-library/reference/crtdbgreport-crtdbgreportw)가 호출되어 어설션 오류를 보고합니다\(기본적으로 메시지 대화 상자 사용\).  메시지 대화 상자에서 **다시 시도** 를 선택하면, `_CrtDbgReport` 가 1을 반환하고 `_CrtDbgBreak` 는 `DebugBreak` 를 통해 디버거를 호출합니다.  
  
### 힙 손상 확인  
 다음 예제에서는 [\_CrtCheckMemory](/visual-cpp/c-runtime-library/reference/crtcheckmemory)를 사용하여 힙 손상을 확인합니다.  
  
```  
_ASSERTE(_CrtCheckMemory());  
```  
  
### 포인터 유효성 확인  
 다음 예제에서는 [\_CrtIsValidPointer](/visual-cpp/c-runtime-library/reference/crtisvalidpointer)를 사용하여 지정한 메모리 범위가 읽기나 쓰기에 적합한지 확인합니다.  
  
```  
_ASSERTE(_CrtIsValidPointer( address, size, TRUE );  
```  
  
 다음 예제에서는 [\_CrtIsValidHeapPointer](/visual-cpp/c-runtime-library/reference/crtisvalidheappointer)를 사용하여 로컬 힙에서 포인터가 메모리를 가리키는지 확인합니다. 이때 로컬 힙이란 이러한 C 런타임 라이브러리의 인스턴스가 만들고 관리하는 힙, 즉 DLL에는 라이브러리의 자체 인스턴스가 있으므로 응용 프로그램 힙 외부에 있는 자체 힙을 의미합니다.  이 어설션은 null이나 범위를 벗어나는 주소 뿐만 아니라 정적 변수, 스택 변수 및 다른 모든 비 로컬 메모리에 대한 포인터를 찾아 냅니다.  
  
```  
_ASSERTE(_CrtIsValidPointer( myData );  
```  
  
### 메모리 블록 확인  
 다음 예제에서는 [\_CrtIsMemoryBlock](/visual-cpp/c-runtime-library/reference/crtismemoryblock)을 사용하여 메모리 블록이 로컬 힙에 있고 블록 형식이 유효한지 확인합니다.  
  
```  
_ASSERTE(_CrtIsMemoryBlock (myData, size, &requestNumber, &filename, &linenumber));  
```  
  
 [항목 내용](#BKMK_In_this_topic)  
  
##  <a name="BKMK_MFC_assertions"></a> MFC 어설션  
 MFC는 [ASSERT](../Topic/ASSERT%20\(MFC\).md) 매크로를 정의하여 어설션을 검사합니다.  또한 `MFC ASSERT_VALID` 및 `CObject`\-파생 개체의 내부 상태를 검사 하기 위한 `CObject::AssertValid` 메소드를 정의합니다.  
  
 MFC `ASSERT` 매크로의 인수가 혹은 false로 계산되면, 매크로는 프로그램 실행을 중지하고 사용자에게 경고를 보냅니다. 그렇지 않으면, 실행이 계속 됩니다.  
  
 어설션 오류가 발생하면, 메시지 대화 상자는 소스 파일의 이름과 어설션 줄 번호를 보여줍니다.  대화 상자에서 다시 시도를 선택하면 [AfxDebugBreak](../Topic/AfxDebugBreak%20\(MFC\).md)를 호출하여 프로그램을 중단하고 디버거를 실행합니다.  이 때, 왜 어설션이 실패했는지 결정하기 위해서 호출 스택을 검사하고 다른 디버거 기능을 사용합니다.  [Just\-In\-Time 디버깅](../debugger/just-in-time-debugging-in-visual-studio.md)을 활성화시키는 경우, 디버거가 이미 실행되지 않고 있다면, 대화 상자는 디버거를 시작할 수 있습니다.  
  
 다음 예제에서는 `ASSERT` 를 사용하여 함수의 반환 값을 확인하는 방법을 보여 줍니다:  
  
```  
int x = SomeFunc(y);  
ASSERT(x >= 0);   //  Assertion fails if x is negative  
```  
  
 [IsKindOf](../Topic/CObject::IsKindOf.md) 함수와 함께 ASSERT를 사용하여 함수 인수의 형식을 확인할 수 있습니다.  
  
```  
ASSERT( pObject1->IsKindOf( RUNTIME_CLASS( CPerson ) ) );  
```  
  
 `ASSERT` 매크로는 릴리스 버전에서는 코드를 생성하지 않습니다.  릴리스 버전에서는 ASSERT 대신 [VERIFY](../Topic/VERIFY.md) 매크로를 사용하여 식을 계산하십시오.  
  
###  <a name="BKMK_MFC_ASSERT_VALID_and_CObject__AssertValid"></a> MFC ASSERT\_VALID 및 CObject::AssertValid  
 [CObject::AssertValid](../Topic/CObject::AssertValid.md) 메서드는 런타임에 개체의 내부 상태를 검사합니다.  `CObject`에서 클래스를 파생할 때 `AssertValid`를 반드시 재정의해야 하는 것은 아니지만, 이렇게 하면 클래스의 안정성이 강화됩니다.  `AssertValid` 는 개체의 모든 멤버 변수를 어설션하여 유효한 값이 들어 있는지 확인해야 합니다.  예를 들어, 포인터 멤버 변수가 NULL이 아닌지 확인합니다.  
  
 다음 예제에서는 `AssertValid` 함수를 선언하는 방법을 보여 줍니다.  
  
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
  
 `AssertValid`를 재정의할 때는 `AssertValid`의 기본 클래스 버전을 먼저 호출하고,  다음과 같이 ASSERT 매크로를 사용하여 파생된 클래스의 고유 멤버를 검사하십시오.  
  
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
  
 개체를 저장하는 멤버 변수가 있고 해당 클래스가 `AssertValid`를 재정의하는 경우, `ASSERT_VALID` 매크로를 사용하여 내부 유효성을 테스트할 수 있습니다.  
  
 예를 들어, `CMyData` 클래스가 멤버 변수 중 하나에 [CObList](/visual-cpp/mfc/reference/coblist-class)를 저장할 경우를 고려해 보십시오.  `CObList` 변수 `m_DataList`는 `CPerson` 개체 모음을 저장합니다.  `CMyData`의 약식 선언은 다음과 같습니다.  
  
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
  
 `CMyData`에서 `AssertValid`는 다음과 같이 재정의합니다.  
  
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
  
 `CMyData`는 `AssertValid` 메커니즘을 사용하여 해당 데이터 멤버에 저장된 개체의 유효성을 테스트합니다.  `CMyData`의 재정의된 `AssertValid`에서 자체 m\_pDataList 멤버 변수에 대해 `ASSERT_VALID` 매크로를 호출합니다.  
  
 클래스 `CObList`도 `AssertValid`를 재정의하기 때문에 이 수준에서는 유효성 테스트가 중지되지 않습니다.  이렇게 재정의하면 목록의 내부 상태 유효성이 추가로 테스트됩니다.  따라서 `CMyData` 개체의 유효성 테스트가 끝나면 저장된 `CObList` 목록 개체의 내부 상태 유효성이 추가로 테스트됩니다.  
  
 목록에 저장된 `CPerson` 개체에 대한 유효성 테스트도 추가할 수 있습니다.  `CObList`에서 `CPersonList` 클래스를 파생시키고 `AssertValid`를 재정의할 수 있습니다.  재정의할 때 `CObject::AssertValid`를 호출한 다음 목록을 반복하여 목록에 저장된 각 `CPerson`개체의 `AssertValid`를 호출합니다.  이 항목의 시작 부분에 나오는 `CPerson` 클래스가 이미 `AssertValid`를 재정의합니다.  
  
 이것은 디버깅을 빌드할 때 효과적인 메커니즘입니다.  계속해서 릴리스를 빌드할 경우 이 메커니즘은 자동으로 해제됩니다.  
  
###  <a name="BKMK_Limitations_of_AssertValid"></a> AssertValid 한계  
 어설션이 트리거되면 개체가 잘못된 것이므로 실행이 중지됩니다.  그러나, 어설션 부족은 발견된 문제가 없다는 것을 나타낼 뿐, 개체가 양호하다고 보장하는 것은 아닙니다.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Using_assertions"></a> 어설션 사용  
  
###  <a name="BKMK_Catching_logic_errors"></a> 논리 오류 찾기.  
 프로그램의 논리에 따라 값이 true인 조건에 어설션을 설정할 수 있습니다.  논리 오류가 발생하지 않으면 어설션은 효과가 없습니다.  
  
 예를 들어, 컨테이너에서 가스 분자를 시뮬레이션하는 경우 변수 `numMols`는 총 분자 수를 나타냅니다.  이 수는 0 이상이기 때문에 다음과 같이 MFC 어설션 문을 포함할 수 있습니다.  
  
```  
ASSERT(numMols >= 0);  
  
```  
  
 또는 다음과 같이 CRT 어설션을 포함할 수 있습니다.  
  
```  
_ASSERT(numMols >= 0);  
```  
  
 프로그램이 제대로 작동하면 이 문은 아무 효과가 없습니다.  논리 오류로 인해 `numMols` 가 0 미만이 되면 어설션은 프로그램 실행을 중지하고 [어설션 오류 대화 상자](../debugger/assertion-failed-dialog-box.md)를 표시합니다.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Checking_results_"></a> 결과 확인  
 결과가 빠른 시각적 개체 검사로부터 분명하게 나타나지 않는 작업을 테스트하는 데 어설션이 유용합니다.  
  
 예를 들어, `mols`가 가리키는 연결 리스트 내용에 따라 다음과 같이 변수 `iMols`를 업데이트하는 코드가 있습니다.  
  
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
  
 `iMols`가 계산한 분자 수는 항상 총 분자 수 `numMols` 이하여야 합니다.  루프에서 원하는 결과가 발생하지 않으면 루프 다음에 어설션 문을 사용하여 조건을 테스트하게 됩니다.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Testing_error_conditions_"></a> 처리 되지 않은 오류 찾기  
 처리할 오류가 있는 코드의 한 지점에서 어설션을 사용하여 오류 조건을 테스트할 수 있습니다.  다음 예제에서는 그래픽 루틴이 오류 코드 또는 0을 성공적으로 반환합니다.  
  
```  
myErr = myGraphRoutine(a, b);  
  
/* Code to handle errors and  
   reset myErr if successful */  
  
ASSERT(!myErr); -- MFC version  
_ASSERT(!myErr); -- CRT version  
```  
  
 오류 처리 코드가 제대로 작동하면 오류가 처리되고 어설션에 도달하기 전에 `myErr`이 0으로 다시 설정되어야 합니다.  `myErr`의 값이 0이 아닌 경우 어설션 오류가 발생하고 프로그램은 중지되며 [어설션 오류 대화 상자](../debugger/assertion-failed-dialog-box.md)가 나타납니다.  
  
 그러나 어설션 문이 오류 처리 코드를 대체하지는 않습니다.  다음 예제는 최종판 코드에서 문제가 될 수 있는 어설션 문을 보여 줍니다.  
  
```  
myErr = myGraphRoutine(a, b);  
  
/* No Code to handle errors */  
  
ASSERT(!myErr); // Don't do this!  
_ASSERT(!myErr); // Don't do this, either!  
```  
  
 이 코드는 어설션 문에 따라 오류 조건을 처리합니다.  따라서 최종판 코드에서는 `myGraphRoutine`이 반환한 어떠한 오류 코드도 처리되지 않습니다.  
  
 [항목 내용](#BKMK_In_this_topic)  
  
## 참고 항목  
 [디버거 보안](../debugger/debugger-security.md)   
 [네이티브 코드 디버깅](../debugger/debugging-native-code.md)   
 [관리 코드에 어설션 사용](../debugger/assertions-in-managed-code.md)