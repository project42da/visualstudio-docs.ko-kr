---
title: "IDispatchEx::DeleteMemberByName | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDispatchEx.DeleteMemberByName
apilocation: scrobj.dll
helpviewer_keywords: 
  - "DeleteMemberByName 메서드"
ms.assetid: a01b4e6a-d989-4b29-bb3f-04554f8c39f7
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDispatchEx::DeleteMemberByName
멤버 이름을 사용 하 여 삭제합니다.  
  
## 구문  
  
```  
HRESULT DeleteMemberByName(  
   BSTR bstrName,  
   DWORD grfdex  
  
```  
  
#### 매개 변수  
 `bstrName`  
 삭제할 멤버의 이름입니다.  
  
 `grfdex`  
 멤버 이름의 대\/소문자 구분 인지 여부를 결정 합니다.  다음 값 중 하나가 될 수 있습니다.  
  
|값|의미|  
|-------|--------|  
|fdexNameCaseSensitive|대\/소문자 구분 방식으로 이름 조회를 수행할 수 있는 요청 수입니다.  대\/소문자 구분 조회를 지원 하지 않는 개체를 무시할 수 있습니다.|  
|fdexNameCaseInsensitive|대\/소문자 이름 조회를 수행할 수 있는 요청 수입니다.  대\/소문자 구분 조회를 지원 하지 않는 개체를 무시할 수 있습니다.|  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|||  
|-|-|  
|`S_OK`|성공|  
|`S_FALSE`|멤버는 존재 하지만 삭제할 수 없습니다.|  
  
## 설명  
 멤버를 삭제 하는 경우에 dispid가 유효한 상태를 유지 해야 `GetNextDispID`.  
  
 이름이 지정 된 멤버를 삭제 하 고 나중에 동일한 이름의 멤버를 다시 만들 경우 DISPID는 동일 해야 합니다.  \(대\/소문자만 다른 멤버 "동일한" 지 개체에 따라 다릅니다.\)  
  
## 예제  
  
```  
BSTR bstrName;  
IDispatchEx *pdex;  
  
// Assign to pdex and bstrName  
pdex->DeleteMemberByName(bstrName, fdexNameCaseSensitive);  
```  
  
## 참고 항목  
 [IDispatchEx 인터페이스](../../winscript/reference/idispatchex-interface.md)