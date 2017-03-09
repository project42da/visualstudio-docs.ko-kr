---
title: "&#39;&lt;filename&gt;&#39; 파일에 서명할 수 없습니다. &lt;error&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc31028"
  - "vbc31028"
helpviewer_keywords: 
  - "BC31028"
ms.assetid: 2cb22e75-5ee2-4e07-afc0-680a0bd543d4
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;filename&gt;&#39; 파일에 서명할 수 없습니다. &lt;error&gt;
지정된 파일에 서명하는 동안 오류가 발생했습니다. 이 오류가 발생한 이유는 여러 가지가 있을 수 있습니다.  
  
-   권한이 부족합니다.  
  
-   Authenticode 서명에 필요한 시스템 파일이 없습니다.  
  
-   존재하지 않는 인증서 또는 개인 키 파일에 대한 참조입니다.  
  
-   파일 이름 또는 URL의 철자가 잘못되었습니다.  
  
 **오류 ID:** BC31028  
  
### 이 오류를 해결하려면  
  
1.  올바른 인증서 및 개인 키 파일 이름을 입력합니다.  
  
2.  Authenticode 서명을 사용하는 경우 Signcode.exe 및 Javasign.dll 파일이 있는지, 읽기 전용 특성이 설정되지 않았는지 확인합니다.  
  
3.  파일에 대한 `Write` 권한이 있는지 확인합니다.  
  
## 참고 항목  
 [File Signing Tool \(Signcode.exe\)](http://msdn.microsoft.com/ko-kr/2d299154-34ea-41ba-ad12-17075bb7e1db)   
 [Deployment and Authenticode Signing](http://msdn.microsoft.com/ko-kr/ecc3f059-da2e-445b-9b87-5b2978e2f8b2)