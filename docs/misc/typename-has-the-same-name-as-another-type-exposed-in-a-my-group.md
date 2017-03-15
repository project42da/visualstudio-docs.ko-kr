---
title: "&#39;&lt;typename&gt;&#39;의 이름이 &#39;My&#39; 그룹에 노출된 다른 형식과 같습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36015"
  - "bc36015"
helpviewer_keywords: 
  - "BC36015"
ms.assetid: cd2286da-49be-461f-bec9-58e9c53e250b
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39;의 이름이 &#39;My&#39; 그룹에 노출된 다른 형식과 같습니다.
'\<typename\>'의 이름이 'My' 그룹에 노출된 다른 형식과 같습니다. 폼 또는 바깥쪽 네임스페이스의 이름을 바꿉니다.  
  
 클래스 또는 구조체가 `My` 개체 중 하나에서 클래스 또는 구조체와 동일한 이름으로 선언되었습니다.  
  
 `My.Forms`와 같은 `My` 개체를 통해 액세스할 수 있는 두 클래스 간에 이름 충돌을 방지할 수 없습니다.  
  
 `My` 개체에서 클래스 간에 이름 충돌이 발생할 수 있는 경우 컴파일러가 형식의 속성 이름을 *ClassName*에서 *RootNamespace*\_*Namespace*\_*ClassName*으로 변경합니다. 예를 들어 `Form1`이라는 두 개의 폼을 고려합니다. 이러한 폼 중 하나가 `WindowsApplication1` 루트 네임스페이스 및 `Namespace1` 네임스페이스에 있는 경우 `My.Forms.WindowsApplication1_Namespace1_Form1`을 통해 해당 폼에 액세스합니다.  
  
 이 오류는 두 클래스의 이름이 같고 해당 이름에 밑줄이 있는 중첩된 네임스페이스에 포함된 경우에 발생할 수 있습니다. 컴파일러가 클래스의 새 속성 이름을 생성하는 경우에도 여전히 이름 충돌이 있습니다.  
  
 **오류 ID:** BC36015  
  
### 이 오류를 해결하려면  
  
1.  새 폼의 이름을 바꿉니다.  
  
2.  네임스페이스의 이름을 바꿉니다.  
  
     클래스 또는 구조체를 기존 항목과 동일한 이름으로 지정하지 마세요.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Form>   
 <xref:Microsoft.VisualBasic.MyGroupCollectionAttribute>   
 [NOTINBUILD: 여러 변수에 동일한 이름이 있는 경우 참조 확인](http://msdn.microsoft.com/ko-kr/9601e39f-1911-44e1-ace5-3f6e090408b9)   
 [My.Forms Object](/dotnet/visual-basic/language-reference/objects/my-forms-object)