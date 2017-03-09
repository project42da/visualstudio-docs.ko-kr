---
title: "&#39;&lt;parameter&gt;&#39; 대신 &#39;&lt;option&gt;&#39; 명령줄 옵션 또는 적절한 프로젝트 설정을 사용하세요. | Microsoft Docs"
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
  - "bc41008"
  - "vbc41008"
helpviewer_keywords: 
  - "BC41008"
ms.assetid: 1c5d6d7a-b767-4dae-aa61-d7fa81d5aad1
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;parameter&gt;&#39; 대신 &#39;&lt;option&gt;&#39; 명령줄 옵션 또는 적절한 프로젝트 설정을 사용하세요.
어셈블리에 대한 공개 키, 어셈블리에 대한 공개 키 컨테이너 또는 부분적으로 서명된 어셈블리를 포함하는 파일을 지정하는 기본 방법은 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러 옵션을 사용하는 것입니다. 코드에서 <xref:System.Reflection.AssemblyKeyFileAttribute>, <xref:System.Reflection.AssemblyKeyNameAttribute> 또는 <xref:System.Reflection.AssemblyDelaySignAttribute> 특성을 사용하지 않는 것이 좋습니다.  
  
 **오류 ID:** BC41008  
  
### 이 오류를 해결하려면  
  
1.  코드에서 <xref:System.Reflection.AssemblyKeyFileAttribute>, <xref:System.Reflection.AssemblyKeyNameAttribute> 또는 <xref:System.Reflection.AssemblyDelaySignAttribute> 특성 대신 [\/keyfile](/dotnet/visual-basic/reference/command-line-compiler/keyfile), [\/keycontainer](/dotnet/visual-basic/reference/command-line-compiler/keycontainer) 또는 [\/delaysign](/dotnet/visual-basic/reference/command-line-compiler/delaysign) [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러 옵션을 사용합니다.  
  
## 참고 항목  
 [방법: 서명된 Friend 어셈블리 만들기](../Topic/How%20to:%20Create%20Signed%20Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Visual Basic Command\-Line Compiler](/dotnet/visual-basic/reference/command-line-compiler/index)   
 [\/keyfile](/dotnet/visual-basic/reference/command-line-compiler/keyfile)   
 [\/keycontainer](/dotnet/visual-basic/reference/command-line-compiler/keycontainer)   
 [\/delaysign](/dotnet/visual-basic/reference/command-line-compiler/delaysign)