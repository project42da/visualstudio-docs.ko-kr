---
title: "예외 문제 해결: System.IO.FileLoadException | Microsoft Docs"
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
  - "FileLoadException 클래스"
ms.assetid: 6b4519e3-4d29-4031-8aec-c2735b4ee16d
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.IO.FileLoadException
<xref:System.IO.FileLoadException> 예외는 관리되는 어셈블리를 찾았지만 로드할 수 없는 경우에 throw됩니다.  
  
## 관련 팁  
 **파일이 올바른 .NET Framework 어셈블리인지 확인하십시오.**  
 이 예외는 파일이 올바른 .NET Framework 어셈블리가 아닌 경우에 throw됩니다. 자세한 내용은 <xref:System.Reflection.Assembly>을 참조하세요.  
  
 **다른 두 개의 증명 정보를 사용하여 어셈블리나 모듈을 두 번 로드하지 않았는지 확인하십시오.**  
 증명 정보는 코드에 부여할 수 있는 권한 같이 보안 정책을 결정하기 위해 입력하는 정보 집합입니다. 자세한 내용은 <xref:System.EnterpriseServices.Internal.Publish.GacRemove%2A> 및 <xref:System.Reflection.Assembly.Evidence%2A>을 참조하십시오.  
  
 **RegisterAssembly 또는 UnregisterAssembly 메서드를 사용하는 경우 어셈블리 이름의 길이가 MAX\_PATH 문자보다 길지 않은지 확인하십시오.**  
 어셈블리 이름의 길이는 MAX\_PATH를 넘을 수 없습니다. 자세한 내용은 <xref:System.EnterpriseServices.Internal.IComSoapPublisher.RegisterAssembly%2A> 및 <xref:System.EnterpriseServices.Internal.IComSoapPublisher.UnRegisterAssembly%2A>를 참조하세요.  
  
 **위성 어셈블리를 로드할 경우 지정된 CultureInfo가 파일의 CultureInfo와 일치하는지 확인하십시오.**  
 위성 어셈블리에는 기본 문화권이나 중립 문화권으로 사용되는 단일 문화권에 대한 리소스와 지역화할 수 없는 실행 코드가 포함된 지역화된 리소스가 들어 있습니다. 자세한 내용은 <xref:System.Reflection.Assembly.GetSatelliteAssembly%2A>을 참조하세요.  
  
## 참고 항목  
 <xref:System.IO.FileLoadException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)