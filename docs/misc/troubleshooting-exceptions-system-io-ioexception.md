---
title: "예외 문제 해결: System.IO.IOException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IOException 클래스"
ms.assetid: 87812daa-0784-43dc-b3dc-6652a960c362
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.IO.IOException
<xref:System.IO.IOException>은 파일에 대한 읽기 또는 쓰기 실패 같은 I\/O 오류가 발생할 때 throw됩니다.  
  
## 관련 팁  
 **파일과 디렉터리가 있는지 확인하십시오.**  
 읽거나 쓰려는 디렉터리가 실제로 있는지 확인하십시오. 읽으려는 파일이 있는지 확인하십시오.  
  
### 설명  
 <xref:System.IO.IOException>은 스트림, 파일 및 디렉터리를 사용하여 정보에 액세스하는 동안 throw되는 예외에 대한 기본 클래스입니다.  
  
 기본 클래스 라이브러리에는 다음과 같은 형식이 포함됩니다. 각 형식은 <xref:System.IO.IOException>의 파생 클래스입니다.  
  
-   <xref:System.IO.DirectoryNotFoundException>  
  
-   <xref:System.IO.EndOfStreamException>  
  
-   <xref:System.IO.FileNotFoundException>  
  
-   <xref:System.IO.FileLoadException>  
  
-   <xref:System.IO.PathTooLongException>  
  
## 참고 항목  
 <xref:System.IO.IOException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [NOTINBUILD 방법: CLR 콘솔 응용 프로그램 만들기](http://msdn.microsoft.com/ko-kr/b8af4197-e65f-4b17-b18e-b9e92965d026)