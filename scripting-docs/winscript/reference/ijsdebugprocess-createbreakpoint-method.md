---
title: "IJsDebugProcess::CreateBreakPoint 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugProcess.CreateBreakPoint
apilocation: jscript9diag.dll
ms.assetid: a2cb4233-2846-4d11-aa13-21de43abda9f
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# IJsDebugProcess::CreateBreakPoint 메서드
문서의 지정된 위치에 중단점을 설정합니다.  
  
## 구문  
  
```  
HRESULT CreateBreakPoint(  
   UINT64 documentId,  
   DWORD characterOffset,  
   DWORD characterCount,  
   BOOL isEnabled,  
   IJsDebugBreakPoint **ppDebugBreakPoint  
);  
```  
  
#### 매개 변수  
 `documentId`  
 \[in\] IDebugDocumentText에 대한 포인터입니다.  
  
 `characterOffset`  
 \[in\] 파일의 시작 부분부터의 문자 오프셋입니다.  
  
 `characterCount`  
 \[in\] 중단점을 삽입되어야 하는 문서 텍스트의 길이입니다.  
  
 `isEnabled`  
 \[in\] 중단점이 사용 가능한지 여부를 지정합니다.  
  
 `ppDebugBreakPoint`  
 \[out\] 만들어진 중단점을 나타내는 개체입니다.  
  
## 반환 값  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugProcess 인터페이스](../../winscript/reference/ijsdebugprocess-interface.md)