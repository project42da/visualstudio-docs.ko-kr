---
title: SAL 이해 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: a94d6907-55f2-4874-9571-51d52d6edcfd
author: mikeblome
ms.author: mblome
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: deb1825bb514afec4db3bf705ac787aadb88cc11
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="understanding-sal"></a>SAL 이해
Microsoft 소스 코드 주석 언어 (SAL)를 함수 매개 변수, 하는 것은 그에 대 한 가정 및 보장 하는 것은 완료 될 때 사용 하는 방법을 설명 하는 데 사용할 수 있는 주석 집합을 제공 합니다. 헤더 파일에 정의 된 주석은 `<sal.h>`합니다. C + +에 대 한 visual Studio 코드 분석 함수에 대 한 분석을 수정 하려면 SAL 주석을 사용 합니다. Windows 드라이버 개발에 대 한 SAL 2.0에 대 한 자세한 내용은 참조 [Windows 드라이버에 대 한 SAL 2.0 주석](http://go.microsoft.com/fwlink/?LinkId=250979)합니다.  
  
 고유 하 게, C 및 c + + 의도 및 불변성의 일관성 있게 표현 하는 개발자를 위한 제한 된 방법만을 제공 합니다. SAL 주석을 사용 하 여에 사용 하는 개발자도 사용 하는 방법에 더 잘 이해할 수 있도록 함수를 더 자세히 설명할 수 있습니다.  
  
## <a name="what-is-sal-and-why-should-you-use-it"></a>SAL의 정의 및 이를 사용해야 하는 이유  
 간단히 말하면 SAL은 하기 위해 코드를 검사 하 고 컴파일러에 저렴 한 방법입니다.  
  
### <a name="sal-makes-code-more-valuable"></a>코드의 품질을 높이는 SAL  
 SAL은 인간이 및 코드 분석 도구에 대 한 코드 디자인을 더 쉽게 만들 수 있습니다. C 런타임 함수를 보여 주는이 예제를 생각해 볼 `memcpy`:  
  
```cpp  
  
void * memcpy(  
   void *dest,   
   const void *src,   
   size_t count  
);  
  
```  
  
 이 함수에서 수행 하는 작업 알 수 있습니까? 함수를 호출 또는 구현 된 경우 프로그램 정확성을 유지 하려면 특정 속성을 유지 되어야 합니다. 이 예제에 대 한 것과 같은 선언에서 보고를 무엇 인지 모릅니다. SAL 주석 없이 설명서 또는 코드 주석에 의존 해야 합니다. 다음에 대 한 MSDN 설명서를은 `memcpy` 표시:  
  
> "복사본의 src dest에 바이트를 계산 하는 데 사용 합니다. 소스와 대상이 겹치는 memcpy의 동작이 정의 되지 않습니다. Memmove를 사용 하 여 겹치는 영역을 처리 합니다.   
> **보안 정보:** 소스 버퍼 보다 크거나 대상 버퍼 동일 인지 확인 합니다. 자세한 내용은 참조 버퍼 오버런 방지. "  
  
 설명서에는 두 가지 프로그램 정확성을 유지 하려면 특정 속성을 유지 하기 위해 코드에는 제안 하는 정보의 비트:  
  
-   `memcpy` 복사는 `count` 소스 버퍼의 바이트를 대상 버퍼입니다.  
  
-   대상 버퍼 최소한 소스 버퍼의 크기 여야 합니다.  
  
 그러나 컴파일러는 설명서 나 비공식 설명을 읽을 수 없습니다. 두 개의 버퍼 간의 관계 임을 알 수 없기 및 `count`, 것도 없습니다 효율적으로 중요 한 관계에 대 한 합니다. SAL 다음과 같이 속성 및 함수를 구현 하는 방법에 대 한 자세한 설명을 제공할 수 있습니다.:  
  
```cpp  
  
void * memcpy(  
   _Out_writes_bytes_all_(count) void *dest,   
   _In_reads_bytes_(count) const void *src,   
   size_t count  
);  
```  
  
 고 해당 데이터베이스 이러한 주석을 MSDN 설명서에 대 한 정보를 유사 하지만 보다 간결 하 게 됩니다 의미 체계는 패턴을 따릅니다. 이 코드를 읽을 때이 함수의 속성 및 버퍼 오버런 보안 문제를 방지 하는 방법을 신속 하 게 이해할 수 있습니다. 더 좋은 SAL 제공 하는 의미 체계 패턴의 효율성과 잠재적 버그의 초기 검색에 대 한 자동화 된 코드 분석 도구의 효과 향상 시킬 수 있습니다. 이 버그가 있는 구현을 쓰는 누군가가 가정해 보세요. `wmemcpy`:  
  
```cpp  
  
wchar_t * wmemcpy(  
   _Out_writes_all_(count) wchar_t *dest,   
   _In_reads_(count) const wchar_t *src,   
   size_t count)  
{  
   size_t i;  
   for (i = 0; i <= count; i++) { // BUG: off-by-one error  
      dest[i] = src[i];  
   }  
   return dest;  
}  
  
```  
  
 이 구현에 일반적인 오프 하루가 오류가 포함 됩니다. 코드 작성자는 SAL 버퍼 크기 주석을 포함 하는 다행히-코드 분석 도구만이 함수를 분석 하 여 버그를 catch 할 수 있습니다.  
  
### <a name="sal-basics"></a>SAL 기본  
 SAL 기본 네 가지 유형의 사용 패턴에 의해 분류 되는 매개 변수를 정의 합니다.  
  
|범주|매개 변수 주석이|설명|  
|--------------|--------------------------|-----------------|  
|**함수 호출에 대 한 입력**|`_In_`|데이터는 호출된 된 함수에 전달 되며 읽기 전용으로 처리 됩니다.|  
|**에 대 한 입력 함수를 호출 하 고 호출자에 게 출력**|`_Inout_`|사용 가능한 데이터는 함수에 전달 하 고 잠재적으로 수정 됩니다.|  
|**호출자에 게 출력**|`_Out_`|호출자에 게는만에 쓰려고 호출된 된 함수에 대 한 공간을 제공 합니다. 호출된 된 함수는 해당 공간에 데이터를 씁니다.|  
|**호출자에 대 한 포인터의 출력**|`_Outptr_`|마찬가지로 **호출자에 게 출력**합니다. 호출된 된 함수에서 반환 되는 값 포인터입니다.|  
  
 이러한 네 가지 기본 주석은 가능 명시적 다양 한 방법으로 합니다. 기본적으로 주석이 추가 된 포인터 매개 변수는 필요한 것으로 가정 됩니다-해야만 해당 NULL이 아닌 성공 하려면 함수에 대 한 합니다. 기본 주석 가장 일반적으로 사용 되는 변형을 포인터 매개 변수가 옵션 임을 나타냅니다.-NULL 인 경우 함수에서 작업은 수행도 실행할 수 있습니다.  
  
 이 표에서 필수 및 선택적 매개 변수를 구분 하는 방법을 보여 줍니다.  
  
||매개 변수는 필요|매개 변수는 선택 사항|  
|-|-----------------------------|-----------------------------|  
|**함수 호출에 대 한 입력**|`_In_`|`_In_opt_`|  
|**에 대 한 입력 함수를 호출 하 고 호출자에 게 출력**|`_Inout_`|`_Inout_opt_`|  
|**호출자에 게 출력**|`_Out_`|`_Out_opt_`|  
|**호출자에 대 한 포인터의 출력**|`_Outptr_`|`_Outptr_opt_`|  
  
 이러한 주석은 가능한 초기화 되지 않은 값을 식별할 및 잘못 된 null 포인터 형식 및 정확한 방식으로 사용 합니다. 필수 매개 변수가 NULL이 전달 충돌이 발생 한 발생할 수 있습니다 또는 "실패" 오류 코드를 반환할 발생할 수 있습니다. 어떤 방법을 사용 하는 함수에서의 작업 계속할 수 없습니다.  
  
## <a name="sal-examples"></a>SAL 예제  
 이 섹션에서는 기본 SAL 주석에 대 한 코드 예제를 보여 줍니다.  
  
### <a name="using-the-visual-studio-code-analysis-tool-to-find-defects"></a>Visual Studio 코드 분석 도구를 사용하여 오류 찾기  
 예제에서 Visual Studio 코드 분석 도구는 코드 오류를 찾을 수 SAL 주석을 함께 사용 됩니다. 작업을 수행 하는 방법은 다음과 같습니다.  
  
##### <a name="to-use-visual-studio-code-analysis-tools-and-sal"></a>Visual Studio 코드 분석 도구 및 SAL을 사용하려면  
  
1.  Visual Studio에서 SAL 주석을 포함 하는 c + + 프로젝트를 엽니다.  
  
2.  메뉴 모음에서 **빌드**, **솔루션에서 코드 분석 실행**합니다.  
  
     _In 고려\_ 이 섹션의 예입니다. 코드 분석을 실행 하는 경우이 경고가 표시 됩니다.  
  
    > **C6387 잘못 된 매개 변수 값**   
    > '고정'는 '0' 일 수 없습니다: 'InCallee' 함수에 대 한 사양을 준수 하지 않습니다.  
  
### <a name="example-the-in-annotation"></a>예: _In\_ 주석  
 `_In_` 주석을 나타냅니다.  
  
-   매개 변수는 유효 해야 하며 수정 되지 않습니다.  
  
-   함수는 단일 요소 버퍼에서 읽을 수만.  
  
-   호출자는 버퍼를 제공 하 고 초기화 해야 합니다.  
  
-   `_In_` "읽기 전용"를 지정합니다. 적용 하는 일반적인 실수는 `_In_` 있어야 하는 매개 변수에 `_Inout_` 주석 대신 합니다.  
  
-   `_In_` 하지만 바로 포인터가 아닌 스칼라에 분석기가 허용 됩니다.  
  
```cpp  
void InCallee(_In_ int *pInt)  
{  
   int i = *pInt;  
}  
  
void GoodInCaller()  
{  
   int *pInt = new int;  
   *pInt = 5;  
  
   InCallee(pInt);  
   delete pInt;     
}  
  
void BadInCaller()  
{  
   int *pInt = NULL;  
   InCallee(pInt); // pInt should not be NULL  
}  
  
```  
  
 이 예제에서 Visual Studio Code 분석을 사용 하면 유효성을 검사는 호출자에 대 한 초기화 된 버퍼를 Null이 아닌 포인터를 전달 `pInt`합니다. 이 경우 `pInt` 포인터에는 NULL 일 수 없습니다.  
  
### <a name="example-the-inopt-annotation"></a>예: _In_opt\_ 주석  
 `_In_opt_` 동일 `_In_`제외 하 고 입력된 매개 변수는 NULL 일 수이 고 따라서 함수는이를 확인 해야 합니다.  
  
```cpp  
  
void GoodInOptCallee(_In_opt_ int *pInt)  
{  
   if(pInt != NULL) {  
      int i = *pInt;  
   }  
}  
  
void BadInOptCallee(_In_opt_ int *pInt)  
{  
   int i = *pInt; // Dereferencing NULL pointer 'pInt'  
}  
  
void InOptCaller()  
{  
   int *pInt = NULL;  
   GoodInOptCallee(pInt);  
   BadInOptCallee(pInt);  
}  
  
```  
  
 Visual Studio 코드 분석 함수 NULL에 대 한 버퍼에 액세스 하기 전에 확인의 유효성을 검사 합니다.  
  
### <a name="example-the-out-annotation"></a>예: _Out\_ 주석  
 `_Out_` 요소 버퍼를 가리키는 NULL이 아닌 포인터 전달 하 고 함수는 요소를 초기화 하는 일반적인 시나리오를 지원 합니다. 호출자를; 호출 하기 전에 버퍼를 초기화할 필요가 없습니다. 호출된 된 함수 프라미스를 반환 하기 전에 초기화 합니다.  
  
```cpp  
  
void GoodOutCallee(_Out_ int *pInt)  
{  
   *pInt = 5;  
}  
  
void BadOutCallee(_Out_ int *pInt)  
{  
   // Did not initialize pInt buffer before returning!  
}  
  
void OutCaller()  
{  
   int *pInt = new int;  
   GoodOutCallee(pInt);  
   BadOutCallee(pInt);  
   delete pInt;  
}  
  
```  
  
 Visual Studio 코드 분석 도구는 호출자에 대 한 버퍼를 NULL이 아닌 포인터를 전달 하는 유효성을 검사 `pInt` 버퍼를 반환 하기 전에 함수에 의해 초기화 되 고 있습니다.  
  
### <a name="example-the-outopt-annotation"></a>예: _Out_opt\_ 주석  
 `_Out_opt_` 동일 `_Out_`한다는 점을 제외 하는 매개 변수는 null을 허용 하 고 따라서 함수는이를 확인 해야 합니다.  
  
```cpp  
  
void GoodOutOptCallee(_Out_opt_ int *pInt)  
{  
   if (pInt != NULL) {  
      *pInt = 5;  
   }  
}  
  
void BadOutOptCallee(_Out_opt_ int *pInt)  
{  
   *pInt = 5; // Dereferencing NULL pointer 'pInt'  
}  
  
void OutOptCaller()  
{  
   int *pInt = NULL;  
   GoodOutOptCallee(pInt);  
   BadOutOptCallee(pInt);  
}  
  
```  
  
 Visual Studio 코드 분석 하기 전에 NULL에 대 한이 함수를 확인 하는 유효성을 검사 `pInt` 역참조 될 경우 `pInt` NULL이 아니면 반환 하기 전에 버퍼 함수에 의해 초기화 됩니다.  
  
### <a name="example-the-inout-annotation"></a>예: _Inout\_ 주석  
 `_Inout_` 포인터 매개 변수는 함수에 의해 변경 될 수 있는 주석을 추가 하는 데 사용 됩니다. 포인터는 호출 전에 올바른 초기화 된 데이터를 가리켜야 및 변경 될 경우에 여전히 있어야 올바른 값을 반환 합니다. 주석은 지정 된 함수 수 자유롭게에서 읽은 요소가 하나인 버퍼에 쓸입니다. 호출자는 버퍼를 제공 하 고 초기화 해야 합니다.  
  
> [!NOTE]
>  마찬가지로 `_Out_`, `_Inout_` 수정 가능한 값에 적용 해야 합니다.  
  
```cpp  
  
void InOutCallee(_Inout_ int *pInt)  
{  
   int i = *pInt;  
   *pInt = 6;  
}  
  
void InOutCaller()  
{  
   int *pInt = new int;  
   *pInt = 5;  
   InOutCallee(pInt);  
   delete pInt;  
}  
  
void BadInOutCaller()  
{  
   int *pInt = NULL;  
   InOutCallee(pInt); // 'pInt' should not be NULL  
}  
  
```  
  
 호출자에 대 한 초기화 된 버퍼를 NULL이 아닌 포인터를 전달 하는 visual Studio 코드 분석의 유효성을 검사 `pInt`, 하며, 반환 하기 전에 `pInt` 여전히 NULL이 고 버퍼를 초기화 합니다.  
  
### <a name="example-the-inoutopt-annotation"></a>예: _Inout_opt\_ 주석  
 `_Inout_opt_` 동일 `_Inout_`제외 하 고 입력된 매개 변수는 NULL 일 수이 고 따라서 함수는이를 확인 해야 합니다.  
  
```cpp  
  
void GoodInOutOptCallee(_Inout_opt_ int *pInt)  
{  
   if(pInt != NULL) {  
      int i = *pInt;  
      *pInt = 6;  
   }  
}  
  
void BadInOutOptCallee(_Inout_opt_ int *pInt)  
{  
   int i = *pInt; // Dereferencing NULL pointer 'pInt'  
   *pInt = 6;  
}  
  
void InOutOptCaller()  
{  
   int *pInt = NULL;  
   GoodInOutOptCallee(pInt);  
   BadInOutOptCallee(pInt);  
}  
  
```  
  
 Visual Studio 코드 분석, 버퍼에 액세스 하기 전에 그리고이 함수 NULL에 대 한 확인 하는 유효성을 검사 `pInt` NULL이 아니면 반환 하기 전에 버퍼 함수에 의해 초기화 됩니다.  
  
### <a name="example-the-outptr-annotation"></a>예: _Outptr\_ 주석  
 `_Outptr_` 포인터를 반환 하기 위한 옵션에 매개 변수를 주석을 추가 하는 데 사용 됩니다.  매개 변수 자체에 NULL를 사용 해야 합니다. 및 호출된 된 함수에 NULL이 아닌 포인터를 반환 하 고 해당 포인터 초기화 된 데이터를 가리킵니다.  
  
```cpp  
  
void GoodOutPtrCallee(_Outptr_ int **pInt)  
{  
   int *pInt2 = new int;  
   *pInt2 = 5;  
  
   *pInt = pInt2;  
}  
  
void BadOutPtrCallee(_Outptr_ int **pInt)  
{  
   int *pInt2 = new int;  
   // Did not initialize pInt buffer before returning!  
   *pInt = pInt2;  
}  
  
void OutPtrCaller()  
{  
   int *pInt = NULL;  
   GoodOutPtrCallee(&pInt);  
   BadOutPtrCallee(&pInt);  
}  
  
```  
  
 호출자에 대 한 NULL이 아닌 포인터를 전달 하는 visual Studio 코드 분석의 유효성을 검사 `*pInt`, 버퍼를 반환 하기 전에 함수에 의해 초기화 되 고 있습니다.  
  
### <a name="example-the-outptropt-annotation"></a>예: _Outptr_opt\_ 주석  
 `_Outptr_opt_` 동일 `_Outptr_`한다는 점을 제외 하는 매개 변수는 선택적-호출자에 게 매개 변수는 NULL 포인터에서 전달할 수 있습니다.  
  
```cpp  
  
void GoodOutPtrOptCallee(_Outptr_opt_ int **pInt)  
{  
   int *pInt2 = new int;  
   *pInt2 = 6;  
  
   if(pInt != NULL) {  
      *pInt = pInt2;  
   }  
}  
  
void BadOutPtrOptCallee(_Outptr_opt_ int **pInt)  
{  
   int *pInt2 = new int;  
   *pInt2 = 6;  
   *pInt = pInt2; // Dereferencing NULL pointer 'pInt'  
}  
  
void OutPtrOptCaller()  
{  
   int **ppInt = NULL;  
   GoodOutPtrOptCallee(ppInt);  
   BadOutPtrOptCallee(ppInt);  
}  
  
```  
  
 Visual Studio 코드 분석 하기 전에 NULL에 대 한이 함수를 확인 하는 유효성을 검사 `*pInt` 역참조가 버퍼를 반환 하기 전에 함수에 의해 초기화 되 고 있습니다.  
  
### <a name="example-the-success-annotation-in-combination-with-out"></a>예: _Success\_ 함께 _Out 주석\_  
 대부분의 개체에 주석은 적용할 수 있습니다.  특히 전체 함수에 주석을 달 수 있습니다.  함수의 가장 확실 한 특징 중 하나에 성공 하거나 실패 수는입니다. 하지만 같은 버퍼 크기와의 연결, 함수 성공 또는 실패 C/c + + 표현할 수 없습니다. 사용 하 여는 `_Success_` 주석, 성공 하는 함수에 대 한 다음과 같은 명령을 실행 합니다.  매개 변수를는 `_Success_` 주석이 되는 식 것은 사실 있음을 나타내도록 함수 성공 했다는 것입니다. 이 식은 주석 파서를 처리할 수 있는 모든 수 있습니다. 함수가 성공 하는 경우에 함수가 반환 되 면 주석의 효과 적용 됩니다. 이 예에서는 어떻게 `_Success_` 와 상호 작용 하 `_Out_` 을 마련해 야 합니다. 키워드를 사용할 수 `return` 반환 값을 나타내는입니다.  
  
```cpp  
  
_Success_(return != false) // Can also be stated as _Success_(return)  
bool GetValue(_Out_ int *pInt, bool flag)  
{  
   if(flag) {  
      *pInt = 5;  
      return true;  
   } else {  
      return false;  
   }  
}  
  
```  
  
 `_Out_` 주석 유효성을 검사 하는 Visual Studio 코드 분석 호출자에 대 한 버퍼를 NULL이 아닌 포인터를 전달 하면 `pInt`, 버퍼를 반환 하기 전에 함수에 의해 초기화 되 고 있습니다.  
  
## <a name="sal-best-practice"></a>SAL 유용한 정보  
  
### <a name="adding-annotations-to-existing-code"></a>기존 코드에 주석 추가  
 SAL는 코드의 안정성 및 보안을 향상 시킬 수 있는 강력한 기술입니다. SAL를 파악 한 후 일상 업무에 새로운 기술을 적용할 수 있습니다. 새 코드에서는 SAL 기반 사양 설계; 전체에서 사용할 수 있습니다. 이전 코드에서 증분 주석을 추가할 수 있으며는 업데이트할 때마다 이점의 향상 시킵니다.  
  
 Microsoft 공용 헤더에 주석을 다는 이미 있습니다. 따라서는 프로젝트에서 먼저 함수와 주석을 달 리프 노드 가장 효과적으로 활용 하는 Win32 Api를 호출 하는 함수는 것이 좋습니다.  
  
### <a name="when-do-i-annotate"></a>주석을 달아야 하는 경우  
 다음은 몇 가지 지침입니다.  
  
-   포인터 매개 변수를 모든 주석을 답니다.  
  
-   코드 분석 버퍼 및 포인터 안전성을 보장할 수 있도록 값 범위 주석은 주석을 답니다.  
  
-   잠금 규칙 및 잠금 부작용에 주석을 답니다. 자세한 내용은 참조 [잠금 동작에 주석 지정](../code-quality/annotating-locking-behavior.md)합니다.  
  
-   드라이버 속성 및 기타 도메인 특정 속성에 주석을 답니다.  
  
 또는 전체에서 사용자 의도 지우기 확인 하 고 쉽게 주석 완료 된 확인할 수 있도록 모든 매개 변수에 주석을 달 수 있습니다.  
  
## <a name="related-resources"></a>관련 참고 자료  
 [코드 분석 팀 블로그](http://go.microsoft.com/fwlink/p/?LinkId=251197)  
  
## <a name="see-also"></a>참고 항목  
 [C/c + + 코드 오류를 줄이기 위한 SAL 주석 사용](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [함수 매개 변수 및 반환 값에 주석 지정](../code-quality/annotating-function-parameters-and-return-values.md)   
 [함수 동작에 주석 지정](../code-quality/annotating-function-behavior.md)   
 [구조체 및 클래스에 주석 지정](../code-quality/annotating-structs-and-classes.md)   
 [잠금 동작에 주석 지정](../code-quality/annotating-locking-behavior.md)   
 [주석 적용 시기 및 위치 지정](../code-quality/specifying-when-and-where-an-annotation-applies.md)   
 [모범 사례 및 예제](../code-quality/best-practices-and-examples-sal.md)