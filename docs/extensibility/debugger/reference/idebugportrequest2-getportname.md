---
title: "IDebugPortRequest2::GetPortName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortRequest2::GetPortName"
helpviewer_keywords: 
  - "IDebugPortRequest2::GetPortName"
ms.assetid: 53e2a3a4-bb34-4a02-a983-6bd84ea70587
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugPortRequest2::GetPortName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

포트의 이름을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetPortName(   
   BSTR* pbstrPortName  
);  
```  
  
```c#  
int GetPortName(   
   out string pbstrPortName  
);  
```  
  
#### 매개 변수  
 `pbstrPortName`  
 \[out\] 포트의 이름을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) 인터페이스 일반적으로 전달 된 디버그 패키지 \(클라이언트\)에서 연결을 얻을 수 있는 포트 공급자에 \(서버\)를 포트에 있습니다.  디버그 패키지 및 포트 공급자 모두를 인식 하는 포트에 대 한 항목입니다.  간단한 문자열을 포트 설명할 수 있는 경우 다음 해당 `IDebugPortRequest2::GetPortName` 메서드는 연결을 만드는 데 충분 한 정보가 없습니다.  그렇지 않으면 추가 인터페이스 서버 사용 하 여 얻을 수 있습니다 클라이언트가 제공할 수 있는 `IDebugPortRequest2::QueryInterface`.  
  
## 참고 항목  
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)