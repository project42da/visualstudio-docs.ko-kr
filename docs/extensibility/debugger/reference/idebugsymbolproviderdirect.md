---
title: "IDebugSymbolProviderDirect | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugSymbolProviderDirect 인터페이스"
ms.assetid: 872b04a8-70de-4ab5-aceb-684c81828545
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# IDebugSymbolProviderDirect
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

메타 데이터 및 주요 기호 인터페이스에 직접 액세스할 수 있는 공급자를 기호를 나타냅니다.  
  
## 구문  
  
```  
IDebugSymbolProviderDirect: IUnknown  
```  
  
## 메서드  
 다음 방법이이 인터페이스를 구현합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetAppIDFromAddress](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getappidfromaddress.md)|디버그 주소 지정 된 응용 프로그램 도메인 식별자를 검색 합니다.|  
|[GetCurrentModulesInfo](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getcurrentmodulesinfo.md)|모듈의 기호 그룹에서 정보를 검색합니다.|  
|[GetCurrentModulesState](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getcurrentmodulesstate.md)|기호 공급자의 구성원으로 있는 기호 그룹에 대 한 정보를 검색 합니다.|  
|[GetMetaDataImport](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getmetadataimport.md)|메타 데이터 가져오기 정보를 검색합니다.|  
|[GetMethodFromAddress](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getmethodfromaddress.md)|메서드가 지정 된 디버그 주소에 대 한 정보를 검색합니다.|  
|[GetSymUnmanagedReader](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getsymunmanagedreader.md)|비관리 코드의 기호 판독기를 검색합니다.|  
  
## 설명  
 대부분이 다른 기호 공급자 인터페이스 대신이 인터페이스를 사용할 수 있습니다.  메타 데이터에 직접 액세스를 제공 하 고 `CorSym` 인터페이스입니다.  
  
## 요구 사항  
 헤더: Sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll