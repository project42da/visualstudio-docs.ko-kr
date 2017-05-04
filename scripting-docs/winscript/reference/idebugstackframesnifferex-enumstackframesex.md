---
title: "IDebugStackFrameSnifferEx::EnumStackFramesEx | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugStackFrameSnifferEx.EnumStackFramesEx
apilocation: jscript.dll
helpviewer_keywords: 
  - "IDebugStackFrameSnifferEx::EnumStackFramesEx"
ms.assetid: b656b581-aff0-4984-8d8a-a1c7a8e6558a
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugStackFrameSnifferEx::EnumStackFramesEx
현재 스레드에 대 한 스택 프레임에 대 한 열거자를 반환합니다.  
  
## 구문  
  
```  
HRESULT EnumStackFramesEx(  
   DWORD_PTR                dwSpMin,  
   IEnumDebugStackFrames**  ppedsf  
);  
```  
  
#### 매개 변수  
 `dwSpMin`  
 \[in\] 스택 프레임을 열거 하는 낮은 주소 제한입니다.  
  
 `ppedsf`  
 \[out\] 열거자의 현재 스레드에 대 한 스택 프레임입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 가장 최근에 푸시된 프레임의 스택 맨 위에 있는 시작 프레임 스택 프레임 열거자를 반환 합니다.  열거자 주소 보다 크거나 스택 프레임만 포함 `dwSpMin`.  
  
## 참고 항목  
 [IDebugStackFrameSnifferEx 인터페이스](../../winscript/reference/idebugstackframesnifferex-interface.md)