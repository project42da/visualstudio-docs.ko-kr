---
title: "IDebugErrorEvent2::GetErrorMessage | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugErrorEvent2::GetErrorMessage"
helpviewer_keywords: 
  - "IDebugErrorEvent2::GetErrorMessage"
ms.assetid: 9e3b0d74-a2dd-4eaa-bd95-21b2f9c79409
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugErrorEvent2::GetErrorMessage
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사람이 읽을 수 있는 오류 메시지를 생성할 때 사용할 수 있는 정보를 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetErrorMessage(  
   MESSAGETYPE* pMessageType,  
   BSTR*        pbstrErrorFormat,  
   HRESULT*     hrErrorReason,  
   DWORD*       pdwType,  
   BSTR*        pbstrHelpFileName,  
   DWORD*       pdwHelpId  
);  
```  
  
```c#  
int GetErrorMessage(  
   out enum_MESSAGETYPE   pMessageType,  
   out string             pbstrErrorFormat,  
   out int                phrErrorReason,  
   out uint               pdwType,  
   out string             pbstrHelpFileName,  
   out uint               pdwHelpId  
);  
```  
  
#### 매개 변수  
 `pMessageType`  
 \[out\] 값을 반환의 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md) 메시지의 형식을 설명 하는 열거형입니다.  
  
 `pbstrErrorFormat`  
 \[out\] 최종 사용자에 게 메시지의 형식 \(자세한 내용은 "설명" 참조\).  
  
 `hrErrorReason`  
 \[out\] 메시지의 오류 코드가입니다.  
  
 `pdwType`  
 \[out\] 오류의 심각도를 \(MB\_XXX 상수를 사용 하 여 `MessageBox`. for example, `MB_EXCLAMATION` or `MB_WARNING`\).  
  
 `pbstrHelpFileName`  
 \[out\] 도움말 파일 \(없음 도움말 파일이 있을 경우 null 값 설정\) 경로입니다.  
  
 `pdwHelpId`  
 \[out\] \(도움말 항목이 없는 경우 0으로 설정\)을 표시 하는 도움말 항목의 ID입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 오류 메시지의 줄 함께 포맷 해야 합니다 `"What I was doing.  %1"`.  `"%1"` 다음 호출자가 오류 코드에서 파생 된 오류 메시지와 함께 바뀝니다 \(반환 됩니다 `hrErrorReason`\).  `pMessageType` 매개 변수 최종 오류 메시지 표시 방법 호출자에 게 알립니다.  
  
## 참고 항목  
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)   
 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)