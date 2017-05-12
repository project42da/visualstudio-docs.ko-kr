---
title: "IDebugDocumentTextExternalAuthor::GetPathName | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentTextExternalAuthor.GetPathName
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugDocumentTextExternalAuthor::GetPathName"
ms.assetid: 445152a1-9cf8-402e-93d6-3d4bf2b81d17
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentTextExternalAuthor::GetPathName
문서의 전체 경로 파일 이름을 반환합니다.  
  
## 구문  
  
```  
HRESULT GetPathName(  
   BSTR*  pbstrLongName,  
   BOOL*  pfIsOriginalFile  
);  
```  
  
#### 매개 변수  
 `pbstrLongName`  
 \[out\] 전체 경로 파일 이름이 포함 된 문자열입니다.  
  
 `pfIsOriginalFile`  
 \[out\] 경로 파일 이름을 참조 하는지 나타내는 부울 원본 문서에 있습니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_FAIL`|소스 파일을 만들거나 결정 될 수 없습니다.|  
  
## 설명  
 이 메서드는 문서의 전체 경로 파일 이름을 반환합니다.  
  
 경우 `pfIsOriginalFile` 거짓, 경로 및 파일 이름이 `pbstrLongName` 새로 만든된 임시 파일을 참조 하십시오.  
  
## 참고 항목  
 [IDebugDocumentTextExternalAuthor 인터페이스](../../winscript/reference/idebugdocumenttextexternalauthor-interface.md)