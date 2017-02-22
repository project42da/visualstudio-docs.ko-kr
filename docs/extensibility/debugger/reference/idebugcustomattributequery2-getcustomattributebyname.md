---
title: "IDebugCustomAttributeQuery2::GetCustomAttributeByName | Microsoft Docs"
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
  - "IDebugCustomAttributeQuery2::GetCustomAttributeByName"
helpviewer_keywords: 
  - "IDebugCustomAttributeQuery2::GetCustomAttributeByName"
ms.assetid: 7428dfeb-8929-41b2-9b99-cb343a86c02d
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugCustomAttributeQuery2::GetCustomAttributeByName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용자 지정 특성의 이름을 지정 하는 사용자 지정 특성 바이트를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetCustomAttributeByName(   
   LPCOLESTR pszCustomAttributeName,  
   BYTE*     ppBlob,  
   DWORD*    pdwLen  
);  
```  
  
```c#  
int GetCustomAttributeByName(  
   [In] string        pszCustomAttributeName,   
   [In, Out] byte[]   ppBlob,   
   [In, Out] ref uint pdwLen  
);  
```  
  
#### 매개 변수  
 `pszCustomAttributeName`  
 \[in\] 검색할 사용자 지정 특성의 이름을 포함 하는 문자열입니다.  
  
 `ppBlob`  
 \[in, out\] 사용 하 여 사용자 지정 특성 바이트를 포함 하는 배열입니다.  
  
 `pdwLen`  
 \[in, out\] 최대 바이트 수를 반환 하려면 지정은 `ppBlob` 배열 및 배열에 실제로 쓴 바이트 수를 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 하거나 사용자 지정 특성이 없으면 S\_FALSE를 반환 합니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 설정에서 `ppBlob` 바이트 사용 가능한 특성을 매개 변수에 null 값의 개수를 반환 합니다.  다음 배열 할당 하 고 해당 배열에 대 한 전달의 `ppBlob` 매개 변수.  
  
 원시 데이터를의 사용자 지정 특성 특성 바이트를 나타냅니다.  
  
 경우는 `ppBlob` 및 `pdwLen` 매개 변수를 null 값으로 설정 됩니다, 단지 사용자 지정 특성이 있는지 여부를 확인 하려면이 메서드를 사용할 수 있습니다.  그러나, 보다 쉽게 대신, 호출 하는 것은 [IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery2-iscustomattributedefined.md) 메서드.  
  
## 참고 항목  
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)   
 [IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery2-iscustomattributedefined.md)