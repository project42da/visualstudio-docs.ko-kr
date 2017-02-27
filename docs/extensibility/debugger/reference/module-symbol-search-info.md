---
title: "MODULE_SYMBOL_SEARCH_INFO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MODULE_SYMBOL_SEARCH_INFO"
helpviewer_keywords: 
  - "MODULE_SYMBOL_SEARCH_INFO 구조"
ms.assetid: 432aff03-08a5-4c5a-b2d5-e212090fc70a
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# MODULE_SYMBOL_SEARCH_INFO
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

에 대 한 검색이 기호 검색 경로 대 한 상태 정보를 포함 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
typedef struct _tagSYMBOL_SEARCH_INFO  
{  
   SYMBOL_SEARCH_INFO_FIELDS dwValidFields;  
   BSTR                      bstrVerboseSearchInfo;  
} MODULE_SYMBOL_SEARCH_INFO;  
```  
  
```c#  
public struct MODULE_SYMBOL_SEARCH_INFO {  
   public uint   dwValidFields;  
   public string bstrVerboseSearchInfo;  
}  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwValidFields`  
 플래그의 조합 된 [SYMBOL_SEARCH_INFO_FIELDS](../../../extensibility/debugger/reference/symbol-search-info-fields.md) 이 구조에 설명 된 검색 정보의 종류를 지정 하는 열거형입니다.  
  
 `bstrVerboseSearchInfo`  
 검색 경로 및 결과 단일 문자열로 연결 합니다.  
  
## <a name="remarks"></a>주의  
 이 구조에 대 한 호출에서 반환 되는 [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md) 메서드.  
  
 하는 경우는 `bstrVerboseSearchInfo` 필드가 비어 있지 않으면 다음 검색 경로 및 해당 검색 결과의 목록을 포함 합니다. 목록 경로, 줄임표 ("..."), 결과 뒤 다음으로 지정 됩니다. 둘 이상의 경로 결과 쌍 이면 각 쌍은 "\r\n" (캐리지 리턴/줄 바꿈) 쌍으로 구분 됩니다. 패턴은 다음과 같습니다.  
  
 \< 경로>... \< 결과>\r\n \< 경로>... \< 결과>\r\n \< 경로>... \< 결과>  
  
 마지막 항목 \r\n 시퀀스 없는 참고 합니다.  
  
 다음은 가능한 `bstrVerboseSearchInfo` 문자열을 표준 출력에 전송 되었습니다.  
  
 `c:\symbols\user32.pdb... File not found.`  
  
 `c:\winnt\symbols\user32.pdb... Version does not match.`  
  
 `\\symbols\symbols\user32.dll\0a8sd0ad8ad\user32.pdb... Symbols loaded.`  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)