---
title: IDebugEngine3::SetSymbolPath | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngine3::SetSymbolPath
helpviewer_keywords: IDebugEngine3::SetSymbolPath
ms.assetid: 47b48f84-8a96-401f-84df-0baa8a96d26e
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8cc60a266a238ee8d3635637b907ce88933b29a0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengine3setsymbolpath"></a>IDebugEngine3::SetSymbolPath
경로 또는 디버깅 기호 검색 경로 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetSymbolPath (  
   LPOLESTR            szSymbolSearchPath,  
   LPOLESTR            szSymbolCachePath,  
   LOAD_SYMBOLS_FLAGS  Flags  
);  
```  
  
```csharp  
int SetSymbolPath(  
   string                    szSymbolSearchPath,   
   string                    szSymbolCachePath,   
   enum_LOAD_SYMBOLS_FLAGS   Flags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`szSymbolSearchPath`|[in] 기호 검색 경로 또는 경로 포함 하는 문자열입니다. 자세한 내용은 "주의"를 참조 하십시오. null일 수 없습니다.|  
|`szSymbolCachePath`|[in] 기호를 캐시할 수 있는 로컬 경로 포함 하는 문자열입니다. null일 수 없습니다.|  
|`Flags`|[in] 사용 되지 않습니다. 항상 0으로 설정 합니다.|  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 문자열 `szSymbolSearchPath` 의 기호를 검색 하려면 세미콜론 구분 하 여 하나 이상의 경로 목록입니다. 이러한 경로 로컬 경로, UNC 스타일 경로 또는 URL 될 수 있습니다. 이러한 경로 다양 한 종류의 혼합 될 수도 있습니다. 경로가 UNC 경로인 경우 (예를 들어 \\\Symserver\Symbols), 경로 기호 서버에 이며 캐시에서 지정 된 경로에서 해당 서버에서 기호를 로드 해야 하는 경우 디버그 엔진 결정 해야 하는 다음 `szSymbolCachePath`합니다.  
  
 기호 경로는 캐시 위치를 하나 이상 포함할 수도 있습니다. 캐시는 먼저 가장 높은 우선 순위 캐시와 우선 순위 순서로 나열 하 고 구분 하 여 * 기호. 예:  
  
```  
\\symbols\symbols;\\someotherserver\symbols;c:\symbols\httpsymbols*http://msdl.microsoft.com  
```  
  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md) 메서드는 기호의 실제 부하를 수행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md)   
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)