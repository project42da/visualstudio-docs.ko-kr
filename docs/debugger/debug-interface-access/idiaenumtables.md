---
title: "IDiaEnumTables | Microsoft Docs"
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
  - "IDiaEnumTables 인터페이스"
ms.assetid: 016190c5-09e4-48f2-bf60-9b02603a03e0
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaEnumTables
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

데이터 원본에 포함 된 여러 테이블을 열거 합니다.  
  
## 구문  
  
```  
IDiaEnumTables : IUnknown  
```  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDiaEnumTables`.  
  
|메서드|설명|  
|---------|--------|  
|[IDiaEnumTables::get\_\_NewEnum](../../debugger/debug-interface-access/idiaenumtables-get-newenum.md)|검색은 [IEnumVARIANT Interface](http://msdn.microsoft.com/ko-kr/139e3c93-faef-4003-9079-e0e94494db3e) 이 열거자의 버전입니다.|  
|[IDiaEnumTables::get\_Count](../../debugger/debug-interface-access/idiaenumtables-get-count.md)|테이블의 수를 검색합니다.|  
|[IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)|테이블의 인덱스 또는 이름을 검색합니다.|  
|[IDiaEnumTables::Next](../../debugger/debug-interface-access/idiaenumtables-next.md)|테이블 열거 시퀀스에서 지정 된 시간을 검색합니다.|  
|[IDiaEnumTables::Skip](../../debugger/debug-interface-access/idiaenumtables-skip.md)|테이블 열거 시퀀스에서 지정 된 수를 건너뜁니다.|  
|[IDiaEnumTables::Reset](../../debugger/debug-interface-access/idiaenumtables-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[IDiaEnumTables::Clone](../../debugger/debug-interface-access/idiaenumtables-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
  
## 설명  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스를 호출 하 여 얻을 [IDiaSession::getEnumTables](../../debugger/debug-interface-access/idiasession-getenumtables.md) 메서드가 있습니다.  
  
## 예제  
 가져오는 방법을 보여 주는이 예제는 `IDiaEnumTables` 인터페이스는 세션에서.  테이블을 사용 하는 전체 예제를 보려면 해당 [IDiaTable](../../debugger/debug-interface-access/idiatable.md) 인터페이스입니다.  
  
```cpp#  
void ShowTableNames(IDiaSession *pSession)  
{  
    CComPtr<IDiaEnumTables> pTables;  
    if ( FAILED( psession->getEnumTables( &pTables ) ) )  
    {  
        Fatal( "getEnumTables" );  
    }  
    // Do something with table  
}  
```  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## 참고 항목  
 [인터페이스\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaSession::getEnumTables](../../debugger/debug-interface-access/idiasession-getenumtables.md)