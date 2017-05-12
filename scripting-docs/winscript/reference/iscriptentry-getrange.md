---
title: "IScriptEntry::GetRange | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptEntry.GetRange
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptEntry::GetRange"
ms.assetid: 3ac18f0a-b470-4f4d-b8f5-2da3fdef74f1
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IScriptEntry::GetRange
시작 위치 및 항목의 길이 반환합니다.  
  
## 구문  
  
```  
HRESULT GetRange(  
   ULONG              *pichMin  
   ULONG              *pcch  
);  
```  
  
#### 매개 변수  
 `pichMin`  
 \[out\] 에 대 한 `IScriptEntry` 0을 반환 하는 스크립트 블록을 지정 하는 개체입니다.  
  
 에 대 한 `IScriptEntry` 함수 개체를 지정 하는 개체는 현재 스크립트 블록에 함수의 시작 위치를 반환 합니다.  
  
 에 대 한 `IScriptScriptlet` 개체, 0을 반환 합니다.  
  
 `pcch`  
 \[out\] 에 대 한 `IScriptEntry` 스크립트 블록을 지정 하는 개체는 텍스트의 길이 반환 합니다.  
  
 에 대 한 `IScriptEntry` 함수 개체를 지정 하는 개체 함수 정의의 길이 반환 합니다.  
  
 에 대 한 `IScriptScriptlet` 개체, 항목의 길이 반환 합니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)