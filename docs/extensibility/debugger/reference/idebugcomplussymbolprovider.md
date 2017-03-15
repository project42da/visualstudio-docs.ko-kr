---
title: "IDebugComPlusSymbolProvider | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugComPlusSymbolProvider 인터페이스"
ms.assetid: 5b98e908-fd15-49a6-9010-933c9b948085
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugComPlusSymbolProvider
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

COM \+ 기호 공급자를 관리 되는 코드에만 적용 되는 메서드를 나타냅니다.  
  
## 구문  
  
```  
IDebugComPlusSymbolProvider : IDebugSymbolProvider  
```  
  
## 구현자 참고 사항  
 식 계산기 \(EE\)에 도움이 되는 인터페이스와는 디버그 엔진 \(DE\)에서 사용 하기에 분리 되지 않습니다 있지만 다음 방법 아마 DE 개발자 전용 관심 됩니다: AreSymbolsLoaded, GetAddressesInModuleFromPosition, GetEntryPoint, GetFunctionLineOffset, GetLocalVariableLayout, IsFunctionStale, LoadSymbols, LoadSymbolsFromStream, ReplaceSymbols, UnloadSymbols 및 UpdateSymbols입니다.  
  
## 메서드  
 메서드 외에 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[AreSymbolsLoaded](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-aresymbolsloaded.md)|응용 프로그램 도메인 식별자를 지정 합니다. 지정 된 모듈에 대해 디버그 기호가 로드 되었는지 확인 합니다.|  
|[CreateTypeFromPrimitive](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-createtypefromprimitive.md)|형식이 지정 된 기본 형식에서 만들어집니다.|  
|[GetAddressesInModuleFromPosition](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getaddressesinmodulefromposition.md)|문서 위치를에 있는 지정 된 모듈의 디버그 주소 배열에 매핑합니다.|  
|[GetArrayTypeFromAddress](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getarraytypefromaddress.md)|검색 해당 디버그 주소를 지정 된 배열에 대 한 정보를 입력 합니다.|  
|[GetAssemblyName](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getassemblyname.md)|모듈 및 응용 프로그램 도메인에서 지정 된 어셈블리의 이름을 검색 합니다.|  
|[GetAttributedClassesForLanguage](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getattributedclassesforlanguage.md)|주어진된 프로그래밍 언어에서 구현 하는 클래스에 지정 된 특성을 검색 합니다.|  
|[GetAttributedClassesinModule](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getattributedclassesinmodule.md)|지정 된 모듈에서 지정 된 특성을 가진 클래스를 검색합니다.|  
|[GetEntryPoint](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getentrypoint.md)|응용 프로그램 진입점을 검색합니다.|  
|[GetFunctionLineOffset](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getfunctionlineoffset.md)|지정한 줄 오프셋을 나타내는 함수 내에서 주소를 검색 합니다.|  
|[GetLocalVariablelayout](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getlocalvariablelayout.md)|레이아웃의 지역 변수를 메서드 집합을 검색합니다.|  
|[GetNameFromToken](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getnamefromtoken.md)|메타 데이터 개체를 지정 합니다. 지정한 토큰에 연결 된 이름을 반환 합니다.|  
|[GetSymAttribute](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getsymattribute.md)|지정 된 부모 특성이 지정 된 모듈에 대 한 디버그 기호를 검색합니다.|  
|[GetSymUnmanagedReader](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getsymunmanagedreader.md)|관리 되지 않는 코드에서 사용 하는 기호 판독기를 검색 합니다.|  
|[GetTypeFromAddress](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-gettypefromaddress.md)|해당 디버그 주소 지정 기호 형식으로 검색 합니다.|  
|[IsFunctionDeleted](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-isfunctiondeleted.md)|함수에 지정 된 디버그 주소를 삭제 하는 경우를 결정 합니다.|  
|[IsFunctionStale](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-isfunctionstale.md)|개체를 함수에 지정 된 디버그 주소 부실 경우 결정 합니다.|  
|[IsHiddenCode](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-ishiddencode.md)|디버거가 지정 된 주소에 있는 코드를 숨길지 여부를 결정 합니다.|  
|[LoadSymbols](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-loadsymbols.md)|메모리에 지정 된 디버그 기호를 로드합니다.|  
|[LoadSymbolsFromStream](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-loadsymbolsfromstream.md)|로드 데이터 스트림을 제공 하는 기호를 디버그 합니다.|  
|[ReplaceSymbols](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-replacesymbols.md)|지정 된 데이터 스트림에서 현재 디버그 기호를 바꿉니다.|  
|[UnloadSymbols](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-unloadsymbols.md)|디버그 기호 지정 된 모듈을 메모리에서 언로드합니다.|  
|[UpdateSymbols](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-updatesymbols.md)|메모리에서 디버그 기호를 지정 된 데이터 스트림에 업데이트 됩니다.|  
  
## 요구 사항  
 헤더: Sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll