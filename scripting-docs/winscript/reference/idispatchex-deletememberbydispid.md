---
title: "IDispatchEx::DeleteMemberByDispID | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDispatchEx.DeleteMemberByDispID
apilocation: scrobj.dll
helpviewer_keywords: 
  - "DeleteMemberByDispID 메서드"
ms.assetid: f61231e5-ba93-4ac3-bde8-d363548356b3
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDispatchEx::DeleteMemberByDispID
DISPID로 멤버를 삭제합니다.  
  
## 구문  
  
```  
HRESULT DeleteMemberByDispID(  
    DISPID id  
);  
```  
  
#### 매개 변수  
 `id`  
 멤버 식별자입니다.  사용 하 여 `GetDispID` 또는 `GetNextDispID` 디스패치 식별자를 얻을 수 있습니다.  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|||  
|-|-|  
|`S_OK`|성공|  
|`S_FALSE`|멤버는 존재 하지만 삭제할 수 없습니다.|  
  
## 설명  
 멤버를 삭제 하는 경우에 dispid가 유효한 상태를 유지 해야 `GetNextDispID`.  
  
 이름이 지정 된 멤버를 삭제 하 고 나중에 동일한 이름의 멤버를 다시 만들 경우 DISPID는 동일 해야 합니다.  \(대\/소문자만 다른 멤버 이름을 "동일한" 지 개체에 따라 다릅니다.\)  
  
## 예제  
  
```  
BSTR bstrName;  
DISPID dispid;  
IDispatchEx *pdex;   
  
// Assign to pdex and bstrName  
if (SUCCEEDED(pdex->GetDispID(bstrName, fdexNameCaseSensitive, &dispid)))  
    pdex->DeleteMemberByDispID(dispid);  
```  
  
## 참고 항목  
 [IDispatchEx 인터페이스](../../winscript/reference/idispatchex-interface.md)   
 [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)   
 [IDispatchEx::GetNextDispID](../../winscript/reference/idispatchex-getnextdispid.md)