---
title: "사용자 지정 데이터 형식 표시 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.data.elements"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "autoexp.dat 파일"
  - "사용자 지정 데이터 형식"
  - "데이터 형식[C#], 사용자 지정"
  - "디버거, 데이터 형식 확장"
  - "관리 코드, 사용자 지정 데이터 형식"
  - "mcee_cs.dat 파일"
  - "mcee_mc.dat 파일"
ms.assetid: 9969e9b2-9008-4729-8a14-0d6deaa61576
caps.latest.revision: 34
caps.handback.revision: 34
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 사용자 지정 데이터 형식 표시
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio에서 디버거 변수 창에 데이터 형식이 표시되는 방식을 사용자 지정할 수 있습니다.  
  
## 특성  
 C\# 및 Visual Basic에서는 <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, <xref:System.Diagnostics.DebuggerDisplayAttribute> 및 <xref:System.Diagnostics.DebuggerBrowsableAttribute>를 사용하여 사용자 지정 데이터에 대한 확장을 추가할 수 있습니다.  
  
 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] 코드에서 Visual Basic은 DebuggerBrowsable 특성을 지원하지 않습니다.  최신 버전의 .NET Framework에서는 이러한 제한 사항이 제거되었습니다.  
  
## 시각화 도우미  
 시각화 도우미를 작성하여 관리되는 데이터 형식을 표시할 수 있습니다.  자세한 내용은 [방법: 시각화 도우미 작성](../debugger/how-to-write-a-visualizer.md)을 참조하십시오.  
  
## 네이티브 코드  
 네이티브 코드를 사용하는 경우 Program Files\\Microsoft Visual Studio 11.0\\Common7\\Packages\\Debugger 디렉터리에 있는 autoexp.dat 파일에 사용자 지정 데이터 형식 확장을 추가할 수 있습니다.  `autoexp` 규칙의 작성 방법에 대한 지침은 해당 파일 내에 있습니다.  
  
> [!CAUTION]
>  이 파일의 구조와 autoexp 규칙의 구문은 Visual Studio 릴리스마다 다를 수 있습니다.  
  
 또한 식 계산기 추가 기능을 작성하여 네이티브 형식 뷰를 사용자 지정할 수도 있습니다.  자세한 내용은 [EEAddIn Sample: Debugging Expression Evaluator Add\-In](http://msdn.microsoft.com/ko-kr/d4f6b068-c812-45bc-9ec0-7e0363c4bb9e)을 참조하십시오.  
  
## 참고 항목  
 [DebuggerTypeProxy 특성 사용](../debugger/using-debuggertypeproxy-attribute.md)   
 [DebuggerDisplay 특성 사용](../debugger/using-the-debuggerdisplay-attribute.md)   
 [조사식 및 간략한 조사식 창](../debugger/watch-and-quickwatch-windows.md)   
 [Enhancing Debugging with the Debugger Display Attributes](../Topic/Enhancing%20Debugging%20with%20the%20Debugger%20Display%20Attributes.md)