---
title: "IDebugContainerField::EnumFields | Microsoft Docs"
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
  - "IDebugContainerField::EnumFields"
helpviewer_keywords: 
  - "IDebugContainerField::EnumFields 메서드"
ms.assetid: 9e5e681b-ad49-4c62-bd95-4afa11d61a57
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugContainerField::EnumFields
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

컨테이너의 필드에 대 한 열거자를 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumFields(   
   FIELD_KIND         dwKindFilter,  
   FIELD_MODIFIERS    dwModifiersFilter,  
   LPCOLESTR          pszNameFilter,  
   NAME_MATCH         nameMatch,  
   IEnumDebugFields** ppEnum  
);  
```  
  
```c#  
int EnumFields(  
   enum_ FIELD_KIND      dwKindFilter,   
   enum_ FIELD_MODIFIERS dwModifiersFilter,   
   string                pszNameFilter,   
   NAME_MATCH            nameMatch,   
   out IEnumDebugFields  ppEnum  
);  
```  
  
#### 매개 변수  
 `dwKindFilter`  
 \[in\] 함께 [FIELD\_KIND](../../../extensibility/debugger/reference/field-kind.md) 열거 될 필드를 선택 하는 상수입니다.  필드 종류는 클래스 기본 형식, 또는 특정 정보 등, 지역, 매개 변수에 "this"이 포인터가 같은 저장소 종류를 설명할 수 있습니다.  
  
 `dwModifiersFilter`  
 \[in\] 함께 [FIELD\_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md) 열거 될 필드를 선택 하는 상수입니다.  필드 한정자는 공용 또는 개인, 또는 저장소 정보를 가상, 정적, 또는 마지막으로 액세스 권한을 수 있습니다.  
  
 `pszNameFilter`  
 \[in\] 열거 될 필드의 이름입니다.  필드를 모두 반환 하는 경우 null 값이 될 수 있습니다.  
  
 `nameMatch`  
 \[in\] 값은 [NAME\_MATCH](../../../extensibility/debugger/reference/name-match.md) 여부를 검색 하는지 여부를 제어 하는 열거형 대\/소문자 구분입니다.  
  
 `ppEnum`  
 \[out\] 반환 된 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 필드를 나타내는 개체입니다.  필드가 없는 경우 null 값을 반환 합니다.  
  
## 반환 값  
 필드가 없으면이 작업이 성공 하면 S\_OK 또는 S\_FALSE를 반환 합니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 `dwKindFilter`, `dwModifiersFilter`, 및 `pszNameFilter` 매개 변수가 결합할 수 있습니다, 예를 들어, 이름이 "MyMethod" 모든 공용 가상 메서드를 선택 합니다.  
  
## 참고 항목  
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [FIELD\_KIND](../../../extensibility/debugger/reference/field-kind.md)   
 [FIELD\_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)   
 [NAME\_MATCH](../../../extensibility/debugger/reference/name-match.md)