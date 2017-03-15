---
title: "IDiaSession::findLinesByAddr | Microsoft Docs"
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
  - "IDiaSession::findLinesByAddr 메서드"
ms.assetid: 640403c0-14cf-403c-ad19-38b3bdc28ca8
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSession::findLinesByAddr
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정 된 주소에 포함 된 지정 된 컴파일 줄을 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT findLinesByAddr (   
   DWORD                 seg,  
   DWORD                 offset,  
   DWORD                 length,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### 매개 변수  
 `seg`  
 \[in\] 섹션 구성 요소 특정 주소를 지정합니다.  
  
 `offset`  
 \[in\] 오프셋된 구성 요소가 특정 주소를 지정합니다.  
  
 `length`  
 \[in\] 바이트 수로이 쿼리를 포함 하는 주소 범위를 지정 합니다.  
  
 `ppResult`  
 \[out\] 반환 된 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) 은 모든 줄을 포함 하는 개체 번호가 해당 표지 지정한 주소 범위가 있습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 예제  
 함수의 주소와 길이 사용 하는 함수에 포함 된 모든 줄 번호를 가져오는 함수를 추가 하는 예제입니다.  
  
```cpp#  
IDiaEnumLineNumbers* GetLineNumbersByAddr(IDiaSymbol *pFunc,  
                                          IDiaSession *pSession)  
{  
    IDiaEnumLineNumbers* pEnum = NULL;  
    DWORD                seg;  
    DWORD                offset;  
    ULONGLONG            length;  
  
    if (pFunc->get_addressSection ( &seg ) == S_OK &&  
        pFunc->get_addressOffset ( &offset ) == S_OK)  
    {  
        pFunc->get_length ( &length );  
        pSession->findLinesByAddr( seg, offset, static_cast<DWORD>( length ), &pEnum );  
    }  
    return(pEnum);  
}  
```  
  
## 참고 항목  
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSession::findLinesByVA](../../debugger/debug-interface-access/idiasession-findlinesbyva.md)