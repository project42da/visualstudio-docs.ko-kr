---
title: "IDebugModule3::GetSymbolInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugModule3::GetSymbolInfo"
helpviewer_keywords: 
  - "GetSymbolInfo 메서드"
  - "IDebugModule3::GetSymbolInfo 메서드"
ms.assetid: dda5e8e1-6878-4aa9-9ee4-e7d0dcc11210
caps.latest.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 17
---
# IDebugModule3::GetSymbolInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

기호 뿐 아니라 각 경로 검색 결과를 검색 하는 경로 목록을 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetSymbolInfo(  
   SYMBOL_SEARCH_INFO_FIELDS  dwFields,  
   MODULE_SYMBOL_SEARCH_INFO* pInfo  
);  
```  
  
```c#  
int GetSymbolInfo(  
   enum_SYMBOL_SEARCH_INFO_FIELDS dwFields,   
   MODULE_SYMBOL_SEARCH_INFO[]    pinfo  
);  
  
```  
  
#### 매개 변수  
 `dwFields`  
 \[in\] 플래그의 조합에서 [SYMBOL\_SEARCH\_INFO\_FIELDS](../../../extensibility/debugger/reference/symbol-search-info-fields.md) 의 필드를 지정 하는 열거형 `pInfo` 를 채울 수 있습니다.  
  
 `pInfo`  
 \[out\] A [MODULE\_SYMBOL\_SEARCH\_INFO](../../../extensibility/debugger/reference/module-symbol-search-info.md) 구조 구성원 인 지정 된 정보를 채울 수 있습니다. 이 메서드가 반환 하는 경우이 null 값, `E_INVALIDARG`합니다.  
  
## 반환 값  
 메서드가 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
> [!NOTE]
>  반환 되는 문자열 \(에 `MODULE_SYMBOL_SEARCH_INFO` 구조\) 비어 있을 수 있음 경우에 `S_OK` 반환 됩니다. 이 경우에 반환할 검색 정보가 없습니다.  
  
## 설명  
 하는 경우는 `bstrVerboseSearchInfo` 필드는 `MODULE_SYMBOL_SEARCH_INFO` 구조 비어 있지 않으면 다음 검색 경로 및 해당 검색 결과의 목록을 포함 합니다. 목록 경로, 줄임표 \("..."\), 결과 뒤 다음으로 지정 됩니다. 둘 이상의 경로 결과 쌍 이면 각 쌍은 "\\r\\n" \(캐리지 리턴\/줄 바꿈\) 쌍으로 구분 됩니다. 패턴은 다음과 같습니다.  
  
 \< 경로 \>... \< 결과 \> \\r\\n \< 경로 \>... \< 결과 \> \\r\\n \< 경로 \>... \< 결과 \>  
  
 마지막 항목 \\r\\n 시퀀스 없는 참고 합니다.  
  
## 예제  
 이 예제에서는이 메서드는 세 개의 서로 다른 검색 결과 함께 3 개의 경로 반환합니다. 각 줄은 캐리지 리턴\/줄 바꿈 쌍으로 종료 됩니다. 방금 예제 출력을 단일 문자열로 검색 결과 인쇄합니다.  
  
> [!NOTE]
>  상태 결과 바로 다음에 "..." 줄의 끝까지 모든 항목입니다.  
  
```cpp#  
void ShowSymbolSearchResults(IDebugModule3 *pIDebugModule3)  
{  
    MODULE_SYMBOL_SEARCH_INFO ssi = { 0 };  
    HRESULT hr;  
    hr = pIDebugModule3->GetSymbolInfo(SSIF_VERBOSE_SEARCH_INFO,&ssi);  
    if (SUCCEEDED(hr)) {  
        CComBSTR searchInfo = ssi.bstrVerboseSearchInfo;  
        if (searchInfo.Length() != 0) {  
            std::wcout << (wchar_t *)(BSTR)searchInfo;  
            std::wcout << std::endl;  
        }  
    }  
}  
```  
  
 **c:\\symbols\\user32.pdb... 파일을 찾을 수 없습니다. c:\\winnt\\symbols\\user32.pdb... 버전이 일치 하지 않습니다. \\\\symbols\\symbols\\user32.dll\\0a8sd0ad8ad\\user32.pdb... 기호를 로드 합니다.**   
## 참고 항목  
 [SYMBOL\_SEARCH\_INFO\_FIELDS](../../../extensibility/debugger/reference/symbol-search-info-fields.md)   
 [MODULE\_SYMBOL\_SEARCH\_INFO](../../../extensibility/debugger/reference/module-symbol-search-info.md)   
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)