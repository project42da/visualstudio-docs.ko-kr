---
title: "IDebugClassField::DoesInterfaceExist | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugClassField::DoesInterfaceExist"
helpviewer_keywords: 
  - "IDebugClassField::DoesInterfaceExist 메서드"
ms.assetid: cc0c8642-1a76-4fda-a309-7018a34883c9
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugClassField::DoesInterfaceExist
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

특정 인터페이스는 클래스에 정의 되어 있는지 확인 합니다.  
  
## 구문  
  
```cpp#  
HRESULT DoesInterfaceExist(   
   LPCOLESTR pszInterfaceName  
);  
```  
  
```c#  
int DoesInterfaceExist(  
   [In] string pszInterfaceName  
);  
```  
  
#### 매개 변수  
 `pszInterfaceName`  
 \[in\] 찾을 대상 인터페이스 이름이 포함 된 문자열입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 하 고 S\_FALSE를 반환 합니다. 인터페이스가 존재 하지 않는 경우. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 실제로이 메서드는 모든 인터페이스의 열거형을 가져옵니다. 그리고 목록에 일치 하는 인터페이스에 대 한 검색.  
  
## 참고 항목  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)