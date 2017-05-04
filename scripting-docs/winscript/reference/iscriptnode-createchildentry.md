---
title: "IScriptNode:: CreateChildEntry | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptNode. CreateChildEntry
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptNode::CreateChildEntry"
ms.assetid: b9682505-4457-40e9-8691-235843637506
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# IScriptNode:: CreateChildEntry
자식 인스턴스를 추가 `IScriptEntry`.  
  
## 구문  
  
```  
HRESULT CreateChildEntry(  
   ULONG              isn,  
   DWORD              dwCookie,  
   LPCOLESTR          pszDelimiter,  
   IScriptEntry       **ppse  
);  
```  
  
#### 매개 변수  
 `isn`  
 \[in\] 부모에서 자식의 인덱스입니다.  
  
 `dwCookie`  
 \[in\] 호스트 개체에 자식 항목을 연결 하는 데 사용 하는 응용 프로그램 정의 값입니다.  
  
 `pszDelimiter`  
 \[in\] 주소 끝의 스크립트 블록 구분 기호입니다.  구문 분석에 대 한 호스트 일반적 구분 \(예: 두 개의 작은따옴표\)를 감지 스크립트 블록의 끝에 사용 합니다.  
  
 구분 기호는 전처리를 제공 하는 엔진 제작 스크립트가 있습니다.  예를 들어, 엔진에 두 개의 작은따옴표를 구분 기호로 사용 단일 인용 부호를 바꿀 수 있습니다.  엔진의 구분 기호를 사용 하는 방법을 결정 합니다.  
  
 스크립트 블록의 끝 구분 기호를 표시 하지 않을 경우 NULL로 설정 합니다.  
  
 `ppse`  
 \[out\] 에 대 한 포인터를 받는 변수의 주소는 `IScriptEntry` 인터페이스 인스턴스의 자식.  
  
 에 대 한 `IScriptNode` 이 매개 변수를 반환 하는 웹 페이지를 나타내는 개체는 `IScriptEntry` 스크립트 블록을 지정 하는 인스턴스.  
  
 에 대 한 `IScriptEntry` 이 매개 변수는 스크립트 블록을 나타내는 개체를 반환는 `IScriptEntry` 인스턴스 함수 개체를 지정 합니다.  
  
 에 대 한 `IScriptEntry` 함수를 나타내는 개체 개체에서이 메서드는 실패 합니다.  
  
 에 대 한 `IScriptScriptlet` 개체에서이 메서드는 실패 합니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 `IScriptNode` 인터페이스 웹 페이지 또는 요소를 나타냅니다.  `IScriptEntry` 인터페이스 \(에서 파생 된 `IScriptNode`\) 함수 개체 또는 스크립트 블록을 나타냅니다.  `IScriptScriptlet` 인터페이스 \(에서 파생 된 `IScriptEntry`\) 이벤트 처리기를 나타냅니다.  
  
## 참고 항목  
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)   
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)