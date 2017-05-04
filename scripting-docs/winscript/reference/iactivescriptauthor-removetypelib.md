---
title: "IActiveScriptAuthor::RemoveTypeLib | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptAuthor.RemoveTypeLib
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptAuthor::RemoveTypeLib"
ms.assetid: 232c3698-024d-4549-8fbc-cb0d3ac17dc5
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# IActiveScriptAuthor::RemoveTypeLib
스크립트 제작 엔진 네임 스페이스에서 형식 라이브러리를 제거 합니다.  
  
## 구문  
  
```  
HRESULT RemoveTypeLib(  
   REFGUID   rguidTypeLib,  
   DWORD     dwMajor,  
   DWORD     dwMinor  
);  
```  
  
#### 매개 변수  
 `rguidTypeLib`  
 \[in\] 제거 하는 CLSID \(클래스 식별자\) 형식 라이브러리의.  
  
 `dwMajor`  
 \[in\] 주 버전 번호입니다.  
  
 `dwMinor`  
 \[in\] 부 버전 번호입니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)