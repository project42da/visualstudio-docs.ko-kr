---
title: "GetAutoInsertExtensions 메서드"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 78388cce-7aae-4163-8db5-ce00d0a0c331
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# GetAutoInsertExtensions 메서드
  디버깅 하는 동안 자동으로 삽입 하는 office 응용 프로그램에 대 한 정보를 가져옵니다.  
  
 이 메서드는 나중에 사용하도록 예약됩니다.  
  
## 구문  
  
```  
HRESULT GetAutoInsertExtensions(  
    [out, retval] SAFEARRAY(BSTR)* psaExtensionNames  
);  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|*psaExtensionNames*|Office 응용 프로그램의 확장 이름입니다.|  
  
## 반환 값  
 메서드가 성공적으로 완료되었는지 여부를 나타내는 HRESULT 값입니다.  
  
## 설명  
 각 삽입 하려면 Office 응용 프로그램에서 HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\WEF\\Developer 값에 해당 하는 Office 응용 프로그램 확장 이름으로 반환 됩니다.  호스트는 이러한 레지스트리 값을 조회 하 고 확장자를 자동으로 삽입 해야 합니다.  
  
  