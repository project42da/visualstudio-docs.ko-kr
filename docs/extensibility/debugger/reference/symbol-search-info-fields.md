---
title: "SYMBOL_SEARCH_INFO_FIELDS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SYMBOL_SEARCH_INFO_FIELDS"
helpviewer_keywords: 
  - "SYMBOL_SEARCH_INFO_FIELDS 열거형"
ms.assetid: bce35af0-722d-46d4-afa6-eaae598c51ff
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# SYMBOL_SEARCH_INFO_FIELDS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

기호 정보를 검색할 수의 종류를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_SYMBOL_SEARCH_INFO_FIELDS  
{  
   SSIF_NONE                = 0x00000000,  
   SSIF_VERBOSE_SEARCH_INFO = 0x00000001  
};  
typedef DWORD SYMBOL_SEARCH_INFO_FIELDS;  
```  
  
```c#  
public enum enum_SYMBOL_SEARCH_INFO_FIELDS  
{  
   SSIF_NONE                = 0x00000000,  
   SSIF_VERBOSE_SEARCH_INFO = 0x00000001  
};  
  
```  
  
## Members  
 SSIF\_NONE  
 플래그가 없음을 나타냅니다.  
  
 SSIF\_VERBOSE\_SEARCH\_INFO  
 반환 모든 기호를 찾는 데 사용 되는 경로 검색 합니다.  
  
## 설명  
 이러한 플래그에 대 한 매개 변수로 전달 되는 [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md) 세부 정보를 확인 하는 메서드를 반환 합니다.  
  
> [!NOTE]
>  현재만 `SSIF_VERBOSE_SEARCH_INFO` 지원 됩니다로 지정 해야 하는 `dwFlags` 매개 변수를 `IDebugModule3::GetSymbolInfo`.  다른 값은 모두 오류를 반환 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)