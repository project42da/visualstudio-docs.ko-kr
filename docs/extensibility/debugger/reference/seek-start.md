---
title: "SEEK_START | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SEEK_START"
helpviewer_keywords: 
  - "SEEK_START 열거형"
ms.assetid: 55bd8901-626e-428b-a263-23b14417f4c6
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# SEEK_START
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디스어셈블리를 스트림으로 검색을 시작할 위치를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_SEEK_START {   
   SEEK_START_BEGIN       = 0x0001,  
   SEEK_START_END         = 0x0002,  
   SEEK_START_CURRENT     = 0x0003,  
   SEEK_START_CODECONTEXT = 0x0004,  
   SEEK_START_CODELOCID   = 0x0005  
};  
typedef DWORD SEEK_START;  
```  
  
```c#  
public enum enum_SEEK_START {   
   SEEK_START_BEGIN       = 0x0001,  
   SEEK_START_END         = 0x0002,  
   SEEK_START_CURRENT     = 0x0003,  
   SEEK_START_CODECONTEXT = 0x0004,  
   SEEK_START_CODELOCID   = 0x0005  
};  
```  
  
## Members  
 SEEK\_START\_BEGIN  
 다음은 현재 문서 시작 부분에 검색을 시작 합니다.  
  
 SEEK\_START\_END  
 다음은 현재 문서 끝에 검색을 시작 합니다.  
  
 SEEK\_START\_CURRENT  
 현재 문서의 현재 위치에서 검색을 시작 합니다.  
  
 SEEK\_START\_CODECONTEXT  
 현재 문서의 특정된 코드 컨텍스트에서 검색을 시작 합니다.  
  
 SEEK\_START\_CODELOCID  
 지정 된 코드 위치 식별자를 찾을 때 시작 됩니다.  코드 위치 식별자를 호출 하 여 가져옵니다 [GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md).  
  
## 설명  
 인수로 전달 되는 [검색](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md) 방법입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [검색](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)   
 [GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md)