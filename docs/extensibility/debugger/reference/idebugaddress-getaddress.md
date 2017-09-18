---
title: "IDebugAddress::GetAddress | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugAddress::GetAddress"
helpviewer_keywords: 
  - "IDebugAddress:GetAddress 메서드"
ms.assetid: 2590387b-5d36-4116-9a75-737957b8898e
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# IDebugAddress::GetAddress
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

개체는 범위 또는 컨테이너 내에서 위치를 설명 하는 구조체를 반환 합니다.  
  
## 구문  
  
```cpp  
HRESULT GetAddress (  
   DEBUG_ADDRESS * pAddress  
);  
```  
  
```c#  
int GetAddress(  
   DEBUG_ADDRESS[] pAddress  
);  
```  
  
#### 매개 변수  
 `pAddress`  
 \[in, out\] A [DEBUG\_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) 이 메서드에 의해 채워진 구조입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 [DEBUG\_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) 구조가 전달 된이 메서드를 다음 적절 한 정보로 채웁니다.  이 정보를 해석 하는 방법을 반환 되는 정보 및 기호 처리기의 종류에 따라 달라 집니다.  자세한 내용은 [DEBUG\_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)을 참조하십시오.  
  
## 참고 항목  
 [DEBUG\_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)