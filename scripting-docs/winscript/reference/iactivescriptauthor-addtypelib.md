---
title: "IActiveScriptAuthor::AddTypeLib | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptAuthor.AddTypeLib
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptAuthor::AddTypeLib"
ms.assetid: d6696547-3eb5-4f31-9c5c-60aa29b6f083
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IActiveScriptAuthor::AddTypeLib
형식 라이브러리의 네임 스페이스를 스크립트에 추가합니다.  
  
## 구문  
  
```  
HRESULT AddTypeLib(  
   REFGUID   rguidTypeLib,  
   DWORD     dwMajor,  
   DWORD     dwMinor,  
   DWORD     dwFlags  
);  
```  
  
#### 매개 변수  
 `rguidTypeLib`  
 \[in\] 추가할 CLSID \(클래스 식별자\) 형식 라이브러리입니다.  
  
 `dwMajor`  
 \[in\] 주 버전 번호입니다.  
  
 `dwMinor`  
 \[in\] 부 버전 번호입니다.  
  
 `dwFlags`  
 \[in\] 사용되지 않습니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드를 호출 합니다. `LoadTypeLib` 형식 라이브러리를 로드할 수 있습니다.  성공한 경우이 메서드를 호출 합니다. `IActiveScriptAuthor::AddNamedItem` 유형 정보를 추가 합니다.  
  
## 참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)   
 [IActiveScriptAuthor::AddNamedItem](../../winscript/reference/iactivescriptauthor-addnameditem.md)   
 [LoadTypeLib](http://msdn.microsoft.com/ko-kr/155b48e5-5438-409e-9342-630a6a500f60)