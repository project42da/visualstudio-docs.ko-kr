---
title: "예외 문제 해결: System.Security.SecurityException | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EHSecurity"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "System.Security.SecurityException 클래스"
  - "SecurityException 클래스"
ms.assetid: 7679ef74-dd15-439f-bfeb-0fb45f8b2373
caps.latest.revision: 26
caps.handback.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Security.SecurityException
<xref:System.Security.SecurityException> 예외는 보안 오류를 발견한 경우에 throw됩니다.  
  
## 관련 팁  
 속성 페이지에서 어셈블리의 권한 수준을 조정합니다.  
 자세한 내용은 <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.SqlPermissionLevel%2A>을 참조하세요.  
  
 응용 프로그램 데이터를 격리된 저장소에 저장합니다.  
 격리된 저장소는 코드와 저장된 데이터를 연결하는 표준화된 방법을 정의하여 격리와 안전을 제공하는 데이터 저장소입니다. 자세한 내용은 [격리된 저장소](../Topic/Isolated%20Storage.md)를 참조하세요.  
  
 <xref:System.Windows.Forms.OpenFileDialog>를 사용하는 경우 <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> 메서드를 사용하여 파일을 열거나 저장합니다.  
 이렇게 하면 부분 신뢰 상황에서 응용 프로그램을 수행할 수 있습니다.  
  
 응용 프로그램이 로컬 컴퓨터의 기존 이벤트 로그를 사용하여 데이터를 읽고 쓰는지 확인합니다.  
 로컬이 아닌 컴퓨터에 로그를 만들거나 기록하는 데 필요한 권한이 응용 프로그램에 없을 수도 있습니다.  
  
 관리되지 않는 라이브러리를 호출하는 경우 이에 상응하는 관리되는 라이브러리를 사용합니다.  
 상응하는 API를 Framework에서 제공할 수도 있습니다. 자세한 내용은 [Troubleshooting Interoperability](/dotnet/visual-basic/programming-guide/com-interop/troubleshooting-interoperability)을 참조하세요.  
  
 안전 창을 사용합니다.  
 <xref:System.Security.Permissions.UIPermissionWindow> 열거형은 코드에서 사용할 수 있는 창의 형식을 지정합니다.  
  
 사용자가 <xref:System.Windows.Forms.PrintDialog> 구성 요소를 통해 인쇄할 수 있도록 합니다.  
 이렇게 하면 부분 신뢰 상황에서 응용 프로그램을 수행할 수 있습니다. 자세한 내용은 <xref:System.Windows.Forms.PrintDialog>을 참조하세요.  
  
 기본 프린터로 인쇄합니다.  
 이렇게 하면 부분 신뢰 상황에서 응용 프로그램을 수행할 수 있습니다. 권한이 없는 프린터에 액세스를 시도할 수도 있습니다.  
  
 데이터를 배포한 것과 동일한 웹 서버에서 데이터를 검색합니다.  
 이렇게 하면 부분 신뢰 상황에서 응용 프로그램을 수행할 수 있습니다.  
  
 Office 솔루션을 배포할 때는 필요한 보안 요구 사항이 모두 충족되었는지 확인합니다.  
 자세한 내용은 [Office 솔루션에 대한 특정 보안 고려 사항](/office-dev/office-dev/specific-security-considerations-for-office-solutions)를 참조하세요.  
  
 사용자 지정 보안 개체를 구현하는 어셈블리가 다른 어셈블리를 참조하는 경우 참조된 어셈블리를 완전 신뢰 어셈블리 목록에 추가합니다.  
 자세한 내용은 [Caspol.exe\(코드 액세스 보안 정책 도구\)](../Topic/Caspol.exe%20\(Code%20Access%20Security%20Policy%20Tool\).md)을 참조하세요.  
  
## 참고 항목  
 <xref:System.Security.SecurityException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)