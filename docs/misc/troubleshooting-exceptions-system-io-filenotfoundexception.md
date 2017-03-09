---
title: "예외 문제 해결: System.IO.FileNotFoundException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "FileNotFoundException 클래스"
  - "System.IO.FileNotFoundException 예외"
ms.assetid: 6e5ab395-7c81-434e-835f-0fc792b9149d
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.IO.FileNotFoundException
<xref:System.IO.FileNotFoundException> 예외는 디스크에 없는 파일이나 디렉터리에 액세스하려 할 때 throw됩니다.  
  
## 관련 팁  
 **지정한 위치에 해당 파일이 있는지 확인하십시오.**  
 파일이 없으면 이 예외가 throw됩니다. 자세한 내용은 <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A>을 참조하세요.  
  
 **상대 경로를 사용하는 경우 현재 디렉터리가 올바른지 확인하십시오.**  
 현재 디렉터리가 올바르지 않으면 상대 경로도 올바르지 않습니다.  
  
## 참고 항목  
 <xref:System.IO.FileNotFoundException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)