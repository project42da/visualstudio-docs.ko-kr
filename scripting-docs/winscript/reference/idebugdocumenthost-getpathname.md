---
title: "IDebugDocumentHost::GetPathName | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugDocumentHost.GetPathName
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDebugDocumentHost::GetPathName"
ms.assetid: 8abe2a86-e467-4ac9-8ccb-8761141bfa0d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugDocumentHost::GetPathName
문서의 소스 파일의 전체 경로 파일 이름을 반환합니다.  
  
## 구문  
  
```  
HRESULT GetPathName(  
   BSTR*  pbstrLongName,  
   BOOL*  pfIsOriginalFile  
);  
```  
  
#### 매개 변수  
 `pbstrLongName`  
 \[out\] 긴 이름을 포함 하는 문자열입니다.  
  
 `pfIsOriginalFile`  
 \[out\] 플래그가 true 이면 즉 `pbstrLongName` 그렇지 않으면 거짓 문서를 원래 파일 참조.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_FAIL`|원본 파일이 없습니다 만들거나 결정 수 있습니다.|  
  
## 설명  
 이 메서드는 문서의 소스 파일의 전체 경로 파일 이름을 반환합니다.  
  
## 참고 항목  
 [IDebugDocumentHost 인터페이스](../../winscript/reference/idebugdocumenthost-interface.md)