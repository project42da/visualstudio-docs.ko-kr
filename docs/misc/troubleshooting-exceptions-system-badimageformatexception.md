---
title: "예외 문제 해결: System.BadImageFormatException | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "BadImageFormatException 클래스"
ms.assetid: 8d2b385a-3d6d-4dfa-8546-7ece562867e3
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.BadImageFormatException
<xref:System.BadImageFormatException> 예외는 DLL이나 실행 프로그램의 파일 이미지가 올바르지 않은 경우에 throw됩니다.  
  
## 관련 팁  
 **32비트 구성 요소를 사용하는 응용 프로그램은 항상 32비트 응용 프로그램으로 실행되도록 해야 합니다.**  
 응용 프로그램 프로젝트의 **플랫폼 대상** 속성이 `AnyCPU`로 설정되어 있는 경우 컴파일된 응용 프로그램은 64비트 또는 32비트 모드에서 실행될 수 있습니다. 64비트 응용 프로그램으로 실행될 때는 JIT\(Just\-In\-Time\) 컴파일러가 64비트 네이티브 코드를 생성합니다. 응용 프로그램에서 관리되거나 관리되지 않는 32비트 구성 요소를 사용하는 경우 해당 구성 요소는 64비트 모드에서 로드되지 않습니다. 이 문제를 해결하려면 프로젝트의 **플랫폼 대상** 속성을 `x86`으로 설정하고 다시 컴파일하세요.  
  
 **다른 버전의 .NET Framework로 만들어진 구성 요소를 사용하고 있지 않아야 합니다.**  
 이 예외는 [!INCLUDE[net_v10_short](../misc/includes/net_v10_short_md.md)] 또는 [!INCLUDE[net_v11_short](../misc/includes/net_v11_short_md.md)]을 사용하여 개발된 응용 프로그램 또는 구성 요소가 [!INCLUDE[net_v20SP1_short](../misc/includes/net_v20sp1_short_md.md)] 이상을 사용하여 개발된 어셈블리를 로드하려고 할 때나 [!INCLUDE[net_v20SP1_short](../misc/includes/net_v20sp1_short_md.md)] 또는 [!INCLUDE[net_v35_short](../misc/includes/net_v35_short_md.md)]를 사용하여 개발된 응용 프로그램이 [!INCLUDE[net_v40_short](../debugger/includes/net_v40_short_md.md)]를 사용하여 개발된 어셈블리를 로드하려고 할 때 throw됩니다.<xref:System.BadImageFormatException> 예외는 컴파일 시간 오류로 보고될 수 있으며, 또는 런타임에 예외가 throw될 수 있습니다. 예제를 보려면 <xref:System.BadImageFormatException> 클래스를 참조하세요.  
  
 **파일 이미지가 관리되는 올바른 어셈블리 또는 모듈이어야 합니다.**  
 이 예외는 관리되지 않는 동적 연결 라이브러리 또는 실행 파일이 로드를 위해 <xref:System.Reflection.Assembly.Load%2A> 메서드에 전달될 때 throw됩니다.  
  
 Visual Basic에 관련된 자세한 내용은 [Troubleshooting Interoperability](/dotnet/visual-basic/programming-guide/com-interop/troubleshooting-interoperability)을 참조하세요.  
  
## 주의  
 C\+\+ 실행 파일을 반영할 때 이 예외가 throw될 수 있습니다. 이 예외는 대부분 C\+\+ 컴파일러가 실행 파일에서 .Reloc 섹션이나 재배치 주소를 제거하는 경우에 발생합니다. C\+\+ 실행 파일에서 재배치 주소를 유지하려면 링크할 때 **\/fixed:no**를 지정합니다.  
  
 이 예외의 발생 원인에 대한 자세한 내용은 <xref:System.BadImageFormatException> 클래스를 참조하세요.  
  
## 참고 항목  
 <xref:System.BadImageFormatException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)