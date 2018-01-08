---
title: SYMBOL_SEARCH_INFO_FIELDS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SYMBOL_SEARCH_INFO_FIELDS
helpviewer_keywords: SYMBOL_SEARCH_INFO_FIELDS enumeration
ms.assetid: bce35af0-722d-46d4-afa6-eaae598c51ff
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3d34cb1c991ccc28d724fa0652204c527147f68c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="symbolsearchinfofields"></a>SYMBOL_SEARCH_INFO_FIELDS
기호 정보를 검색의 종류를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_SYMBOL_SEARCH_INFO_FIELDS  
{  
   SSIF_NONE                = 0x00000000,  
   SSIF_VERBOSE_SEARCH_INFO = 0x00000001  
};  
typedef DWORD SYMBOL_SEARCH_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_SYMBOL_SEARCH_INFO_FIELDS  
{  
   SSIF_NONE                = 0x00000000,  
   SSIF_VERBOSE_SEARCH_INFO = 0x00000001  
};  
  
```  
  
## <a name="members"></a>멤버  
 SSIF_NONE  
 플래그가 없음을 나타냅니다.  
  
 SSIF_VERBOSE_SEARCH_INFO  
 기호를 찾는 데 사용 되는 경로 검색 하는 모든 반환  
  
## <a name="remarks"></a>설명  
 이러한 플래그에 대 한 매개 변수로 전달 되는 [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md) 정보의 양을 결정 하는 메서드를 반환 합니다.  
  
> [!NOTE]
>  현재만 `SSIF_VERBOSE_SEARCH_INFO` 지원으로 지정 해야 합니다는 `dwFlags` 매개 변수를 `IDebugModule3::GetSymbolInfo`합니다. 다른 모든 값은 오류를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)