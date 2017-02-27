---
title: "IDebugTypeFieldBuilder::CreatePrimitive | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CreatePrimitive"
  - "IDebugTypeFieldBuilder::CreatePrimitive"
ms.assetid: 512c6ff0-97c5-409f-939f-4cc969bc4bb9
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugTypeFieldBuilder::CreatePrimitive
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

기본 형식을 나타내는 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
HRESULT CreatePrimitive (  
   DWORD          dwElementType,  
   IDebugField ** pTypeField  
);  
```  
  
```c#  
int CreatePrimitive (  
   uint            dwElementType,  
   out IDebugField pTypeField  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwElementType`  
 [in] 값의 [CorElementType 열거형](CorElementType%20Enumeration.xml) 기본 형식을 나타내는 합니다.  
  
 `pTypeField`  
 [out] 새 형식에 대 한 IDebugField 인터페이스를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugTypeFieldBuilder](../../../extensibility/debugger/reference/idebugtypefieldbuilder.md)