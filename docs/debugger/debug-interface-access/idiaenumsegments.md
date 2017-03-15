---
title: "IDiaEnumSegments | Microsoft Docs"
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
  - "IDiaEnumSegments 인터페이스"
ms.assetid: 0c9edd5e-b9ce-43e1-a791-cd4c5d16d923
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IDiaEnumSegments
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

데이터 소스에 포함 된 다양 한 세그먼트를 열거 합니다.  
  
## 구문  
  
```  
IDiaEnumSegments : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDiaEnumSegments`.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaEnumSegments::get\_\_NewEnum](../../debugger/debug-interface-access/idiaenumsegments-get-newenum.md)|검색은 [IEnumVARIANT Interface](http://msdn.microsoft.com/ko-kr/139e3c93-faef-4003-9079-e0e94494db3e) 이 열거자의 버전입니다.|  
|[IDiaEnumSegments::get\_Count](../../debugger/debug-interface-access/idiaenumsegments-get-count.md)|세그먼트의 수를 검색합니다.|  
|[IDiaEnumSegments::Item](../../debugger/debug-interface-access/idiaenumsegments-item.md)|세그먼트의 인덱스를 검색합니다.|  
|[IDiaEnumSegments::Next](../../debugger/debug-interface-access/idiaenumsegments-next.md)|세그먼트 열거 시퀀스에서 지정 된 수를 검색합니다.|  
|[IDiaEnumSegments::Skip](../../debugger/debug-interface-access/idiaenumsegments-skip.md)|세그먼트 열거 시퀀스에서 지정 된 수를 건너뜁니다.|  
|[IDiaEnumSegments::Reset](../../debugger/debug-interface-access/idiaenumsegments-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[IDiaEnumSegments::Clone](../../debugger/debug-interface-access/idiaenumsegments-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
  
## 설명  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 얻을 `QueryInterface` 방법에는 [IDiaTable](../../debugger/debug-interface-access/idiatable.md) 개체입니다.  자세한 내용은 예제를 참조 하십시오.  
  
## 예제  
 가져오는 방법을 보여 주는이 예제는 `IDiaEnumSections` 인터페이스의 테이블에서입니다.  세그먼트를 사용 하는 전체 예제를 참조 하십시오은 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md) 인터페이스입니다.  
  
```cpp#  
void ShowSegments(IDiaTable *pTable, IDiaSession *pSession)  
{  
    CComPtr<IDiaEnumSegments> pSegments;  
    if ( SUCCEEDED( pTable->QueryInterface(  
                                __uuidof( IDiaEnumSegments ),  
                                (void**)&pSegments )  
                  )  
       )  
    {  
        // Do something with this enumeration  
    }  
}  
```  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)