---
title: "&#39;&lt;typename&gt;&#39;을 포함하는 &#39;&lt;projectname&gt;&#39; 프로젝트에 대한 간접 참조를 만듭니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31533"
  - "bc31533"
helpviewer_keywords: 
  - "BC31533"
ms.assetid: e3f55f9f-92be-4ecb-bc8f-9e57049a0805
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39;을 포함하는 &#39;&lt;projectname&gt;&#39; 프로젝트에 대한 간접 참조를 만듭니다.
'\<typename\>'을 포함하는 '\<projectname\>' 프로젝트에 대한 간접 참조를 만듭니다. '\<projectname\>'에 대한 프로젝트 참조를 프로젝트에 추가하세요.  
  
 식 또는 문에서 다른 프로젝트에 정의된 형식에 액세스하지만 프로젝트에는 정의 프로젝트에 대한 직접 참조가 없습니다.  
  
 형식은 클래스, 구조체, 인터페이스, 모듈 또는 열거형일 수 있습니다.  
  
 해당 형식을 정의하는 프로젝트에서 형식을 포함하는 어셈블리를 생성합니다. 프로젝트에서 정의 프로젝트를 직접 참조하지 않는 경우 컴파일러에서 형식을 포함하는 어셈블리가 솔루션에 있고 액세스에 사용할 수 있다고 보장할 수 없습니다.  
  
 **오류 ID:** BC31533  
  
### 이 오류를 해결하려면  
  
-   해당 형식을 정의하는 프로젝트를 결정하고 해당 프로젝트에 프로젝트 참조를 추가합니다.  
  
## 참고 항목  
 [NIB: 네임스페이스 및 구성 요소 참조](http://msdn.microsoft.com/ko-kr/568fa759-796b-44cd-bf5e-1cf8de6e38fd)   
 [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)   
 [NIB: 참조 관리](http://msdn.microsoft.com/ko-kr/910912ce-0dc9-4569-9274-32c44a20cb2c)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)