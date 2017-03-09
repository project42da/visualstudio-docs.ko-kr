---
title: "컴파일러 오류 CS1569 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1569"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1569"
ms.assetid: 1d5e89d6-0a05-4e4f-b472-9089146696bb
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1569
XML 문서 파일 'Filename'\('reason'\)을 생성하는 동안 오류가 발생했습니다.  
  
 메시지에서 이름이 지정된 파일에 XML 문서를 작성하려고 시도할 때 지정된 이유로 인해 오류가 발생했습니다. "네트워크 드라이브를 찾을 수 없습니다" 또는 "액세스가 거부되었습니다"와 같은 이유 때문일 수 있습니다. 종종 이유에서 오류를 수정하기 위해 수행해야 하는 작업이 제안됩니다. 예를 들어 오류에서 "액세스가 거부되었습니다"라고 하면 파일에 대한 쓰기 권한이 있는지 확인합니다.  
  
## 예제  
  
```  
// 1569a.cs // compile with: /doc:CS1569.xml // post-build command: attrib +r CS1569.xml class Test { /// <summary>Test.</summary> public static void Main() {} }  
```  
  
## 예제  
 앞의 샘플이 읽기 전용으로 설정된 .xml 파일을 생성했습니다. 이 샘플은 같은 파일에 기록하려고 시도합니다. 다음 샘플에서는 CS1569를 생성합니다.  
  
```  
// CS1569.cs // compile with: /doc:CS1569.xml // CS1569 expected class Test { /// <summary>Test.</summary> public static void Main() {} }  
  
```