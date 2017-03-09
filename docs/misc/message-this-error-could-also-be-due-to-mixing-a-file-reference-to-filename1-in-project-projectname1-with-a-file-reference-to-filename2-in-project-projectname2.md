---
title: "&lt;message&gt; 이 오류는 &#39;&lt;projectname1&gt;&#39; 프로젝트의 &#39;&lt;filename1&gt;&#39;에 대한 파일 참조와 &#39;&lt;projectname2&gt;&#39; 프로젝트의 &#39;&#39;&lt;filename2&gt;&#39;에 대한 파일 참조가 섞여 있기 때문에 발생할 수도 있습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30970"
  - "vbc30970"
helpviewer_keywords: 
  - "BC30970"
ms.assetid: 81cc4f7b-cc16-46cc-9a49-74980300e158
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;message&gt; 이 오류는 &#39;&lt;projectname1&gt;&#39; 프로젝트의 &#39;&lt;filename1&gt;&#39;에 대한 파일 참조와 &#39;&lt;projectname2&gt;&#39; 프로젝트의 &#39;&#39;&lt;filename2&gt;&#39;에 대한 파일 참조가 섞여 있기 때문에 발생할 수도 있습니다.
\<message\> 이 오류는 '\<projectname1\>' 프로젝트의 '\<filepathname1\>'에 대한 파일 참조와 '\<projectname2\>' 프로젝트의 ''\<filepathname2\>'에 대한 파일 참조가 섞여 있기 때문에 발생할 수도 있습니다.  두 어셈블리가 동일하면 동일한 대상을 참조하도록 두 참조를 바꿔 보세요.  
  
 프로젝트 코드에서 다른 프로젝트의 멤버에 액세스하지만 솔루션 구성상 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러에서 참조를 확인할 수 없습니다.  
  
 다른 어셈블리에 정의된 형식에 액세스하려면 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러에 해당 어셈블리에 대한 참조가 있어야 합니다. 이 참조는 프로젝트 간의 순환 참조를 발생시키지 않는 명확한 단일 참조여야 합니다.  
  
 **오류 ID:** BC30970  
  
### 이 오류를 해결하려면  
  
1.  참조할 프로젝트에 가장 적합한 어셈블리를 생성하는 프로젝트를 결정합니다. 이러한 결정을 위해 파일 접근성 및 업데이트 빈도 등의 조건을 사용할 수 있습니다.  
  
2.  프로젝트 속성에서 사용 중인 형식을 정의하는 어셈블리가 포함된 파일에 대한 참조를 추가합니다.  
  
## 참고 항목  
 [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)   
 [NIB: 네임스페이스 및 구성 요소 참조](http://msdn.microsoft.com/ko-kr/568fa759-796b-44cd-bf5e-1cf8de6e38fd)   
 [NOTINBUILD: 여러 변수에 동일한 이름이 있는 경우 참조 확인](http://msdn.microsoft.com/ko-kr/9601e39f-1911-44e1-ace5-3f6e090408b9)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [NIB 방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [끊어진 참조 문제 해결](../ide/troubleshooting-broken-references.md)