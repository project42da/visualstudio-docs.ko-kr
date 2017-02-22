---
title: "IDiaStackWalker | Microsoft Docs"
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
  - "IDiaStackWalker 인터페이스"
ms.assetid: 4a61a22a-9cf8-4ea1-9e6e-b42f96872d40
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaStackWalker
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

.Pdb 파일의 정보를 사용 하 여 스택 작업을 수행 하는 방법 안내를 제공 합니다.  
  
## 구문  
  
```  
IDiaStackWalker: IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDiaStackWalker`.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)|X86 플랫폼은 스택 프레임 열거자를 검색합니다.|  
|[IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)|플랫폼 특정 형식에 대 한 스택 프레임 표시기를 검색합니다.|  
  
## 설명  
 이 인터페이스를 사용 하 여 로드 된 모듈에 대 한 스택 프레임의 목록을 보려면.  메서드에 전달 되는 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md) \(클라이언트 응용 프로그램에 의해 구현\) 스택 프레임의 목록을 만드는 데 필요한 정보를 제공 하는 개체입니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 가져온는 `CoCreateInstance` 메서드는 클래스 식별자를 `CLSID_DiaStackWalker` 와의 인터페이스 ID `IID_IDiaStackWalker`.  이 인터페이스를 받는 방법을 보여 줍니다.  
  
## 예제  
 가져오는 방법을 보여 주는이 예제는 `IDiaStackWalker` 인터페이스입니다.  
  
```cpp#  
  
      IDiaStackWalker* pStackWalker;  
HRESULT hr = CoCreateInstance(CLSID_DiaStackWalker,  
                              NULL,  
                              CLSCTX_INPROC_SERVER,  
                              IID_IDiaStackWalker,  
                              (void**) &pStackWalker);  
if (FAILED(hr))  
{  
    // Report error and exit  
}  
```  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)