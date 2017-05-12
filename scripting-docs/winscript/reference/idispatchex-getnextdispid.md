---
title: "IDispatchEx::GetNextDispID | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDispatchEx.GetNextDispID
apilocation: scrobj.dll
helpviewer_keywords: 
  - "GetNextDispID 메서드"
ms.assetid: 8263d441-85ee-47f4-bdba-fbf2ad07e85f
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDispatchEx::GetNextDispID
개체의 멤버를 열거합니다.  
  
## 구문  
  
```  
HRESULT GetNextDispID(  
   DWORD grfdex,  
   DISPID id,  
   DISPID *pid  
);  
```  
  
#### 매개 변수  
 `grfdex`  
 어떤 항목 집합을 열거할 수를 결정 합니다.  이 다음 값 조합이 될 수 있습니다.  
  
|값|의미|  
|-------|--------|  
|fdexEnumDefault|요청 개체의 기본 요소를 열거 합니다.  개체 집합의 요소를 열거할 수 있습니다.|  
|fdexEnumAll|요청 개체의 모든 요소를 열거 합니다.  개체 집합의 요소를 열거할 수 있습니다.|  
  
 `id`  
 현재 멤버를 식별합니다.  GetNextDispID 열거형이 뒤에 있는 항목을 검색합니다.  GetDispID 또는 Getnextdispid에 대 한 이전 호출을 사용 하 여이 식별자를 얻으려면.  첫째 식별자의 첫 번째 항목을 얻으려면 DISPID\_STARTENUM 값을 사용 합니다.  
  
 `pid`  
 열거형에서 다음 항목의 식별자를 받는 DISPID 변수의 주소.  
  
 구성원 삭제 하는 경우 `DeleteMemberByName` 또는 `DeleteMemberByDispID`, `DISPID` 에 대 한 유효한 상태를 유지 해야 `GetNextDispID`.  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|||  
|-|-|  
|`S_OK`|성공|  
|`S_FALSE`|열거를 수행 합니다.|  
  
## 예제  
  
```  
HRESULT hr;  
   BSTR bstrName;  
   DISPID dispid;  
   IDispatchEx *pdex;  
  
   // Assign to pdex  
   hr = pdex->GetNextDispID(fdexEnumAll, DISPID_STARTENUM, &dispid);  
   while (hr == NOERROR)  
   {  
      hr = pdex->GetMemberName(dispid, &bstrName);  
      if (!wcscmp(bstrName, OLESTR("Bar")))  
      {  
         SysFreeString(bstrName);  
         return TRUE;  
      }  
      SysFreeString(bstrName);  
      hr = pdex->GetNextDispID(fdexEnumAll, dispid, &dispid);  
   }  
```  
  
## 참고 항목  
 [IDispatchEx 인터페이스](../../winscript/reference/idispatchex-interface.md)   
 [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)   
 [IDispatchEx::GetNextDispID](#lrfidispatchexgetnextdispid)   
 [IDispatchEx::DeleteMemberByName](../../winscript/reference/idispatchex-deletememberbyname.md)   
 [IDispatchEx::DeleteMemberByDispID](../../winscript/reference/idispatchex-deletememberbydispid.md)