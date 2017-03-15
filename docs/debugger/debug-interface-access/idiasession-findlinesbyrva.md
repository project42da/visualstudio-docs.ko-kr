---
title: "IDiaSession::findLinesByRVA | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaSession::findLinesByRVA 메서드"
ms.assetid: 06f53b0b-b5b4-42cf-9252-dcee0dbe2d71
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaSession::findLinesByRVA
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정한 상대 가상 주소 \(RVA\) 포함 된 줄은 지정 된 컴파일 대상에서 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT findLinesByRVA (   
   DWORD                 rva,  
   DWORD                 length,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### 매개 변수  
 `rva`  
 \[in\] RVA로 주소를 지정합니다.  
  
 `length`  
 \[in\] 바이트 수로이 쿼리를 포함 하는 주소 범위를 지정 합니다.  
  
 `ppResult`  
 \[out\] 반환 된 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) 은 모든 줄을 포함 하는 개체 번호가 해당 표지 지정한 주소 범위가 있습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 예제  
 이 예제 함수는 함수의 상대 가상 주소와 길이 사용 하 여 지정한 함수에 포함 된 모든 줄 번호를 가져옵니다.  
  
```cpp#  
IDiaEnumLineNumbers* GetLineNumbersByRVA(IDiaSymbol *pFunc, IDiaSession *pSession)  
{  
    IDiaEnumLineNumbers* pEnum = NULL;  
    DWORD                rva;  
    ULONGLONG            length;  
  
    if (pFunc->get_relativeVirtualAddress ( &rva ) == S_OK)  
    {  
        pFunc->get_length ( &length );  
        pSession->findLinesByRVA( rva, static_cast<DWORD>( length ), &pEnum );  
    }  
    return(pEnum);  
}  
```  
  
## 참고 항목  
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)