---
title: "IJsDebugDataTarget::GetTlsValue 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugDataTarget.GetTlsValue
apilocation: jscript9diag.dll
ms.assetid: db575be9-7b24-45c5-9008-e4f2f76d6757
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugDataTarget::GetTlsValue 메서드
디버깅 중인 스레드의 경우 지정된 TLS 인덱스에 대해 TLS\(스레드 로컬 저장소\)에서 값을 검색합니다.  
  
## 구문  
  
```  
HRESULT GetTlsValue(  
   DWORD threadId,  
   UINT32 tlsIndex,  
   UINT64 *pValue  
);  
```  
  
#### 매개 변수  
 `threadId`  
 \[in\] 읽을 대상 프로세스에서 실행되는 스레드입니다.  
  
 `tlsIndex`  
 \[in\] 대상 프로세스에서 TlsAlloc 함수가 호출되었을 때 할당된 TLS 인덱스입니다.  
  
 `pValue`  
 \[out\] 스레드의 TLS 슬롯에 저장된 포인터 크기의 값입니다.  대상 스레드가 32비트인 경우 32비트를 넘는 이 값이 0이 됩니다.  
  
## 반환 값  
  
## 설명  
 각 프로세스의 스레드에는 각 TLS 인덱스에 대한 슬롯이 있습니다.  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)