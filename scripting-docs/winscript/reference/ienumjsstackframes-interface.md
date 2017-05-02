---
title: "IEnumJsStackFrames 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 49e7b425-df17-4d7f-87ff-0bc82715c911
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IEnumJsStackFrames 인터페이스
디버거를 통해 구현되어 JavaScript의 jscript9diag.dll에 대한 스택 해제를 제공합니다.  
  
## 구문  
  
```  
IEnumJsStackFrames : public IUnknown;  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[IEnumJsStackFrames::Next 메서드](../../winscript/reference/ienumjsstackframes-next-method.md)|지정된 프레임 수를 가져옵니다.|  
|[IEnumJsStackFrames::Reset 메서드](../../winscript/reference/ienumjsstackframes-reset-method.md)|첫 번째 요소 앞의 위치로 스택 프레임을 다시 설정합니다.|  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [Windows 스크립트 인터페이스 참조](../../winscript/reference/windows-script-interfaces-reference.md)