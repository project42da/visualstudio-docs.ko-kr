---
title: "IActiveScriptAuthor::IsCommitChar | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptAuthor.IsCommitChar
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptAuthor::IsCommitChar"
ms.assetid: 7857c6f9-61e6-41e5-8e01-f56588c10421
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# IActiveScriptAuthor::IsCommitChar
지정 된 문자 완료 commit 문을 응용 프로그램에서 실행 됩니다 여부를 나타내는 값을 반환 합니다.  
  
## 구문  
  
```  
HRESULT IsCommitChar(  
   OLECHAR    ch,  
   BOOL       *pfcommit  
);  
```  
  
#### 매개 변수  
 `ch`  
 \[in\] 테스트할 문자입니다.  
  
 `pfcommit`  
 \[out\] `True` 문자의 경우 커밋 문자입니다. 그렇지 않으면 `False`.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)