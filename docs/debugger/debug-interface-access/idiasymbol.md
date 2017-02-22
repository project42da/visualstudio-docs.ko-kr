---
title: "IDiaSymbol | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "IDiaSymbol 인터페이스"
ms.assetid: 01ad328a-736c-4933-a9f8-c2ded19ddd8c
caps.latest.revision: 30
caps.handback.revision: 30
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기호 인스턴스의 속성에 대해 설명합니다.  
  
## 구문  
  
```  
IDiaSymbol : IUnknown  
```  
  
## 메서드\(사전순\)  
 다음 표에서는 `IDiaSymbol`의 메서드를 보여 줍니다.  
  
> [!NOTE]
>  기호는 기호 형식에 따라 이러한 메서드 중 일부에 대해서만 의미 있는 데이터를 반환합니다.  메서드가 `S_OK`를 반환할 경우 해당 메서드는 의미 있는 데이터를 반환합니다.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)|모든 기호의 자식을 검색합니다.|  
|[IDiaSymbol::findChildrenEx](../../debugger/debug-interface-access/idiasymbol-findchildrenex.md)|기호의 자식을 검색합니다.  이 메서드는 [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)의 확장 버전입니다.|  
|[IDiaSymbol::findChildrenExByAddr](../../debugger/debug-interface-access/idiasymbol-findchildrenexbyaddr.md)|지정된 주소에 유효한 기호의 자식을 검색합니다.|  
|[IDiaSymbol::findChildrenExByRVA](../../debugger/debug-interface-access/idiasymbol-findchildrenexbyrva.md)|지정된 상대 가상 주소\(RVA\)에 유효한 기호의 자식을 검색합니다.|  
|[IDiaSymbol::findChildrenExByVA](../../debugger/debug-interface-access/idiasymbol-findchildrenexbyva.md)|지정된 가상 주소에 유효한 기호의 자식을 검색합니다.|  
|[IDiaSymbol::findInlineFramesByAddr](../../debugger/debug-interface-access/idiasymbol-findinlineframesbyaddr.md)|주어진된 주소에서 인라인 프레임을 통해 반복 하는 클라이언트를 허용 하는 열거형을 가져옵니다.|  
|[IDiaSymbol::findInlineFramesByRVA](../../debugger/debug-interface-access/idiasymbol-findinlineframesbyrva.md)|지정한 상대 가상 주소 \(RVA\)에서 인라인 프레임을 통해 반복 하는 클라이언트가 열거형을 검색 합니다.|  
|[IDiaSymbol::findInlineFramesByVA](../../debugger/debug-interface-access/idiasymbol-findinlineframesbyva.md)|인라인 프레임에 지정 된 가상 주소 \(VA\)을 통해 반복 하는 클라이언트를 허용 하는 열거형을 가져옵니다.|  
|[IDiaSymbol::findInlineeLines](../../debugger/debug-interface-access/idiasymbol-findinlineelines.md)|줄 번호 정보가 직접 인라인에 모든 기능 또는이 기호에 간접적으로 반복 하는 클라이언트가 열거형을 검색 합니다.|  
|[IDiaSymbol::findInlineeLinesByAddr](../../debugger/debug-interface-access/idiasymbol-findinlineelinesbyaddr.md)|열거형에는 줄 번호 정보를 직접 또는 간접적으로,이 기호는 지정 된 주소 범위 내에서 인라인인 모든 함수를 반복 하는 클라이언트 수를 검색 합니다.|  
|[IDiaSymbol::findInlineeLinesByRVA](../../debugger/debug-interface-access/idiasymbol-findinlineelinesbyrva.md)|열거형에는 줄 번호 정보를 직접 또는 간접적으로,이 기호는 지정한 상대 가상 주소 \(RVA\) 내에서 인라인, 될 모든 함수를 반복 하는 클라이언트 수를 검색 합니다.|  
|[IDiaSymbol::findInlineeLinesByVA](../../debugger/debug-interface-access/idiasymbol-findinlineelinesbyva.md)|열거형에는 줄 번호 정보를 직접 또는 간접적으로,이 기호에 지정 된 가상 주소 \(VA\) 내에서 인라인, 될 모든 함수를 반복 하는 클라이언트 수를 검색 합니다.|  
|[IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag](../../debugger/debug-interface-access/idiasymbol-findsymbolsbyrvaforacceleratorpointertag.md)|해당 태그 값이 주어진 경우이 메서드 스텁 함수에 지정한 상대 가상 주소에 포함 된 기호의 열거형을 반환 합니다.|  
|[IDiaSymbol::findSymbolsForAcceleratorPointerTag](../../debugger/debug-interface-access/idiasymbol-findsymbolsforacceleratorpointertag.md)|가속기 포인터 태그 C\+\+ AMP 스텁 함수를 반환합니다.|  
|[IDiaSymbol::get\_acceleratorPointerTags](../../debugger/debug-interface-access/idiasymbol-get-acceleratorpointertags.md)|C \+ \+ AMP 가속기 스텁 함수에 해당 하는 모든 가속기 포인터 태그 값을 반환 합니다.|  
|[IDiaSymbol::get\_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|클래스 멤버의 액세스 한정자를 검색합니다.|  
|[IDiaSymbol::get\_addressOffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|주소 위치의 오프셋 부분을 검색합니다.|  
|[IDiaSymbol::get\_addressSection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|주소 위치의 섹션 부분을 검색합니다.|  
|[IDiaSymbol::get\_addressTaken](../../debugger/debug-interface-access/idiasymbol-get-addresstaken.md)|기호가 다른 주소를 참조하는지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_age](../../debugger/debug-interface-access/idiasymbol-get-age.md)|프로그램 데이터베이스의 보존 기간 값을 검색합니다.|  
|[IDiaSymbol::get\_arrayIndexType](../../debugger/debug-interface-access/idiasymbol-get-arrayindextype.md)|기호의 배열 인덱스 형식 식별자를 검색합니다..|  
|[IDiaSymbol::get\_arrayIndexTypeId](../../debugger/debug-interface-access/idiasymbol-get-arrayindextypeid.md)|기호의 배열 인덱스 형식 식별자를 검색합니다..|  
|[IDiaSymbol::get\_backEndMajor](../../debugger/debug-interface-access/idiasymbol-get-backendmajor.md)|백 엔드 주 버전 번호를 검색합니다.|  
|[IDiaSymbol::get\_backEndMinor](../../debugger/debug-interface-access/idiasymbol-get-backendminor.md)|백 엔드 부 버전 번호를 검색합니다.|  
|[IDiaSymbol::get\_backEndBuild](../../debugger/debug-interface-access/idiasymbol-get-backendbuild.md)|백 엔드 빌드 번호를 검색합니다.|  
|[IDiaSymbol::get\_baseDataOffset](../../debugger/debug-interface-access/idiasymbol-get-basedataoffset.md)|기본 데이터의 오프셋을 검색합니다.|  
|[IDiaSymbol::get\_baseDataSlot](../../debugger/debug-interface-access/idiasymbol-get-basedataslot.md)|기본 데이터 슬롯을 검색합니다.|  
|[IDiaSymbol::get\_baseSymbol](../../debugger/debug-interface-access/idiasymbol-get-basesymbol.md)|포인터를 기준으로 심볼을 검색 합니다.|  
|[IDiaSymbol::get\_baseSymbolId](../../debugger/debug-interface-access/idiasymbol-get-basesymbolid.md)|기호 ID를 기준으로 포인터를 검색 합니다.|  
|[IDiaSymbol::get\_baseType](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)|단순 형식의 형식 태그를 검색합니다.|  
|[IDiaSymbol::get\_bitPosition](../../debugger/debug-interface-access/idiasymbol-get-bitposition.md)|위치의 비트 위치를 검색합니다.|  
|[IDiaSymbol::get\_builtInKind](../../debugger/debug-interface-access/idiasymbol-get-builtinkind.md)|기본 제공 되는 HLSL 형식 중 하나인을 검색합니다.|  
|[IDiaSymbol::get\_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)|메서드 호출 규칙 표시기가 반환됩니다.|  
|[IDiaSymbol::get\_classParent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|기호의 부모 클래스에 대한 참조를 검색합니다.|  
|[IDiaSymbol::get\_classParentId](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|기호의 클래스 부모 식별자를 검색합니다.|  
|[IDiaSymbol::get\_code](../../debugger/debug-interface-access/idiasymbol-get-code.md)|코드 주소를 가리키는 공용 기호가 있는지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_compilerGenerated](../../debugger/debug-interface-access/idiasymbol-get-compilergenerated.md)|기호가 컴파일러에서 생성되었는지 여부를 나타내는 플래그입니다.|  
|[IDiaSymbol::get\_compilerName](../../debugger/debug-interface-access/idiasymbol-get-compilername.md)|만드는 데 사용 되는 컴파일러의 이름을 검색 하는 [컴파일 대상](../../debugger/debug-interface-access/compiland.md).|  
|[IDiaSymbol::get\_constructor](../../debugger/debug-interface-access/idiasymbol-get-constructor.md)|사용자 정의 데이터 형식에 생성자가 있는지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_container](../../debugger/debug-interface-access/idiasymbol-get-container.md)|이 기호를 포함 하는 심볼을 검색합니다.|  
|[IDiaSymbol::get\_constType](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|사용자 정의 데이터 형식이 상수인지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_count](../../debugger/debug-interface-access/idiasymbol-get-count.md)|목록 또는 배열의 항목 수를 검색합니다.|  
|[IDiaSymbol::get\_countLiveRanges](../../debugger/debug-interface-access/idiasymbol-get-countliveranges.md)|로컬 기호와 연관 된 유효한 주소 범위의 수를 검색합니다.|  
|[IDiaSymbol::get\_customCallingConvention](../../debugger/debug-interface-access/idiasymbol-get-customcallingconvention.md)|함수는 사용자 지정 호출 규칙을 사용 하는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_dataBytes](../../debugger/debug-interface-access/idiasymbol-get-databytes.md)|OEM 기호의 데이터 바이트를 검색합니다.|  
|[IDiaSymbol::get\_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)|데이터 기호의 변수 분류를 검색합니다.|  
|[IDiaSymbol::get\_editAndContinueEnabled](../../debugger/debug-interface-access/idiasymbol-get-editandcontinueenabled.md)|컴파일 된 프로그램 또는 단위의 편집 하며 계속 하기 기능을 설명하는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_farReturn](../../debugger/debug-interface-access/idiasymbol-get-farreturn.md)|까지 반환 함수를 사용 하는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_frontEndMajor](../../debugger/debug-interface-access/idiasymbol-get-frontendmajor.md)|프론트 엔드 주 버전 번호를 검색합니다.|  
|[IDiaSymbol::get\_frontEndMinor](../../debugger/debug-interface-access/idiasymbol-get-frontendminor.md)|프론트 엔드 부 버전 번호를 검색합니다.|  
|[IDiaSymbol::get\_frontEndBuild](../../debugger/debug-interface-access/idiasymbol-get-frontendbuild.md)|프론트 엔드 빌드 번호를 검색합니다.|  
|[IDiaSymbol::get\_function](../../debugger/debug-interface-access/idiasymbol-get-function.md)|함수를 가리키는 공용 기호가 있는지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_guid](../../debugger/debug-interface-access/idiasymbol-get-guid.md)|기호의 GUID를 검색합니다.|  
|[IDiaSymbol::get\_hasAlloca](../../debugger/debug-interface-access/idiasymbol-get-hasalloca.md)|함수 호출이 포함 되어 있는지 여부를 나타내는 플래그를 검색 합니다. `alloca`.|  
|[IDiaSymbol::get\_hasAssignmentOperator](../../debugger/debug-interface-access/idiasymbol-get-hasassignmentoperator.md)|사용자 정의 데이터 형식에 지정된 할당 연산자가 있는지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_hasCastOperator](../../debugger/debug-interface-access/idiasymbol-get-hascastoperator.md)|사용자 정의 데이터 형식에 지정된 캐스트 연산자가 있는지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_hasDebugInfo](../../debugger/debug-interface-access/idiasymbol-get-hasdebuginfo.md)|컴파일 대상에 디버깅 정보가 포함 되어 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_hasEH](../../debugger/debug-interface-access/idiasymbol-get-haseh.md)|함수 스타일 C\+\+ 예외 처리기 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_hasEHa](../../debugger/debug-interface-access/idiasymbol-get-haseha.md)|이 함수는 비동기 예외 처리기 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_hasInlAsm](../../debugger/debug-interface-access/idiasymbol-get-hasinlasm.md)|함수가 인라인 어셈블리가 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_hasLongJump](../../debugger/debug-interface-access/idiasymbol-get-haslongjump.md)|함수 명령을 longjmp \(C 스타일 예외 처리 부분\)이 포함 되어 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_hasManagedCode](../../debugger/debug-interface-access/idiasymbol-get-hasmanagedcode.md)|모듈에 관리 코드가 포함되어 있는지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_hasNestedTypes](../../debugger/debug-interface-access/idiasymbol-get-hasnestedtypes.md)|사용자 정의 데이터 형식에 중첩 형식 정의가 있는지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_hasSecurityChecks](../../debugger/debug-interface-access/idiasymbol-get-hassecuritychecks.md)|검색 기능이 나 컴파일 보안 검사를 컴파일된 있는지 여부를 나타내는 플래그 \(통해는 [\/GS\(버퍼 보안 검사\)](/visual-cpp/build/reference/gs-buffer-security-check) 컴파일러 스위치\).|  
|[IDiaSymbol::get\_hasSEH](../../debugger/debug-interface-access/idiasymbol-get-hasseh.md)|함수 스타일 Win32 구조적 예외 처리 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_hasSetJump](../../debugger/debug-interface-access/idiasymbol-get-hassetjump.md)|함수에 setjmp 명령이 포함 되어 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_indirectVirtualBaseClass](../../debugger/debug-interface-access/idiasymbol-get-indirectvirtualbaseclass.md)|사용자 정의 데이터 형식에 간접적 가상 기본 클래스가 있는지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_InlSpec](../../debugger/debug-interface-access/idiasymbol-get-inlspec.md)|함수가 인라인 특성으로 표시 되었는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_interruptReturn](../../debugger/debug-interface-access/idiasymbol-get-interruptreturn.md)|함수는 인터럽트 명령에서 반환 되어 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_intro](../../debugger/debug-interface-access/idiasymbol-get-intro.md)|함수가 기본 클래스 가상 함수인지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_isAcceleratorGroupSharedLocal](../../debugger/debug-interface-access/idiasymbol-get-isacceleratorgroupsharedlocal.md)|기호 그룹 공유 로컬 변수는 C\+\+ AMP 가속기에 대 한 컴파일된 코드에 해당 하는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_isAcceleratorPointerTagLiveRange](../../debugger/debug-interface-access/idiasymbol-get-isacceleratorpointertagliverange.md)|기호에 해당 하는지 여부를 나타내는 플래그를 검색은  *정의 범위 기호* 포인터 변수는 C\+\+ AMP 가속기에 대 한 컴파일된 코드에서 태그 구성 요소에 대 한.  범위 정의 기호 주소 범위 변수의 위치입니다.|  
|[IDiaSymbol::get\_isAcceleratorStubFunction](../../debugger/debug-interface-access/idiasymbol-get-isacceleratorstubfunction.md)|기호에 해당 하는 가속기에 대 한 컴파일된 셰이더 최상위 함수 기호에 해당 하는지 여부를 나타냅니다.는 `parallel_for_each` 를 호출 합니다.|  
|[IDiaSymbol::get\_isAggregated](../../debugger/debug-interface-access/idiasymbol-get-isaggregated.md)|데이터 집계의 많은 기호 부분 인지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_isCTypes](../../debugger/debug-interface-access/idiasymbol-get-isctypes.md)|기호 파일 C 유형이 포함 되어 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_isCVTCIL](../../debugger/debug-interface-access/idiasymbol-get-iscvtcil.md)|모듈 공용 중간 언어 \(CIL에서\) 네이티브 코드로 변환 되었는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_isDataAligned](../../debugger/debug-interface-access/idiasymbol-get-isdataaligned.md)|사용자 정의 데이터 형식 요소의 특정 경계에 정렬 되어 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_isHLSLData](../../debugger/debug-interface-access/idiasymbol-get-ishlsldata.md)|이 기호 높은 수준 셰이더 언어 \(HLSL\) 데이터를 나타내는지 여부를 지정 합니다.|  
|[IDiaSymbol::get\_isHotpatchable](../../debugger/debug-interface-access/idiasymbol-get-ishotpatchable.md)|[\/hotpatch\(핫 패치 가능 이미지 만들기\)](/visual-cpp/build/reference/hotpatch-create-hotpatchable-image) 컴파일러 스위치를 사용하여 모듈이 컴파일되었는지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_isLTCG](../../debugger/debug-interface-access/idiasymbol-get-isltcg.md)|관리 되는 컴파일 링커의 LTCG에 연결 되어 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_isMatrixRowMajor](../../debugger/debug-interface-access/idiasymbol-get-ismatrixrowmajor.md)|행렬 행 주 여부를 지정 합니다.|  
|[IDiaSymbol::get\_isMSILNetmodule](../../debugger/debug-interface-access/idiasymbol-get-ismsilnetmodule.md)|관리 되는 컴파일 대상 인지 여부를 나타내는 플래그를 검색을 합니다.  netmodule \(메타 데이터만 포함\)입니다.|  
|[IDiaSymbol::get\_isMultipleInheritance](../../debugger/debug-interface-access/idiasymbol-get-ismultipleinheritance.md)|지정 여부는 `this` 포인터가 가리키는 데이터 멤버를 여러 상속을 사용 합니다.|  
|[IDiaSymbol::get\_isNaked](../../debugger/debug-interface-access/idiasymbol-get-isnaked.md)|검색 함수가 있는지 여부를 나타내는 플래그는 [naked](/visual-cpp/cpp/naked-cpp) 특성.|  
|[IDiaSymbol::get\_isOptimizedAway](../../debugger/debug-interface-access/idiasymbol-get-isoptimizedaway.md)|변수 최적화 여부를 지정 합니다.|  
|[IDiaSymbol::get\_isPointerBasedOnSymbolValue](../../debugger/debug-interface-access/idiasymbol-get-ispointerbasedonsymbolvalue.md)|지정 여부는 `this` 포인터 기호 값을 기반으로 합니다.|  
|[IDiaSymbol::get\_isPointerToDataMember](../../debugger/debug-interface-access/idiasymbol-get-ispointertodatamember.md)|이 기호에 대 한 포인터 데이터 멤버 인지 여부를 지정 합니다.|  
|[IDiaSymbol::get\_isPointerToMemberFunction](../../debugger/debug-interface-access/idiasymbol-get-ispointertomemberfunction.md)|이 기호는 멤버 함수에 대 한 포인터 인지 여부를 지정 합니다.|  
|[IDiaSymbol::get\_isReturnValue](../../debugger/debug-interface-access/idiasymbol-get-isreturnvalue.md)|변수 반환 값을 전달 하는지 여부를 지정 합니다.|  
|[IDiaSymbol::get\_isSdl](../../debugger/debug-interface-access/idiasymbol-get-issdl.md)|\/SDL 옵션으로 컴파일 모듈을 지정 합니다.|  
|[IDiaSymbol::get\_isSingleInheritance](../../debugger/debug-interface-access/idiasymbol-get-issingleinheritance.md)|지정 여부는 `this` 포인터가 가리키는 데이터와 단일 상속 멤버.|  
|[IDiaSymbol::get\_isSplitted](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md)|별도 기호에 집계 데이터 분할 되었습니다 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_isStatic](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|함수 또는 썽크 계층이 정적인지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_isStripped](../../debugger/debug-interface-access/idiasymbol-get-isstripped.md)|개인 기호 기호 파일에서 추출 했는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_isVirtualInheritance](../../debugger/debug-interface-access/idiasymbol-get-isvirtualinheritance.md)|지정 여부는 `this` 포인터가 가리키는 데이터 멤버 가상 상속을 사용 합니다.|  
|[IDiaSymbol::get\_language](../../debugger/debug-interface-access/idiasymbol-get-language.md)|언어의 소스를 검색합니다.|  
|[IDiaSymbol::get\_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|이 기호로 표시되는 개체에 사용된 메모리의 바이트 수를 검색합니다.|  
|[IDiaSymbol::get\_lexicalParent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|기호의 어휘 부모에 대한 참조를 검색합니다.|  
|[IDiaSymbol::get\_lexicalParentId](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|기호의 어휘 부모 식별자를 검색합니다.|  
|[IDiaSymbol::get\_libraryName](../../debugger/debug-interface-access/idiasymbol-get-libraryname.md)|개체가 로드된 라이브러리 또는 개체 파일의 파일 이름을 검색합니다.|  
|[IDiaSymbol::get\_liveRangeLength](../../debugger/debug-interface-access/idiasymbol-get-liverangelength.md)|로컬 기호가 유효한 주소 범위의 길이가 반환됩니다.|  
|[IDiaSymbol::get\_liveRangeStartAddressSection](../../debugger/debug-interface-access/idiasymbol-get-liverangestartaddresssection.md)|로컬 기호가 유효한 시작 주소 범위의 섹션 부분이 반환됩니다.|  
|[IDiaSymbol::get\_liveRangeStartAddressOffset](../../debugger/debug-interface-access/idiasymbol-get-liverangestartaddressoffset.md)|로컬 기호가 유효한 시작 주소 범위의 오프셋 부분이 반환됩니다.|  
|[IDiaSymbol::get\_liveRangeStartRelativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-liverangestartrelativevirtualaddress.md)|로컬 기호가 유효한 주소 범위의 시작이 반환됩니다.|  
|[IDiaSymbol::get\_locationType](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|데이터 기호의 위치 유형을 검색합니다.|  
|[IDiaSymbol::get\_lowerBound](../../debugger/debug-interface-access/idiasymbol-get-lowerbound.md)|FORTRAN 배열 차원의 하한 값을 검색합니다.|  
|[IDiaSymbol::get\_lowerBoundId](../../debugger/debug-interface-access/idiasymbol-get-lowerboundid.md)|FORTRAN 배열 차원의 하한을 나타내는 기호 식별자를 검색합니다.|  
|[IDiaSymbol::get\_machineType](../../debugger/debug-interface-access/idiasymbol-get-machinetype.md)|대상 CPU의 형식을 검색합니다.|  
|[IDiaSymbol::get\_managed](../../debugger/debug-interface-access/idiasymbol-get-managed.md)|관리 코드를 가리키는 기호가 있는지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_memorySpaceKind](../../debugger/debug-interface-access/idiasymbol-get-memoryspacekind.md)|메모리 공간 종류를 검색합니다.|  
|[IDiaSymbol::get\_msil](../../debugger/debug-interface-access/idiasymbol-get-msil.md)|Microsoft 중간 언어\(MSIL\) 코드를 가리키는 공용 기호가 있는지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|기호의 이름을 검색합니다.|  
|[IDiaSymbol::get\_nested](../../debugger/debug-interface-access/idiasymbol-get-nested.md)|사용자 정의 데이터 형식이 중첩인지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_noInline](../../debugger/debug-interface-access/idiasymbol-get-noinline.md)|검색 기능으로 표시 되어 있는지 여부를 나타내는 플래그는 [noinline](/visual-cpp/cpp/noinline) 특성.|  
|[IDiaSymbol::get\_noReturn](../../debugger/debug-interface-access/idiasymbol-get-noreturn.md)|검색으로 함수를 선언 했습니다 여부를 나타내는 플래그는 [noreturn](/visual-cpp/cpp/noreturn) 특성.|  
|[IDiaSymbol::get\_noStackOrdering](../../debugger/debug-interface-access/idiasymbol-get-nostackordering.md)|스택 순서 없는 스택 버퍼 검사의 일부로 할 수 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_notReached](../../debugger/debug-interface-access/idiasymbol-get-notreached.md)|함수 또는 레이블 절대로 도달할 수 있는지 여부를 나타내는 플래그를 검색 합니다.|  
|[IDiaSymbol::get\_numberOfAcceleratorPointerTags](../../debugger/debug-interface-access/idiasymbol-get-numberofacceleratorpointertags.md)|가속기 포인터 태그 C\+\+ AMP 스텁 함수를 반환합니다.|  
|[IDiaSymbol::get\_numberOfModifiers](../../debugger/debug-interface-access/idiasymbol-get-numberofmodifiers.md)|원래 형식에 적용 되는 한정자를 검색 합니다.|  
|[IDiaSymbol::get\_numberOfRegisterIndices](../../debugger/debug-interface-access/idiasymbol-get-numberofregisterindices.md)|레지스터 인덱스를 검색합니다.|  
|[IDiaSymbol::get\_numberOfRows](../../debugger/debug-interface-access/idiasymbol-get-numberofrows.md)|행렬의 행 수를 검색합니다.|  
|[IDiaSymbol::get\_numberOfColumns](../../debugger/debug-interface-access/idiasymbol-get-numberofcolumns.md)|행렬의 열 수를 검색합니다.|  
|[IDiaSymbol::get\_objectFileName](../../debugger/debug-interface-access/idiasymbol-get-objectfilename.md)|개체 파일 이름을 검색합니다.|  
|[IDiaSymbol::get\_objectPointerType](../../debugger/debug-interface-access/idiasymbol-get-objectpointertype.md)|클래스 메서드에 대한 개체 포인터 형식을 검색합니다.|  
|[IDiaSymbol::get\_oemId](../../debugger/debug-interface-access/idiasymbol-get-oemid.md)|기호의 `oemId` 값을 검색합니다.|  
|[IDiaSymbol::get\_oemSymbolId](../../debugger/debug-interface-access/idiasymbol-get-oemsymbolid.md)|기호의 `oemSymbolId` 값을 검색합니다.|  
|[IDiaSymbol::get\_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|기호 위치의 오프셋을 검색합니다.|  
|[IDiaSymbol::get\_optimizedCodeDebugInfo](../../debugger/debug-interface-access/idiasymbol-get-optimizedcodedebuginfo.md)|최적화 된 코드는 함수 또는 레이블 포함 되어 있는지 여부를 나타내는 플래그를 검색으로 정보를 디버그도.|  
|[IDiaSymbol::get\_overloadedOperator](../../debugger/debug-interface-access/idiasymbol-get-overloadedoperator.md)|사용자 정의 데이터 형식에 오버로드 된 생성자가 있는지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_packed](../../debugger/debug-interface-access/idiasymbol-get-packed.md)|사용자 정의 데이터 형식이 packed인지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_platform](../../debugger/debug-interface-access/idiasymbol-get-platform.md)|프로그램이나 컴파일이 컴파일 된 플랫폼 형식을 검색합니다.|  
|[IDiaSymbol::get\_pure](../../debugger/debug-interface-access/idiasymbol-get-pure.md)|함수가 순수 가상 함수인지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_rank](../../debugger/debug-interface-access/idiasymbol-get-rank.md)|FORTRAN 다차원 배열의 순위를 검색합니다.|  
|[IDiaSymbol::get\_reference](../../debugger/debug-interface-access/idiasymbol-get-reference.md)|포인터 형식이 참조인지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_registerId](../../debugger/debug-interface-access/idiasymbol-get-registerid.md)|레지스터 디자이너의 위치를 검색합니다.|  
|[IDiaSymbol::get\_registerType](../../debugger/debug-interface-access/idiasymbol-get-registertype.md)|레지스터 형식을 검색합니다.|  
|[IDiaSymbol::get\_relativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|위치의 RVA\(상대 가상 주소\)를 검색합니다.|  
|[IDiaSymbol::get\_restrictedType](../../debugger/debug-interface-access/idiasymbol-get-restrictedtype.md)|지정 여부는 `this` 포인터는 플래그가 지정으로 제한 합니다.|  
|[IDiaSymbol::get\_samplerSlot](../../debugger/debug-interface-access/idiasymbol-get-samplerslot.md)|샘플러 슬롯을 검색합니다.|  
|[IDiaSymbol::get\_scoped](../../debugger/debug-interface-access/idiasymbol-get-scoped.md)|사용자 정의 데이터 형식을 비 전역 어휘 범위에서 표시할지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_signature](../../debugger/debug-interface-access/idiasymbol-get-signature.md)|기호의 시그니처 값을 검색합니다.|  
|[IDiaSymbol::get\_sizeInUdt](../../debugger/debug-interface-access/idiasymbol-get-sizeinudt.md)|사용자 정의 형식의 멤버를 검색합니다.|  
|[IDiaSymbol::get\_slot](../../debugger/debug-interface-access/idiasymbol-get-slot.md)|레지스터 디자이너의 위치를 검색합니다.|  
|[IDiaSymbol::get\_sourceFileName](../../debugger/debug-interface-access/idiasymbol-get-sourcefilename.md)|소스 파일의 파일 이름을 검색합니다.|  
|[IDiaSymbol::getSrcLineOnTypeDefn](../../debugger/debug-interface-access/idiasymbol-getsrclineontypedefn.md)|지정 된 사용자 정의 형식이 정의 된 위치를 나타내는 소스 파일 및 줄 번호를 검색 합니다.|  
|[IDiaSymbol::get\_stride](../../debugger/debug-interface-access/idiasymbol-get-stride.md)|Stride는 행렬 또는 strided 배열의 검색합니다.|  
|[IDiaSymbol::get\_subType](../../debugger/debug-interface-access/idiasymbol-get-subtype.md)|하위 형식을 검색합니다.|  
|[IDiaSymbol::get\_subTypeId](../../debugger/debug-interface-access/idiasymbol-get-subtypeid.md)|하위 유형 ID를 검색합니다.|  
|[IDiaSymbol::get\_symbolsFileName](../../debugger/debug-interface-access/idiasymbol-get-symbolsfilename.md)|기호가 로드된 파일의 이름을 검색합니다.|  
|[IDiaSymbol::get\_symIndexId](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|고유 기호 식별자를 검색합니다.|  
|[IDiaSymbol::get\_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|기호 형식 분류자를 검색합니다.|  
|[IDiaSymbol::get\_targetOffset](../../debugger/debug-interface-access/idiasymbol-get-targetoffset.md)|썽크 대상의 오프셋 섹션을 검색합니다.|  
|[IDiaSymbol::get\_targetRelativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-targetrelativevirtualaddress.md)|썽크 대상의 RVA\(상대 가상 주소\)를 검색합니다.|  
|[IDiaSymbol::get\_targetSection](../../debugger/debug-interface-access/idiasymbol-get-targetsection.md)|썽크 대상의 주소 섹션을 검색합니다.|  
|[IDiaSymbol::get\_targetVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-targetvirtualaddress.md)|썽크 대상의 VA\(가상 주소\)를 검색합니다.|  
|[IDiaSymbol::get\_textureSlot](../../debugger/debug-interface-access/idiasymbol-get-textureslot.md)|질감 슬롯을 검색합니다.|  
|[IDiaSymbol::get\_thisAdjust](../../debugger/debug-interface-access/idiasymbol-get-thisadjust.md)|메서드에 대한 논리적인 `this` 조정자를 검색합니다.|  
|[IDiaSymbol::get\_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)|함수의 썽크 형식을 검색합니다.|  
|[IDiaSymbol::get\_timeStamp](../../debugger/debug-interface-access/idiasymbol-get-timestamp.md)|숨겨진 실행 파일의 타임스탬프를 검색합니다.|  
|[IDiaSymbol::get\_token](../../debugger/debug-interface-access/idiasymbol-get-token.md)|관리되는 함수 또는 변수의 메타 데이터 토큰을 검색합니다.|  
|[IDiaSymbol::get\_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|함수 시그니처에 대한 참조를 검색합니다.|  
|[IDiaSymbol::get\_typeId](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|기호의 형식 식별자를 검색합니다..|  
|[IDiaSymbol::get\_types](../../debugger/debug-interface-access/idiasymbol-get-types.md)|이 기호에 대한 컴파일러 전용 형식 값의 배열을 기호를 검색합니다.|  
|[IDiaSymbol::get\_typeIds](../../debugger/debug-interface-access/idiasymbol-get-typeids.md)|이 기호에 대한 컴파일러 전용 형식 식별자 값의 배열을 기호를 검색합니다.|  
|[IDiaSymbol::get\_uavSlot](../../debugger/debug-interface-access/idiasymbol-get-uavslot.md)|Uav 슬롯을 검색합니다.|  
|[IDiaSymbol::get\_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)|다양한 UDT\(사용자 정의 형식\)을 검색합니다.|  
|[IDiaSymbol::get\_unalignedType](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|사용자 정의 데이터 형식이 unaligned인지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_undecoratedName](../../debugger/debug-interface-access/idiasymbol-get-undecoratedname.md)|C\+\+ 장식된 이름 또는 링크에 대한 데코레이팅 되지 않은 이름을 검색합니다.|  
|[IDiaSymbol::get\_undecoratedNameEx](../../debugger/debug-interface-access/idiasymbol-get-undecoratednameex.md)|확장 필드 값을 기반으로 데코레이팅되지 않은 이름을 검색하는 `get_undecoratedName` 메서드의 확장입니다.|  
|[IDiaSymbol::get\_unmodifiedTypeId](../../debugger/debug-interface-access/idiasymbol-get-unmodifiedtypeid.md)|원래 \(수정 되지 않은\) 형식의 ID를 검색합니다.|  
|[IDiaSymbol::get\_upperBound](../../debugger/debug-interface-access/idiasymbol-get-upperbound.md)|FORTRAN 배열 차원의 상한 값을 검색합니다.|  
|[IDiaSymbol::get\_upperBoundId](../../debugger/debug-interface-access/idiasymbol-get-upperboundid.md)|FORTRAN 배열 차원의 상한을 나타내는 기호 식별자를 검색합니다.|  
|[IDiaSymbol::get\_value](../../debugger/debug-interface-access/idiasymbol-get-value.md)|상수 값을 검색합니다.|  
|[IDiaSymbol::get\_virtual](../../debugger/debug-interface-access/idiasymbol-get-virtual.md)|함수가 가상인지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_virtualAddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|위치의 VA\(가상 주소\)를 검색합니다.|  
|[IDiaSymbol::get\_virtualBaseClass](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseclass.md)|사용자 정의 데이터 형식에 가상 기본 클래스가 있는지 여부를 나타내는 플래그를 검색합니다.|  
|[IDiaSymbol::get\_virtualBaseDispIndex](../../debugger/debug-interface-access/idiasymbol-get-virtualbasedispindex.md)|가상 기본 치환 테이블에 대한 인덱스를 검색합니다.|  
|[IDiaSymbol::get\_virtualBaseOffset](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseoffset.md)|가상 함수의 가상 함수 테이블에서 오프셋을 검색합니다.|  
|[IDiaSymbol::get\_virtualBasePointerOffset](../../debugger/debug-interface-access/idiasymbol-get-virtualbasepointeroffset.md)|가상 기본 포인터의 오프셋을 검색합니다.|  
|[IDiaSymbol::get\_virtualBaseTableType](../../debugger/debug-interface-access/idiasymbol-get-virtualbasetabletype.md)|가상 기본 테이블 포인터의 형식을 검색합니다.|  
|[IDiaSymbol::get\_virtualTableShape](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshape.md)|사용자 정의 유형에 대한 가상 테이블 형식의 기호 인터페이스를 검색합니다.|  
|[IDiaSymbol::get\_virtualTableShapeId](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshapeid.md)|기호의 가상 테이블 셰이프 식별자를 검색합니다.|  
|[IDiaSymbol::get\_volatileType](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|사용자 정의 데이터 형식이 volatile인지 여부를 나타내는 플래그를 검색합니다.|  
  
## 설명  
  
## 호출자를 위한 정보  
 다음 메서드 중 하나를 호출하여 이 인터페이스를 가져옵니다.  
  
-   [IDiaEnumSymbols::Item](../../debugger/debug-interface-access/idiaenumsymbols-item.md)  
  
-   [IDiaEnumSymbols::Next](../../debugger/debug-interface-access/idiaenumsymbols-next.md)  
  
-   [IDiaEnumSymbolsByAddr::Next](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-next.md)  
  
-   [IDiaEnumSymbolsByAddr::Prev](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-prev.md)  
  
-   [IDiaEnumSymbolsByAddr::symbolByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyaddr.md)  
  
-   [IDiaEnumSymbolsByAddr::symbolByRVA](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyrva.md)  
  
-   [IDiaEnumSymbolsByAddr::symbolByVA](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyva.md)  
  
-   [IDiaSession::findSymbolByAddr](../../debugger/debug-interface-access/idiasession-findsymbolbyaddr.md)  
  
-   [IDiaSession::findSymbolByRVA](../../debugger/debug-interface-access/idiasession-findsymbolbyrva.md)  
  
-   [IDiaSession::findSymbolByRVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyrvaex.md)  
  
-   [IDiaSession::findSymbolByVA](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)  
  
-   [IDiaSession::findSymbolByVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyvaex.md)  
  
-   [IDiaSession::findSymbolByToken](../../debugger/debug-interface-access/idiasession-findsymbolbytoken.md)  
  
-   [IDiaSession::symbolById](../../debugger/debug-interface-access/idiasession-symbolbyid.md)  
  
-   [IDiaStackWalkHelper::symbolForVA](../../debugger/debug-interface-access/idiastackwalkhelper-symbolforva.md)  
  
-   [IDiaSymbol::get\_types](../../debugger/debug-interface-access/idiasymbol-get-types.md)  
  
## 예제  
 이 예는 주어진 상대 가상 어드레스에서 함수에 대한 지역 변수를 나타내는 방법을 보여줍니다.   다른 유형의 기호가 서로 관련된 방식도 보여줍니다.  
  
> [!NOTE]
>  `CDiaBSTR`는 `BSTR`를 래핑하고 인스턴스화가 범위를 벗어날 때 문자열 해제를 자동으로 처리하는 클래스입니다.  
  
```cpp#  
void DumpLocalVars( DWORD rva, IDiaSession *pSession )  
{  
    CComPtr< IDiaSymbol > pBlock;  
    if ( FAILED( psession->findSymbolByRVA( rva, SymTagBlock, &pBlock ) ) )  
    {  
        Fatal( "Failed to find symbols by RVA" );  
    }  
    CComPtr< IDiaSymbol > pscope;  
    for ( ; pBlock != NULL; )  
    {  
        CComPtr< IDiaEnumSymbols > pEnum;  
        // local data search  
        if ( FAILED( pBlock->findChildren( SymTagNull, NULL, nsNone, &pEnum ) ) )  
        {  
            Fatal( "Local scope findChildren failed" );  
        }  
        CComPtr< IDiaSymbol > pSymbol;  
        DWORD tag;  
        DWORD celt;  
        while ( pEnum != NULL &&  
                SUCCEEDED( pEnum->Next( 1, &pSymbol, &celt ) ) &&  
                celt == 1)  
        {  
            pSymbol->get_symTag( &tag );  
            if ( tag == SymTagData )  
            {  
                CDiaBSTR name;  
                DWORD    kind;  
                pSymbol->get_name( &name );  
                pSymbol->get_dataKind( &kind );  
                if ( name != NULL )  
                    wprintf_s( L"\t%s (%s)\n", name, szDataKinds[ kind ] );  
            }  
            else if ( tag == SymTagAnnotation )  
            {  
                CComPtr< IDiaEnumSymbols > pValues;  
                // local data search  
                wprintf_s( L"\tAnnotation:\n" );  
                if ( FAILED( pSymbol->findChildren( SymTagNull, NULL, nsNone, &pValues ) ) )  
                    Fatal( "Annotation findChildren failed" );  
                pSymbol = NULL;  
                while ( pValues != NULL &&  
                        SUCCEEDED( pValues->Next( 1, &pSymbol, &celt ) ) &&  
                        celt == 1 )  
                {  
                    CComVariant value;  
                    if ( pSymbol->get_value( &value ) != S_OK )  
                        Fatal( "No value for annotation data." );  
                    wprintf_s( L"\t\t%ws\n", value.bstrVal );  
                    pSymbol = NULL;  
                }  
            }  
            pSymbol = NULL;  
        }  
        pBlock->get_symTag( &tag );   
        if ( tag == SymTagFunction )    // stop when at function scope  
            break;  
        // move to lexical parent  
        CComPtr< IDiaSymbol > pParent;  
        if ( SUCCEEDED( pBlock->get_lexicalParent( &pParent ) )  
            && pParent != NULL ) {  
            pBlock = pParent;  
        }  
        else  
        {  
            Fatal( "Finding lexical parent failed." );  
        }  
    };  
}  
```  
  
## 요구 사항  
 `Header:` Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [기호 형식의 클래스 계층 구조](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)   
 [기호 및 기호 태그](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)   
 [컴파일 대상](../../debugger/debug-interface-access/compiland.md)