---
title: "방법: Office 다국어 사용자 인터페이스 대상 선택"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "전역화[Visual Studio에서 Office 개발], 사용자 인터페이스 대상 지정"
  - "지역화[Visual Studio에서 Office 개발], 사용자 인터페이스 대상 지정"
  - "MUI[Visual Studio에서 Office 개발]"
  - "다국어 사용자 인터페이스[Visual Studio에서 Office 개발]"
  - "Office 응용 프로그램[Visual Studio에서 Office 개발], 전역화"
  - "Office 응용 프로그램[Visual Studio에서 Office 개발], 지역화"
ms.assetid: b1f03164-f0cf-42e3-942b-8cf90c242ffb
caps.latest.revision: 30
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 29
---
# 방법: Office 다국어 사용자 인터페이스 대상 선택
  Microsoft Office 기능인 MUI\(다국어 사용자 인터페이스\)를 사용하면 최종 사용자가 UI\(사용자 인터페이스\) 언어를 바꿀 수 있습니다.  예를 들어, 영어 UI를 사용하여 작업 중인 최종 사용자가 UI의 언어를 스페인어로 변경할 수 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 여러 언어로 Office를 사용하는 사람을 위한 응용 프로그램을 만드는 경우, 사용자 컴퓨터에 있는 Office 언어에 맞도록 UI 문자열의 언어를 자동으로 변경하는 코드를 추가할 수 있습니다. 이 경우 사용자 컴퓨터에 해당 리소스가 설치되어 있어야 합니다.  
  
### 현재 Office UI 설정을 확인하려면  
  
1.  현재 스레드의 <xref:System.Threading.Thread.CurrentUICulture%2A> 속성을 사용합니다.  UI 문자열의 언어를 사용자 컴퓨터에서 현재 실행되는 Office 버전에 사용되는 언어와 일치하도록 설정합니다.  
  
     [!code-csharp[Trin_VstcoreCreatingExcel#10](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreCreatingExcel/CS/Sheet1.cs#10)]
     [!code-vb[Trin_VstcoreCreatingExcel#10](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreCreatingExcel/VB/Sheet1.vb#10)]  
  
## 참고 항목  
 [방법: 주 Interop 어셈블리를 통한 Office 응용 프로그램 대상 선택](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [Office 솔루션에서 런타임에 바인딩](../vsto/late-binding-in-office-solutions.md)  
  
  