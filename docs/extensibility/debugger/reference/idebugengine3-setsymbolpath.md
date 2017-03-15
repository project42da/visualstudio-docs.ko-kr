---
title: "IDebugEngine3::SetSymbolPath | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEngine3::SetSymbolPath"
helpviewer_keywords: 
  - "IDebugEngine3::SetSymbolPath"
ms.assetid: 47b48f84-8a96-401f-84df-0baa8a96d26e
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugEngine3::SetSymbolPath
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

경로 또는 디버깅 기호 검색 경로 설정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetSymbolPath (  
   LPOLESTR            szSymbolSearchPath,  
   LPOLESTR            szSymbolCachePath,  
   LOAD_SYMBOLS_FLAGS  Flags  
);  
```  
  
```c#  
int SetSymbolPath(  
   string                    szSymbolSearchPath,   
   string                    szSymbolCachePath,   
   enum_LOAD_SYMBOLS_FLAGS   Flags  
);  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`szSymbolSearchPath`|\[in\] 기호 검색 경로 또는 경로 포함 하는 문자열입니다.  "주의"를 참조 하십시오.  null일 수 없습니다.|  
|`szSymbolCachePath`|\[in\] 기호를 캐시할 수 있습니다 로컬 경로 포함 하는 문자열입니다.  null일 수 없습니다.|  
|`Flags`|\[in\] 사용. 항상 0으로 설정 합니다.|  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 문자열 `szSymbolSearchPath` 기호를 검색할 세미콜론으로 구분 하 여 하나 이상의 경로 목록입니다.  이 경로 로컬 경로, UNC 스타일 경로 또는 URL을 수 있습니다.  다음이 경로 다른 종류의 혼합 될 수도 있습니다.  \(예를 들어, \\\\Symserver\\Symbols\), UNC 경로 다음 디버그 엔진 경로 기호 서버에 및 기호를 지정한 경로에 캐싱 서버를 로드할 수 있습니다 경우 결정 해야 하면 `szSymbolCachePath`.  
  
 기호 경로 캐시 위치를 하나 이상 포함 될 수도 있습니다.  캐시를 먼저 우선 순위가 가장 높은 캐시 우선 순위에 따라 나열 하 고 구분 하 여 \* 기호입니다.  예를 들면 다음과 같습니다.  
  
```  
\\symbols\symbols;\\someotherserver\symbols;c:\symbols\httpsymbols*http://msdl.microsoft.com  
```  
  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md) 메서드 기호 실제 로드를 수행 합니다.  
  
## 참고 항목  
 [LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md)   
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)