---
title: IDebugComPlusSymbolProvider | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugComPlusSymbolProvider interface
ms.assetid: 5b98e908-fd15-49a6-9010-933c9b948085
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c6d356274998d07975dfce3cb3ba367c62c72ffb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcomplussymbolprovider"></a>IDebugComPlusSymbolProvider
관리 코드에만 적용 되는 메서드와 함께 COM + 기호 공급자를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugComPlusSymbolProvider : IDebugSymbolProvider  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 다음 메서드는 DE 개발자만 관심 때문일 수 없는 구분 (EE)는 식 계산기에 사용 되는 인터페이스와 디버그 엔진 (DE)에서 사용 하는 경우에: AreSymbolsLoaded, GetAddressesInModuleFromPosition, GetEntryPoint, GetFunctionLineOffset, GetLocalVariableLayout, IsFunctionStale, LoadSymbols, LoadSymbolsFromStream, ReplaceSymbols, UnloadSymbols, 및 UpdateSymbols 합니다.  
  
## <a name="methods"></a>메서드  
 메서드 외에도 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[AreSymbolsLoaded](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-aresymbolsloaded.md)|응용 프로그램 도메인 식별자를 지정 하는 지정된 된 모듈에 대 한 디버그 기호는 로드를 결정 합니다.|  
|[CreateTypeFromPrimitive](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-createtypefromprimitive.md)|지정된 된 기본 형식에서 형식을 만듭니다.|  
|[GetAddressesInModuleFromPosition](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getaddressesinmodulefromposition.md)|디버그 주소 배열로 지정된 된 모듈에 문서 위치를 매핑합니다.|  
|[GetArrayTypeFromAddress](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getarraytypefromaddress.md)|형식 지정된 된 배열의 해당 디버그 주소를 지정 하는 방법에 대 한 정보를 검색 합니다.|  
|[GetAssemblyName](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getassemblyname.md)|모듈 및 응용 프로그램 도메인을 지정 된 어셈블리의 이름을 검색 합니다.|  
|[GetAttributedClassesForLanguage](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getattributedclassesforlanguage.md)|지정 된 프로그래밍 언어로 구현 되는 지정 된 특성이 있는 클래스를 검색 합니다.|  
|[GetAttributedClassesinModule](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getattributedclassesinmodule.md)|지정 된 모듈에 지정된 된 특성을 사용 하 여 클래스를 검색합니다.|  
|[GetEntryPoint](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getentrypoint.md)|응용 프로그램 진입점을 검색합니다.|  
|[GetFunctionLineOffset](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getfunctionlineoffset.md)|지정 된 줄 오프셋을 나타내는 함수 내에서 주소를 검색 합니다.|  
|[GetLocalVariablelayout](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getlocalvariablelayout.md)|지역 변수는 메서드 집합에 대 한 레이아웃을 검색합니다.|  
|[GetNameFromToken](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getnamefromtoken.md)|지정된 된 토큰을 지정 된 해당 메타 데이터 개체와 연결 된 이름을 반환 합니다.|  
|[GetSymAttribute](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getsymattribute.md)|지정 된 부모 특성이 있는 지정된 된 모듈에 대 한 디버그 기호를 검색합니다.|  
|[GetSymUnmanagedReader](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getsymunmanagedreader.md)|비관리 코드에서 사용할 기호 판독기를 검색 합니다.|  
|[GetTypeFromAddress](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-gettypefromaddress.md)|해당 디버그 주소 지정 된 기호 형식으로 검색 합니다.|  
|[IsFunctionDeleted](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-isfunctiondeleted.md)|지정 된 디버그 주소에서 함수는 삭제를 확인 합니다.|  
|[IsFunctionStale](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-isfunctionstale.md)|함수는 지정 된 디버그 주소에서 것으로 간주 됩니다 부실 결정 합니다.|  
|[IsHiddenCode](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-ishiddencode.md)|지정한 디버거 주소에 있는 코드는 숨겨져 있는지 확인 합니다.|  
|[LoadSymbols](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-loadsymbols.md)|메모리에 지정 된 디버그 기호를 로드합니다.|  
|[LoadSymbolsFromStream](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-loadsymbolsfromstream.md)|로드 된 데이터 스트림에 지정 된 기호를 디버깅 합니다.|  
|[ReplaceSymbols](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-replacesymbols.md)|지정된 된 데이터 스트림에 설정과 현재 디버그 기호를 바꿉니다.|  
|[UnloadSymbols](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-unloadsymbols.md)|메모리에서 지정된 된 모듈에 대 한 디버그 기호를 언로드합니다.|  
|[UpdateSymbols](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-updatesymbols.md)|지정된 된 데이터 스트림에와 메모리에 있는 디버그 기호를 업데이트합니다.|  
  
## <a name="requirements"></a>요구 사항  
 헤더: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll