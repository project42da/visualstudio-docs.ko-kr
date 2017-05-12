---
title: "DOCUMENTNAMETYPE 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: DOCUMENTNAMETYPE
apilocation: scrobj.dll
helpviewer_keywords: 
  - "DOCUMENTNAMETYPE 열거형"
ms.assetid: d36d550e-efb4-493d-8971-4de267005654
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# DOCUMENTNAMETYPE 열거형
가져올 문서에 대 한 입력을 설명 합니다.  
  
## 구문  
  
```  
typedef enum tagDOCUMENTNAMETYPE {  
   DOCUMENTNAMETYPE_APPNODE,  
   DOCUMENTNAMETYPE_TITLE,  
   DOCUMENTNAMETYPE_FILE_TAIL,  
   DOCUMENTNAMETYPE_URL,  
DOCUMENTNAMETYPE_UNIQUE_TITLE,  
} DOCUMENTNAMETYPE;  
```  
  
## Members  
  
|멤버|설명|  
|--------|--------|  
|DOCUMENTNAMETYPE\_APPNODE|응용 프로그램 트리에 표시 되는 이름을 가져옵니다.|  
|DOCUMENTNAMETYPE\_TITLE|뷰어 제목 표시줄에 표시 되는 이름을 가져옵니다.|  
|DOCUMENTNAMETYPE\_FILE\_TAIL|경로 없이 파일 이름을 가져옵니다.|  
|DOCUMENTNAMETYPE\_URL|문서의 URL을 가져옵니다.|  
|DOCUMENTNAMETYPE\_UNIQUE\_TITLE|식별을 위해 열거형에 추가 된 제목을 가져옵니다.|  
  
## 참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)