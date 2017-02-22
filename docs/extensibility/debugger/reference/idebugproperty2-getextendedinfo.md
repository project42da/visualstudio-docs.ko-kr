---
title: "IDebugProperty2::GetExtendedInfo | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProperty2::GetExtendedInfo"
helpviewer_keywords: 
  - "IDebugProperty2::GetExtendedInfo"
ms.assetid: 0c9c0b2b-7540-4424-adb5-fce7aa37a026
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProperty2::GetExtendedInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

확장 속성에 대 한 정보를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetExtendedInfo (   
   REFGUID* guidExtendedInfo,  
   VARIANT* pExtendedInfo  
);  
```  
  
```c#  
int GetExtendedInfo (   
   ref Guid guidExtendedInfo,  
   out object pExtendedInfo  
);  
```  
  
#### 매개 변수  
 `guidExtendedInfo`  
 \[in\] 확장 된 정보를 검색할 형식을 지정 하는 GUID입니다.  에 대 한 자세한 내용은 설명 부분을 참조 하십시오.  
  
 `pExtendedInfo`  
 \[out\] 반환 된 `VARIANT` \(c \+ \+\) 또는 확장된 속성 정보를 검색 하는 데 사용할 수 있는 개체 \(C\#\).  예를 들어,이 매개 변수를 반환할 수 있습니다는 `IUnknown` 에 대해 쿼리할 수 있는 인터페이스는 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md) 인터페이스입니다.  에 대 한 자세한 내용은 설명 부분을 참조 하십시오.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  반환 `S_GETEXTENDEDINFO_NO_EXTENDEDINFO` 검색에 확장 된 정보가 없으면 합니다.  
  
## 설명  
 이 메서드 자체를 호출 하 여 검색 하려면 충분 하지 않습니다 하는 정보를 검색 하는 것은 [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) 메서드가 있습니다.  
  
 다음 Guid는 일반적으로 \(이름 모든 어셈블리를 사용할 수 없으므로 GUID 값 C\#에 지정 된\)이이 방법으로 인식 됩니다.  내부 사용을 위해 추가 Guid는 만들 수 있습니다.  
  
|Name|GUID|설명|  
|----------|----------|--------|  
|guidDocument|{3f98de84\-fee9\-11d0\-b47f\-00a0244a1dd2}|반환 된 `IUnknown` 문서 인터페이스입니다.  일반적으로 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md) 인터페이스 얻을 수 있습니다에서이 `IUnknown` 인터페이스입니다.|  
|guidCodeContext|{e2fc65e\-56ce\-11 d 1\-b528\-00aax004a8797}|반환 된 `IUnknown` 문서 컨텍스트 인터페이스입니다.  일반적으로 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) 인터페이스 얻을 수 있습니다에서이 `IUnknown` 인터페이스입니다.|  
|guidCustomViewerSupported|{d9c9da31\-ffbe\-4eeb\-9186\-23121e3c088c}|CLSID는 식 계산기가 일반적으로 구현 하는 사용자 지정 뷰어를 포함 하는 문자열을 반환 합니다.|  
|guidExtendedInfoSlot|{6df235ad\-82c6\-4292\-9c97\-7389770bc42f}|로컬 주소를 관리 코드로이 속성을 나타내는 경우 원하는 슬롯 수를 나타내는 32 비트 숫자를 반환 합니다.|  
|guidExtendedInfoSignature|{b5fb6d46\-f805\-417f\-96a3\-8ba737073ffd}|서명 속성 개체와 연관 된 변수를 포함 하는 문자열을 반환 합니다.|  
  
## 참고 항목  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)