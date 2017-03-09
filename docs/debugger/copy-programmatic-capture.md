---
title: "복사(프로그램 방식 캡처) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 복사(프로그램 방식 캡처)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

액티브 그래픽 \(.vsglog\) 로그 파일의 내용을 새 파일에 복사합니다.  
  
## 구문  
  
```cpp  
void Copy(  
  wchar_t const * szNewVSGLog  
);  
```  
  
#### 매개 변수  
 `szNewVSGLog`  
 새 그래픽 로그 파일의 파일 이름입니다.  
  
## 설명  
 그래픽 정보를 새 파일로 복사하기 위해서는 이미 캡처한 일부 그래픽 정보를 가지고 있어야 합니다. 그렇지 않으면 아무것도 나타나지 않습니다.