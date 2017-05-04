---
title: "IDebugProperty::GetExtendedInfo | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugProperty.GetExtendedInfo
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDebugProperty::GetExtendedInfo"
ms.assetid: a989ade5-16d5-4ee6-8d8a-8dcbfad24034
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugProperty::GetExtendedInfo
확장 속성에 대 한 정보를 가져옵니다.  
  
## 구문  
  
```  
HRESULT GetExtendedInfo (  
   ULONG  cInfos,  
   GUID*  rgguidExtendedInfo,  
   VARIANT* pExtendedInfo  
);  
```  
  
#### 매개 변수  
 `cInfos`  
 \[in\] 확장된 된 정보 개체 수입니다.  
  
 `rgguidExtendedInfo`  
 \[in\] 배열을 `GUID`s 동시에 여러 항목의 확장된 된 정보를 검색할 수 있도록 전달 합니다.  
  
 `pExtendedInfo`  
 \[out\] 배열을 반환 합니다. `VARIANT`s 확장된 속성 정보를 검색 하는 데 사용할 수 있습니다.  
  
## 반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## 설명  
 이 인터페이스는이 개체에 대 한 정보를 확장을 가져옵니다.  API 존재 자체를 사용 하 여 검색 하려면 충분 하지 않습니다 정보를 검색 목적만 `IDebugProperty::GetPropertyInfo`\).  
  
## 참고 항목  
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)