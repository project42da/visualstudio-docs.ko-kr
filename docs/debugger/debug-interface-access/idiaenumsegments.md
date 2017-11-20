---
title: IDiaEnumSegments | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumSegments interface
ms.assetid: 0c9edd5e-b9ce-43e1-a791-cd4c5d16d923
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d0f30e266389a3abfa3c0af1275cada34c9cfe11
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumsegments"></a>IDiaEnumSegments
데이터 원본에 포함 된 다양 한 세그먼트를 열거 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDiaEnumSegments : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDiaEnumSegments`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IDiaEnumSegments::get__NewEnum](../../debugger/debug-interface-access/idiaenumsegments-get-newenum.md)|검색 된 [IEnumVARIANT 인터페이스](http://msdn.microsoft.com/en-us/139e3c93-faef-4003-9079-e0e94494db3e) 이 열거자의 버전입니다.|  
|[IDiaEnumSegments::get_Count](../../debugger/debug-interface-access/idiaenumsegments-get-count.md)|세그먼트의 수를 검색합니다.|  
|[IDiaEnumSegments::Item](../../debugger/debug-interface-access/idiaenumsegments-item.md)|인덱스를 사용 하 여 세그먼트를 검색합니다.|  
|[IDiaEnumSegments::Next](../../debugger/debug-interface-access/idiaenumsegments-next.md)|열거형 시퀀스에 있는 세그먼트의 지정된 된 수를 검색 합니다.|  
|[IDiaEnumSegments::Skip](../../debugger/debug-interface-access/idiaenumsegments-skip.md)|열거형 시퀀스에 있는 세그먼트의 지정 된 수를 건너뜁니다.|  
|[IDiaEnumSegments::Reset](../../debugger/debug-interface-access/idiaenumsegments-reset.md)|열거형 시퀀스 시작 부분으로 다시 설정합니다.|  
|[IDiaEnumSegments::Clone](../../debugger/debug-interface-access/idiaenumsegments-clone.md)|현재 열거자와 동일한 열거 상태가 포함 하는 열거자를 만듭니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 호출 하 여이 인터페이스를 가져옵니다는 `QueryInterface` 에서 메서드는 [IDiaTable](../../debugger/debug-interface-access/idiatable.md) 개체입니다. 자세한 내용은 예제를 참조 하십시오.  
  
## <a name="example"></a>예제  
 가져오는 방법을 보여 주는이 예제는 `IDiaEnumSections` 테이블에서 인터페이스입니다. 세그먼트를 사용 하 여의 자세한 예제에 대 한 참조는 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md) 인터페이스입니다.  
  
```C++  
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
  
## <a name="requirements"></a>요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스 (디버그 인터페이스 액세스 SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)