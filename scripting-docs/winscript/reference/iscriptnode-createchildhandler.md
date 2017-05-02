---
title: "IScriptNode::CreateChildHandler | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptNode.CreateChildHandler
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptNode::CreateChildHandler"
ms.assetid: 4ce5eb10-1a3f-43b0-a4b7-599a397ed3a2
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# IScriptNode::CreateChildHandler
스크립트릿으로 자식 인스턴스를 추가 된 `IScriptNode`.  
  
## 구문  
  
```  
HRESULT CreateChildHandler(  
   LPCOLESTR          pszDefaultName,  
   LPCOLESTR          *prgpszNames,  
   ULONG              cpszNames,  
   LPCOLESTR          pszEvent,  
   LPCOLESTR          pszDelimiter,  
   ITypeInfo*         ptiSignature,  
   ULONG              iMethodSignature,  
   ULONG              isn,  
   DWORD              dwCookie,  
   IScriptEntry       **ppse  
);  
```  
  
#### 매개 변수  
 `pszDefaultName`  
 \[in\] 주소 스크립트릿으로 연결할 기본 이름입니다.  
  
 `prgpszNames`  
 in, size\_is\(`cpszNames`\)\] 호스트의 정규화 된 이름과 식별자 목록이 있습니다.  
  
 `cpszNames`  
 \[in\] 식별자의 개수는 `prgpszNames` 매개 변수.  
  
 `pszEvent`  
 \[in\] 버퍼 주소가 스크립트릿와 연관 된 이벤트 이름을 식별 합니다.  
  
 `pszDelimiter`  
 \[in\] 주소 끝의 스크립트 블록 구분 기호입니다.  구문 분석에 대 한 호스트 일반적 구분 \(예: 두 개의 작은따옴표\)를 감지 스크립트 블록의 끝에 사용 합니다.  
  
 전처리 스크립트 엔진 제작에서 구분 기호 수 있습니다.  예를 들어, 엔진에 두 개의 작은따옴표를 구분 기호로 사용 단일 인용 부호를 바꿀 수 있습니다.  엔진의 구분 기호를 사용 하는 방법을 결정 합니다.  
  
 구분 기호 없음 스크립트 블록의 끝을 식별 하는 경우 NULL로 설정 합니다.  
  
 `ptiSignature`  
 \[in\] 함수 개체의 형식 정보입니다.  
  
 `iMethodSignature`  
 \[in\] Index 함수에 `ITypeInfo``ptiSignature` 매개 변수.  
  
 `isn`  
 \[in\] 부모에서 자식의 인덱스입니다.  
  
 `dwCookie`  
 \[in\] 호스트 개체에 항목을 연결 하는 데 사용 되는 응용 프로그램 정의 값입니다.  
  
 `ppse`  
 \[out\] 에 대 한 포인터를 받는 변수의 주소는 `IScriptEntry` 인터페이스 인스턴스의 자식.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 스크립트릿은 이벤트 처리기를 지정합니다.  호출 하는 경우이 메서드는 스크립트릿 만듭니다는 `IScriptNode` 웹 페이지를 나타내는 개체입니다.  다른 인터페이스를 호출 하는 경우이 메서드는 성공 하지 않습니다.  
  
## 참고 항목  
 [IScriptNode 인터페이스](../../winscript/reference/iscriptnode-interface.md)   
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)